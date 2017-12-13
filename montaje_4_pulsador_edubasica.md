
# Montaje 4: Pulsador EDUBASICA

Hasta ahora hemos visto como programar Arduino para que ejecute repetitivamente acciones, pero este actuaba de manera autónoma y nosotros sólo podíamos observar.  Pero podemos interactuar con Arduino, por ejemplo, realizando una acción cuando activamos un pulsador. .

En este ejemplo, vamos a encender un led cuando actuamos sobre el pulsador. Por sencillez usaremos EduBásica. (también puedes hacer el montaje en una protoboard). 

Vamos a verlo en acción:

<video width="320" height="240" class="mediaelement" src="pulsador.mp4" controls="controls">[pulsador.mp4](pulsador.mp4)</video>

El pin 2 corresponde al pulsador y el pin 3 al led verde, solo nos queda cargar el programa y probar. Aparece un comando nuevo “**digitalRead(buttonPin)**” . Retorna el valor del pin que se ha configurado como entrada y al igual que en el caso de los pines que se configuran como salida, puede tener dos valores HIGH y LOW.

Si es HIGH significa que este pin está unido a la señal de 5v, si es LOW significa que está unido a 0v.

 ¿Por qué cuando el pulsador está en OFF D2 está a 0V? espero que esta cuestión la has resuelto [en la sección anterior.](resistencias_pullup_y_pulldown.html)



Otra opción es utilizar este programa donde se ve más visual:

