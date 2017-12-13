
# Montaje 4: Mapeo Potenciometro EDUBASICA

```cpp
float val = 0;

void setup(){
Serial.begin(9600);
}
void loop(){
val = analogRead(A0); 
//leemos el potenciómetro (0-1024)
val = val/204,6; 
//mapeamos los valores para que sean de 0 a 5V
Serial.print (val); 
//vemos por pantalla el valor en Voltios
Serial.println("V");
delay(1000);
}
```

Este es el vídeo:

{% youtube %}https//www.youtube.com/watch?v=mL-8-sFbuR4?rel=0{% endyoutube %}
