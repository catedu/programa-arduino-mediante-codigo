
# Montaje 6 Regular intesidad de un LED con EDUBASICA

Se trata de obtener el mismo efecto que se consiguió en [la práctica correspondiente al potenciómetro](montaje_4_mapeo_potenciometro_edubasica.html), las instrucciones principales eran:

Pero en este caso utilizaremos el mapeo. 

La descripción de la práctica es la siguiente:

La regulación del potenciómetro provocará una variación de voltaje en el pin de entrada analógico 0 de Arduino. Se realizará una conversión analógica-digital en el que los valores de tensión analógicos entre 0 y 5 V se transforma a un rango discreto de valores de 0 a 1023. Para modificar la intensidad del led rojo le se enviará una señal pseudoanalógica PWM utilizando la salida 5 digital de Arduino. Para ello se enviará un valor de 0 a 255 que marcará el ciclo de trabajo de la onda cuadrada PWM. Previamente habrá que realizar un mapeo (instrucción map) para asignar valores desde el intervalo [0, 1023] al [0, 255].

{% youtube %}https//www.youtube.com/watch?v=y4OAnbQkR-c{% endyoutube %}


**PROGRAMA:**

