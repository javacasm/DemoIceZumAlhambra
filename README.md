# Demo IceZum Alhambra

@javacasm para la OSL

29 de noviembre de 2016

![Licencia CC](./images/Licencia_CC.png)

Es una placa totalmente [libre](https://github.com/FPGAwars/icezum) que incluye una FPGA en un formato similar a Arduino


## Orígenes

Juan Gonzalez (Obijuan)
Eladio Delgado: diseñador y constructor de la placa
Jesús Arroyo: desarrollador del software


* En sus inicios fue un proyecto financiado por bq

([Historia](https://github.com/FPGAwars/icezum#history))

## ¿FPGA?


## Descripción

![iceZum Alhambra](./images/IceZumAlhambra.jpg)

* FPGA development board (iCE40HX1K-TQ144 from lattice)
* Open hardware
* Compatible with the opensource icestorm toolchain
* Arduino like board: similar pinout than Arduino one / BQ zum.
* You can Reuse most of available shields
* Control your robots / printbots from an FPGA
* 12 MHZ MEMS oscillator
* ON/OFF switch (turn off your mobile robot easily)
* Input power voltage: 6 - 17v
* Max input current: 3A (Perfect for powering your robots)
* 20 Input/output 5v pins
* 8 Input/Output 3.3V pins
* USB micro-B connector for programming the FPGA from the PC (same than zum board)
* FTDI 2232H USB device allows FPGA programming and UART interface to a PC
* Reset pushbutton
* 8 general purpose leds (user leds)
* 2 general purpose pushbuttons
* 4 analogue inputs though I2C bus

[Pinout](https://github.com/FPGAwars/icezum/wiki#pinout)

![pinout](https://github.com/FPGAwars/icezum/raw/master/doc/pinout/icezum-pinout.png)

## Uso

### Herramientas

Podemos elegir entre usar Verilog o un diseño visual

### Ejemplos

* [Ejemplos de iceZum](https://github.com/FPGAwars/icezum/tree/master/examples)

### Instalación

## Trabajo por hacer

* Mejora del software
* Implementación hardware de un periferico I2C
* Implementación del protocolo I2C para el ADC
* Implementación de bloques generales


## Recursos

* [Lista de correo: FPGAWars explorando el lado libre](https://groups.google.com/forum/#!forum/fpga-wars-explorando-el-lado-libre)
Preséntate y si quieres puedes pedir una Alhambra
Ahora mismo se está entregando la 1a tirada de 110 placas y hay una lista de espera (con casi 80 apuntados) para una segunda tirada

* [Organización de Github FPGAWars](https://github.com/FPGAwars)
Puedes ver los proyectos actuales y la documentación sobre las [charlas](https://github.com/FPGAwars/workshops)

* [Wiki de la IceZum Alhambra](https://github.com/FPGAwars/icezum/wiki)
