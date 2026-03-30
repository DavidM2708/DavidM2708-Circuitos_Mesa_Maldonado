![image alt](https://github.com/DavidM2708/DavidM2708-Circuitos_Mesa_Maldonado/blob/445aa7ad51c4a87ae4bed16605c140ddb8756f26/COMPENSAR.png)
# TALLER CIRCUITOS INTEGRADOS ARDUINO

## Integrantes:

Daniel Alejandro Maldonado Silva
[danielamaldonado@ucompensar.edu.co](mailto:danielamaldonado@ucompensar.edu.co)

David Esteban Mesa González
[destebanmesa@ucompensar.edu.co](mailto:destebanmesa@ucompensar.edu.co)

## Asignatura:

SISTEMAS DIGITALES

## Docente:

Diego Alejandro Barragan Vargas

## INGENIERIA EN SISTEMAS

BOGOTA D.C
2026

# 1. COMPUERTAS LOGICAS:

https://www.tinkercad.com/things/1oe0SCwXXUi-surprising-kasi-jarv/editel?returnTo=https%3A%2F%2Fwww.tinkercad.com%2Fdashboard&sharecode=AGTm_pPk1HZK8eEJm-0bXzFlNnnJI-8sTeZYFz-EJ0c

## COMPONENTES:

* Arduino Uno R3
* Breadboard Small
* Pushbutton (2 unidades)
* LED (3 unidades)
* Resistor (3 unidades)
* 220 Ω para LEDS

## BASE:
![image alt](https://github.com/DavidM2708/DavidM2708-Circuitos_Mesa_Maldonado/blob/b84934bb4530b3115fdf8688b2828024802c4ccb/GIT2.png)
![image alt](https://github.com/DavidM2708/DavidM2708-Circuitos_Mesa_Maldonado/blob/b84934bb4530b3115fdf8688b2828024802c4ccb/GIT1.png)


Los cables rojo y verde se usaron para distribuir la alimentación en la protoboard desde Arduino Uno: el rojo lleva 5V y el verde lleva GND (tierra). El cable rojo conecta el pin de 5 voltios del Arduino con la línea positiva de la protoboard para tener una fuente de energía disponible en el circuito, mientras que el cable verde conecta GND con la línea negativa para establecer el retorno de corriente. Esto permite que todos los componentes tengan acceso ordenado a alimentación y tierra sin tener que llevar cables individuales desde Arduino a cada elemento. En otras palabras, esos dos cables crean la base eléctrica del circuito: 5V como fuente de energía y GND como referencia y retorno.

![GIT3](https://github.com/DavidM2708/DavidM2708-Circuitos_Mesa_Maldonado/raw/2b1c49c4e67fc0be535ffadb85c0f230db59d81b/GIT3.png)

Los cables morados de los botones se conectaron a GND (tierra) en Arduino Uno porque su función es completar la entrada cuando el botón se presiona. Como en el código usamos INPUT_PULLUP, los pines 12 y 13 normalmente están en estado HIGH gracias a una resistencia interna del Arduino; al presionar el botón, el cable morado conecta ese pin directamente a tierra y el estado cambia a LOW. Ese cambio es el que Arduino detecta para saber que el botón fue activado. En resumen, los cables morados permiten que al presionar cada botón se genere la señal de entrada correcta, actuando como la referencia a tierra necesaria para que el programa interprete cada pulsación como una entrada lógica.

![GIT4](https://github.com/DavidM2708/DavidM2708-Circuitos_Mesa_Maldonado/raw/2b1c49c4e67fc0be535ffadb85c0f230db59d81b/GIT4.png)

Los cables azules conectados a los pines 12 y 13 se usaron para llevar las señales de entrada desde los botones hacia Arduino Uno. Esos pines fueron definidos en el código como las entradas principales (A = 12 y B = 13), por lo que cada cable azul conecta un botón con su respectivo pin para que Arduino pueda leer si está presionado o no. Cuando se oprime un botón, el pin correspondiente cambia de estado y Arduino detecta esa señal para procesarla en las compuertas lógicas AND, OR y NOT. En otras palabras, esos cables azules son los que permiten ingresar la información al sistema, es decir, representan las dos variables de entrada que luego el programa evalúa para decidir qué LED debe encenderse.

![GIT5](https://github.com/DavidM2708/DavidM2708-Circuitos_Mesa_Maldonado/raw/2b1c49c4e67fc0be535ffadb85c0f230db59d81b/GIT5.png)

Los tres cables negros de los LEDs se colocaron para conectar el lado negativo de cada LED hacia GND (tierra) en Arduino Uno, permitiendo cerrar el circuito eléctrico. Después de que la corriente sale del pin digital por los cables de colores (rosado, gris y amarillo), pasa por el LED y por la resistencia de 220 Ω, y finalmente necesita regresar a tierra para completar el recorrido; ahí es donde entran los cables negros. Sin esa conexión a GND, la corriente no tendría retorno y el LED no encendería. En resumen, los cables negros funcionan como el camino de retorno de la corriente y aseguran que cada LED pueda encender correctamente cuando Arduino activa los pines 4, 3 o 2.

![GIT6](https://github.com/DavidM2708/DavidM2708-Circuitos_Mesa_Maldonado/raw/2b1c49c4e67fc0be535ffadb85c0f230db59d81b/GIT6.png)

Pusimos los cables rosado, gris y amarillo para conectar las salidas digitales del Arduino Uno con cada LED y así representar las compuertas lógicas programadas. Cada cable sale de un pin específico del Arduino: el rosado del pin 4, el gris del pin 3 y el amarillo del pin 2, porque en el código esos pines fueron definidos como salidas (ledAND = 4, ledOR = 3, ledNOT = 2). De esta manera, cuando Arduino procesa la lógica de los botones, envía señal por cada uno de esos pines según corresponda: el pin 4 activa el LED rojo para la compuerta AND, el pin 3 activa el LED azul para la compuerta OR y el pin 2 activa el LED verde para la compuerta NOT. En otras palabras, esos cables permiten que cada pin entregue el voltaje necesario para encender el LED correspondiente y mostrar físicamente el resultado de cada operación lógica.

![GIT7](https://github.com/DavidM2708/DavidM2708-Circuitos_Mesa_Maldonado/raw/2b1c49c4e67fc0be535ffadb85c0f230db59d81b/GIT7.png)

Les pusimos 220 ohmios a las resistencias de los LEDs porque su función es limitar la corriente que sale del Arduino Uno hacia cada LED, evitando que reciba demasiada corriente y se queme. El pin digital de Arduino entrega aproximadamente 5 voltios, mientras que un LED normalmente trabaja alrededor de 2 voltios a 3 voltios dependiendo del color, así que la resistencia absorbe la diferencia de voltaje y controla la cantidad de corriente que circula. Con 220 Ω se obtiene una corriente segura cercana a 10–15 mA, suficiente para que el LED encienda bien sin sobrecargar ni el LED ni el Arduino. Si no se colocara resistencia, la corriente sería demasiado alta y podría dañarse el LED o incluso el pin del Arduino.

![GIT8](https://github.com/DavidM2708/DavidM2708-Circuitos_Mesa_Maldonado/raw/2b1c49c4e67fc0be535ffadb85c0f230db59d81b/GIT8.png)

## Explicacion CODIGO:

```cpp
int A = 12;
int B = 13;

int ledAND = 4;
int ledOR = 3;
int ledNOT = 2;

void setup() {
  pinMode(A, INPUT_PULLUP);
  pinMode(B, INPUT_PULLUP);

  pinMode(ledAND, OUTPUT);
  pinMode(ledOR, OUTPUT);
  pinMode(ledNOT, OUTPUT);
}

void loop() {
  int a = !digitalRead(A);
  int b = !digitalRead(B);

  digitalWrite(ledAND, a && b);
  digitalWrite(ledOR, a || b);
  digitalWrite(ledNOT, !a);
}
```

El código primero define las entradas y salidas del Arduino Uno: int A = 12; y int B = 13; indican que los botones están conectados a los pines 12 y 13, mientras que int ledAND = 4;, int ledOR = 3; y int ledNOT = 2; indican que los LEDs rojo, azul y verde están conectados a los pines 4, 3 y 2 respectivamente. Luego, en setup(), se configuran los botones como entradas usando INPUT_PULLUP, lo que significa que Arduino activa una resistencia interna para que normalmente el botón lea HIGH y al presionarlo pase a LOW. También se configuran los LEDs como salidas para que Arduino pueda encenderlos o apagarlos. Después, en loop(), que se ejecuta continuamente, se leen los botones con digitalRead(A) y digitalRead(B), pero se usa ! para invertir el valor, de modo que cuando el botón está presionado el valor se interpreta como 1 y cuando no está presionado como 0. Finalmente, digitalWrite(ledAND, a && b); enciende el LED rojo solo si ambos botones están presionados porque && representa la compuerta lógica AND; digitalWrite(ledOR, a || b); enciende el LED azul si al menos uno de los botones está presionado porque || representa OR; y digitalWrite(ledNOT, !a); enciende o apaga el LED verde invirtiendo únicamente el valor del botón A, representando la compuerta NOT.

## Resultados esperados:

✅ Sin tocar botones
🔴 rojo apagado
🔵 azul apagado
🟢 verde encendido
porque verde hace NOT de A.

![GIT9](https://github.com/DavidM2708/DavidM2708-Circuitos_Mesa_Maldonado/raw/2b1c49c4e67fc0be535ffadb85c0f230db59d81b/GIT9.png)

✅ Presionas botón A
🔴 rojo apagado
🔵 azul encendido
🟢 verde apagado

![GIT10](https://github.com/DavidM2708/DavidM2708-Circuitos_Mesa_Maldonado/raw/2b1c49c4e67fc0be535ffadb85c0f230db59d81b/GIT10.png)

✅ Presionas botón B
🔴 rojo apagado
🔵 azul encendido
🟢 verde encendido

![GIT11](https://github.com/DavidM2708/DavidM2708-Circuitos_Mesa_Maldonado/raw/2b1c49c4e67fc0be535ffadb85c0f230db59d81b/GIT11.png)

✅ Presionas A + B
🔴 rojo encendido
🔵 azul encendido
🟢 verde apagado

![GIT12](https://github.com/DavidM2708/DavidM2708-Circuitos_Mesa_Maldonado/raw/2b1c49c4e67fc0be535ffadb85c0f230db59d81b/GIT12.png)

🎯 Resumen rápido

* rojo = AND
* solo prende con ambos.
* azul = OR
* prende con cualquiera.
* verde = NOT A
* depende solo de A.

# 2. SIMULACION DE CONVERSOR BINARIO A HEXADECIMAL: 

https://www.tinkercad.com/things/hk1E3C8UH8m-convertidor-de-binario-a-hexadecimal?sharecode=YU6Csivr-VOBAx-n6FyZRAqWSyzmIFvF69KOStj3eZ0 :

## COMPONENTES: 
* Protoboard
* Arduino UNO
*  Display de 7 segmentos en CATODO COMÚN 
* El DIP switch  
* Resistencias 7 de 330 Ω y 4 10 KΩ

## BASE


Las resistencias conectadas al DIP switch se colocaron hacia GND porque funcionan como resistencias pull-down. Esto significa que aseguran que cuando el interruptor está apagado, el pin lea un valor LOW (0) estable, evitando señales erráticas o “flotantes”. Cuando el switch se activa, el pin recibe 5V y cambia a HIGH. En resumen, estas resistencias garantizan que las entradas sean estables y correctas. 
Las resistencias conectadas al display se usan para limitar la corriente que pasa por cada segmento. Como cada segmento es un LED, sin estas resistencias podría circular demasiada corriente y dañarlos. Estas resistencias protegen el display y aseguran un brillo adecuado. En resumen, son un elemento de protección esencial del circuito. 


El cable rojo se conecta al pin de 5V del Arduino y lleva la alimentación positiva a la protoboard, mientras que el cable negro se conecta a GND y completa el circuito proporcionando la referencia de tierra. Ambos son fundamentales para que todo el sistema funcione correctamente. 


Cada switch será un bit: 

Switch 1 → pin 13 (valor 1)  
Switch 2 → pin 12 (valor 2)  
Switch 3 → pin 11 (valor 4)  
Switch 4 → pin 10 (valor 8) 

Los cables Naranjas del DIP switch se conectaron a los pines de entrada del Arduino porque su función es enviar el valor binario al sistema. Cada interruptor representa un bit (1 o 0), y al activarlo o desactivarlo se genera una señal eléctrica que el Arduino puede leer. Estos cables llevan esa información directamente a los pines digitales, permitiendo que el Arduino interprete combinaciones binarias de 4 bits. En resumen, los cables amarillos son los que transportan la información de entrada que luego será convertida a hexadecimal. 


Cada segmento (a, b, c, d, e, f, g): 

Se conecta a un pin del Arduino (ejemplo):  

a → 8 
b → 7 
c → 4  
d → 3  
e → 2  
f → 6  
g → 5  

Cada conexión debe llevar resistencia 


Los cables morados del display se conectaron a los pines digitales del Arduino Uno porque su función es controlar cada uno de los segmentos del display de 7 segmentos. Cada cable corresponde a un segmento (a, b, c, d, e, f, g), y el Arduino envía señales HIGH o LOW según el número que debe mostrarse. Cuando un pin está en HIGH, el segmento correspondiente se enciende, y cuando está en LOW, se apaga. De esta forma, el Arduino puede formar números del 0 al 9 y letras de la A a la F combinando los segmentos encendidos. En resumen, los cables verdes permiten que el Arduino muestre visualmente el resultado del número binario ingresado. 


## EXPLICACIÓN CODIGO
```
int A; 

int B; 

int C; 

int D; 

void setup(){ 

  pinMode(13,INPUT); 

  pinMode(12,INPUT); 

  pinMode(11,INPUT); 

  pinMode(10,INPUT); 

  pinMode(8,OUTPUT); 

  pinMode(7,OUTPUT); 

  pinMode(6,OUTPUT); 

  pinMode(5,OUTPUT); 

  pinMode(4,OUTPUT); 

  pinMode(3,OUTPUT); 

  pinMode(2,OUTPUT); 

} 

  

void loop(){ 

  A=digitalRead(13); 

  B=digitalRead(12); 

  C=digitalRead(11); 

  D=digitalRead(10); 

   

  if (A==0 & B==0 & C==0 & D==0){ 

  digitalWrite(7,1); 

  digitalWrite(8,1); 

  digitalWrite(4,1); 

  digitalWrite(3,1); 

  digitalWrite(2,1); 

  digitalWrite(6,1); 

  digitalWrite(5,0); 

  } 

  else if (A==0 & B==0 & C==0 & D==1){ 

  digitalWrite(7,0); 

  digitalWrite(8,1); 

  digitalWrite(4,1); 

  digitalWrite(3,0); 

  digitalWrite(2,0); 

  digitalWrite(6,0); 

  digitalWrite(5,0); 

  } 

  else if (A==0 & B==0 & C==1 & D==0){ 

  digitalWrite(7,1); 

  digitalWrite(8,1); 

  digitalWrite(4,0); 

  digitalWrite(3,1); 

  digitalWrite(2,1); 

  digitalWrite(6,0); 

  digitalWrite(5,1); 

  } 

  else if (A==0 & B==0 & C==1 & D==1){ 

  digitalWrite(7,1); 

  digitalWrite(8,1); 

  digitalWrite(4,1); 

  digitalWrite(3,1); 

  digitalWrite(2,0); 

  digitalWrite(6,0); 

  digitalWrite(5,1); 

  } 

  else if (A==0 & B==1 & C==0 & D==0){ 

  digitalWrite(7,0); 

  digitalWrite(8,1); 

  digitalWrite(4,1); 

  digitalWrite(3,0); 

  digitalWrite(2,0); 

  digitalWrite(6,1); 

  digitalWrite(5,1); 

  } 

  else if (A==0 & B==1 & C==0 & D==1){ 

  digitalWrite(7,1); 

  digitalWrite(8,0); 

  digitalWrite(4,1); 

  digitalWrite(3,1); 

  digitalWrite(2,0); 

  digitalWrite(6,1); 

  digitalWrite(5,1); 

  } 

  else if (A==0 & B==1 & C==1 & D==0){ 

  digitalWrite(7,1); 

  digitalWrite(8,0); 

  digitalWrite(4,1); 

  digitalWrite(3,1); 

  digitalWrite(2,1); 

  digitalWrite(6,1); 

  digitalWrite(5,1); 

  } 

  else if (A==0 & B==1 & C==1 & D==1){ 

  digitalWrite(7,1); 

  digitalWrite(8,1); 

  digitalWrite(4,1); 

  digitalWrite(3,0); 

  digitalWrite(2,0); 

  digitalWrite(6,0); 

  digitalWrite(5,0); 

  } 

  else if (A==1 & B==0 & C==0 & D==0){ 

  digitalWrite(7,1); 

  digitalWrite(8,1); 

  digitalWrite(4,1); 

  digitalWrite(3,1); 

  digitalWrite(2,1); 

  digitalWrite(6,1); 

  digitalWrite(5,1); 

  } 

  else if (A==1 & B==0 & C==0 & D==1){ 

  digitalWrite(7,1); 

  digitalWrite(8,1); 

  digitalWrite(4,1); 

  digitalWrite(3,1); 

  digitalWrite(2,0); 

  digitalWrite(6,1); 

  digitalWrite(5,1); 

  } 

  else if (A==1 & B==0 & C==1 & D==0){ 

  digitalWrite(7,1); 

  digitalWrite(8,1); 

  digitalWrite(4,1); 

  digitalWrite(3,0); 

  digitalWrite(2,1); 

  digitalWrite(6,1); 

  digitalWrite(5,1); 

  } 

  else if (A==1 & B==0 & C==1 & D==1){ 

  digitalWrite(7,0); 

  digitalWrite(8,0); 

  digitalWrite(4,1); 

  digitalWrite(3,1); 

  digitalWrite(2,1); 

  digitalWrite(6,1); 

  digitalWrite(5,1); 

  } 

  else if (A==1 & B==1 & C==0 & D==0){ 

  digitalWrite(7,1); 

  digitalWrite(8,0); 

  digitalWrite(4,0); 

  digitalWrite(3,1); 

  digitalWrite(2,1); 

  digitalWrite(6,1); 

  digitalWrite(5,0); 

  } 

  else if (A==1 & B==1 & C==0 & D==1){ 

  digitalWrite(7,0); 

  digitalWrite(8,1); 

  digitalWrite(4,1); 

  digitalWrite(3,1); 

  digitalWrite(2,1); 

  digitalWrite(6,0); 

  digitalWrite(5,1); 

  } 

  else if (A==1 & B==1 & C==1 & D==0){ 

  digitalWrite(7,1); 

  digitalWrite(8,0); 

  digitalWrite(4,0); 

  digitalWrite(3,1); 

  digitalWrite(2,1); 

  digitalWrite(6,1); 

  digitalWrite(5,1); 

  } 

  else{ 

  digitalWrite(7,1); 

  digitalWrite(8,0); 

  digitalWrite(4,0); 

  digitalWrite(3,0); 

  digitalWrite(2,1); 

  digitalWrite(6,1); 

  digitalWrite(5,1); 

  } 

} 

```
Este código convierte un número binario de 4 bits en su equivalente hexadecimal y lo muestra en un display de 7 segmentos utilizando Arduino. Primero se declaran cuatro variables llamadas A, B, C y D, las cuales representan los bits de entrada provenientes de un DIP switch, donde A es el bit más significativo y D el menos significativo. En la función setup() se configuran los pines 13, 12, 11 y 10 como entradas, ya que allí se conectan los switches que generan el número binario, y los pines 8, 7, 6, 5, 4, 3 y 2 como salidas, porque controlan cada uno de los segmentos del display de 7 segmentos. Luego, en la función loop(), que se ejecuta continuamente, el Arduino lee el estado de cada uno de los pines de entrada con digitalRead, obteniendo valores de 0 o 1 según la posición de cada switch, lo que forma un número binario entre 0000 y 1111. Después de leer estos valores, el programa utiliza una serie de condiciones if y else if para comparar la combinación de A, B, C y D con todos los posibles casos binarios; cada condición representa un número distinto, por ejemplo 0000 corresponde a 0, 0001 a 1, y así sucesivamente hasta 1111 que corresponde a F en hexadecimal. Cuando se cumple una condición, se ejecutan varias instrucciones digitalWrite que envían señales HIGH o LOW a los pines de salida, encendiendo o apagando los segmentos necesarios del display para formar el número o letra correspondiente. De esta manera, cada combinación binaria activa un patrón específico de segmentos que permite visualizar correctamente los valores del 0 al 9 y de la A a la F. Finalmente, el último else cubre el caso restante, asegurando que siempre se muestre un valor válido. En resumen, el código toma una entrada binaria de 4 bits, la interpreta mediante condiciones lógicas y controla un display de 7 segmentos para mostrar su equivalente en hexadecimal de forma visual.

 

# 3. SEMAFORO VIAL CON TIEMPOS

## Simulación en Tinkercad

https://www.tinkercad.com/things/9zKmpwO6POz-semaforo?sharecode=DL5nbw0LOcujEC4UHv5PlYX-0HmhdZAcF_ATla-rVkM

---

## Base

* Arduino Uno R3
* Breadboard Small
* LED (3 unidades)
* Resistor (3 unidades)
* 200 Ω para LEDS

![GITI7](https://github.com/DavidM2708/DavidM2708-Circuitos_Mesa_Maldonado/raw/8366db2bc88715399dd5d493210f420e158c2c1b/GITI7.png)
![GITI6](https://github.com/DavidM2708/DavidM2708-Circuitos_Mesa_Maldonado/raw/8366db2bc88715399dd5d493210f420e158c2c1b/GITI6.png)


---

## Explicación del montaje

Los tres cables de colores (rojo, amarillo y verde) se colocaron para conectar cada LED a un pin digital diferente de Arduino Uno y así poder controlarlos de manera independiente desde el código. Cada cable lleva la señal eléctrica desde un pin del Arduino hasta el ánodo (pata positiva) de cada LED, permitiendo que cuando el programa active ese pin, circule corriente y el LED correspondiente se encienda. Esto se hace porque cada LED representa una salida distinta y el Arduino necesita enviar una señal separada a cada uno para decidir cuál encender según la lógica programada.


![GITI5](https://github.com/DavidM2708/DavidM2708-Circuitos_Mesa_Maldonado/raw/8366db2bc88715399dd5d493210f420e158c2c1b/GITI5.png)


El cable negro se colocó para conectar el lado negativo del circuito a GND (tierra), cerrando el recorrido de la corriente. Después de que la energía sale del pin digital, pasa por el LED y por la resistencia de 220 Ω, y necesita regresar al Arduino para completar el circuito; ese retorno se hace a través del cable negro. Sin esa conexión a tierra, la corriente no tendría camino de regreso y los LEDs no podrían encenderse. En resumen, los cables de colores llevan la señal de salida y el cable negro permite el retorno de corriente para que el circuito funcione correctamente.

![GITI4](https://github.com/DavidM2708/DavidM2708-Circuitos_Mesa_Maldonado/raw/8366db2bc88715399dd5d493210f420e158c2c1b/GITI4.png)

---

## Código

```cpp id="6w3h4k"
int rojo=13;
int amarillo=12;
int verde=11;

void setup()
{
  pinMode(rojo, OUTPUT);
  pinMode(amarillo, OUTPUT);
  pinMode(verde, OUTPUT);
}
 
void loop()
{
  digitalWrite(rojo, HIGH);
  digitalWrite(amarillo, LOW);
  digitalWrite(verde, LOW);
  delay(6000);

  digitalWrite(verde, HIGH);
  digitalWrite(rojo, LOW);
  digitalWrite(amarillo, LOW);
  delay(4000);

  digitalWrite(amarillo, HIGH);
  digitalWrite(verde, LOW);
  digitalWrite(rojo, LOW);
  delay(2000);
}
```

---

## Explicación del código

Este código controla tres LEDs conectados a Arduino Uno simulando el funcionamiento básico de un semáforo. Primero se crean tres variables: rojo = 13, amarillo = 12 y verde = 11, donde cada una guarda el número del pin digital al que está conectado cada LED. Luego, dentro de setup(), se usa pinMode(..., OUTPUT) para indicar que esos tres pines funcionarán como salidas, es decir, Arduino enviará señal eléctrica por ellos para encender o apagar los LEDs. Después, en loop(), que se repite continuamente, se programa la secuencia del semáforo: primero se enciende el LED rojo con digitalWrite(rojo, HIGH) mientras amarillo y verde permanecen apagados con LOW, y se mantiene así durante 6 segundos con delay(6000). Luego se enciende el LED verde, se apaga el rojo y el amarillo, y permanece encendido durante 4 segundos con delay(4000). Finalmente se enciende el LED amarillo, se apagan rojo y verde, y permanece encendido durante 2 segundos con delay(2000). Al terminar esta secuencia, el ciclo vuelve a comenzar automáticamente, logrando una repetición continua del comportamiento de un semáforo.

---

## Funcionamiento

### Led Verde

![GITI3](https://github.com/DavidM2708/DavidM2708-Circuitos_Mesa_Maldonado/raw/8366db2bc88715399dd5d493210f420e158c2c1b/GITI3.png)

### Led Amarillo

![GITI2](https://github.com/DavidM2708/DavidM2708-Circuitos_Mesa_Maldonado/raw/8366db2bc88715399dd5d493210f420e158c2c1b/GITI2.png)

### Led Rojo

![GITI1](https://github.com/DavidM2708/DavidM2708-Circuitos_Mesa_Maldonado/raw/8366db2bc88715399dd5d493210f420e158c2c1b/GITI1.png)


---

## ¿Cómo funciona?

El Arduino envía señales eléctricas por sus pines digitales:

* Cuando manda HIGH (5V) → el LED enciende 💡
* Cuando manda LOW (0V) → el LED se apaga

El programa hace una secuencia:

* 🔴 Enciende el rojo (los otros apagados)
* 🟢 Luego enciende el verde
* 🟡 Luego el amarillo
* 🔁 Y repite el ciclo

Todo esto se controla con tiempos usando delay().


## CONCLUSIÓN
En conclusión, el desarrollo de los tres circuitos permitió comprender de manera práctica y aplicada los fundamentos de los sistemas digitales utilizando Arduino como herramienta principal. En el primer circuito, correspondiente a las compuertas lógicas, se logró evidenciar cómo a partir de entradas simples, como los botones, es posible implementar operaciones básicas de la lógica booleana como AND, OR y NOT, cuyos resultados se representan mediante LEDs. Esto facilita la comprensión del comportamiento de las variables binarias y cómo estas influyen directamente en las salidas del sistema, además de reforzar conceptos como estados HIGH y LOW.

En el segundo circuito, el conversor de binario a hexadecimal, se profundiza en el manejo de datos digitales, ya que se trabaja con números binarios de 4 bits que son interpretados por el Arduino y transformados en su equivalente hexadecimal. Este proceso se visualiza a través de un display de 7 segmentos, lo que permite observar de forma clara cómo una combinación de bits puede representar diferentes valores numéricos y alfanuméricos. Este circuito no solo refuerza la lógica de programación mediante condiciones, sino también el entendimiento de sistemas numéricos y su aplicación en la electrónica digital.

Por otro lado, el tercer circuito del semáforo vial introduce el concepto de sistemas secuenciales, donde el comportamiento de las salidas no depende únicamente de las entradas, sino también del tiempo. A través del uso de retardos (delay), el Arduino controla el encendido y apagado de los LEDs simulando el funcionamiento real de un semáforo, lo que permite comprender cómo se pueden automatizar procesos cotidianos mediante programación.

En conjunto, estos tres proyectos integran conceptos clave como entradas y salidas digitales, lógica booleana, conversión de sistemas numéricos y control secuencial, demostrando cómo Arduino puede ser utilizado como una herramienta didáctica para el diseño y comprensión de sistemas electrónicos. Además, permiten desarrollar habilidades en montaje de circuitos, interpretación de señales y programación, sentando una base sólida para proyectos más avanzados en el área de la ingeniería de sistemas y la electrónica.
