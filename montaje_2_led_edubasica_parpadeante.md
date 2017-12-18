
# Montaje 2: LED EDUBASICA parpadeante

Igual que en el caso anterior, pero vamos a utilizar un LED de la shield de Edubásica, tenemos tres opciones:

- LED VERDE pin 3
- LED AMARILLO pin 4
- LED ROJO pin 5

![](img/m2img0.png)

El programa es igual que el anterior, pero cambiando el número del pin:


<pre>
<font color="#00979c">void</font> <font color="#5e6d03">setup</font><font color="#000000">(</font><font color="#000000">)</font> <font color="#000000">{</font> 
<font color="#434f54">&#47;&#47; inicializamos el pin 3 en Edubásica tiene el LED VERDE</font>
<font color="#434f54">&#47;&#47; para que sea de salida</font>
<font color="#d35400">pinMode</font><font color="#000000">(</font><font color="#000000">3</font><font color="#434f54">,</font> <font color="#00979c">OUTPUT</font><font color="#000000">)</font><font color="#000000">;</font> 
<font color="#000000">}</font>
<font color="#434f54">&#47;&#47; Definimos la rutina cíclica</font>
<font color="#00979c">void</font> <font color="#5e6d03">loop</font><font color="#000000">(</font><font color="#000000">)</font> <font color="#000000">{</font>
<font color="#d35400">digitalWrite</font><font color="#000000">(</font><font color="#000000">3</font><font color="#434f54">,</font> <font color="#00979c">HIGH</font><font color="#000000">)</font><font color="#000000">;</font> <font color="#434f54">&#47;&#47; Encendemos el pin 3</font>
<font color="#d35400">delay</font><font color="#000000">(</font><font color="#000000">1000</font><font color="#000000">)</font><font color="#000000">;</font> <font color="#434f54">&#47;&#47; esperamos 1 segundo</font>
<font color="#d35400">digitalWrite</font><font color="#000000">(</font><font color="#000000">3</font><font color="#434f54">,</font> <font color="#00979c">LOW</font><font color="#000000">)</font><font color="#000000">;</font> <font color="#434f54">&#47;&#47; Apagamos el pin 3 </font>
<font color="#d35400">delay</font><font color="#000000">(</font><font color="#000000">1000</font><font color="#000000">)</font><font color="#000000">;</font> <font color="#434f54">&#47;&#47; esperamos 1 segundo</font>
<font color="#000000">}</font>


</pre>``
```

```



{% youtube %}https//www.youtube.com/watch?v=UHttCda49Vo?rel=0{% endyoutube %}
