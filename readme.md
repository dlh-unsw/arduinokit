## Arduino Kit Guide

This guide will go through the components in your arduino kit from UNSW Art & Design, providing links to example code and projects, as well as to more in-depth, technical information about the sensors and actuators included in the kits. If you have further questions about any components, ask someone in the Digital Learning Hub in E110 for more info.

**NB: Never solder anything directly to the components in the kits, and remember to [bend legs/leads properly](https://www.youtube.com/watch?v=_MWwMQvWbOs). If you need a component soldered into a project, talk to staff at the Digital Learning Hub in E110, or the Makerspace, about how you can achieve the desired effect without soldering the part directly.**

## Sensors (inputs)

<p align="left">
  <img src="https://raw.githubusercontent.com/dlh-unsw/arduinokit/master/images/tilt.jpg" width="250">
</p>
**Tilt sensor**

The tilt sensor included with your kit provides an on/off (digital) signal which can be plugged into one of the Arduino's digital pins. Upright should return on/true/1, while tilted any other way will provide off/false/0. See Adafruit's [Reading Switch State with a Microcontroller](https://learn.adafruit.com/tilt-sensor/using-a-tilt-sensor) example, which shows how to connect the sensor on your breadboard, and provides code to debounce the signal to remove unwanted noise from the readings. For more info on debouncing, see [this example](https://www.arduino.cc/en/Tutorial/Debounce) on the Arduino website.

<p align="left">
  <img src="https://raw.githubusercontent.com/dlh-unsw/arduinokit/master/images/temp.jpg" width="250">
</p>
**Temperature sensor**

The temperature sensor included with your kit provides an analog value (0-1023) relative to the temperature around it. The output pin can be plugged directly into an analog input on your Arduino, where you can convert the reading in voltage into a temperature. See [this Adafruit walkthrough](https://learn.adafruit.com/tmp36-temperature-sensor/using-a-temp-sensor), with included code, for how to convert the voltage to degrees celsius.

<p align="left">
  <img src="https://raw.githubusercontent.com/dlh-unsw/arduinokit/master/images/ultrasonic.jpg" width="250">
</p>

**Proximity sensor**

The ultrasonic proximity sensors in the kits are a little quirky and can be tricky to work with in certain circumstances. The sensors rely on emitting a sound beyond the human hearing range and measuring how long it takes to bounce off whatever is in front of it to calculate how far away the object is.

Keep in mind, many Arduino example projects make use of multiple instances of the `delay()` function to slow the Serial monitor, or adjust the speed of a Servo motor, for example. The `delay()` function halts all other functionality of the Arduino for the duration of time specified, and so it can lead to unpredictable behaviour from the sensor, which uses the time between sending a ping and receiving it back to calculate distance. The *Ping* example (File>Examples>Sensors>Ping) is a good starting point, **but** if your code utilises the `delay()` function elsewhere, see this Adafruit guide on how to [Ditch the `delay()`](https://learn.adafruit.com/multi-tasking-the-arduino-part-1/ditch-the-delay).

These sensors are not supported by the CRL Arduino-Max Package.

<p align="left">
  <img src="https://raw.githubusercontent.com/dlh-unsw/arduinokit/master/images/pushbutton.png" width="250">
</p>

**Push button**

Push buttons are useful for triggering some sort of event in your code, turning components on and off, and so on. When pressed, the button connects two parts of a circuit together. Occasionally the readings from these buttons can see some interference from various parts of your circuit and other electrical equipment, so if you are not getting consistent results, it is recommended to use a pullup resistor, which you can learn more about [here](https://www.baldengineer.com/arduino-internal-pull-up-resistor-tutorial.html). Also see this information on [debouncing](https://www.arduino.cc/en/Tutorial/Debounce).

<p align="left">
  <img src="https://raw.githubusercontent.com/dlh-unsw/arduinokit/master/images/potentiometer.jpg" width="250">
</p>


**Potentiometer**

Potentiometers are variable resistors with a knob to control the amount of voltage and current they allow to pass. See this basic [Arduino example](https://www.arduino.cc/en/tutorial/potentiometer), using a potentiometer to control the speed at which an LED blinks.

<p align="left">
  <img src="https://raw.githubusercontent.com/dlh-unsw/arduinokit/master/images/soundin.jpg" width="250">
</p>

**Sound In**

This sensor has a small microphone which provides an analog signal (0-1023) to your Arduino according to the loudness of sound it receives. This sensor is not intended to be used to record sounds, but to use the amplitude of any given sound to control other elements within your Arduino sketch, like, for example, using a clap to trigger some lights. See some examples [here](https://randomnerdtutorials.com/guide-for-microphone-sound-sensor-with-arduino/).

<p align="left">
  <img src="https://raw.githubusercontent.com/dlh-unsw/arduinokit/master/images/photoresistor.jpg" width="250">
</p>

**Photoresistor**

Photoresistors change their resistance according to the amount of light they receive. See [this Arduino example](https://www.arduino.cc/en/Tutorial/AnalogInput) on using a photoresistor as an analog input.

<p align="left">
  <img src="https://raw.githubusercontent.com/dlh-unsw/arduinokit/master/images/flex.jpg" width="250">
</p>

**Flex Sensor**

The flex sensor bends in one direction and increases its resistance as it bends. See this [Instructables tutorial](https://www.instructables.com/id/How-to-use-a-Flex-Sensor-Arduino-Tutorial/) on how to wire it up and control the brightness of an LED.

## Actuators (outputs)

<p align="left">
  <img src="https://raw.githubusercontent.com/dlh-unsw/arduinokit/master/images/led.jpg" width="250">
</p>

**LEDs**

Light Emitting Diodes are great for blinking and flashing in various projects, but they will burn out very quickly if they receive too much power or current. Like other diodes, electrical energy will only flow through them in one direction, so it's important to have power connected to the postive (anode) leg, which is usually longer. [Read all about LEDs here](https://learn.adafruit.com/all-about-leds).

<p align="left">
  <img src="https://raw.githubusercontent.com/dlh-unsw/arduinokit/master/images/servo.jpg" width="250">
</p>

**Servo**

There are two types of Servos across the range of UNSW A&D Arduino kits. Some are the more [common models](https://learn.adafruit.com/adafruit-motor-selection-guide/rc-servos), where passing the motor a value between 0 and 180 will make it move to that angle. Others are the less common [*continuous movement*](https://learn.adafruit.com/adafruit-motor-selection-guide/continuous-rotation-servos) variety, where 0 is full speed in one direction, 180 is full speed in the opposite direction, and somewhere around 90 results in no movement at all. See the Arduino reference for the Servo library [here](https://www.arduino.cc/en/Reference/Servo).

## Other components

<p align="left">
  <img src="https://raw.githubusercontent.com/dlh-unsw/arduinokit/master/images/resistor.jpg" width="250">
</p>

**Resistors**

Resistors are passive components which *resist* the flow of electrical energy. Sparkfun's in-depth walkthrough of resistors can be found [here](https://learn.sparkfun.com/tutorials/resistors). Take particular notice of the section on *decoding resistor markings and colour bands*, and see [this handy chart](https://cdn.sparkfun.com/assets/learn_tutorials/6/4/Resistors.png) to figure out what value your resistors are, as they are not necessarily consistent across all kits. If you need more resistors, or a specific value, ask at the Digital Learning Hub in E110.

<p align="left">
  <img src="https://raw.githubusercontent.com/dlh-unsw/arduinokit/master/images/diode.jpg" width="250">
</p>

**Diodes**

Diodes allow electrical energy to flow in only one direction. Any energy flowing in the "wrong" direction is blocked. They are often used with DC motors so as to block any kickback the motor may create. Read more [here](https://learn.sparkfun.com/tutorials/diodes/all).

<p align="left">
  <img src="https://raw.githubusercontent.com/dlh-unsw/arduinokit/master/images/capacitor.jpg" width="250">
</p>

**Capacitors**

Capacitors can store electrical energy and are often used to avoid voltage spikes damaging other components, or to otherwise smooth out a signal. Read more [here](https://learn.sparkfun.com/tutorials/capacitors).

<p align="left">
  <img src="https://raw.githubusercontent.com/dlh-unsw/arduinokit/master/images/transistormosfet.jpg" width="250">
</p>

**Transistors & MOSFETs**

Transistors and MOSFETs are really handy when it comes to working with components that may require more power than your Arduino can provide. They can be thought of as switches or amplifiers, where you can use a digital output pin on your Arduino to connect a larger power source to components such as motors and LED strips. You can read a basic guide on the uses of transistors and MOSFETs [here](https://learn.adafruit.com/transistors-101/overview).
