# Truck-README

CONTENTS OF THIS FILE
---------------------

 * Introduction
 * Requirements
 * Complete Code
 * Configuration
 * Maintainers
 
INTRODUCTION
------------

The JEM Truck&Track is exactly what it sounds like. A 3D designed and printed truck, track, and car wash. Everything was coded using PowerShell ad RaspberryPi, 

REQUIREMENTS
------------

1 Servo Motor
1 D.C Motor
3D Printer
Python
Windows PowerShell
Tape
Pom Pom Strings

COMPLETE CODE
------------

- Truck: -

- Car Wash: -

import RPi.GPIO as GPIO
import time

servoPIN = 18
GPIO.setmode(GPIO.BCM)
GPIO.setup(servoPIN, GPIO.OUT)

p = GPIO.PWM(servoPIN, 50)
p.start(2.0)
p.ChangeDutyCycle(0)

try:
        while True:
                angle = float(input('Start your carwash:'))
                duty = (2.0 + angle/18)
                p.ChangeDutyCycle(duty)
                time.sleep(0.25)
                p.ChangeDutyCycle(0)
except KeyboardInterrupt:
        p.stop()
        GPIO.cleanup()

Downloads Available
------------
- Truck Body [Body for the Truck]
- Truck Wheel (Print 4) [The Wheels]
- Connector [To Connect The Back Wheels]
- Car Wash Body [Main Frame of The Car Wash]
- Car Wash Rod [Rod That Connects The Car Wash to The Servo Motor]
- Track [The Road For The Truck]
