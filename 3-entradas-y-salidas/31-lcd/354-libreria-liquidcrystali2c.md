#Librería LiquidCrystal

Sólo nos falta incorporar la librería LiquidCrystal_I2C que te [lo puedes descargar aquí](https://codeload.github.com/marcoschwartz/LiquidCrystal_I2C/zip/master)

Una vez descargado, es un fichero comprimido .zip o .rar **no lo descomprimas** diréctamente desde el menú del entorno de programación lo incorporas de esta manera :

![](/assets/librerias.gif)


##Principales funciones
**LiquidCrystal_I2C(lcd_Addr, lcd_cols, lcd_rows)**
Crea una variable (informáticamente un objeto de la clase LiquidCrystal_I2C) para poder utilizar sus funciones, hay que indicar entre paréntesis la dirección, columnas y filas indicadas. Por ejemplo LiquidCrystal_I2C lcd(0x3F,16,2);

_¿No sabes la dirección?. Eso es que te has saltado [esta lección](/3-entradas-y-salidas/31-lcd/313-escaneo.md)_ en mi caso es 0x3F.

Después de crear esa variable hay que inicializarlo con lcd.**init()**

>lcd es el nombre de la variable, puedes poner el nombre que quieras

lcd.**clear()**
Borra la pantalla y posiciona el cursor en la esquina superior izquierda (0,0).

lcd.**setCursor(columna, fila)**
Posiciona el cursor del LCD en la posición indicada por columna y fila.

lcd.**print("**texto**")**
Escribe el texto 

lcd.**scrollDisplayLeft()**
Se desplaza el contenido de la pantalla (texto y el cursor) un espacio hacia la izquierda.

lcd.**scrollDisplayRight()**
Se desplaza el contenido de la pantalla (texto y el cursor) un espacio a la derecha.

lcd.**backlight()**
Enciende la Luz del Fondo del LCD

lcd.**noBacklight();**
Apaga la Luz del Fondo del LCD

lcd.**createChar (num, datos)**
Crea un carácter personalizado permite crear hasta 8. Para usar esta función [ver esta página.](https://www.arduino.cc/en/Reference/LiquidCrystalCreateChar)