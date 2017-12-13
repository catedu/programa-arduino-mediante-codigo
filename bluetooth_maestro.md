
# Bluetooth maestro

Vamos a hacer una especial mención a este tipo de módulos.

Hemos comentado que las redes bluetooth se crean entre 2 dispositivos. Normalmente uno emite y el otro recibe, pero puede darse que los dos emitan y reciban. Para esto el módulo tiene que ser capaz de poder cambiar de modo master a slave. No todos los BT permiten hacer esto. Si compramos algún módulo económico para arduino, seguramente estaremos comprando un módulo SLAVE. Este sólo podrá recibir datos de otro dispositivo. Si queremos que nuestra arduino envíe datos deberemos usar un módulo MASTER.

El módulo master es físicamente igual que el esclavo , aunque incorpora un firmware distinto  HC-05 (firmware: las intrucciones que hacen que funcione al hardware). Otra diferencia es que lleva soldado al menos un pin más. Este pin llamado key, es necesario para que el módulo entre en modo de “comandos AT”, y así podamos programar su funcionamiento. Esto lo podemos hacer con el mísmo código que te hemos mostrado en el punto anterior. Para acceder a este modo especial en el master lo podemos hacer de 2 formas:

1. Conectando Key a 3.3v y encender el módulo. Así funciona a 38400 bauds.
1. Encendiendo el módulo y después conectando el key a 3.3v. Así funciona a 9600 bauds, (es más sencillo pues es el que usa por defecto).

Los comandos AT en HC-05, al contrario que en el HC-06 (esclavo), que es el que tendrá mucha gente , tienen que llevar el símbolo "=", por ejemplo:

En HC-06: AT+NAMEnombre

En HC-05: AT+NAME=nombre

El datasheet indica que por defecto vienen con el modo CMODE=1 (para conectarse a cualquier esclavo disponible), sin embargo hay que comporbarlo (AT+CMODE?) por si tienen el CMODE=0 por lo que se intenta conectar al último emparejado, (en este caso no se emparejaría con ningún esclavo), así que hay que cambiar el CMODE con AT+CMODE=1)

