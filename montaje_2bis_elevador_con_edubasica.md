
# Montaje 2bis ELEVADOR con EDUBASICA

Con EDUBASICA es utilizar el mismo esquema que [AND con EDUBASICA](montaje_1bis_and_con_edubasica.html) pero cambiando la función AND por la XOR

```cpp
/*
  Boole
  Función XOR con 2 variables
 */
//////////////////// entradas ///////////////////////////////////////////////////////////////////////////
int var1 = 2;       //Pin D2 de entrada del pulsador 1
int var2 = 5;       //Pin D5 de entrada del pulsador 1 y led(rojo), conectamos V1 con D5 con un cable
int ledvar1 = 4;    //Pin D4 de salida para el var1 led(amarillo)
//////////////////// salidas /////////////////////////////////////////////////////////////////////////
int ledsalida = 3;    //Pin de salida para el led(verde)
////////////////////////////////////////////////////////////////////////////////////////////////////
int A = 0;    //Para almacenar el estado de la variable1
int B = 0;    //Para almacenar el estado de la variable2
int resultado = 0;  //Para almacenar el resultado      

void setup() {
  pinMode(var1, INPUT);         //Iniciliza el pin de entrada 1 como salida
  pinMode(var2, INPUT);         //Iniciliza el pin de entrada 2 como salida  
  pinMode(ledvar1, OUTPUT);     //Inicialliza led de var1 como salida
  ///////////////////////////////// no hace falta inicializar D5 como salida, pues estará con un cable visualizando V1
  pinMode(ledsalida, OUTPUT);     //Iniciliza el pin del led como salida 
}

void loop(){
  A = digitalRead(var1);      //Lee el estado del botón y lo almacena
  digitalWrite(ledvar1, A);   //Se visualiza en el led amarillo la entrada var1
  B = digitalRead(var2);      //Lee el estado del botón y lo almacena
  resultado = (!A && B) || (A && !B);
  digitalWrite(ledsalida, resultado);    //Escribimos el resultado en el led
}
```

El resultado es:

{% youtube %}https://www.youtube.com/watch?v=JZIogNIKYbg&feature=youtu.be{% endyoutube %}