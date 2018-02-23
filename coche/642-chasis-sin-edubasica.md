#Chasis sin Edubásica
Tenemos que comprar el chasis anterior y además un [L298N, recomendamos ver esta página de Luis Llamas](https://www.luisllamas.es/arduino-motor-corriente-continua-l298n/)

![](https://www.luisllamas.es/wp-content/uploads/2016/05/arduino-l298n.png)

##Conexiones

La circuitería se complica, pues necesitamos cablear los pines de control:

![](https://www.luisllamas.es/wp-content/uploads/2016/05/arduino-l298n-conexion.png)

Tal y como dice Luis Llamas:

>Siempre que uséis más de una fuente de tensión recordar poner en común todos los GND incluido el de Arduino. De lo contrario podéis dañar un componente.

![](http://fritzing.org/media/fritzing-repo/projects/w/working-with-l298n-dc-motor-driver/images/Breadboard.png)

###Ordenes
Para respetar los mismos programas que Luis Llamas, estos son los pines que hay que activar:

|Orden|MotorA|MotorB|
|--|--|--|
|Velocidad|6|11|
|Dirección 1|7|9|
|Dirección 2|8|10|

La tabla de verdad es muy fácil:

**MOTOR A**

|Pin 6|Pin 7|Pin 8|MotorA|
|--|--|--|--|
|HIGH|HIGH|LOW|giro|
|HIGH|LOW|HIGH|giro contrario|
|LOW|X|X|STOP|

**MOTOR B**

|Pin 11|Pin 9|Pin 10|MotorB|
|--|--|--|--|
|HIGH|HIGH|LOW|giro|
|HIGH|LOW|HIGH|giro contrario|
|LOW|X|X|STOP|








