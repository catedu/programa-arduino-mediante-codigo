
# Montaje 11 detección linea blanca

El problema del CNY70 es que tiene los pines muy juntos que no se puede poner enmedio de la placa protoboard, tenemos pues que utlizar dos opciones:

- Utilizar cables Dupond macho-hembra
- Ponerlo inclinado aprovechando que dos extremos de la diagonal tienen que estar conectados a 5V

Lo mejor es utilizar cables M-H pero si no se tienen, vamos a utilizar la segunda opción, este es el esquema:

![](img/m1_img0.1.png)
El programa a cargar en el Arduino es:

El resultado es:

{% youtube %}https//www.youtube.com/watch?v=d6QXe9t__wE?rel=0{% endyoutube %}
Y en el monitor serie sale:

<br />Linea negra<br />Linea negra<br />Linea negra<br />Linea blanca<br />Linea blanca<br />Linea blanca<br />Linea blanca<br />Linea blanca<br />Linea negra<br />Linea negra<br />Linea negra<br />Linea ...

