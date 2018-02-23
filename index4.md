
# Tecnologías de la comunicación

![](img/Captura_de_pantalla_2015-04-03_a_las_16.52.42.png)

Las tecnologías de comunicaciones se basan en la transmisión de datos entre puntos distantes. Estos datos, se transmiten en forma de señales eléctricas y pueden ser enviadas através de cables o de manera inalámbrica.

En el Arduino trabajamos con dos tipos de comunicaciones:
* **Alámbrica** Comunicación puerto serie:
    * *PC-Arduino*: La comunicación vía puerto serie:
        * Lo vimos por primera vez en el [semáforo](/montaje_3_semforo_edubasica.md).
        * Hay que incializar el puerto serie **Serial.begin(9600)**
        * Con la función **Serial.print** Arduino puede enviar al ordenador los datos que queramos.
    * *Arduino- Arduino*
        * Veremos en esta unidad una forma muy sencilla de comunicarse dos arduinos también por puerto serie.
* **Inalámbrica**: La comunicación vía *Bluetooth*
    * En esta unidad vamos a utilizar un nuevo dispositivo **JY-MCU**
    * Emparejaremos con nuestro Smartphone (Android) y podremos enviar órdenes de nuestro móvil al Arduino.

