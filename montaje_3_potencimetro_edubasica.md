
# Montaje : Potenciómetro
Vamos a realizar un programa para comprobar que al variar el valor de una resistencia mediante un potenciómetro, también variará la cantidad de luz que emite un led. Como se puede ver en el siguiente vídeo, a medida que giramos el potenciómetro el led varía su luminosidad.

{% youtube %}https://www.youtube.com/watch?v=EAryWgTyt8Y&feature=youtu.be{% endyoutube %}

##CON EDUBASICA

Vamos a aprovechar el A0 que está conectado al potenciómetro y utilizaremos el D3 que está conectado al LED VERDE 

![Esquema del potenciómetro y de los diodos en EDUBÁSICA](img/m3img1.1.png)

##SIN EDUBASICA

Pues se necesita hacer el cableado correspondiente A0 con el potenciómetro y D3 a un led:

![](/assets/Selection_013.png)

##Continuamos ...
El programa sería el siguiente
```cpp+lineNumbers:true
//Declaramos una variable para almacenar el valor recibido en pin 0.
int val = 0;

void setup() {
//El pin 3 corresponde al LED verde
pinMode(3, OUTPUT);
}

void loop() {
/*leemos el valor del pin O modificado por el potenciómetro que va desde 0 a 1023*/
val = analogRead(0);
/*Escribimos el valor obtenido en el LED verde que puede ser entre 0 y 255. Por eso dividimos val por 4 */
analogWrite(3, val/4);
}
```

