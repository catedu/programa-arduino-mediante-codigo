
# Montaje 1: Testea tu servo

En el siguiente programa de testeo en el [obtenido del forum arduino](http://forum.arduino.cc/index.php?topic=118333.0) que lo tienes más abajo, puedes probar tu servo.

- Conecta el servo al pin 7 
- Utiliza el puerto serie para teclear el ángulo que quieras con el teclado de tu ordenador.
- No queremos que entiendas todo el código, pues el puerto serie lee es carácteres ASCII y tiene que convertir el carácter a ángulos.
- Si tecleas un valor más grande de 500 se le indica al servo no el ángulo que se tiene que mover, sino cuanto tiempo en ms se tiene que mover.

Por ejemplo en este Servo **HD-1440A** con el anterior programa se ve que es un servo barato:

- No puede hacer ángulos de +180º luego es un servo convencional
- No puede hacer ángulos de menos de 10º no llega a parar, o sea tiene deriva.

El resultado se puede ver aquí:

{% youtube %}https//www.youtube.com/watch?v=b7JWiL-tucg?rel=0{% endyoutube %}

Si eliges uno un poco más caro como el **MG90S** no tiene estos problemas en los extremos. [Ver](https://catedu.github.io/programa-arduino-con-echidna/55-rele.html)

Mira la diferencia con un **servo de rotación continúa**, fíjate como:
- Los extremos 0º y 180º es a máxima velocidad, pero un sentido u otro.
- 90º es parado.
- Un valor intermedio es menos velocidad (se ve el ejemplo 80º y 100º)
- Si tiene deriva, (cosa frecuente) hay un potenciómetro para ajustar.

>El vídeo está realizado con otra Shield: [Echidna](https://www.gitbook.com/book/catedu/programa-arduino-con-echidna/details).

{% youtube %}https://www.youtube.com/watch?v=Z-5SerXmRY0&feature=youtu.be{% endyoutube %}

## Programa

```cpp+lineNumbers:true
// zoomkat 10-22-11 serial servo test
// type servo position 0 to 180 in serial monitor
// or for writeMicroseconds, use a value like 1500
// for IDE 0022 and later
// Powering a servo from the arduino usually *DOES NOT WORK*.

String readString;
#include <Servo.h> 
Servo myservo;  // create servo object to control a servo 

void setup() {
  Serial.begin(9600);
  myservo.writeMicroseconds(1500); //set initial servo position if desired
  myservo.attach(7);  //the pin for the servo control 
  Serial.println("servo-test-22-dual-input"); // so I can keep track of what is loaded
}

void loop() {
  while (Serial.available()) {
    char c = Serial.read();  //gets one byte from serial buffer
    readString += c; //makes the string readString
    delay(2);  //slow looping to allow buffer to fill with next character
  }

  if (readString.length() >0) {
    Serial.println(readString);  //so you can see the captured string 
    int n = readString.toInt();  //convert readString into a number

    // auto select appropriate value, copied from someone elses code.
    if(n >= 500)
    {
      Serial.print("writing Microseconds: ");
      Serial.println(n);
      myservo.writeMicroseconds(n);
    }
    else
    {   
      Serial.print("writing Angle: ");
      Serial.println(n);
      myservo.write(n);
    }

    readString=""; //empty for next input
  } 
}

```

