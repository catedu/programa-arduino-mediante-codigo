# Montaje3 Texto en LCD

Vamos a realizar un ejemplo para practicar:

* El encendido y apagado de la pantalla
* Visualización de texto
* Visualización de texto con desplazamiento

Practicaremos qué código tiene que estar en el código dentro de _setup_ y qué código dentro de _bool_:

{% youtube %}    
https://www.youtube.com/watch?v=CBcGb9WWihY
{% endyoutube%}

El código es sencillo, la primera parte que sólo lo hace una vez, tiene que estar en setup y en loop sólo la parte de que se desplaza contínuamente.

**OJO CAMBIA TU DIRECCIÓN 0x3F si no es esa**
```cpp+lineNumbers:true
include <Wire.h> 
#include <LiquidCrystal_I2C.h>


LiquidCrystal_I2C lcd(0x3F,16,2);  ////Crear el objeto lcd  dirección  0x3F y 16 columnas x 2 filas


void setup() {
  // Inicializar el LCD
  lcd.init();
 
  for (int i=0; i <= 255; i++){
      lcd.backlight(); //Encender la luz de fondo.
      lcd.setCursor(1, 0);  // Escribimos el Mensaje en el LCD en una posición 1,0 
      lcd.print("ATENTOS EN:");
      lcd.setCursor(1, 1); // Escribimos el Mensaje en el LCD en una posición  1,1
      lcd.print("www.catedu.es");
      delay (400);
      lcd.backlight();
      delay (200);
  }
  lcd.setCursor(1, 0);
  lcd.print("CURSO DE ARDUINO ACTUALIZADO");
  lcd.setCursor(1, 1);
  lcd.print("APUNTATE ESTE VERANO EN AULARAGON");
}

void loop() {
  //desplazamos una posición a la izquierda
  lcd.scrollDisplayLeft(); 
  delay(400);
}
```