
# Montaje 3: Semáforo EDUBASICA

Montaremos un semáforo con los tres leds de la EduBásica. La EduBásica es opcional y podemos montar el circuito correspondiente con una protoboard, pero EduBásica nos ahorra trabajo. 

Necesitamos añadir una resistencia entre el pin y el led, para evitar que el led se funda. EduBásica ya lleva estas resistencias integradas por lo que podemos ir directamente al montaje.

Vamos a ver el efecto que queremos realizar:

<video width="320" height="240" class="mediaelement" src="semaforo.mp4" controls="controls">[semaforo.mp4](semaforo.mp4)</video>

Carga el programa de la página siguiente en Arduino y verás como actúa.

Aparece un nuevo comando: **Serial.print**.

Este comando nos manda un texto al puesto serial por el que nos comunicamos con Arduino. De esta manera podemos depurar un programa sabiendo siempre por que línea está.

Para que funcione debemos tener en cuenta que:

- Hay que inicializar Serial. Esto se hace poniendo **Serial.begin(9600)** dentro de la rutina de setup(). 9600 se refiere a la velocidad que se comunicará.
- Serial.print(“xxx”) escribe lo que ponemos entre comillas tal cual.
- Serial.print(x) escribe el valor que contenga la variable x.
- Serial.println() es similar a lo anterior pero después añade un salto de línea.

Para ver lo que nuestro Arduino nos comunica por Serial, abrimos el monitor Serial que tenemos en el programa Arduino:

![](img/img3.png)
![](img/Captura_de_pantalla_2015-05-19_a_las_12.00.34.png)


