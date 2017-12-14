
# Montaje 6 Giro motor

El programa hace que el motor gire en un sentido durante 1 segundo, cambie de sentido y gire durante otro segundo. Esta secuencia la repite 5 veces y después el motor se para. La configuración de los pines ya está preparado para EDUBASICA

Si no se tiene EDUBASICA, hay que seguir el esquema [visto en la anterior página](descripcin_y_esquemas2.html) y cambiar las 3 primeras instrucciones por:

```cpp
///////////////////// SIN EDUBASICA /////////// MOTOR EN LOS PINES 3 Y 6 DEL L293
#define ENABLE 3
#define DIRB 4
#define DIRA 5
```

```cpp
////////////// CON EDUBASICA ////////////////
#define ENABLE 10
#define DIRB 8
#define DIRA 9

void setup() {
  int i = 0;
  pinMode(ENABLE,OUTPUT);
  pinMode(DIRA,OUTPUT);
  pinMode(DIRB,OUTPUT);
  digitalWrite(ENABLE,HIGH);
  for (i=0;i<5;i++) {
    digitalWrite(DIRA,HIGH); 
    digitalWrite(DIRB,LOW);
    delay(1000); 
    digitalWrite(DIRA,LOW);  
    digitalWrite(DIRB,HIGH);
    delay(1000); 
  }
  digitalWrite(ENABLE,LOW); 

}
void loop(){
  
}
```
{% youtube %}https://www.youtube.com/watch?v=mkcNlET4-58&feature=youtu.be{% endyoutube%}

Otro programas para conseguir el giro del motor, en este caso utilizando dos motores y funciones con un lenguaje de programación más profesional

Vamos a ver dos programas de test distintos que hacen funcionar ambos motores (A y B) mediante el circuito L293 de Edubasica:

#### MOTOR A

```cpp
/*
  Test del motor A controlado un puente en H
  del C.I. L293D
  Comprueba el funcionamiento del motor A  
  EL INTERRUPTOR DE CORRIENTE DE EDUBASICA 
  TIENE QUE ESTAR EN POSICION ON

  Sketch Test for motorA controlled 
  by L239D H bridge (600mA)
  THE POWER SWITCH PROVIDEED ON EDUBASICA 
  MUST TO BE ON 
  
  Manuel Hidalgo - LeoBot  Julio 2014
  Pablo Garcia - May 2015
*/


//Etiquetas de identificación de los pines 
// labels for pins
//pines para controlar la direccion de giro 
// with 2 pins we control de spinning direction
const int motorA_Dir1 = 8;        
const int motorA_Dir2 = 9;
const int motorA_Velocidad = 10;  

//salida PWM para controlar la velocidad 
// PWM for speed

//Variables
int vPWM = 155;    //valor de la velocidad en PWM
 // PWM speed

void setup(){
  //configuracion de los pines //pins setup
  pinMode(motorA_Dir1, OUTPUT);
  pinMode(motorA_Dir2, OUTPUT);
  
}

void loop(){
  forward();
  delay(4000);              
  stop();
  delay(2000);
  backw();
  delay(4000); 
  stop();
  delay(2000);  
}

void forward(){
    //Activamos el motor A en un sentido de giro
  //spinning direction 1 (high-low)
  digitalWrite(motorA_Dir1,HIGH);
  digitalWrite(motorA_Dir2,LOW); 
  analogWrite(motorA_Velocidad,vPWM);
}
   
void backw(){
  //Activamos el motor A en un sentido de giro
  //spinning direction 1 (high-low)
  digitalWrite(motorA_Dir1,LOW);
  digitalWrite(motorA_Dir2,HIGH); 
  analogWrite(motorA_Velocidad,vPWM);
}

void stop(){
 //Paramos el motor durante 2s //stop for 2 secs
 //STOP (low, low)
  digitalWrite(motorA_Dir1,LOW);
  digitalWrite(motorA_Dir2,LOW);
}
```

#### MOTOR

```cpp
/*
  Test del motor B controlado un puente en H
  del C.I. L293D
  Comprueba el funcionamiento del motor B  
  Manuel Hidalgo - LeoBot
  Julio 2014
*/

//Etiquetas de identificación de los pines
const int motorB_Dir1 = 12;        
//pines para controlar la direccion de giro
const int motorB_Dir2 = 13;
const int motorB_Velocidad = 11;  
//salida PWM para controlar la velocidad

//Variables
int vPWM = 155;    //valor de la velocidad en PWM

void setup(){
  //configuracion de los pines
  pinMode(motorB_Dir1, OUTPUT);
  pinMode(motorB_Dir2, OUTPUT);
  
}

void loop(){
  //Activamos el motor B en un sentido de giro
  digitalWrite(motorB_Dir1,HIGH);
  digitalWrite(motorB_Dir2,LOW); 
  analogWrite(motorB_Velocidad,vPWM);
  delay(5000);                //permanece activado 5s
  
  //Paramos el motor durante 2 segundo
  digitalWrite(motorB_Dir1,LOW);
  digitalWrite(motorB_Dir2,LOW);
  delay(2000);
  
  //Activamos el motor B en un sentido de giro
  digitalWrite(motorB_Dir1,LOW);
  digitalWrite(motorB_Dir2,HIGH); 
  analogWrite(motorB_Velocidad,vPWM);
  delay(5000);                //permanece activado 5s
  
  //Paramos el motor durante 1 segundo
  digitalWrite(motorB_Dir1,LOW);
  digitalWrite(motorB_Dir2,LOW);
  delay(2000);
}
```

