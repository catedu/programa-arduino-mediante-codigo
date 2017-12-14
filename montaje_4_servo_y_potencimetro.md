
# Montaje 4 servo y potenciómetro

# Actividad

Podemos probar una aplicación muy importante que está basada en mover el servo según una determinada entrada analógica. Este nos puede ser  muy útil si queremos controlar servos por medio de joysticks por ejemplo o cualquier dispositivo que cuente con potenciómetros para realizar un movimiento.

Para este ejemplo símplemente carga el ejemplo que viene incluido en la IDE de de Arduino (Knob) que encontrarás en:

 Archivo-&gt;Ejemplos-&gt;Servo 

Para que funcione en Edubásica sólo tienes que cambiar el número de pin de la conexión del servo: **myservo.attach(7)**;  

Lo que hace este programa es variar la posición del servo enfunción de la posición del potenciómetro que leemos de manera analógica.

Sólo nos queda mapear la lectura para que se mueva de 0 a 180º.

```cpp
/*
 Controlling a servo position using a potentiometer (variable resistor)
 by Michal Rinott <http://people.interaction-ivrea.it/m.rinott>

 modified on 8 Nov 2013
 by Scott Fitzgerald
 http://www.arduino.cc/en/Tutorial/Knob
*/

#include <Servo.h>

Servo myservo;  // create servo object to control a servo

int potpin = 0;  // analog pin used to connect the potentiometer
int val;    // variable to read the value from the analog pin

void setup() {
  myservo.attach(7);  // attaches the servo on pin 9 to the servo object
}

void loop() {
  val = analogRead(potpin);            // reads the value of the potentiometer (value between 0 and 1023)
  val = map(val, 0, 1023, 0, 180);     // scale it to use it with the servo (value between 0 and 180)
  myservo.write(val);                  // sets the servo position according to the scaled value
  delay(15);                           // waits for the servo to get there
}
```

{% youtube %}https://www.youtube.com/watch?v=_knaXSFBF_M&feature=youtu.be{% endyoutube %}