
# Montaje con Circuito L293

El circuito integrado L293 permite controlar motoresDC de pequeña potencia, pero en general bobinas, o sea cualquier elemento que precise pico de potencia, como los relés, etc..  Para utilizarlo hay que hacer un montaje externo a Arduino, en una placa de pruebas, y alimentar a los motores a través de este circuito integrado.

El CI L293 tiene las siguientes características:

- Se pueden controlar hasta 2 motores.
- Proporciona 1A a los motores (en total)  y permite cambiar el sentido de giro.
- Utiliza un puente en H que funciona según se observa en las figuras (internamente utiliza transistores para conmutar*) :

![](img/461px-H_bridge.png)

Modos de operación para invertir el sentido de giro:

![](/assets/circuitoL293.png)

"[H bridge operating](https://commons.wikimedia.org/wiki/File:H_bridge_operating.svg#/media/File:H_bridge_operating.svg)" by Cyril BUTTAY - own work, made using inkscape. Licensed under [CC BY-SA 3.0](http://creativecommons.org/licenses/by-sa/3.0/) via [Wikimedia Commons](//commons.wikimedia.org/wiki/).

*Datasheet: http://www.me.umn.edu/courses/me2011/arduino/technotes/dcmotors/L293/l293.pdf

