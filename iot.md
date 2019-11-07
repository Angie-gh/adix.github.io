# Unit 2 - Reflections: IoT - Programming a device with Python
### [Return to Angie Home](https://angie-gh.github.io/adix.github.io/)


*********************************************************************************** 

### Purpose of this page:
We just finished a two week session on IoT and Python Programming.  We are reflecting on techniques and lessons learned while programming a micro:bit controller as well as reviewing Javascript logic that allows for more impressive bluetooth connections. 
The below comments are specific to me.

### Overall reaction to scripting an IoT:
Wow, the sky is the limit on what can be automated.  The micro:bit controller we used has many built in features (such as: an accelerometer, temperature gauge, LED display and built-in LED images).  Tapping into these features requires minimal scripting. There are also sufficient online snipets of code to answer most questions regarding needed parameters as well as how one can format the output.     


### IoT modules that are useful to import into code:
- ####  "from microbit import *" module
	The "microbit" module allows the coder to access many of the built-in sensors of a micro:bit controller.  
	**Example of accessing an Accelerometer sensor on the micro:bit controller:**
	```
	#>>>>>We are using the "x" coordinate to indicate the right side of the card is being tilted <<<<<
        x = accelerometer.get_x()
	```
	
- #### "music" module
	The "music" module allows the coder to reference pre-stored music.  The "BA_DING" sound is particularly useful because it sounds like an error beep. 
	<br/>**Example of using a method from the Music module:**
	```
	#>>>>>controller projects an error sound via the speaker <<<<<
        music.play(music.BA_DING)
	```
- #### "speech" module
	Although the sound volume is very limited, the "speech" module is an incredible tool for making an IoT device for someone with vision limitations.  Also, a coder is able to both generate new "music-like" tones as well as convert written text to audible sentences.
	<br/>**Example of using a method from the Speech module:**
	```
	#>>>>>controller projects a verbal message via the speaker <<<<<
        speech.say(Encouragement_phrases[random_index], speed=120, pitch=100, throat=100, mouth=200)
	```
### Side Topic:  IoT and Javascript:
Although the course is a study in "Python Programming", we experimented with pre-coded javascript solutions that demonstrate the bluetooth capabilities of a micro:bit controller.  With Javascript, one can easily code a device to interact with a mobile device via bluetooth and a mobile application.
<br/>Note:  The micro:bit does not have a dedicated temperature sensor. Instead, the temperature provided is actually the temperature of the silicon die on the main CPU. As the processor generally runs cold though (it is a high efficiency ARM core), the temperature is a good approximation of the ambient temperature.  Reference:  https://makecode.microbit.org/reference/bluetooth/start-temperature-service
<br/>**Javascript: Example of the single line of javascript code for accessing the temperature sensor:**
```
function startTemperatureService(): void;
```
<br/>**Screenshots of the micro:bit free mobile app that interacts with the built-in sensors, such as the Temperature sensor**
<br/><img src="https://raw.githubusercontent.com/Angie-gh/adix.github.io/master/microbit_mobileapp_mainmenu.jpg" height="300" width="250">  <img src="https://raw.githubusercontent.com/Angie-gh/adix.github.io/master/microbit_mobileapp_monitorcontrol.jpg" height="300" width="250">

### How my programs differ from other coders:
**Part A:**
<br/>I take pride in making sure that my code is well-commented.  I think it is disrespectful to not provide sufficient remarks if you are expecting others to support your original logic. 
<br/>**Example of Commenting an IoT Device:**
```
#>>>>>>>>>>>>>>>>>>>>>>>>Initializing Variables <<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<
#>>>>Below variable used to limit variable assingments "one time" per head tilt <<<
Loop_FirstIteration = True
#>>>>Below variable used to count number of times the person tilts their head <<<
count_headtilts=0
#>>>>Below variable provides flag for exiting the monitoring and display a head tilt count <<<
continue_monitor=False
#>>>>Below list contains phrases that will be said repeatedly to the user if they tilt their head <<<
Encouragement_phrases=["Lift YOUR HEAD!","Look up at your partner!","Where are you looking?","Concentrate"]
#>>>>Below variable is used to randomize the message that is spoken to the user when they tilt their head<<<
random_index=0
```
<br/>**Part B:**
<br/>I try to give the user an option to start the IoT device again so that they don't have to press the "Reset" button on the micro controller.  No matter the nature of the solution, there is no reason not to provide a user-friendly experience. 
<br/>**Example of writing logic so that program stays running on IoT and user does not need to use Reset button.**
```
#>>>>Continuously looping through the program so that user can use the "a" and "b" buttons to start and stop<<<
while True:
    #>>>>>Checking to see if user has indicated that they want to start monitoring of tilts <<<<<
    if button_a.is_pressed() or continue_monitor==True:
        #>>>>>Below flag set to have more control over whether user intention is to enable monitoring <<<<<
        continue_monitor=True
        #>>>>>Obtaining x value from the accelerometer.  Based on the way the controller is placed on the head, 
        #>>>>>We are using the "x" coordinate to indicate the right side of the card is being tilted <<<<<
        x = accelerometer.get_x()
```


### Functioning Prototype - Head-tilt Dance Headset 
I created a IoT device that alerts the user when they have tilted their head a few degrees.  This is a useful tool for dance instructors to assist their students with keeping their head at a position that gives them the most balance and esthetics.  
This device provides the following:
- A green LED, placed at eye level, to confirm that the device is running
- A red blinking LED, placed at eye level, that alerts the user if the user has tilted their head to a level that will interfere with their dancing.
- A small speaker is placed near the user's ear that provides:
    A repeated audible alarm when head is tilted.
    A random message is repeated, that are customized sentences typed by the instructor, that encourages the user to lift their head.
- Once the user lifts their head, all sounds stop and the green LED displays.  <br/><img src="https://raw.githubusercontent.com/Angie-gh/adix.github.io/master/IoT_headset.jpg" height="300" width="250">  <img src="https://raw.githubusercontent.com/Angie-gh/adix.github.io/master/IoT_standalone_headset.jpg" height="300" width="250">
*********************************************************************************** 

### [Return to Angie Home](https://angie-gh.github.io/adix.github.io/)


