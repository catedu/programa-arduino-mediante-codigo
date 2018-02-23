#Montaje 6 Coche loco
Vamos a realizar un programa que cuando se apriete el botón de Edubásica, pues el coche haga un baile:

{% youtube %}https://www.youtube.com/watch?v=j6Z9botrgdo{% endyoutube%}

%accordion%Solución%accordion%

Los programas con motor son sencillos pero engorrosos, este programa es sencillo y verás que tiene muchas líneas, un poco de complicación y se complica mucho más:

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

void setup() {
  pinMode(ENABLEA,OUTPUT);
  pinMode(DIR1A,OUTPUT);
  pinMode(DIR2A,OUTPUT);
  pinMode(ENABLEB,OUTPUT);
  pinMode(DIR1B,OUTPUT);
  pinMode(DIR2B,OUTPUT);
  pinMode(BOTON,INPUT);
}
void loop(){
 int i = 0;
 if (digitalRead(BOTON) == HIGH) {     
      digitalWrite(LEDVERDE, HIGH);  
      digitalWrite(ENABLEA,HIGH);
      digitalWrite(ENABLEB,HIGH);
      for (i=0;i<5;i++) {
        digitalWrite(DIR1A,HIGH); 
        digitalWrite(DIR2A,LOW);
        digitalWrite(DIR1B,HIGH); 
        digitalWrite(DIR2B,LOW);
        delay(1000); 
        digitalWrite(DIR1A,LOW);  
        digitalWrite(DIR2A,HIGH);
        digitalWrite(DIR1B,LOW);  
        digitalWrite(DIR2B,HIGH);
        delay(1000); 
      }
 }else {
    digitalWrite(LEDVERDE, LOW); 
    digitalWrite(ENABLEA,LOW); 
    digitalWrite(ENABLEB,LOW); 
 }
}
```


%/accordion%

##Reto
¿Que tal si en vez de activarse con el botón, que simplemente cuando este oscuro (utiliza el valor del pin analógico 2 = LDR), se ponga a bailar? 

