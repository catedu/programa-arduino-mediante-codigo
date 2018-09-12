#Chasis coche Con Edubásica

Puedes ver en [esta página de Luis Llamas ](https://www.luisllamas.es/coche-robot-barato-con-arduino-presupuesto/) cómo hacer un coche teledirigido puede salir por menos de 20€, nosotros como ya tenemos el L298N integrado en **Edubasica**, sólo hemos comprado el [chasis](https://es.aliexpress.com/item/Free-shipping-Smart-car-chassis-Tracing-car-The-robot-car-chassis-With-code-disc-tachometer-Four/32554236304.html) por 7€ y no vamos a poner sensor ultrasonidos y sensor de línea:

![](/assets/coche1.png)

Si quieres hacerlo todo terreno [Luis Llamas te explica cómo hacerlo con cadenas](https://www.luisllamas.es/arduino-robot-cadenas/).

###Conexiones

Las conexiones son muy sencillas:

* Pines motor A al conector pines motor A de Edubásica
* Pines motor B al conector pines motor B de Edubásica
* Cables de las pilas a Vin y GND

![](/assets/2018-02-05 12_57_31-Documento1 - Microsoft Word.png)

>NOTA: Si funciona pero con las oŕdenes cambiadas (es decir que queremos que gire a la izquierda y va hacia delante, queremos que vaya hacia delante y gira a la izquierda...) es debido a que tenemos los cables rojo y negro de un motor intercambiados.

###Ordenes
Estos son los pines que hay que activar:

|Orden|MotorA|MotorB|
|--|--|--|
|Velocidad|10|11|
|Dirección 1|8|12|
|Dirección 2|9|13|

La tabla de verdad es muy fácil:

**MOTOR A**

|Pin 10|Pin 8|Pin 9|MotorA|
|--|--|--|--|
|HIGH|HIGH|LOW|giro|
|HIGH|LOW|HIGH|giro contrario|
|LOW|X|X|STOP|

**MOTOR B**

|Pin 11|Pin 12|Pin 13|MotorB|
|--|--|--|--|
|HIGH|HIGH|LOW|giro|
|HIGH|LOW|HIGH|giro contrario|
|LOW|X|X|STOP|

##AUN TE QUEDA UNA CONEXIÓN
Recuerda que en el transistor aún puedes poner otro motor.
Respecto a terminales digitales, te quedan pines para poner servos, sensor de ultrasonidos, sensor de líneas...

<iframe src="https://giphy.com/embed/RhdxqQ81tfURi" width="480" height="270" frameBorder="0" class="giphy-embed" allowFullScreen></iframe><p><a href="https://giphy.com/gifs/arduino-RhdxqQ81tfURi">via GIPHY</a></p>

... en fin que las posibilidades son muchas

<iframe src="https://giphy.com/embed/8lQwnL1gIp5G8" width="480" height="270" frameBorder="0" class="giphy-embed" allowFullScreen></iframe><p><a href="https://giphy.com/gifs/arduino-8lQwnL1gIp5G8">via GIPHY</a></p>


