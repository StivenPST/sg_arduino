# SISTEMAS DIGITALES - ARDUINO (HISTORIA, ARQUITECTURA, PERIFICRICOS, ETC.)
## Autores
* **Nombres:** Edwin Stiven Pasto Arévalo / Julian Felipe Romero Bocanegra
* **Carrera:** Ingeniería de Sistemas
* **Docente:** Diego Alejandro Barragan Vargas
* **Año:** 2026

## Historia de Arduino
<img width="738" height="576" alt="image" src="https://github.com/user-attachments/assets/5f5c4bcb-2e77-45c1-81d5-8f4a28849501" />

Arduino UNO - Fuente Propia

En el año 2005, en Italia, surgió el proyecto Arduino desde el Interaction Design Institute Ivrea (IDII) como solución a la demanda de los alumnos de tener un instrumento asequible y económico para desarrollar proyectos de interacción física. El equipo, que fue dirigido en un principio por Massimo Banzi, tenía como objetivo encontrar una opción más económica al microcontrolador BASIC Stamp, que costaba alrededor de 100 dólares y suponía un obstáculo para la mayoría de los estudiantes.

La intervención de Hernando Barragán, un alumno colombiano que creó Wiring, una plataforma que estableció los fundamentos del lenguaje de programación y el entorno de desarrollo que ahora conocemos como Arduino, fue un hito esencial en la creación de esta última. El nombre "Arduino" tiene un origen interesante: viene de "Bar di Re Arduino" (Bar del Rey Arduino), un sitio que Massimo Banzi iba a menudo en Ivrea.

Tom Igoe (un profesor estadounidense), Massimo Banzi, David Mellis (un estudiante) y David Cuartielles (un ingeniero español) fueron los integrantes del equipo fundador que decidieron liberar el diseño del hardware bajo una licencia de código abierto inspirada en Creative Commons. Esto posibilitó que cualquiera tuviera la capacidad de reproducir, modificar y difundir sus propias versiones de la placa, lo cual promovió una adopción masiva en todo el mundo. La única marca registrada que se guardaron es "Arduino".

## Arquitectura, ventajas y funcionalidad.
Es una plataforma basada en un microcontorlador de arquitectuta Harvard, donde la memoria se programa y la memoria de datos tambien se encuentran separada:

### Cerebro (MCU - Unidad de microcontrolador)
El microcontrolador ATmega328P está integrado al famoso modelo Arduino Uno. Este chip de 8 bits, que pertenece a la familia AVR y fue fabricado por Atmel (actualmente forma parte de Microchip Technology), es famoso por su avanzada arquitectura RISC (Reduced Instruction Set Computer).

### Arquitectura de Harvard:
La arquitectura Harvard, a diferencia de la arquitectura Von Neumann, utiliza buses y áreas de memoria separados físicamente para los datos e instrucciones del programa. Esto posibilita que el procesador, en un proceso denominado pipeline de 1 nivel, ejecute una instrucción y obtenga la siguiente al mismo tiempo. Esta concurrencia es lo que posibilita que la mayor parte de las instrucciones se ejecuten en un único ciclo de reloj, con lo cual se optimiza el rendimiento.

## Velocidad de reloj
El Arduino Uno funciona con una frecuencia de reloj de 16 MHz. Gracias a su arquitectura Harvard y pipeline, es capaz de lograr un rendimiento que ronda los 16 MIPS (Millones de Instrucciones Por Segundo), lo cual le permite responder casi al instante en aplicaciones en tiempo real.

## Gestion de memoria
El ATmega328P tiene tres clases de memoria, cada una con un propósito particular:
### Memoria Flash (32 KB): 
Es una memoria permanente en la que se guarda el programa creado por el usuario (denominado sketch). Aproximadamente 31.5 KB quedan libres para el código, ya que el bootloader emplea alrededor de 0.5 KB de esta capacidad. Apoya cerca de 10,000 ciclos de escritura.
### Memoria SRAM (de 2 KB): 
Es una memoria volátil de acceso extremadamente veloz. Su tarea es guardar las variables, los datos temporales y la pila (stack) mientras el programa se ejecuta. Cuando la placa queda desconectada, su contenido se pierde.
### Memoria EEPROM (1 KB): 
Es una memoria no volátil de lectura/escritura. Se utiliza para guardar configuraciones o datos que deben persistir incluso cuando la placa no recibe alimentación. Soporta un mayor número de ciclos de escritura (hasta 100,000) en comparación con la Flash

## Periféricos de Arduino y su uso
### UART (Transmisor-receptor asíncrono universal):
Pines: 0 (RX, recepción) y 1 (TX, transmisión).
Descripción: Es el protocolo de comunicación serial asíncrono esencial. Se emplea para comunicarse con la computadora por medio del convertidor USB-Serie de la placa, lo que posibilita cargar los bocetos y depurar usando el Monitor Serie.

### I2C (Inter-Integrated Circuit)
Pinos: A4 (SDA - línea de datos) y A5 (SCL - línea de reloj).
Descripción: Un protocolo síncrono que emplea únicamente dos líneas (de reloj y de datos) para establecer comunicación con varios dispositivos (esclavos), cada uno de los cuales está identificado a través de una dirección única. En teoría, permite la conexión de hasta 128 dispositivos en un solo bus.

### SPI (Interfaz de periféricos en serie):
Pines: 10 (SS - Selección de esclavo), 11 (MOSI - Salida del maestro hacia el esclavo), 12 (MISO - Entrada del maestro desde el esclavo) y 13 (SCK - Reloj serial).
Descripción: Es un protocolo de alta velocidad con capacidad full-duplex que emplea cuatro líneas. Es perfecto para aplicaciones que necesitan una rápida transmisión de datos, por ejemplo módulos de comunicación sin cables, tarjetas SD o pantallas gráficas.

<img width="3210" height="1165" alt="image" src="https://github.com/user-attachments/assets/dc7ad0e4-7eb9-4b92-aa86-a87514e42b77" />
Puertos USB 2.0 Tipo A & Tipo B - Fuente Propia

## Ficha técnica, pines de conexión
<img width="1216" height="530" alt="image" src="https://github.com/user-attachments/assets/cbd1cb03-25f8-488a-b309-f75ef27b9b09" />
Esquema Arduino UNO - Datasheet Arduino UNO Rev3


### Los pines de entrada/salida (GPIO - General Purpose Input/Output) permiten la interacción con el entorno físico.
Entrada (Sensores): El Arduino percibe las señales del ambiente.
Entradas digitales: Interpretan estados binarios (HIGH o LOW), como la salida de un sensor de movimiento (PIR) o el pulso de un botón.
Entradas que son de tipo analógico: Miden un rango de voltaje continuo (0 a 5V) y lo transforman en una cifra digital entre 0 y 1023 (con una resolución de diez bits). Se emplean con elementos como potenciómetros o sensores de temperatura (por ejemplo, el LM35). Están localizados en los pines A0 a A5.

### Procesamiento (lógica): 
El código que se ha instalado en la MCU decodifica las señales de entrada. Aplica estructuras de control de flujo, características del lenguaje C/C++ (for, while, if, switch), para tomar decisiones basadas en la lógica programada.

### Salidas PWM (Modulación por ancho de pulso):
Simula una salida analógica alterando el ciclo de trabajo de una señal digital rápida. Se emplea para regular la intensidad de un LED o el lugar de un servomotor. Los pines 3, 5, 6, 9, 10 y 11 del Uno tienen la habilidad PWM.

### Salida (Actuadores): 
El Arduino produce una respuesta con el fin de regular el entorno. Salida digital (ON/OFF): Encienden o apagan componentes como LEDs, o encienden relés, al establecer un pin en estado HIGH (5V) o LOW (0V). 


---
## 📚 Referencias y Atribuciones

* **Estándares de Hardware:** La identificación de conectores se basa en las especificaciones del [USB Implementers Forum (USB-IF)](https://www.usb.org/documents) para el estándar **USB 2.0**, definiendo las interfaces físicas **Tipo-A** (Host) y **Tipo-B** (Device).
* **Documentación Técnica y Datasheets:**
    * Especificaciones del microcontrolador extraídas de la [Hoja de Datos (Datasheet) oficial del Arduino UNO Rev3](https://docs.arduino.cc/resources/datasheets/A000066-datasheet.pdf).
    * Diagramas de arquitectura y referencia de pines del [Modelo A000046 (pág. 8)](https://elcodis.com/parts/1938089/A000046_p8.html#datasheet).
* **Conceptos de Hardware Libre y Sistemas Digitales:**
    * Análisis sobre la filosofía del [Hardware Libre en Arduino](https://cnti.gob.ve/arduino-el-hardware-libre/) por el CNTI.
    * Fundamentos de [Circuitos y Sistemas Digitales](https://digsys.upc.edu/csd/P09/L09_1/L9_1.html#L2) proporcionados por la EETAC - UPC.
    * Información enciclopédica sobre la evolución de la [Plataforma Arduino](https://www.ecured.cu/index.php?title=Arduino&oldid=3461228) vía EcuRed.
* **Asistencia Técnica:** La estructura de la documentación, la organización técnica del repositorio y la clarificación de roles de conectividad contaron con el apoyo de **Gemini (IA de Google)** para asegurar estándares de documentación profesional.
* **Licencia:** Este proyecto se distribuye bajo fines académicos para la **Universidad Compensar**.
