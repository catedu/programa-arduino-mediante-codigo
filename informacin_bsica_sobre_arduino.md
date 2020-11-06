
# Información básica sobre Arduino

### **¿Qué es Arduino?**

Arduino es una tarjeta electrónica que integra básicamente a un microcontrolador y un conjunto de pines de conexión de entradas y salidas que permiten, mediante un determinado programa, interaccionar con el medio físico mediante sensores y actuadores electrónicos. De esta forma podrás crear tus propios proyectos tecnológicos, dotarlos de sensores que detecten magnitudes físicas como luz, calor, fuerza, etc… y en base a esa información, escribiendo un programa, activar otros dispositivos (actuadores) como pequeñas bombillas, ledes, servomotores, pequeños motores DC, relés, etc… Los sensores se conectan a los pines de entrada y los actuadores a los de salida.

**¿Sabías que.... ?** Uno de los co-creadores de Arduino es Español, de Zaragoza: David Cuartieles [+info](https://es.wikipedia.org/wiki/Arduino)

### **¿Qué es un microcontrolador?**

Es un circuito integrado que se puede programar, o sea que puede ejecutar las órdenes que tenga almacenadas en su memoria. Tiene las tres funciones principales de un computador: la unidad central de proceso, memoria y entradas y salidas.

Arduino utiliza la marca ATMEL, y el modelo de microcontrolador depende del tipo de tarjeta, por ejemplo la tarjeta Arduino Uno utiliza el micro ATMEL MEGA 328P.

### **¿Qué se puede hacer con Arduino, algún ejemplo?**

![](img/Captura_de_pantalla_2015-04-06_a_las_11.52.39.png)

Realmente el límite lo marca tu imaginación pero por dar alguna pista, podrías diseñar un sistema para la apertura y cierre de la puerta de un garaje, hacer un robot móvil que detecte objetos o que siga una línea negra, crear un detector de luz y oscuridad, implementar un termómetro, controlar un cilindro neumático, etc…

En este manual tienes múltiples ejemplos de pequeños proyectos para el aula, aunque Arduino es una herramienta que también se utiliza en el ámbito profesional para monitorización de sensores y automatización a pequeña escala por su flexibilidad, fiabilidad y precio.

### **¿Qué son las entradas y salidas?**

Mediante los conectores de Arduino correspondientes a las entradas y salidas podemos comunicar nuestros programas con el “mundo exterior”. Si queremos leer el valor de la magnitud física medida por un sensor, por ejemplo una LDR que detecta el nivel de luminosidad, lo tendremos que hacer conectando el sensor a uno de los pines de entrada (en este caso analógicas) de la tarjeta.

De esta forma con una simple instrucción de lectura en el programa, podremos obtener el valor de la magnitud física. Si nuestra intención es actuar o “hacer algo” una vez leído el valor del sensor, por ejemplo encender un led si el sensor de luminosidad detecta oscuridad, tendremos que conectar el actuador (en este caso el led) a un pin de salida que proporcionará la corriente necesaria para activarlo.

En Arduino las entradas pueden ser analógicas o digitales y las salidas sólo digitales. Cada pin digital tiene doble función entrada o salida. En la zona de configuración del programa hay que indicar explícitamente mediante una instrucción cuál es función desempeña un determinado pin.

### **¿Dónde se conectan los sensores a las entradas analógicas o digitales?**

Los sensores utilizados en los proyectos que vamos a utilizar son de salida analógica, es decir proporcionan una variación de voltaje dentro de un rango (normalmente de 0 a +5V) dependiendo de lo que varíe la magnitud física medida. Muchos sensores son resistivos (luz, temperatura, humedad,…), es decir que varían su resistencia eléctrica con la magnitud física, pero mediante un sencillo montaje de divisor de tensión conseguimos una variación de voltaje apta para Arduino. Estos montajes los veremos en las prácticas del manual.

Una vez realizadas las conexiones, si midiéramos la salida del sensor con un voltímetro nos daría un valor decimal, por ejemplo un nivel de luz “intermedio” (rango de 0 a 5V) de un sensor de luz podría dar 3,3 voltios. Este tipo de información el microcontrolador no la entiende tal cual, sólo es capaz de interpretar números binarios (“0” ó “1”) por lo que para traducir los valores analógicos dispone internamente de un conversor analógico – digital que hará la conversión entre los dos sistemas, de forma que podremos tener valores discretos de la medida de los sensores analógicos.

**Las entradas analógicas** leen valores analógicos entre 0V y la alimentación (normalmente 0-5V) y lo convierte en números entre **0 y 1024**.

### Entonces, ¿qué utilidad tienen las entradas digitales?

Las entradas digitales son útiles cuando las señales a leer son valores discretos. Por ejemplo queremos poner un pulsador o un interruptor que encienda un led. Hacemos un montaje que cuando se pulse, entren 5 voltios en el pin digital de entrada y cuando no se pulse que “entren” 0 voltios. De esta manera la lectura del pin digital de entrada será “HIGH” con 5 voltios o “LOW” con 0 voltios.

### **¿Qué son las salidas digitales etiquetadas con PWM (~)?**

Son salidas digitales que simulan una salida analógica. Las siglas significan Modulación por Ancho de Pulso (Pulse Width Modulation) o proporcionan una onda cuadrada con un nivel alto (+5V) de “cierta” duración.

**Los valores PWM** que podemos proporcionar pueden ir desde **0 a 255** que corresponderían a un 0V analógico y a la máxima tensión (la de alimentación, normalmente 5V). 

Es muy útil para activar servomotores y llevarlos a una posición determinada o variar la luminosidad de un led. Lo puedes ver más explicado en la siguiente sección.

### **¿Puedo accionar motores DC con Arduino?**

Si son motores muy pequeños sí sería posible aunque no es recomendable. Los motores necesitan un consumo alto de corriente, sobre todo si tienen que mover cierta carga, por lo que se recomienda o bien utilizar una tarjeta Shield o extensión de Arduino que dispone de circuitería apta para proporcionar dicha corriente (transistores). En este manual utilizamos una Shield bautizada como Edubásica de elaboración propia que dispone de un transistor y un circuito integrado LM293 para realizar esta función, además de otras ventajas para el aprendizaje de Arduino.

### **Para saber más ...**
Te recomendamos esta página donde indica la historia y la electrónica al detalle de esta placa. https://programarfacil.com/blog/arduino-blog/arduino-uno-r3/

