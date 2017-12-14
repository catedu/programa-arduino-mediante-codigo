
# Montaje 9 Representación gráfica de medidas con Processing.

Una vez obtenidos los datos de temperatura y humedad a través del sensor DHT11 desde Arduino, enviamos, a través del puerto serie, estos datos al PC, donde tenemos ejecutando un programa en Processing que está "escuchando" el puerto serie, obteniendo los datos y representándolos en pantalla. Simultáneamente guardamos los datos en un archivo de texto que posteriormente podremos analizar en una hoja de cálculo.

### Programa a cargar en el ARDUINO

Cargamos este programa, fíjate que sólo ponemos un valor de la temperatura, si queremos representar la humedad, quitamos el comentario de la temperatura y ponemos el de la humedad

**IMPORTANTE**: No hay que tener abierto el monitor serie del IDE de Arduino porque ocupa el puerto y, por lo tanto, no deja leer los datos a Processing.

Si fuera un DHT12 en vez de un DHT11 poner comentarios a las 4 primeras líneas delante // y quitárselas a las 3 siguientes

```cpp
/// ////////////// CON DHT11 ////////////////////////
#include "DHT.h"
#define DHTPIN 2   
#define DHTTYPE DHT11   // DHT 11 
DHT dht(DHTPIN, DHTTYPE);
////////////////////////////////// SI FUERA DHT12 ///
//#include "cactus_io_DHT22.h"
//#define DHT22_PIN 2 
//DHT22 dht(DHT22_PIN);
/////////////////////////////////////////////
void setup() {
  Serial.begin(9600); 
  dht.begin();
}
void loop() {

  delay(2000);
  float h = dht.readHumidity();
  float t = dht.readTemperature();
  if (isnan(h) || isnan(t)) {
    Serial.println("Fallo al leer el sensor DHT11");
    return;
  }
  // Únicamente enviar a Processing una variables t o h 
  //Serial.println(h);
  Serial.println(t);
}
```

### Programa a Cargar en PROCESING

[Aquí lo tienes](http://aularagon.catedu.es/materialesaularagon2013/Arduino-codigo/6_Control_robotica/MiProgramaProcesing.rar) (rar - 1,96 <abbr title="KiloBytes" lang="en">KB</abbr>), sólo representa un valor, está puesto en el puerto 0 puertoArduino = new Serial(this, Serial.list()[0], 9600);

El resultado puedes verlo aquí abajo para la temperatura, el aumento se debe a aplicar vaho al sensor:

Otra versión más sofisticada lo tienes en [esta página ](http://diymakers.es/arduino-processing-primeros-pasos/)

![](img/img0.1.png)
## Otro programa de visualización de datos

En este caso no vamos a representar los datos en forma de gráfica, sino por colores, y además vamos a añadir un botón que encienda un LED conectado por simplicidad en el pin 13

### Programa a cargar en el ARDUINO

El programa lee la temperatura y lo escribe en el puerto serie en forma de byte. También lee el puerto serie para cambiar el estado del led.

```cpp
#include "DHT.h"
#define DHTPIN 2   
#define DHTTYPE DHT11   // DHT 11 
DHT dht(DHTPIN, DHTTYPE);

boolean status=LOW; //Estado del led
void setup() {
  Serial.begin(9600); 
  pinMode(13,OUTPUT);
  dht.begin();
}

void loop() {
  delay(100);
  
  //float h = dht.readHumidity();
  int temp = dht.readTemperature();
  Serial.write(temp); //Enviamos los datos en forma de byte
  if(Serial.available()>0)//Si el Arduino recibe datos a través del puerto serie
  {
    byte dato = Serial.read(); //Los almacena en la variable "dato"
    if(dato==65)  //Si recibe una "A" (en ASCII "65")
    {
      status=!status; //Cambia el estatus del led
    }
    digitalWrite(13,status);
  }
  
}
```

En el Arduino tenemos que poner el sensor de temperatura y humedad tal y como se ha explicado en el Montaje 8 y además un led en el 13

![](img/img1.1.png)
### Programa en Processing

Extraido de la página [http://diymakers.es/arduino-processing-primeros-pasos/](http://diymakers.es/arduino-processing-primeros-pasos/) pero adaptado, [te lo puedes descargar aquí ](http://aularagon.catedu.es/materialesaularagon2013/Arduino-codigo/6_Control_robotica/dymakers.rar) (rar - 31,02 <abbr title="KiloBytes" lang="en">KB</abbr>)(recuerda cambiar port = new Serial(this, Serial.list()[0], 9600); por tu puerto )

![](img/img2.1.png)






