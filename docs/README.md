# SilentStepStick
The Silent-Step-Stick is a Stepper Motor Driver Board for 2-Phase Motors based on a [Trinamic TMC 2100](http://www.trinamic.com/products/integrated-circuits/details/tmc2100/), [Trinamic TMC 2130](http://www.trinamic.com/products/integrated-circuits/details/tmc2130/) or [Trinamic TMC 2208](http://www.trinamic.com/products/integrated-circuits/details/tmc2208-la/).

* Hardware compatible with [StepStick](http://reprap.org/wiki/StepStick) and [Pololu A4988](https://www.pololu.com/product/1182)
* Trinamic stepper motor driver (chopper drive / constant current drive)
* Components on bottom PCB side for better heat emission, further infos [here](https://github.com/watterott/SilentStepStick/blob/master/docs/FAQ.md#why-is-the-trinamic-driver-chip-on-the-bottom-pcb-side)
* Automatic standby current reduction
* **microPlyer** - microstep interpolator for increased smoothness of microstepping
* **stealthChop** - for quiet operation and smooth motion
* **spreadCycle** - highly dynamic motor control chopper
* Extra features of **TMC2130**:
  * SPI configuration interface (up to 4MHz)
  * up to 256 native microsteps (without interpolation)
  * **coolStep** - current control for energy savings
  * **stallGuard2** - sensorless motor load detection
  * **dcStep** - load dependent speed control
  * Automatic stealthChop and spreadCycle switchover depending on velocity
* Extra features of **TMC2208**:
  * UART configuration interface (9600...500k Baud)
  * up to 256 native microsteps (without interpolation)
  * **stealthChop2** - faster motor acceleration/deceleration than stealthChop
  * Automatic stealthChop and spreadCycle switchover depending on velocity

SilentStepStick          | TMC2100 (5V)        | TMC2100 (3-5V)      | TMC2130 (3-5V)      | TMC2208 (3-5V)
------------------------ | ------------------- | ------------------- | ------------------- | -------------------
SilentStepStick          | ![SSS](https://github.com/watterott/SilentStepStick/raw/master/hardware/SilentStepStick-TMC2100_v13_5V.jpg) | ![SSS](https://github.com/watterott/SilentStepStick/raw/master/hardware/SilentStepStick-TMC2100_v13.jpg) | ![SSS](https://github.com/watterott/SilentStepStick/raw/master/hardware/SilentStepStick-TMC2130_v11.jpg) | ![SSS](https://github.com/watterott/SilentStepStick/raw/master/hardware/SilentStepStick-TMC2208_v12.jpg)
Interface                | Step/Dir            | Step/Dir            | Step/Dir or [SPI](https://en.wikipedia.org/wiki/Serial_Peripheral_Interface_Bus) | Step/Dir
Configuration            | CFG Pins            | CFG Pins            | CFG Pins or [SPI](https://en.wikipedia.org/wiki/Serial_Peripheral_Interface_Bus) | CFG Pins or [UART](https://en.wikipedia.org/wiki/UART)
Native Microsteps*       | up to 1/16          | up to 1/16          | up to 1/256         | up to 1/256
microPlyer Microsteps    | 1/256               | 1/256               | 1/256               | 1/256
Logic Voltage ```VIO```  | 5V                  | 3 - 5V              | 3 - 5V              | 3 - 5V
Motor Voltage ```VM```   | 4.75 - 46V          | 5.5 - 46V           | 5.5 - 46V           | 5.5 - 36V
Motor Phase Current      | 1.2A RMS, 2.5A Peak | 1.2A RMS, 2.5A Peak | 1.2A RMS, 2.5A Peak | 1.2A RMS, 2.0A Peak
```VM``` always needed** | no                  | yes                 | yes                 | yes
Internal V-Regulator**   | disabled            | enabled             | enabled             | enabled
RDSon                    | >=0.5 Ohm           | >=0.5 Ohm           | >=0.5 Ohm           | <=0.3 Ohm
stealthChop (quiet)      | yes                 | yes                 | yes                 | yes
spreadCycle              | yes                 | yes                 | yes                 | yes
coolStep                 | no                  | no                  | yes                 | no
stallGuard               | no                  | no                  | yes                 | no
dcStep                   | no                  | no                  | yes                 | no

_* without interpolation (microPlyer), ** further infos [here](https://github.com/watterott/SilentStepStick/blob/master/docs/FAQ.md#what-is-the-difference-between-silentstepsticks-with-3-5v-and-5v-logic-voltage)_


## Shop
* Trinamic **TMC2100** based drivers, recommended for most applications (CFG pins for configuration)
  * [TMC2100 SilentStepStick (3-5V logic voltage)](http://www.watterott.com/en/SilentStepStick)
  * [TMC2100 SilentStepStick (3-5V logic voltage) with soldered Pin Headers](http://www.watterott.com/en/SilentStepStick-with-Pins)
  * [TMC2100 SilentStepStick (5V logic voltage)](http://www.watterott.com/en/SilentStepStick-TMC2100-5V)
  * [TMC2100 SilentStepStick (5V logic voltage) with soldered Pin Headers](http://www.watterott.com/en/SilentStepStick-TMC2100-5V-with-Pins)
* Trinamic **TMC2130** based drivers (CFG pins or SPI for configuration)
  * [TMC2130 SilentStepStick (3-5V logic voltage)](http://www.watterott.com/en/SilentStepStick-TMC2130)
  * [TMC2130 SilentStepStick (3-5V logic voltage) with soldered Pin Headers](http://www.watterott.com/en/SilentStepStick-TMC2130-with-Pins)
* Trinamic **TMC2208** based drivers (CFG pins or UART for configuration)
  * [TMC2208 SilentStepStick (3-5V logic voltage)](http://www.watterott.com/en/SilentStepStick-TMC2208)
  * [TMC2208 SilentStepStick (3-5V logic voltage) with soldered Pin Headers](http://www.watterott.com/en/SilentStepStick-TMC2208-with-Pins)
* Accessories
  * [SilentStepStick Protector (with flyback diodes)](http://www.watterott.com/en/SilentStepStick-Protector)
  * [SilentStepStick Tester/Programmer](http://www.watterott.com/en/SilentStepStick-Tester)
  * [Suitable Heatsink 9x9mm](http://www.watterott.com/en/Heatsink-9-x-9-x-12)
  * [Suitable Heatsink 10x10mm](http://www.watterott.com/en/Pin-heatsink-square-ICK-S-10-x-10-x-125)
  * [Suitable Heatsink 10x6mm](http://www.watterott.com/en/Heatsink-for-DIL-IC-PLCC-und-SMD-10-x-6-mm)


## Hardware and Software
* [Schematics + Layout](https://github.com/watterott/SilentStepStick/tree/master/hardware) (PDF files include additional infos)
* [FAQ (Frequently Asked Questions)](https://github.com/watterott/SilentStepStick/blob/master/docs/FAQ.md)
* [Arduino Examples](https://github.com/watterott/SilentStepStick/tree/master/software)
* [TMC2208 Configurator](https://github.com/watterott/SilentStepStick/tree/master/docs/ScriptCommunicator#tmc2208-configurator)
* [Eagle CAD Part](https://github.com/watterott/Eagle-Libs)


## Reviews and Tests

* TMC2100 and TMC2130 Reviews from Thomas Sanladerer

  [![SilentStepStick TMC2100](https://img.youtube.com/vi/g6Bxoqr8QlY/0.jpg)](https://www.youtube.com/watch?v=g6Bxoqr8QlY)

  [![SilentStepStick TMC2100 Update](https://img.youtube.com/vi/mYuZqx8xwTg/0.jpg)](https://www.youtube.com/watch?v=mYuZqx8xwTg)

  [![SilentStepStick TMC2130](https://img.youtube.com/vi/sPvTB3irCxQ/0.jpg)](https://www.youtube.com/watch?v=sPvTB3irCxQ)

* TMC2100 Review from Peter Recktenwald

  [![SilentStepStick TMC2100](https://img.youtube.com/vi/P3ebhi-vZRY/0.jpg)](https://www.youtube.com/watch?v=P3ebhi-vZRY)

* TMC2130 Review from Moritz Walter

  [<img src="https://hackadaycom.files.wordpress.com/2016/09/tmc_thumb1.jpg" width="400" height="400">](http://hackaday.com/2016/09/30/3d-printering-trinamic-tmc2130-stepper-motor-drivers-shifting-the-gears/)

* TMC2208 Review from Trinamic

  [![SilentStepStick TMC2208](https://img.youtube.com/vi/FvW93yCbqFE/0.jpg)](https://www.youtube.com/watch?v=FvW93yCbqFE)

* What is Trinamic spreadCycle and stealthChop?

  [![Trinamic spreadCycle and stealthChop](https://img.youtube.com/vi/Q0sJlGh9WNY/0.jpg)](https://www.youtube.com/watch?v=Q0sJlGh9WNY)

* What is Trinamic stallGuard and coolStep?

  [![Trinamic stallGuard and coolStep](https://img.youtube.com/vi/Prw7wNa20Gk/0.jpg)](https://www.youtube.com/watch?v=Prw7wNa20Gk)

* More Tests and Reviews on [YouTube](https://www.youtube.com/results?search_query=SilentStepStick)
