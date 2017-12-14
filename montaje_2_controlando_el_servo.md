
# Montaje 2 controlando el servo

Arduino incluye una librería con funciones para mover de una manera sencilla un servo, lo primero es introducir un include con la librería al principio, luego creamos el objeto (que será el nombre que usaremos en todo el programa para cada servo que queramos controlar) .

Por último, asociamos el servo al pin al que lo hemos conectado (7).

Una vez declarado, para usarlo, dentro de loop simplemente usamos la función **servo.write(posicion)**

Moverá el servo los grados que le indiquemos mediante la variable entera: **posicion**.

A continuación verás un sencillo ejemplo , dejamos un pequeño delay , para permitir que el servo alcance la posición antes de darle la siguiente orden:

```cpp
#include <Servo.h> 
 
Servo myservo;        // crea un objeto tipo servo para controlar el servo 
int pos ;          // variable para almacenar la posición del servo
 
void setup(){ 
  myservo.attach(7);  // En EduBasica el servo se conecta al pin 7 
}

void loop() 
{ 
  pos=90;        
  myservo.write(pos); 
  delay(1000);        
  pos=180;       
  myservo.write(pos); 
  delay(1000);  
  pos=45;        
  myservo.write(pos); 
  delay(1000);  
}
```


