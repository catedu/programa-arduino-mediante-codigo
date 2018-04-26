#Librería LiquidCrystal

Sólo nos falta incorporar la librería LiquidCrystal_I2C que te [lo puedes descargar aquí](https://codeload.github.com/marcoschwartz/LiquidCrystal_I2C/zip/master)

Una vez descargado, es un fichero comprimido .zip o .rar **no lo descomprimas** diréctamente desde el menú del entorno de programación lo incorporas


##Principales funciones
**LiquidCrystal_I2C(lcd_Addr, lcd_cols, lcd_rows)**
Crea una variable (informáticamente un objeto de la clase LiquidCrystal_I2C) para poder utilizar sus funciones, hay que indicar entre paréntesis la dirección, columnas y filas indicadas.

_¿No sabes la dirección?. Eso es que te has saltado [esta lección](/3-entradas-y-salidas/31-lcd/313-escaneo.md)_ en mi caso es 0x3F.

init()
Inicializa el modulo adaptador LCD a I2C, esta función internamente configura e inicializa el I2C y el LCD.

clear()
Borra la pantalla LCD y posiciona el cursor en la esquina superior izquierda (posición (0,0)).

setCursor(col, row)
Posiciona el cursor del LCD en la posición indicada por col y row(x,y); es decir, establecer la ubicación en la que se mostrará posteriormente texto escrito para la pantalla LCD.

print()
Escribe un texto o mensaje en el LCD, su uso es similar a un Serial.print

scrollDisplayLeft()
Se desplaza el contenido de la pantalla (texto y el cursor) un espacio hacia la izquierda.

scrollDisplayRight()
Se desplaza el contenido de la pantalla (texto y el cursor) un espacio a la derecha.

backlight();
Enciende la Luz del Fondo del LCD

noBacklight();
Apaga la Luz del Fondo del LCD

createChar (num, datos)
Crea un carácter personalizado para su uso en la pantalla LCD. Se admiten hasta ocho caracteres de 5x8 píxeles (numeradas del 0 al 7). Dónde: num es el número de carácter y datos es una matriz que contienen los pixeles del carácter