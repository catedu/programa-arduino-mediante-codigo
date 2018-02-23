#Montaje 7 Coche teledirigido
Sé que lo estabas pensando... ponerle [el Bluetooth](/mdulo_bluetooth.md), vamos allá:

{% youtube %}https://www.youtube.com/watch?v=_cn9sSBwZXA&feature=youtu.be{% endyoutube%}

%accordion%Solución%accordion%

##CON EDUBASICA

```cpp
////////////// CON EDUBASICA ////////////////
#define ENABLEA 10
#define DIR1A 8
#define DIR2A 9
#define ENABLEB 11
#define DIR1B 12
#define DIR2B 13
#define BOTON 2
#define LEDVERDE 3
byte dato;
/////////////////////////////////////////////////////////////////////////////////////////////////////
void setup() {
  Serial.begin(9600);
  pinMode(ENABLEA,OUTPUT);
  pinMode(DIR1A,OUTPUT);
  pinMode(DIR2A,OUTPUT);
  pinMode(ENABLEB,OUTPUT);
  pinMode(DIR1B,OUTPUT);
  pinMode(DIR2B,OUTPUT);
  pinMode(BOTON,INPUT);
  pinMode(LEDVERDE,OUTPUT);
 
}
/////////////////////////////////////////////////////////////////////////////////////////////////////
void loop() {
  if (Serial.available()) //Guardamos en la variable dato el valor leido
        dato= Serial.read();
   //Comprobamos el dato
   switch(dato) {//Si recibimos una  ...  85=ARRIBA  68=U=ABAJO 67=D=CENTRO  76=L=IZQUIERDA 82=R=DCHA  97=a  98=B  99=C
         case 85: //UP HACIA DELANTE
         {
           digitalWrite(LEDVERDE, HIGH);
           digitalWrite(ENABLEA,HIGH);
           digitalWrite(ENABLEB,HIGH);  
           digitalWrite(DIR1A,HIGH); 
           digitalWrite(DIR2A,LOW);
           digitalWrite(DIR1B,HIGH); 
           digitalWrite(DIR2B,LOW);
           break;
         }
         case 68: //"D": ABAJO
         {
           digitalWrite(LEDVERDE, HIGH);
           digitalWrite(ENABLEA,HIGH);
           digitalWrite(ENABLEB,HIGH);  
           digitalWrite(DIR2A,HIGH); 
           digitalWrite(DIR1A,LOW);
           digitalWrite(DIR2B,HIGH); 
           digitalWrite(DIR1B,LOW);
           break;
         }
         case 76: //"L": IZQUIERDA
         {
            digitalWrite(LEDVERDE, HIGH);
           digitalWrite(ENABLEA,HIGH);
           digitalWrite(ENABLEB,HIGH);  
           digitalWrite(DIR1A,HIGH); 
           digitalWrite(DIR2A,LOW);
           digitalWrite(DIR2B,HIGH); 
           digitalWrite(DIR1B,LOW);
           break;
         }
         case 82: //"R": ABAJO
         {
           digitalWrite(LEDVERDE, HIGH);
           digitalWrite(ENABLEA,HIGH);
           digitalWrite(ENABLEB,HIGH);  
           digitalWrite(DIR2A,HIGH); 
           digitalWrite(DIR1A,LOW);
           digitalWrite(DIR1B,HIGH); 
           digitalWrite(DIR2B,LOW);
           break;
         }
         default:   //en caso contrario que apague todo
         {
           digitalWrite(LEDVERDE, LOW);
           digitalWrite(ENABLEA,LOW);
           digitalWrite(ENABLEB,LOW);  
           break;
         }      
  }
}

```

## SIN EDUBASICA
Cambia el principio de la cabecera :

```cpp+lineNumbers:true
////////////// SIN EDUBASICA ////////////////
#define ENABLEA 6
#define DIR1A 7
#define DIR2A 8
#define ENABLEB 11
#define DIR1B 9
#define DIR2B 10

```


%/accordion%

<iframe src="https://giphy.com/embed/l3vQYPi2ow7YWXQFW" width="480" height="274" frameBorder="0" class="giphy-embed" allowFullScreen></iframe><p><a href="https://giphy.com/gifs/aardman-fun-cartoon-l3vQYPi2ow7YWXQFW">via GIPHY</a></p>



