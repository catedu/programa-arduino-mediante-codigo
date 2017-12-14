
# Montaje 1: Testea tu servo

En el siguiente programa de testeo en el [forum arduino](http://forum.arduino.cc/index.php?topic=118333.0) que te lo puedes [descargar aquí](http://aularagon.catedu.es/materialesaularagon2013/Arduino-codigo/6_Control_robotica/control-servo.ino) (ino - 1,36 <abbr title="KiloBytes" lang="en">KB</abbr>), puedes probar tu servo <br />

- Conecta el servo al pin 7 
- Utiliza el puerto serie para teclear el ángulo que quieras con el teclado de tu ordenador.
- No queremos que entiendas todo el código, pues el puerto serie lee es carácteres ASCII y tiene que convertir el carácter a ángulos.
- Si tecleas un valor más grande de 500 se le indica al servo no el ángulo que se tiene que mover, sino cuanto tiempo en ms se tiene que mover.

Por ejemplo en este Servo **HD-1440A** con el anterior programa se ve que es un servo barato:

- No puede hacer ángulos de +180º luego es un servo convencional
- No puede hacer ángulos de menos de 10º no llega a parar, o sea tiene deriva.

El resultado se puede ver aquí:

{% youtube %}https//www.youtube.com/watch?v=b7JWiL-tucg?rel=0{% endyoutube %}

Mira la diferencia con un servo de rotación continúa, fíjate como:
- Los extremos 0º y 180º es a máxima velocidad, pero un sentido u otro.
- 90º es parado.
- Un valor intermedio es menos velocidad (se ve el ejemplo 80º y 100º)
- Si tiene deriva, (cosa frecuente) hay un potenciómetro para ajustar.

https://www.youtube.com/watch?v=Z-5SerXmRY0&feature=youtu.be

