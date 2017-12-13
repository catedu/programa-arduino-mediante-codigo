
# Montaje 5: Control de la intensidad de iluminación de un LED EDUBASICA

Como ejemplo práctico de la señal PWM vamos a realizar un control de iluminación  sobre un diodo led.

### En una protoboard

- El circuito formado por el potenciómetro conectado a la entrada analógica A0.

![](img/Captura_de_pantalla_2015-05-19_a_las_14.22.42.png)
- El circuito conectado al pin digital D3, utilizado como salida PWM, de esta manera nos va a permitir variar la luminosidad del LED.

![](img/Captura_de_pantalla_2015-05-19_a_las_14.22.51.png)
### En la shield EDUBASICA

En este caso ya tiene integrado un potenciómetro conectado a la entrada A0

Y vamos a utilizar de salida el diodo verde conectado a D3 y a una resistencia ya integrado en EDUBASICA:

Vamos a ver una pequeña demostración:

<video width="320" height="240" class="mediaelement" src="intensidadled.mp4" controls="controls">[intensidadled.mp4](intensidadled.mp4)</video>

Cargamos el programa ejemplo, en la placa Arduino y teniendo acoplada la placa EduBásica o montados los circuitos en una placa protoboard, podemos ver su funcionamiento.

 Para ver su funcionamiento activamos el monitor serie del IDE de programación y variamos el potenciómetro. El resultado es una variación de luminosidad y variación de valores en el monitor serie.

 El siguiente gráfico es una pantalla del monitor serie con los valores leídos y el valor aplicado a la señal PWM para variar la luminosidad.

![](img/Captura_de_pantalla_2015-05-19_a_las_21.17.31.png)


