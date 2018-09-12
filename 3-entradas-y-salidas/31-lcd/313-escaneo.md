#Escaneo
El bus I2C está vinculado en el Arduino Uno a los Pines A4 y A5 como hemos visto en [la anterior página](/3-entradas-y-salidas/31-lcd/312-i2c.md), el protocolo serie I2C necesita **la librería Wire.h **que está de forma nativa en el programa [Arduino IDE](https://www.arduino.cc/en/Main/Software), pero la **dirección de dispositivo no lo sabemos** PARA ELLO HAY QUE EJECUTAR ESTE CÓDIGO:
```cpp+lineNumbers:true
#include <Wire.h>
 
 
void setup()
{
  Wire.begin();
 
  Serial.begin(9600);
  while (!Serial);             // Leonardo: wait for serial monitor
  Serial.println("\nI2C Scanner");
}
 
 
void loop()
{
  byte error, address;
  int nDevices;
 
  Serial.println("Scanning...");
 
  nDevices = 0;
  for(address = 1; address < 127; address++ )
  {
    // The i2c_scanner uses the return value of
    // the Write.endTransmisstion to see if
    // a device did acknowledge to the address.
    Wire.beginTransmission(address);
    error = Wire.endTransmission();
 
    if (error == 0)
    {
      Serial.print("I2C device found at address 0x");
      if (address<16)
        Serial.print("0");
      Serial.print(address,HEX);
      Serial.println("  !");
 
      nDevices++;
    }
    else if (error==4)
    {
      Serial.print("Unknown error at address 0x");
      if (address<16)
        Serial.print("0");
      Serial.println(address,HEX);
    }    
  }
  if (nDevices == 0)
    Serial.println("No I2C devices found\n");
  else
    Serial.println("done\n");
 
  delay(5000);           // wait 5 seconds for next scan
}
```
Extraido de [Arduino.cc](https://playground.arduino.cc/Main/I2cScanner) o también de [Luis Llamas](https://www.luisllamas.es/arduino-i2c/)

Nos tiene que salir lo siguiente:

![](/assets/escanerI2c.gif)

En mi caso como ves la dirección me ha salido **0x3F** pero puede ser cualquier otro, por ejemplo otro valor muy típico es **0x27**
