#Montaje por LCD

Ahora vamos a conectarlo por LCD :

{% youtube %} 
https://www.youtube.com/watch?v=6J8PKruEcD4&feature=youtu.be
{% endyoutube%}

##Conexiones
Si tienes el DHT11 o si tienes el DH12 [lo has visto ya](/descripcin_y_esquemas2.md)
Ahora añade el [LCD con el I2C](/3-entradas-y-salidas/31-lcd/312-i2c.md)

##Programa

En este caso lo hacemos con el DHT12 ya sabes que si utilizas DHT11 no mide la humedad y la sensación térmica

```cpp+lineNumbers:true
#include <Wire.h>
#include <LiquidCrystal_I2C.h>

#include "cactus_io_DHT22.h"

#define DHT22_PIN 2     // what pin on the arduino is the DHT22 data line connected to

DHT22 dht(DHT22_PIN);
LiquidCrystal_I2C lcd(0x3F,16,2); ////Crear el objeto lcd dirección 0x3F y 16 columnas x 2 filas

int trigPin = 8;
int echoPin = 9;
float duration; //tiempo de ida/vuelta
float cm=0; //Para almacenar el valor obtenido en cm valor=0

void setup() {

  
  // Inicializar el LCD
  lcd.init();
  lcd.backlight(); //Encender la luz de fondo.
  
}
void loop(){
  
  dht.readHumidity();
  dht.readTemperature();

  lcd.setCursor(0, 0); // Escribimos el Mensaje en el LCD en una posición 1,0
  lcd.print("H=");
  lcd.print(dht.humidity,0); lcd.print("% T=");
  lcd.print(dht.temperature_C,2); lcd.print("*C");
  lcd.setCursor(0, 1); // Escribimos el Mensaje en el LCD en una posición 1,0
  lcd.print("SEN= ");
  lcd.print(dht.computeHeatIndex_C()); lcd.print(" *C");
  delay(3000);
}
```