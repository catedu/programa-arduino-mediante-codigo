
# Processing

Es un programa similar al IDE de Arduino que has estado manejando hasta ahora, sólo cambia en un botón de PLAY y en otro de STOP., es software abierto desarrollado en Java por Ben Fry y Casey Reas a raiz de una reflexiones en un congreso donde se detecto esta necesidad. Te lo puedes descargar de [http://processing.org](http://processing.org) 

### ¿Para qué sirve?

Es muy común tener la necesidad te representar los datos que nos da Arduino en un entorno visual mucho más atractivo que el monitor serie que nos ofrece IDE Arduino. Si quieres saber las instrucciones que tiene y más información [consulta esta página](http://diymakers.es/arduino-processing-primeros-pasos/).

### Saber el puerto de conexión

Para empezar a utilizar Processing con nuestro Arduino necesitamos saber en qué puerto se conecta, una forma fácil es cargar y ejecutar este código con el Arduino conectado y que liste los puerto, esta instrucción **printArray(Serial.list());** nos lo puede decir 



Y el resultado puedes ver que sale abajo en la consola [0] "COM4" luego es el 0 en mi caso

![](img/img0.png)
