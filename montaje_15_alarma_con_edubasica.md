
# Montaje 15: Alarma

Teniendo en EDUBASICA los LEDs, el LDR que nos puede servir como sensor y el altavóz amplificado con un transistor, y nosotros que somos expertos programadores, NOS ESTÁ PIDIENDO A GRITOS hacer una alarma:

**Enunciado: Cuando el LDR esté tapado, tiene que sonar un pitido intermitente de un segundo, con visualización también en los LEDs**

##SIN EDUBASICA

Pues hay que poner el LDR en A1, las luces (por simplicidad uno), el altavoz y el transistor con la conexión en la base por D5:

![](/assets/sin-edubasica-alarm.png)

##CON EDUBASICA

Se simplifica mucho la conexión sólo el altavoz tal y como está conectado en el montaje 14

##Programa:

```cpp+lineNumbers:true
void setup() {
  pinMode(6, OUTPUT);
  pinMode(3, OUTPUT); 
  pinMode(4, OUTPUT); 
  pinMode(5, OUTPUT); 
  Serial.begin(9600);
  
}

void loop() {
  Serial.print("valor analogico leido=");Serial.println(analogRead(1));  //así visualizamos los valores y determinamos cuando es oscuro o no
  ///////////////////////////////////////////////////////////////////////////////////////////////////////////////////////
  if (analogRead(1)<950 ){    // LDR NO TAPADO: NO SALTA LA ALARMA
    digitalWrite(3, LOW);  digitalWrite(4, LOW); digitalWrite(5, LOW); // Se apagan los TRES LEDS
    digitalWrite(6, LOW);                                             //Se apaga el altavoz
  }else{                      /// LDR TAPADO, SALTA LA ALARMA 
    digitalWrite(3, HIGH);  digitalWrite(4, HIGH); digitalWrite(5, HIGH); // Se enciende los TRES LEDS: 
    /////////////////////////////////////////////////SUENA LA ALARMA durante un segundo 1ms x 1000 = 1 seg ////////////////////
    for (int j=0;j<1000;j++){
           digitalWrite(6, HIGH);   // Encendemos e
          delay(1);              // esperamos 1 segundo
          digitalWrite(6, LOW);    // Apagamos el pin13  
          delay(1);        
    }
    digitalWrite(3, LOW);  digitalWrite(4, LOW); digitalWrite(5, LOW); // Se apagan los TRES LEDS
    digitalWrite(6, LOW);                                             //Se apaga el altavoz
    delay(1000);
  }  
}
```

##Resultado:

{% youtube %}https//www.youtube.com/watch?v=Eit6hQzr57U?rel=0{% endyoutube %}


