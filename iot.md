# This is Internet of Things (IoT) 

**Example of one of my first IoT python scripts.
<br/>It utilizes a potentiometer on a breadboard to demonstrate how the dial can increase/decrease the flashing LED:**
```
from microbit import *

while True:
    potVal = pin2.read_analog()
    pin0.write_digital(1)
    sleep(potVal)
    pin0.write_digital(0)
    sleep(potVal)
```
# Unit 2 - Reflections: IoT - Programming a device with Python
### [Return to Angie Home](https://angie-gh.github.io/adix.github.io/)


*********************************************************************************** 

### Purpose of this page:
We just finished a two week session on IoT and Python Programming.  We are reflecting on techniques and lessons learned while programming a micro:bit controller as well as reviewing Javascript logic that allowed for more impressive bluetooth connections. 
The below comments are specific to me.

### Overall reaction to scripting an IoT:
Wow, the sky is the limit on what can be automated.  The micro:bit controller we used had many built in features (accelerometer, temperature gauge, LED display, built-in LED images).  Tapping into these features required minimal scripting. There is also sufficient sample scripts online to answer most questions on parameters and formating that is needed.     

### Ah-ha Moments:
**Below are some of my observations:**
- #### The colon is your friend
	With any kind of loop declaration or function definition, a colon (:) is needed to indicate that some decision making logic is about to follow.  As a Python coder, remember you need to add a colon for these scenarios.  Note:  When the py source code is compiled, the runtime complier will let you know if an expected colon is missing.
- #### Semi-colons at the end of sentences are overrated
	If you have ever coded in C#, you will be thrilled to know that in Python scripting, a semi-colon is not used at the end of a line.  It is like having Christmas all year long.  No need to search for missing semi-colons in your code.
- #### Indents are sensitive
	*Don't panic when you get a compile error.  50% of the time it is an extra space after an indentation.*
	Although the single spaces can seem petty, visually it makes the code dependably easy to read.
- #### Numeric commas can't be taken for granted
	In many languages, the coder can often take for granted that the comma (,) in numeric values will automatically be displayed.  In Python, an additional formating command format(numeric_value,",d") needs to be included:
	<br/>**Example:**
	<br/>print (format(42500, ",d"))
	<br/> **Screenshot example:**
	<br/>![Formatting a numeric value](FormatNumericWithCommas.PNG)
- #### "While True" is a nice automatic loop
	When needing to generate a quick error-handling loop, it is nice and simple to use a "While True" loop and then only exit by performing a "break" statement. 
	<br/>**Screenshot example:**
	<br/>![While Loop](While_True_simpleloop.PNG)
- #### Built-In modules/features are timesavers
	There is the ability to use the Dictionary datatype to strip out duplicate entries in a string.
	<br/>Screenshot example:
	<br/>![Dictionary remove duplicates](Dictionary_abilityTostripDuplicates.PNG)
- #### Quickly changing lists into strings and vice versa
	One of the biggest timesavers so far has been learning how to quickly translate a list into a string and vice versa.
	<br/>Examples:
	<br/>"".join(x)   turns a list "x" into a string
	<br/>list(x)      turns a string "x" into a list
	<br/>x.split      turns a string "x" into a list
	<br/>**Screenshot example 1:**
	<br/>![lists to strings](quick_listsFromStrings.PNG)
	<br/>**Screenshot example 2:**
	<br/>![lists to strings](SimpleClearLogic_CreatingEncryptionKey.PNG)

### Useful modules, specific to IoT, that are useful to import into code:
- #### "random" module
	The "random" module allows the coder to generate random output with a single line of code.  
	**Example Code: A game that users the random module:**
	<br/>[Rock, Paper Scissors Game](https://github.com/Angie-gh/unit1/blob/master/week03_RockPaperScissors_Angie.py)
- #### "getpass" module
	The "getpass" module is a super valuable module for quickly blocking the display of a user's keystrokes when they are inputting sensitive information like a password.  
	**Example Code: A password encryption tool that uses the getpass module:**
	<br/>[Encrypting and Decrypting Passwords](https://github.com/Angie-gh/unit1/blob/master/week05_EncryptionProject_Angie_ExtraCredit_Part7_Part8_b.py)
- #### "pyperclip" module
	This is one of my favorite modules.  The "pyperclip" module can retrieve input or place output via the user's clipboard.  This provides a level of security by protecting unencrypted text. If a third party is shoulder surfing the user of a python program, the observer won't have privy to whatever sensitive data is being sent or returned to the user.  Ideally, the user would paste their output
into a protected input text field, so that the text would never be visible, or minimally hidden with asterisks.
	**Screenshot example 1 - outputing content from program to clipboard:**
	<br/>![PyperclipCopy](PyperclipCopyExample.PNG)
	<br/>**Screenshot example 2 - retrieving input for program from clipbard:**
	<br/>![PyperclipPaste](PyperclipPasteExample_viaUserInput.PNG)	
	


### How my programs differ from other coders:
**Part A:**
<br/>I take pride in making sure that my code is well-commented.  I think it is disrespectful to not provide sufficient remarks if you are expecting others to support your original logic. 
<br/>**Example of Commenting an IoT device:**
<br/>![Sample comments]
<br/>**Part B:**
<br/>I try to give the user an option to start the IoT device again so that they don't have to press the "Reset" button on the micro controller.  No matter the nature of the solution, there is no reason not to provide a user-friendly experience. 
<br/>**Example Code: A Password Locker tool that utilizes both a menu and a continue prompt:**
<br/>[IoT - headtilt device]

### I'm proud of my simple but functional head-tilt detector:
I am most proud of solutions that use minimal lines of code to accomplish something that would otherwise be exptremely time-consuming to process manually. Employing well-named functions helps to make repetitive code easier to follow.
<br/>**Example Code: An encryption and decryption tool that is efficient in its use of logic:**
<br/>[Encrypting and Decrypting Passwords](https://github.com/Angie-gh/unit1/blob/master/week05_EncryptionProject_Angie_ExtraCredit_Part7_Part8_b.py)

### What can hinder my progress?:
My learning curve is affected by how well the instructor prepares for their lecture, whether the in-class demonstrations run smoothly, and whether I receive timely responses to email requests for assistance.  Even a reply that "I'm sorry, I do not have time to help you" is better than no reply.

### Functioning Prototype - Head-tilt Dance Headset 
I created a IoT device that alerts the user when they have tilted their head a few degrees.  This is a useful tool for dance instructors to assist their students with keeping their head at a position that gives them the most balance and esthetics.  
This device provides the following:
- A green LED, placed at eye level, to confirm that the device is running
- A red blinking LED, placed at eye level, that alerts the user if the user has tilted their head to a level that will interfere with their dancing.
- A small speaker is placed near the user's ear that provides:
    A repeated audible alarm when head is tilted.
    A random message is repeated, that are customized sentences typed by the instructor, that encourages the user to lift their head.
- Once the user lifts their head, all sounds stop and the green LED displays.
&nbsp &nbsp<img src="https://raw.githubusercontent.com/Angie-gh/adix.github.io/master/IoT_headset.jpg" height="300" width="250">&nbsp &nbsp<img src="https://raw.githubusercontent.com/Angie-gh/adix.github.io/master/IoT_standalone_headset.jpg" height="300" width="250">
*********************************************************************************** 

### [Return to Angie Home](https://angie-gh.github.io/adix.github.io/)


