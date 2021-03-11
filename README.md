# gesture-control-car
robotics
![WhatsApp Image 2021-03-11 at 2 29 58 PM](https://user-images.githubusercontent.com/76094061/110767930-c1911b00-827c-11eb-923c-3d3d7e4127f2.jpeg)
## Abstract
Gesture recognition means response to the change in
spatial position of a object by the system being
manipulated.There are two end the receiving one and the
transmitting one.The Transmitting end having three-axis
accelerometer interfaced with arduino nano ATMega328 board
as input and a NRF24L01 as output.The Receiving end having
NRF24L01 as input interfaced with arduino nano and two
motors connected as output.

## INTRODUCTION
Gesture recognition is an alternative way for communicating
with our system.It can be a better way to manipulate our
system than the conventional cognition methods.The main
qualities of a good gesture recognition system is its ability to
accurately interpret gestures and a fast response to input
data.Controlling any system which can be a industrial
robot,a medical instrument or a military asset becomes
arduous as the complexity increases.The operator has to deal
with a lots of switches and controllers on the interface.A
little mistake can cost a lot if the robot is doing some task
demanding utmost delicacy.
Our project deal with a human gesture based small
prototype. We have made a small robot which is being
controlled by our gesture. We have installed two micro
controllers on each receiving and transmitting end. The
transciever used in this prototype is NRF(Nordic Radio
Frequency) which is sending data from accelerometer to our
receiver end of the system.

## FRAMEWORK
In this Project we use a hand glove equipped with a
accelerometer.The accelerometer gives a numerical data
corresponding to every hand gesture which is accepted by
arduino nano and transmitted to receiving end with the help
of NRF(Nordic Radio frequency).The receiving end receives
the data also through a NRF then NRF forwards the data to
arduino nano which then commands the L293D to rotate the
motors in response to gestures.

In this project nRF24L01 has been used in Enhanced
ShockBurst mode.The radio front-end utilises GFSK
modulation and is configurable to 2Mbps of air data
rate.Enhanced ShockBurst mode offers 1-32 bytes of
Dynamic payload length,Automatic Packet handling,Auto Packet transaction handling and 6 data pipe multiceiver for
1:6 star networks.

## Transmitter

![WhatsApp Image 2021-02-27 at 20 30 47](https://user-images.githubusercontent.com/74725425/109392724-c03e2500-7943-11eb-87df-72d476f52d8b.jpeg)

Pins of nrf24L01 is connected as follows:MOSI of nrf is
connected to MOSI of Nano and MISO of nrf is
connected to MISO of Nano.nrf24L01 receives
power from 3.3V voltage regulator.
IC7805 receives power from 3.3V voltage regulator and
its output pin is connected to one of five pin
set.Accelerometer is connected with this five pins.
Output of Power jack(J1) is connected to inputs of both
7805 and 3.3V voltage regulator.
Output of accelerometer is connected to analog input
pins of nano.Corresponding to each gesture a data is
supplied to analog input pins.Nano is equipped with
inbuilt analog to digital data converter.Digital data is
sent to transmitter via nrf24L01.
The Arduino nano contains an inbuilt analog to digital
conversion module.The data supplied by
accelerometer is analog so it is given to analog
pins.The number of elements in the sample space of
the input provided by accelerometer is very large.So
we set a resolution.The number of values used to
replicate the analog data provide is called resolution.
ADC conveys the analog data to corresponding digital
values which is sent using nrf24L01 IC.

## Receiver

Receiver is also equipped with nrf24L01 IC.When
address at transmitter and receiver matches the
communication between our car and hand gesture
input end begins.
The connection for nrf24L01 is same as in
transmitter.The MOSI and MISO is connected to
MOSI and MISO of arduino nano respectively.The
nrf24L01 here also receives power from 3.3 V
voltage regulator.
IC 7805 receives power from output end of power jack
and supplies power to L293D IC.Output pin of IC
7805 is connected pins enable 1, enable 2 .
L293D is used to drive motors.Connection of its enable
pins is described above. It receives power from IC
7805.Pins D8 , D7 , D6 , D5 of Arduino nano is
connected to pins in1 , in2 , in3 and in4 of L293D
respectively.Pins out 1 , out 2 of L293D drives motor 1 and out 3 and
out 4 drives motor 2.
The data received by the nrf24L01 IC on receiving end
is fed to Arduino nano , which processes it and
forward it to L293D IC to drive motors according to
users gesture.

## ACCELEROMETER

![download](https://user-images.githubusercontent.com/74725425/109392784-08f5de00-7944-11eb-9d0c-4a744f9177d7.jpg)

A sensor with accelerometer (ADXL335) module is used here, which senses the coordinate axis of direction of the
movements of the hand, then the car starts moving according to the movement of the hand. The ADXL335 is words on the
principle of Piezoelectric effect on measuring, the static acceleration amounts due to gravity, the ball of the angle tilted at
with respect to the earth is determined. On sensing the dynamic acceleration amount, the way of moving the car is
analyzed.


![WhatsApp Image 2021-02-27 at 20 30 49](https://user-images.githubusercontent.com/74725425/109392753-e06de400-7943-11eb-9fcd-654e9019e056.jpeg)

This L298N Motor Driver Module is a high power motor driver module for driving DC and Stepper Motors. This module consists of an L298 motor driver IC and a 78M05 5V regulator. L298N Module can control up to 4 DC motors, or 2 DC motors with directional and speed control.

 

L298N Module Pin Configuration:
Pin Name

Description

IN1 & IN2

Motor A input pins. Used to control the spinning direction of Motor A

IN3 & IN4

Motor B input pins. Used to control the spinning direction of Motor B

ENA

Enables PWM signal for Motor A

ENB

Enables PWM signal for Motor B

OUT1 & OUT2

Output pins of Motor A

OUT3 & OUT4

Output pins of Motor B

12V

12V input from DC power Source

5V

Supplies power for the switching logic circuitry inside L298N IC

GND

Ground pin
