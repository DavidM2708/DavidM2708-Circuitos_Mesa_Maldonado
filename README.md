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
* El display de 7 segmentos tiene que está en CATODO COMÚN 
* El DIP switch  
* Resistencias de 330 ohmios 

