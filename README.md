# Demo IceZum Alhambra

@javacasm para la OSL

29 de noviembre de 2016

![box](./images/IceZumAlhambra_box.jpg)

![Licencia CC](./images/Licencia_CC.png)


## IceZum Alhambra


Es una placa totalmente [libre](https://github.com/FPGAwars/icezum) que incluye una FPGA en un formato similar a Arduino

## Orígenes

* Juan Gonzalez (Obijuan)
* Eladio Delgado: diseñador y constructor de la placa
* Jesús Arroyo: desarrollador del software


* En sus inicios fue un proyecto financiado por bq

([Historia](https://github.com/FPGAwars/icezum#history))

## ¿FPGA?

Las FPGAs no se programa, se reconfiguran para que adopten un diseño y un esquema de conexión interno

### ¿Qué es una FPGA?

(Del [Capítulo 0 de Tutorial de @Obijuan sobre Verilog](https://github.com/Obijuan/open-fpga-verilog-tutorial/wiki/Cap%C3%ADtulo-0:-you-are-leaving-the-privative-sector))

"Las [FPGAs](https://es.wikipedia.org/wiki/Field_Programmable_Gate_Array) son unos chips "en blanco" que nos permiten configurarlos para crear dentro de ellos nuestros propios circuitos digitales. ¡Si! ¡Con las FPGAs estamos creando hardware!

![](https://github.com/Obijuan/open-fpga-verilog-tutorial/raw/master/tutorial/ICESTICK/T00-Intro/images/fpga-config1.png)

Los circuitos se describen usando un **Lenguaje de Descripción de Hardware** (HDL) como Verilog o VHDL. A partir de ellos se genera un bitstream que describe las uniones entre los elementos usados.

![](https://github.com/Obijuan/open-fpga-verilog-tutorial/raw/master/tutorial/ICESTICK/T00-Intro/images/fpga-bitstream1.png)

**1 Síntesis**: La herramienta de síntesis infiere los elementos hardware básicos a partir de su descripción, y obtiene un fichero **netlist** que describe las uniones entre ellos. Esta fase no depende de la FPGA a usar

**2 Emplazado y rutado**. Los componentes del netlist se hacen corresponder con los elementos físicos de la FPGA, se determina su colocación y se realiza el rutado. Toda la información de configuración de la FPGA se condensa en el bitstream. Esta fase sí depende del modelo concreto de FPGA que se disponga

### ¿Para qué se utilizan las FPGAs?

Nos permiten sustituir a muchos circuitos digitales discretos necesarios en dispositivos.

[Apple usa FPGAs en su iPhone](http://www.fool.com/investing/2016/09/19/1-more-surprise-winner-inside-the-apple-inc-iphone.aspx) posiblemente para sustituir a docenas de componentes.

Podemos modificar el comportamiento de una FPGA cambiando su bitstream, por tanto podríamos resolver errores y aportar mejoras a un diseño hardware.

### Un poco de historia

En **mayo de 2015** ocurrió un **hito histórico**: se tuvieron por primera vez todas las herramientas necesarias para **generar el bitstream** a partir de **código en Verilog** usando **sólo software libre**, gracias al [proyecto icestorm](http://www.clifford.at/icestorm/), liderado por **Clifford Wolf**.  A partir de ese momento,ya tenemos herramientas que pertenecen al **patrimonio tecnológico de la humanidad** para trabajar con FPGAs, y poder desarrollar hardware usando sólo herramientas de este patrimonio

### Las herramientas del proyecto Icestorm

Las herramientas libres para trabajar con las FPGAs de lattice son las siguientes:

**Sintetizador**: [Yosys](http://www.clifford.at/yosys/) ([Repo en github](https://github.com/cliffordwolf/yosys))
**Place & route**: [Arachne-pnr](https://github.com/cseed/arachne-pnr) (en github)
**Utilidades y descarga en FPGA**: [Proyecto icestorm](http://www.clifford.at/icestorm/)

En la siguiente figura se muestran las diferentes herramientas usadas en las etapas, y las extensiones de los archivos que se van generando:

![](https://github.com/Obijuan/open-fpga-verilog-tutorial/raw/master/tutorial/ICESTICK/T00-Intro/images/icestorm-1.png)

Se parte de los ficheros **fuente en verilog** (.v). Usando el sintetizador **Yosys**, se generan los ficheros **netlist** (.blif). El emplazado y rutado se realiza con **arachne-pnr**, generándose el **bitstream en formato ascii** (.txt). Con **icepack** se crea el **bitstream binario** (.bin) que finalmente se envía a la FPGA con **iceprog**

## Descripción de la ICEZum Alhambra

![iceZum Alhambra](./images/IceZumAlhambra.jpg)

![iceZum Alhambra back](./images/IceZumAlhambra_back.jpg)

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

## Mucho trabajo por hacer

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

* [Tutorial de Verilog de @Obijuan](https://github.com/Obijuan/open-fpga-verilog-tutorial/wiki)

* [Presentaciones de Obijuan sobre FPGAs](https://github.com/Obijuan/myslides)

* [OSHWDem 2016: Charla FPGAs Libres - Juan González ( Obijuan ](https://www.youtube.com/watch?v=XWC1B7UKv98)

* [Juan Gonzalez Obijuan FPGAWars Explorando el lado libre de las FPGAs](https://www.youtube.com/watch?v=rdlEpW_Ce5g)

* [Vídeos sober FPGAs de @Obijuan](https://www.youtube.com/user/obijuancube/videos)
