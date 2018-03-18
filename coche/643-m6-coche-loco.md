#Montaje 6 Coche loco
Vamos a realizar un programa que cuando se apriete el botón de Edubásica, pues el coche haga un baile:

{% youtube %}https://www.youtube.com/watch?v=j6Z9botrgdo{% endyoutube%}

Los programas con motor son sencillos pero engorrosos, este programa es sencillo y verás que tiene muchas líneas, un poco de complicación y se complica mucho más

##CODIGO CON EDUBÁSICA

```cpp
////////////// CON EDUBASICA ////////////////
#define ENABLEA 10
#define DIR1A 8
#define DIR2A 9
#define ENABLEB 11
#define DIR1B 12
#define DIR2B 13
#define BOTON 2
#define LEDVERDE 3
#define LEDAMARILLO 4
#define LEDROJO 5
byte dato;
/////////////////////////////////////////////////////////////////////////////////////////////////////
void setup() {
  ///configuraciones inicio
  pinMode(ENABLEA,OUTPUT);  pinMode(DIR1A,OUTPUT);  pinMode(DIR2A,OUTPUT);
  pinMode(ENABLEB,OUTPUT);  pinMode(DIR1B,OUTPUT);  pinMode(DIR2B,OUTPUT);
  pinMode(BOTON,INPUT);
  pinMode(LEDVERDE,OUTPUT); pinMode(LEDAMARILLO,OUTPUT);  pinMode(LEDROJO,OUTPUT);
  /// delante
  digitalWrite(LEDVERDE, HIGH);    digitalWrite(LEDROJO, LOW);   digitalWrite(LEDAMARILLO, LOW);
  digitalWrite(ENABLEA,HIGH);      digitalWrite(DIR1A,HIGH);     digitalWrite(DIR2A,LOW);
  digitalWrite(ENABLEB,HIGH);      digitalWrite(DIR1B,HIGH);     digitalWrite(DIR2B,LOW);
  delay(1000);
  //atras
  digitalWrite(LEDVERDE, LOW);     digitalWrite(LEDROJO, HIGH);   digitalWrite(LEDAMARILLO, LOW);
  digitalWrite(ENABLEA,HIGH);      digitalWrite(DIR1A,LOW);      digitalWrite(DIR2A,HIGH);
  digitalWrite(ENABLEB,HIGH);      digitalWrite(DIR1B,LOW);      digitalWrite(DIR2B,HIGH);
  delay(1000);
  //derecha
  digitalWrite(LEDVERDE, HIGH);     digitalWrite(LEDROJO, LOW);    digitalWrite(LEDAMARILLO, HIGH);
  digitalWrite(ENABLEA,HIGH);      digitalWrite(DIR1A,LOW);       digitalWrite(DIR2A,HIGH);
  digitalWrite(ENABLEB,HIGH);      digitalWrite(DIR1B,HIGH);      digitalWrite(DIR2B,LOW);
  delay(1000);
  //izquierda  
  digitalWrite(LEDVERDE, HIGH);     digitalWrite(LEDROJO, HIGH);    digitalWrite(LEDAMARILLO, HIGH);
  digitalWrite(ENABLEA,HIGH);      digitalWrite(DIR1A,HIGH);      digitalWrite(DIR2A,LOW);
  digitalWrite(ENABLEB,HIGH);      digitalWrite(DIR1B,LOW);       digitalWrite(DIR2B,HIGH);
  delay(1000);
  //stop 
  digitalWrite(LEDVERDE, LOW);     digitalWrite(LEDROJO, LOW);    digitalWrite(LEDAMARILLO, LOW);
  digitalWrite(ENABLEA,LOW);
  digitalWrite(ENABLEB,LOW);  
}
void loop(){
}
```

## SIN EDUBASICA

Cambia el principio de la cabecera, y omite los LEDs:

```cpp+lineNumbers:true
////////////// SIN EDUBASICA ////////////////
#define ENABLEA 6
#define DIR1A 7
#define DIR2A 8
#define ENABLEB 11
#define DIR1B 9
#define DIR2B 10
```

##Reto
¿Que tal si en vez de activarse con el botón, que simplemente cuando este oscuro (utiliza el valor del pin analógico 2 = LDR), se ponga a bailar? 

