# Lab08 - Actividad Evaluativa: Integración de ADC, LCD 16x2 con protocolo I²C y protocolo UART

En esta actividad evaluativa, los estudiantes deberán combinar lo aprendido en el manejo del ADC (Conversor Analógico-Digital), el control de una pantalla LCD $16\times 2$ en modo I²C y el protocolo de comunicaciones UART (Universal Asynchronous Receiver-Transmitter ), para desarrollar un sistema embebido que permita visualizar en tiempo real una lectura analógica y mostrar información dinámica tanto en la pantalla como en una gráfica en tiempo real usando Python.
## Integrantes
 *[Andrés Felipe Muñoz Martinéz](https://github.com/Andresfmm2007)

 *[Paula Andrea Cortés Espinosa](https://github.com/Cortes271)

 *[Reny Alexander Roncancio](https://github.com/renyroncancio-glitch)

 *[Laura Katerin Sanchez](https://github.com/laurakasanchezgu-oss)

## Documentación
-	En esta práctica trabajamos con el microcontrolador PIC18F45K22 para aprender cómo integrar diferentes módulos y lograr la comunicación entre el circuito y el computador. El montaje se realizó en una protoboard, conectando un potenciómetro como entrada analógica, una pantalla LCD con comunicación I2C y un módulo USB-UART para enviar la información al PC.
-	El PIC se encargó de leer el valor analógico del potenciómetro mediante el ADC y convertirlo en un valor de voltaje. Después, este voltaje se mostraba en tiempo real en la pantalla LCD y también se enviaba por comunicación serial UART hacia el computador. En Python, los datos recibidos se procesaron para generar una gráfica de voltaje vs tiempo, lo que permitió observar de una manera más visual cómo cambiaba la señal.
-	Gracias a esta práctica fue posible entender mejor cómo funcionan los módulos ADC, UART e I2C dentro del microcontrolador, además de ver cómo se pueden combinar para crear sistemas de monitoreo y adquisición de datos. También ayudó a reforzar el manejo de comunicación serial entre el PIC y el computador, haciendo la práctica mucho más dinámica y fácil de analizar.

## Descripción General
Implementar un sistema de adquisición y transmisión de datos utilizando el microcontrolador PIC18F45K22, integrando comunicación serial UART, conversión ADC y visualización de datos tanto en una pantalla LCD como en Python.

## Objetivos específicos
-	Comprender el funcionamiento de la comunicación serial UART y su aplicación en la transmisión de datos.
-	Configurar la comunicación entre el microcontrolador PIC18F45K22 y el computador mediante un módulo USB-UART.
-	Realizar la lectura de una señal analógica utilizando el módulo ADC del PIC18F45K22.
-	Mostrar los valores de voltaje obtenidos en una pantalla LCD con interfaz I2C.
-	Enviar los datos de voltaje desde el microcontrolador hacia el computador a través de UART.
-	Recibir y procesar los datos seriales en Python para su análisis.
-	Generar una gráfica de voltaje en función del tiempo para visualizar el comportamiento de la señal adquirida.
-	Analizar el funcionamiento conjunto de los módulos ADC, UART e I2C dentro de un sistema de monitoreo básico.

## Procedimiento
Primero se realizó el montaje del circuito en una protoboard utilizando el microcontrolador PIC18F45K22. Se conectó un potenciómetro al pin AN0 para generar la señal analógica de entrada, una pantalla LCD con módulo I2C para visualizar los datos y un módulo USB-UART para establecer la comunicación con el computador. Después se creó el proyecto en MPLAB X IDE con el compilador XC8 y se configuró el PIC para trabajar con el oscilador interno de 16 MHz. También se configuraron los módulos ADC, UART e I2C necesarios para el funcionamiento de la práctica. Se programó el ADC para leer el valor analógico del potenciómetro y convertirlo en un valor digital. Luego, ese dato se transformó a voltaje utilizando una referencia de 5 V. Posteriormente se configuró la comunicación UART a 9600 baudios para enviar continuamente los valores de voltaje desde el PIC hacia el computador. Al mismo tiempo, el voltaje también se mostraba en la pantalla LCD mediante comunicación I2C. Durante el desarrollo fue necesario realizar algunos ajustes en el código relacionados con la transmisión serial y la configuración de ciertos pines, hasta lograr que la comunicación y la visualización de datos funcionarán correctamente. Finalmente, en Python se desarrolló un programa utilizando las librerías pyserial y matplotlib para recibir los datos enviados por el microcontrolador y generar una gráfica de voltaje en función del tiempo en tiempo real. Esto permitió visualizar y analizar de manera más clara el comportamiento de la señal adquirida.
## Diagramas internos de conexion
<img width="941" height="355" alt="image" src="https://github.com/user-attachments/assets/bf6a90a5-1c7f-4e50-9203-76b9a22e56ce" />

<img width="941" height="499" alt="image" src="https://github.com/user-attachments/assets/45ce55bf-429b-4300-9fb3-174e60ab493b" />

<img width="940" height="665" alt="image" src="https://github.com/user-attachments/assets/a178a556-f033-459c-ba74-01e3aa983343" />

-	El potenciómetro genera un voltaje analógico.
-	El ADC del PIC convierte ese voltaje en un valor digital.
-	El PIC calcula el voltaje correspondiente.
-	El valor se muestra en la pantalla LCD usando I2C.
-	Simultáneamente, el dato se envía al computador por UART.
-	El módulo FT232RL convierte UART a USB.
-	Python recibe los datos y genera la gráfica en tiempo real.
De esta forma, todos los dispositivos trabajan juntos para crear un sistema básico de adquisición, visualización y transmisión de datos.

##  Montaje

<img width="681" height="579" alt="image" src="https://github.com/user-attachments/assets/81db3526-e889-48d9-8a40-5e8b2168b8f8" />

<img width="557" height="814" alt="image" src="https://github.com/user-attachments/assets/9856e3f6-c573-4ce7-ae0b-611ab84911c5" />

<img width="503" height="806" alt="image" src="https://github.com/user-attachments/assets/893c580a-5e17-4fe5-b21a-e3bacba53e5b" />

Durante la práctica se realizó el montaje de un sistema con el microcontrolador PIC18F45K22, un potenciómetro, una pantalla LCD I2C y un módulo USB-UART. El PIC leía el voltaje generado por el potenciómetro, lo mostraba en la pantalla LCD y lo enviaba al computador mediante comunicación serial UART.
También se comprobó el correcto funcionamiento de los módulos ADC, UART e I2C, logrando una transmisión de datos estable entre el microcontrolador y el computador. Finalmente, los datos recibidos fueron procesados en Python para generar una gráfica de voltaje en función del tiempo y observar el comportamiento de la señal en tiempo real.

## Documentación del código 

<img width="956" height="40" alt="image" src="https://github.com/user-attachments/assets/3be5541b-447c-46be-98d2-e75c4d817c57" />

Aquí se convierte el valor digital leído por el ADC en un voltaje real entre 0V y 5V. Este dato es el que luego se muestra en el LCD y se envía al computador. 

<img width="945" height="51" alt="image" src="https://github.com/user-attachments/assets/3656cb17-f439-4dae-890f-02ac0cf1a9f5" />

Este bloque inicia la conversión analógica-digital y espera hasta que termine la lectura del voltaje en el pin AN0. 

<img width="957" height="82" alt="image" src="https://github.com/user-attachments/assets/9ba5973c-2531-4868-a74f-3c2e68e4f0a5" />

Configura la comunicación serial UART a 9600 baudios y habilita la transmisión de datos entre el PIC y el computador. 

<img width="942" height="52" alt="image" src="https://github.com/user-attachments/assets/e1c71674-bf5e-4151-b79b-1d80f707ee16" />

Configura el PIC como maestro I2C y establece la velocidad de comunicación con la pantalla LCD. 

<img width="952" height="37" alt="image" src="https://github.com/user-attachments/assets/54aca535-ce48-4481-8a53-f7a86b2c1f00" />

Mueve el cursor al inicio de la pantalla LCD para mostrar correctamente el valor del voltaje. 
