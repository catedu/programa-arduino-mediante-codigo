
# Montaje 12 Barrera I por Bluetooth

Conectamos la Shield de Edubásica, el módulo Bluetooth en el zócalo correspondiente [tal y como vimos](http://aularagon.catedu.es/materialesaularagon2013/Arduino-codigo/5_Comunicaciones/mdulo_bluetooth.html), con piezas de lego fijamos el servo y le añadimos un cartón que simule una barrera. El pin del servo lo conectaremos en el 7 de Edubásica. La configuración de los ángulos de abierto y cerrado depende en qué posición atornillamos la barrera, luego lo mejor es [probarlo con el programa que test que vimos](montaje_1_testea_tu_servo.html), y en nuestro caso nos sale que 40º es abierto y 140º es cerrado.

El propósito es que cuando se pulse la flecha arriba de la app BlueControl la barrera suba y se enciende la luz verde, y cuando se pulsa la flecha abajo, baje la barrera y se enciende la luz roja, esta es una manera eficaz de que nadie entre en el recinto si no está autorizado, y que mejor que con una aplicación móvil.

**(no hagas caso de los sensores de ultrasonidos por ahora, corresponde al siguiente montaje)**

{% youtube %}https//www.youtube.com/watch?v=tg0k7ZHvmCg?rel=0{% endyoutube %}
El programa en el Arduino es el siguiente:



