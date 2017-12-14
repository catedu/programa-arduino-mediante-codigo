
# dweet.io

Disponemos del portal web **dweet.io** que nos ofrece un servicio para enviar y representar datos en la nube sin necesidad, ni si quiera, de registrarnos en la plataforma.

Vamos a ver los pasos a seguir:

1. Probamos la plataforma introduciendo un dato, para ello en el navegador tecleamos por ejemplo (cambia **catedu** por tu nombre): [https://dweet.io/dweet/for/catedu?temperatura=20](http://dweet.io/dweet/for/jorgeroden?temperatura=20)
1. Abre otra pestaña del navegador o utiliza un móvil para seguir el dato: [https://dweet.io/follow/catedu](http://dweet.io/follow/jorgeroden)
1. Prueba añadiendo otra variable, en este caso la humedad: [https://dweet.io/dweet/for/catedu?temperatura=20&amp;humedad=8](http://dweet.io/dweet/for/jorgeroden?temperatura=20&amp;humedad=8)

![](img/2017-10-10_19_44_57-dweet.io_-_Share_your_thing-_like_it_aint_no_thang..png)

Automatizamos el proceso de recogida de datos desde Arduino con un programa en Processing, que enviará datos a través del navegador a dweet.io.

**IMPORTANTE**: No hay que tener abierto el monitor serie del IDE de Arduino porque ocupa el puerto y, por lo tanto, no deja leer los datos a Processing.

### REPRESENTACIÓN DE DATOS EN EL NAVEGADOR:

**Dweet.io** nos ofrecerá los datos de la siguiente manera:

![](img/dweetio-jorgeroden-2.png)

Si queremos algo más vistoso podemos utilizar el servicio [freeboard.io](freeboard.io) aunque en este caso nos tendremos que registrar en la web.

Una vez registrados podemos crear paneles indicadores configurados a nuestro gusto para visualizar la información. Primero habrá que añadir como fuente de datos Dweet.io y nuestro nombre utilizado allí (jorgeroden en el ejemplo).

Después creamos un panel indicando que la fuente de datos que queremos utilizar y la variable en cuestión a visualizar. 

![](img/freeb-1.png)

¡Y  resultado puede ser de este tipo!

![](img/freeb-2.png)
