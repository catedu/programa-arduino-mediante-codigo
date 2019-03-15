# Entorno de programación

El entorno de desarrollo Arduino IDE \(IDE,  Integrated development environment\)\(aquí [https://www.arduino.cc/en/Main/Software](https://www.arduino.cc/en/Main/Software) para descargártelo\) 

> OJO, existe la versión web del editor [https://create.arduino.cc/editor ](https://create.arduino.cc/editor)para trabajar online, puedes probarlo, pero seguimos recomendando la versión de escritorio por ser más rápida, no obstante es una buena solución si trabajas en varios equipos y quieres que tus proyectos estén disponibles.
>
> En Linux puede salir este mensaje _"can't open device "/dev/ttyUSB0": Permission denied"_ donde 0 puede ser otro número, la solución [aquí](https://arduino.stackexchange.com/questions/21215/first-time-set-up-permission-denied-to-usb-port-ubuntu-14-04)

Está constituido por un **editor de texto** para escribir el código, un **área de mensajes**, una barra de herramientas con botones para las funciones comunes, y una serie de menús.

Arduino utiliza para escribir el código fuente o programa de aplicación lo que denomina "sketch" \(programa\). Estos programas son escritos en el editor de texto. Existe la posibilidad de cortar/pegar y buscar/remplazar texto.

 ![](/assets/entorno.jpg)
  
Permite la conexión, por USB, con el hardware de Arduino para cargar los programas y comunicarse con ellos.

![](/assets/puertoide.jpg)

Y permite varias placas, tenemos que elegir la nuestra, en el KIT de CATEDU es Arduino UNO pero si tienes otro modelo este curso seguro que puede ser válido:

![](/assets/2019-03-15 19_41_29-puerto ide arduino - Buscar con Google.jpg)

En el área de mensajes se muestra información mientras se cargan los programas y también muestra errores. 

** Lo importante es cuando pinchemos en la flecha de subir nuestro programa, no salga ningún error, sino simplemente "Subido"**.

![](/assets/flecha.jpg)

## ¿Cómo se programa Arduino?

Las partes principales de un programa hecho en Arduino son: Bloque de inclusión de módulos y declaración de variables, bloque de configuración **void setup\(\)** donde se indica el modo de funcionamiento de los pines \(entrada y salida\), comunicación serie, etc... y bloque de ejecución continua **void loop\(\)**, en este bloque se incluyen las acciones que queremos que realice el programa. Se ejecutará línea a línea de forma secuencial y continua. Cuando llegue a la última instrucción incluída en la función **loop\(\)** volverá a ejecutar la primera y continuará en un bucle infinito.

![](img/Captura_de_pantalla_2015-04-13_a_las_12.34.57.png)

## ¿Arduino tiene que estar continuamente conectada a un ordenador?

Sólo es necesario que esté conectado al ordenador mediante el USB para cargar los programas o para visualizar en tiempo de ejecución datos del programa mediante la consola serie. El ordenador proporciona la energía eléctrica suficiente para que funcionen los programas, pero una vez cargado el programa en la memoria del microcontrolador de Arduino se puede desconectar del USB y alimentar a la tarjeta mediante una fuente externa mediante el jack de alimentación con un margen de \(5 a 20 Voltios\). El programa cargado en Arduino queda grabado permanentemente aunque cese el suministro eléctrico.

## **¿Qué voy a aprender con este manual?**

Aprenderás a realizar pequeños proyectos y prácticas cuya base de control es la tarjeta Arduino y en algunos casos la shield “Edubásica”. EDUBÁSICA es una tarjeta que se coloca sobre Arduino y lleva integrados muchos de los componentes básicos para realizar las prácticas de electrónica, y ciertos proyectos tecnológicos de una manera muy sencilla, aunque todas las prácticas se pueden implementar sin el uso de esta tarjeta.  La idea del manual es integrar los contenidos del currículo en 4º de Enseñanza Secundaria Obligatoria \(alumnos de 15-16 años\) con diferentes proyectos para que el alumno consiga un aprendizaje significativo de la Tecnología.

Para una mayor información y manejo de la instalación del entorno de programación, lenguaje de programación y librerías se encuentra en la página web de la comunidad Arduino:

[www.arduino.cc ](http://www.arduino.cc ) \(portal en inglés, más actualizada\).

[www.arduino.es](http://www.arduino.es) \(portal en español\).

