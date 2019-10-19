# This is Internet of Things (IoT) 

from microbit import *

while True:
    potVal = pin2.read_analog()
    #pin0.write_analog(potVal)
    #sleep(potval)
    pin0.write_digital(1)
    sleep(potVal)
    pin0.write_digital(0)
    sleep(potVal)
