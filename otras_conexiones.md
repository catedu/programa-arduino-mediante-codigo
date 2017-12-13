
# Otras conexiones

Para la comunicación en una dirección:

![](img/img0.1.png)
 [  maestro(izquierda)-&gt;esclavo(derecha)  ] sólo necesitamos 1 conexión:

NOTA: 

Ocurre que esos pines también los usa para comunicarse por USB cuando está conectado al ordenador, de manera que si queremos tener ambas conexiones (USB/trasmisión serie) deberemos crear una nueva conexión serie (en una conexión software). Sólo podemos conectar 2 Arduinos pues sólo hay un puerto de serie en cada uno de ellos. Aunque la conexión es en un sentido, es necesario conectar los dos cables TX-RX y RX-TX

En este ejemplo, una de las Arduino la vamos a tener conectada al PC, por tanto, en el MAESTRO vamos a crear la conexión software serie sobre los pines 10(RX), 11(TX). 

Lo puedes comprobar en la siguiente imagen:

![](img/img1.png)
El programa sería el siguiente:

