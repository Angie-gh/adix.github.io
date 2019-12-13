# Unit 4 - Reflections - Final Project 
### [Return to Angie Home](https://angie-gh.github.io/adix.github.io/)


*********************************************************************************** 

### Purpose of this page:
This is a presentation/demonstration of a final project(Hackathon) in a video.

### Highlighted Python functionalty included in this final project:
Text messaging implemented to communicate web scraping results from a Podcast website.

### Modules used in this project:  
The below modules (**Requests**, **Sys**, **Webbrowser**, **Beautiful Soup** and **Twilio**) were instrumental in accomplishing this script.
```
import requests, sys, webbrowser, bs4
from twilio.rest import Client
```

### Audience:  
This script is written for a podcast listener who references podcast websites instead of using mobile apps that consume too much storage.
This is a person who does not like the task of manually "checking" the website to see if a new podcast has been published and whether they have any interest in listening to the speaker.<br/>
The existing manual process:</br>
- Opening a browser and clicking on the bookmarked podcast website 
- Waiting for the page to load to see if a new podcast has been published.
- If a new podcast has been posted, and you don't recognize the guest's name, you must click again to see a short "guest bio" or to listen to the audio.
- You wait for the second page to load before you can continue.

### Description of Features:  
This script has been written for a specific podcast (**Armchair Expert**) but can be modified for other podcast sites.
- A recipient provides their mobile phone number.</br>  
- On the first run of the script, the recipient will receive a text alert informing them of the most recent podcast guest and the date of the recording.</br>
- The recipient will not receive another text message until the recording date has changed (meaning there is a newly published podcast for a different guest).

### Contents of each Text Message:  
The text message will contain the following information: 
- Guest's Name</br> 
- Episode Published Date</br> 
- Optional -- Background Information about the guest (Sometimes the person is not a public figure)</br>
<img src="https://raw.githubusercontent.com/Angie-gh/adix.github.io/master/screenshot_sample_text_msg.jpeg" height="400" width="250">

### Implementing the script:
This script should be scheduled to be run as a daily task from a computer.  Even if the podcast site markets that they release 
their episodes on specific days, this script will text message the recipient if they release them earlier.

### Video - Review of code and Demonstration:
<video src="testrecording1.mp4" poster="poster1.jpg" width="320" height="200" controls preload></video>

### Sample web-scraping script
- [web scraping with text message](https://github.com/Angie-gh/unit2/blob/master/photoresister_withImageDisplays_githubversion.py)
<br/>
*********************************************************************************** 

### [Return to Angie Home](https://angie-gh.github.io/adix.github.io/)


