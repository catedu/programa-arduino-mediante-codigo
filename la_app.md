
# La APP

Interactuar con el medio es uno de los objetivos primordiales de Arduino. En esta unidad vamos a ver cómo nos podemos comunicar con un dispositivo móvil, posibilitando así el control remoto de la placa. 

La comunicación con Arduino es muy sencilla, el uso común de este dispositivo, será como receptor o emisor de datos. 

En nuestro caso usaremos caracteres (bytes)  que enviaremos desde un master, como un teléfono móvil. Hay muchas aplicaciones gratuitas para enviar datos, por ejemplo, para dispositivos Android podemos utilizar de manera gratuita. Podemos usar **cualquier APP que emita un código por Bluetooth**.

#Arduino Bluetooth Control

Esta APP es muy completa y configurable, [aquí para descargarla de Google Play](https://play.google.com/store/apps/details?id=com.broxcode.arduinobluetoothfree).

![](/assets/Selection_018.png)

El código de programa que tenemos que cargar en el Arduino se basa en escuchar de forma continua el puerto serie.** Cuando llegue el dato, se ejecutará la acción que le indiquemos**. ¡¡así de sencillo !!

<iframe src="https://giphy.com/embed/xTiIzoyw4Yh3mRM5DG" width="480" height="208" frameBorder="0" class="giphy-embed" allowFullScreen></iframe><p><a href="https://giphy.com/gifs/starwars-star-wars-episode-3-xTiIzoyw4Yh3mRM5DG">via GIPHY</a></p>



