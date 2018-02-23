
# Montaje 14 Barrera II con sensores US

Ahora **le añadimos ** *(esperamos que no hayas desmontado el montaje anterior)* dos sensores de ultrasonidos, si detecta el coche a la entrada de la barrera, se enciende la luz amarilla en espera que el coche pueda abrir con el móvil.

Una vez recibido el código de abrir barrera, se abre y se enciende la luz verde.

Una vez cruzado el coche, lo detecta el ultrasonido de la salida que cerrará la barrera poniendo el semáforo en rojo otra vez.

{% youtube %}https//www.youtube.com/watch?v=nlnxai_u360?rel=0{% endyoutube %}

La configuración de pines de los ultrasonidos que hemos elegido esta en los comentarios del programa (o sea, dónde hay que conectar *Trg* y *Echo* de los sensores). Puedes [ver aquí cómo se conectan los ultrasonidos](/montaje_7_medicin_de_la_distancia.md).

Si no tienes edubásica tendras que añadir los leds de [semáforo, pincha aquí](/montaje_3_semforo_edubasica.md).

>El programa por supuesto es mejorable (tiene fallos a ver si los adivinas).



```cpp
String readString;
#include <Servo.h> 
#include <Servo.h> 
 
Servo myservo;        // crea un objeto tipo servo para controlar el servo 
int pos ;          // variable para almacenar la posición del servo
byte dato=0; 
int ledArriba = 3; //LED VERDE DE EDUBASICA
int ledCentro = 4; //LED AMARILLO DE EDUBASICA
int ledAbajo = 5; // LED ROJO DE EDUBASICA
///////////////// SENSOR ULTRASONIDOS 1 ENTRADA ///////////////
int trigPinE = 4; //CONECTAR AL D4 EL TRIG ULTRASONIDOS 1
int echoPinE = 2; //CONECTAR A D2 EL ECHO ULTRASONIDOS 1
long durationE; //tiempo de ida/vuelta
int cmE=0; //Para almacenar el valor obtenido en cm valor=0
///////////////// SENSOR ULTRASONIDOS 2 SALIDA ///////////////
int trigPinS = 6; //CONECTAR AL D6 EL TRIG ULTRASONIDOS 2

int echoPinS = 5; //CONECTAR A D5 EL ECHO ULTRASONIDOS 2

long durationS; //tiempo de ida/vuelta
int cmS=0; //Para almacenar el valor obtenido en cm valor=0
//////////////////////////////////////////////////////////////////

void setup(){ 
  myservo.attach(7);  // En EduBasica el servo se conecta al pin 7 
  Serial.begin(9600);
  ////////////////// configuramos como salida los leds del semáforo
  pinMode(ledArriba,OUTPUT);
  pinMode(ledAbajo,OUTPUT);
  pinMode(ledCentro,OUTPUT);
  //////////////////// configuramos las entradas y salidas de los ultrasonidos E y S
   pinMode(trigPinE, OUTPUT);
  pinMode(echoPinE, INPUT);
   pinMode(trigPinS, OUTPUT);
  pinMode(echoPinS, INPUT);
 //////////////// empezamos con el semároro en rojo
  digitalWrite(ledArriba, LOW);
  digitalWrite(ledAbajo, HIGH);
  digitalWrite(ledCentro, LOW);
  //////////////////// Cerramos la barrera al principio
  pos=140;        
  myservo.write(pos); 
}

void loop() 
{ 
  digitalWrite(trigPinE, LOW);
  delayMicroseconds(2);
  digitalWrite(trigPinE, HIGH);
  delayMicroseconds(10);
  digitalWrite(trigPinE, LOW);
  durationE = pulseIn(echoPinE, HIGH);
  durationE=durationE/2;
  cmE = durationE/ 29;
  Serial.println(cmE);
  if (cmE<10){ ///////////////////////////HAY UN COCHE EN LA ENTRADA /////////////
      /////////////// PONEMOS AMARILLO EL SEMAFORO
      digitalWrite(ledArriba, LOW);
      digitalWrite(ledAbajo, LOW);
      digitalWrite(ledCentro, HIGH);
      /////////////////// ESPERAMOS A QUE DE LA ORDEN DE SUBIR BARRERA 
      if (Serial.available())
        dato= Serial.read();
      switch(dato) {//Si recibimos una  ...  85=ARRIBA  68=U=ABAJO
         case 85: //ARRIBA
           digitalWrite(ledArriba, HIGH);
           digitalWrite(ledAbajo, LOW);
           digitalWrite(ledCentro, LOW);
           pos=40;        
           myservo.write(pos); 
           delay(1000); 
           dato=0;
           break;
       }
       
  }
  ///////////////////////////////////////////////////////////////////////////
  digitalWrite(trigPinS, LOW);
  delayMicroseconds(2);
  digitalWrite(trigPinS, HIGH);
  delayMicroseconds(10);
  digitalWrite(trigPinS, LOW);
  durationS = pulseIn(echoPinS, HIGH);
  durationS=durationS/2;
  cmS = durationS/ 29;
  Serial.println(cmS);
  if (cmS<10){ ///////////////////////////HAY UN COCHE EN LA SALIDA /////////////
       //////////////// ponemos con el semároro en rojo
      digitalWrite(ledArriba, LOW);
      digitalWrite(ledAbajo, HIGH);
      digitalWrite(ledCentro, LOW);
      //////////////////// Cerramos la barrera
      delay(3000);
      pos=140;        
      myservo.write(pos); 
  }
}
```
# FINNNN
Esperamos que este curso, no sólo te has formado, sino que has disfrutado. Cualquier sugerencia, cambio, propuesta, fallos... puedes hacerlo en [www.catedu.es](https://www.catedu.es) en la sección de Tickets ¡¡gracias!!!

<iframe src="https://giphy.com/embed/T9zBDkhqJznwI" width="480" height="360" frameBorder="0" class="giphy-embed" allowFullScreen></iframe><p><a href="https://giphy.com/gifs/robots-T9zBDkhqJznwI">via GIPHY</a></p>

