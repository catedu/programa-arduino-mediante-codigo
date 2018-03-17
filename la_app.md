
# La APP

Interactuar con el medio es uno de los objetivos primordiales de Arduino. En esta unidad vamos a ver cómo nos podemos comunicar con un dispositivo móvil, posibilitando así el control remoto de la placa. 

La comunicación con Arduino es muy sencilla, el uso común de este dispositivo, será como receptor o emisor de datos. 

En nuestro caso usaremos caracteres (bytes)  que enviaremos desde un master, como un teléfono móvil. Hay muchas aplicaciones gratuitas para enviar datos, por ejemplo, para dispositivos Android podemos utilizar de manera gratuita. Podemos usar **cualquier APP que emita un código por Bluetooth**.

#Arduino Bluetooth Control

Esta APP es muy completa y configurable, [aquí para descargarla de Google Play](https://play.google.com/store/apps/details?id=com.broxcode.arduinobluetoothfree).

![](/assets/Selection_018.png)




#Arduino Bluetooth Controller
Esta es otra alternativa: [ Arduino bluetooth controller](https://play.google.com/store/apps/details?id=com.giumig.apps.bluetoothserialmonitor) de Android, pero nos gusta más la anterior Arduino Bluetooth Control pues tiene más opciones.

![](/assets/2018-02-11 07_19_27-¿Cómo emparejar el Bluetooth del Arduino con el móvil y la APP Bluecontrol - Pre.png)


Podemos hacer que un robot o vehículo se mueva dependiendo de las órdenes (letras) que reciba desde la aplicación del teléfono.

Esta aplicación nos ha gustado PORQUE PERMITE CONFIGURAR LAS TECLAS QUÉ CARACTER QUEREMOS ENVIAR luego nosotros vamos a definir estos carácteres:

- Arriba: U
- Abajo: D
- Izquierda: L
- Derecha: R

![](/assets/2018-02-11 07_24_57-¿Cómo emparejar el Bluetooth del Arduino con el móvil y la APP Bluecontrol - Pre.png)

El código de Arduino se basa en escuchar de forma continua el puerto serie. Cuando llegue un dato se ejecutará la acción que le indiquemos. 

