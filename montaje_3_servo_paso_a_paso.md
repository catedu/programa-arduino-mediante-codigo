
# Montaje 3 servo paso a paso

En este caso queremos que practiques la función for

```cpp
#include <Servo.h> 
 
Servo myservo;        // crea un objeto tipo servo para controlar el servo 
int pos ;          // variable para almacenar la posición del servo
 
void setup(){ 
  myservo.attach(7);  // En EduBasica el servo se conecta al pin 7 
}

void loop() 
{ 
 for (pos=10; pos<=180; pos+=10) { 
  myservo.write(pos); //orden con los grados en cada iteración
  delay(1000);
 }
}
```

{% youtube %}https://www.youtube.com/watch?v=IfpJzziVuFw&feature=youtu.be{% endyoutube %}