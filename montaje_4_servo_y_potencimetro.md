
# Montaje 4 servo y potenciómetro

# Actividad

Podemos probar una aplicación muy importante que está basada en mover el servo según una determinada entrada analógica. Este nos puede ser  muy útil si queremos controlar servos por medio de joysticks por ejemplo o cualquier dispositivo que cuente con potenciómetros para realizar un movimiento.

Para este ejemplo símplemente carga el ejemplo que viene incluido en la IDE de de Arduino (Knob) que encontrarás en:

 Archivo-&gt;Ejemplos-&gt;Servo 

Para que funcione en Edubásica sólo tienes que cambiar el número de pin de la conexión del servo: **myservo.attach(7)**;  

Lo que hace este programa es variar la posición del servo enfunción de la posición del potenciómetro que leemos de manera analógica.

Sólo nos queda mapear la lectura para que se mueva de 0 a 180º.

