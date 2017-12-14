
# Montaje 1 Encender LEDs con EDUBASICA

El objetivo de esta práctica es encender los LEDs de EDUBASICA con el móvil:

- Cuando se pulsa la **flecha arriba**, la APP BlueControl lanza el dato **85** y tiene que encenderse el led **ROJO.**
- Cuando se pulsa el botón **centro**, la APP BlueControl lanza el dato **67 **y tiene que encenderse el led **AMARILLO.**
- Cuando se pulsa la **flecha arriba**, la APP BlueControl lanza el dato **68 **y tiene que encenderse el led **VERDE.**
- **Cualquier otra letra **tienen que apagarse.

(si no tienes Edubásica, no pasa nada, con una placa Protoboard pon 3 leds en D3,D4 y D5)

{% youtube %}https://www.youtube.com/watch?v=b6YviyYLsTk&feature=youtu.be{% endyoutube %}

Este es el programa que tienes que cargar en el Arduino. Súbelo, empareja tu móvil[ como hemos visto aquí](vincular_mvil.html) y conseguirás que **blue control** encienda los leds como en el vídeo.

```cpp
//PROGRAMA DONDE SE ENCIENDEN LOS LEDS DE EDUBASICA SEGÚN LA APP BLUECONTROL ///////////////////
//
// FLECHA ARRIBA -> SE ENCIENDE EL LED ROJO
// BOTON CENTRO  -> SE ENCIENDE EL LED AMARILLO
// FLECHA ABAJO ->  SE ENCIENDE EL LED VERDE
//
///////////////////////////////////////////////////////////////////////////////////////////////
int ledArriba = 5; //LED ROJO DE EDUBASICA
int ledCentro = 4; //LED AMARILLO DE EDUBASICA
int ledAbajo = 3; // LED VERDE DE EDUBASICA
byte dato;
//////////////////////////////////////////////////////////////////////////////////////////////
void setup() {
Serial.begin(9600);
pinMode(ledArriba,OUTPUT);
pinMode(ledAbajo,OUTPUT);
pinMode(ledCentro,OUTPUT);
}
/////////////////////////////////////////////////////////////////////////////////////////////////////
void loop() {
  if (Serial.available()) //Guardamos en la variable dato el valor leido
        dato= Serial.read();
   //Comprobamos el dato
   switch(dato) {//Si recibimos una  ...  85=ARRIBA  68=U=ABAJO 67=D=CENTRO  76=L=IZQUIERDA 82=R=DCHA  97=a  98=B  99=C
         case 85: //ARRIBA
         {
           digitalWrite(ledArriba, HIGH);
           digitalWrite(ledAbajo, LOW);
           digitalWrite(ledCentro, LOW);        
           break;
         }
         case 68: //"U": ABAJO
         {
           digitalWrite(ledArriba, LOW);
           digitalWrite(ledAbajo, HIGH);
           digitalWrite(ledCentro, LOW);
           break;
         }
         case 67: //"D": CENTRO
         {
           digitalWrite(ledArriba, LOW);
           digitalWrite(ledAbajo, LOW);
           digitalWrite(ledCentro, HIGH);
           break;
         }
         default:   //en caso contrario que apague todo
         {
           digitalWrite(ledArriba, LOW);
           digitalWrite(ledAbajo, LOW);
           digitalWrite(ledCentro, LOW);
           break;
         }      
  }
}
```