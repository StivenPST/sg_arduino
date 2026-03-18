# SISTEMAS DIGITALES - ARDUINO (HISTORIA, ARQUITECTURA, PERIFICRICOS, ETC.)
## 👨‍💻 Autores
* **Nombres:** Edwin Stiven Pasto Arévalo / Julian Felipe Romero Bocanegra
* **Carrera:** Ingeniería de Sistemas
* **Docente:** Diego Alejandro Barragan Vargas
* **Año:** 2026

## Historia de Arduino
En el año 2005, en Italia, surgió el proyecto Arduino desde el Interaction Design Institute Ivrea (IDII) como solución a la demanda de los alumnos de tener un instrumento asequible y económico para desarrollar proyectos de interacción física. El equipo, que fue dirigido en un principio por Massimo Banzi, tenía como objetivo encontrar una opción más económica al microcontrolador BASIC Stamp, que costaba alrededor de 100 dólares y suponía un obstáculo para la mayoría de los estudiantes.

La intervención de Hernando Barragán, un alumno colombiano que creó Wiring, una plataforma que estableció los fundamentos del lenguaje de programación y el entorno de desarrollo que ahora conocemos como Arduino, fue un hito esencial en la creación de esta última. El nombre "Arduino" tiene un origen interesante: viene de "Bar di Re Arduino" (Bar del Rey Arduino), un sitio que Massimo Banzi iba a menudo en Ivrea.

Tom Igoe (un profesor estadounidense), Massimo Banzi, David Mellis (un estudiante) y David Cuartielles (un ingeniero español) fueron los integrantes del equipo fundador que decidieron liberar el diseño del hardware bajo una licencia de código abierto inspirada en Creative Commons. Esto posibilitó que cualquiera tuviera la capacidad de reproducir, modificar y difundir sus propias versiones de la placa, lo cual promovió una adopción masiva en todo el mundo. La única marca registrada que se guardaron es "Arduino".

## Arquitectura, ventajas y funcionalidad.
Es una plataforma basada en un microcontorlador de arquitectuta Harvard, donde la memoria se programa y la memoria de datos tambien se encuentran separada:

### Cerebro (MCU - Unidad de microcontrolador)
El microcontrolador ATmega328P está integrado al famoso modelo Arduino Uno. Este chip de 8 bits, que pertenece a la familia AVR y fue fabricado por Atmel (actualmente forma parte de Microchip Technology), es famoso por su avanzada arquitectura RISC (Reduced Instruction Set Computer).

#### Arquitectura de Harvard:
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
<img width="3210" height="1165" alt="image" src="https://github.com/user-attachments/assets/dc7ad0e4-7eb9-4b92-aa86-a87514e42b77" />
Puertos USB 2.0 Tipo A & Tipo B - Fuente Propia


### UART (Universal Asynchronous Receiver-Transmitter)
Utiliza los pines 0 (RX) y 1 (TX) es la comunicación de serie basica para cargar codigo desde la PC y el monitor en serie.
### I2C (Inter-Integrated Circuit)
Se encuentra localizado en los pines A4 (SDA) y A5 (SCL), permite conectar hasta 128 dispositivos, usando solo 2 cables de direccionamiento
### SPI (Serial Peripheral Interface)
Ubicado en los pines 10 (SS), 11 (MOSI), 12 (MISO) y 13 (SCK), es un protocolo de velocidad ideal para tarjetas SD, pantallas rápidas o modulos de comunicación inalambrica.

## Ficha técnica, pines de conexión
1. Entrada (Sensores)
Detecta señales del entorno físico.

Digitales: Estados binarios (encendido/apagado), como un pulsador o un sensor PIR.

Analógicas: Valores continuos (0 a 1023), como un potenciómetro o un sensor de temperatura LM35.

2. Procesamiento (Lógica)
El código cargado interpreta las entradas. Utiliza estructuras condicionales (if, switch) y bucles (for, while) para decidir qué acción tomar según los parámetros programados.

3. Salida (Actuadores)
Genera una respuesta física.

Control ON/OFF: Encender luces, activar relés.

Modulación PWM: Controlar la intensidad de un LED o la posición de un servomotor simulando voltajes variables.



---

## 📚 Referencias y Atribuciones

* **Estándares de Hardware:** La identificación de conectores se basa en las especificaciones del [USB Implementers Forum (USB-IF)](https://www.usb.org/usb-20-documents) para el estándar **USB 2.0**, definiendo las interfaces físicas **Tipo-A** (Host) y **Tipo-B** (Device).
* **Asistencia Técnica:** La estructura de la documentación, la organización técnica del repositorio y la clarificación de roles de conectividad contaron con el apoyo de **Gemini (IA de Google)** para asegurar estándares de documentación profesional.
* de documentación profesional.
* **Licencia:** Este proyecto se distribuye bajo fines académicos para la Universidad Compensar.
