# SISTEMAS DIGITALES - ARDUINO (HISTORIA, ARQUITECTURA, PERIFICRICOS, ETC.)
## 👨‍💻 Autores
* **Nombres:** Edwin Stiven Pasto Arévalo / Julian Felipe Romero Bocanegra
* **Carrera:** Ingeniería de Sistemas
* **Docente:** Diego Alejandro Barragan Vargas
* **Año:** 2026

## Historia de Arduino
El arduino nacio en el Instituto Interaction Design Institute Ivrea en el año 2005 por un equipo investigativo liberado por Massimo Banzi.

El objetivo era crear una herramienta de bajo costo y de hardware abierto (Open source) para el uso de los estudiante, con el fin de poder manipular dispositivos electronicos, sin necesidad de tener conocimiento de progrmacion compleja.

## Arquitectura, ventajas y funcionalidad.
Es una plataforma basada en un microcontorlador de arquitectuta Harvard, donde la memoria se programa y la memoria de datos tambien se encuentran separada:

## Cerebro (MCU)
El modelo estandar del arduino uno integra ATMEGA328P, es un chip de 8 bits basado en la arquitectura RISC avanzado de AVR.

## Velocidad de reloj

Opera con una frecuencia 16 MHZ, por su diseño puedo ejecutar cerca de 16 MIPS, lo que permite obtener una respuesta de manera inmediata en tiempo real.

## Gestion de memoria
### Flash
Cuenta con una memoria de 32 KB, es una memoria no volatil donde se almacena el codigo del programa sketch 
### SRAM
Cuenta con una memoria de 2KB, donde se gaurdan las variables cuando el programa corre.
### EEPROM
Cuenta con una memoria de 1 KB, es la memoria no volatil.

## Periféricos de Arduino y su uso

### UART: 
Pines 0 (RX) y 1 (TX) para hablar con la computadora.
### I2C: 
Pines A4 (SDA) y A5 (SCL) para conectar muchos sensores con solo dos cables.
### SPI: 
Pines 10 al 13, usados para tarjetas SD o pantallas rápidas.

## Ficha técnica, pines de conexión
Arduino actúa como el "sistema nervioso" de un proyecto. Su flujo de trabajo es simple:
### Entrada: 
Lee el entorno (un sensor de temperatura, un botón, un receptor de luz).
### Procesamiento: 
Ejecuta la lógica que escribiste (ej: "Si hace calor, enciende el ventilador").
### Salida: 
Actúa sobre el mundo físico (mueve un motor, enciende un LED, envía un mensaje Wi-Fi).



---

## 📚 Referencias y Atribuciones
* **Simulación:** 
* **Asistencia Técnica:** La estructura de la documentación y organización del repositorio contó con el apoyo de **Gemini (IA de Google)** para asegurar estándares de documentación profesional.
* **Licencia:** Este proyecto se distribuye bajo fines académicos para la Universidad Compensar.
