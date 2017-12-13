
# Montaje 7 Estudio de la tensión umbral de un LED

Vamos a realizar el siguiente esquema:

![](img/2017-09-08_12_54_01-Electronic_circuit_design_-_EasyEDA.png)

Para conectar un cable con A0 tenemos que localizar el orificio (señalado en esta imagen) y para la masa utilizamos el segundo tornillo

![](img/m3img2.png)

Montamos:

![](img/2017-09-08_12_37_40-TRANSISTOR-CORTE-SAT.fzz__-_Fritzing_-_[Vista_de_Protoboard_(placa_de_Prototipos.png)

Carga este código en tu placa Arduino:

```cpp
float val = 0;

void setup(){
    Serial.begin(9600);
}
void loop(){
    val = analogRead(A0);  //leemos el potenciómetro (0-1024)
    val = val/204,6; //mapeamos los valores para que sean de 0 a 5V
    Serial.print (val);  
    Serial.print ("V"); //vemos por pantalla el valor en Voltios
    Serial.println();
    delay(1000);
}
```

Abre el Monitor serial de Arduino (ctrl+may+M) y verás el voltaje que está ofreciendo Arduino al montaje que has hecho.

Mueve el potenciómetro y verás que el valor va cambiando. Intenta averiguar cual es la tensión umbral a partir de la cual tu led empieza a emitir luz.

Nota: inicialmente la corriente puede ser muy baja por lo que debes fijarte bien cuando empieza a iluminarse.

Verás que alrededor **de 2.5V** el led empieza a iluminarse

![](img/img3.2.png)

**TRUCO**

Se puede hacer **sin ningún circuito exterior**, utilizando la resistencia R5 y **el diodo de VIN**, para ello bastaría:

- Desconectar el interruptor que une V1 con Vin
- Unir con un cable V1 con A0

![](img/img5.1.png)
![](img/img4.png)

Poner interruptor en OFF y unir el cable uniendo V1 con A0 (dibujado en morado) :

![](img/img6.1.png)
