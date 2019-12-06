# w10-11_codepath_honeypot_project

Seting up a honepot and intercepting attempted attacks using Modern Honey Network.

<hr>

## Objective
From the codepath page:

> In this assignment, you will stand up a basic honeypot and demonstrate its effectiveness at detecting and/or collecting data about an attack. 
<hr>

Codepath gave instructions on how to set-up and deploy a honeypot. the same instructions also work to deploy more honeypots of my choice. 

### Honeypots Deployed

* Dionaea
* snort
* suricata


### hours spent:
  About 10 hrs


<hr>


<b><h3>Issues Encountered</h3></b>
* Though the instructions were easy to follow, I coiuld not get the MHN server to show some of the icons. Could be that I missed a command. Deploying a honeypot was no a problem whatsoever and setting up the other two was straight forward.
![image](https://user-images.githubusercontent.com/42822276/70299097-c37e4b80-17a8-11ea-9b75-469201c56839.png)

* Downloading the .json file was a bit complicated, not sure if it was becasue I'm using Windows for this project, or I was running the commands from the worng instance. I needed more instructions and how to troubleshoot some errors.  
![user enumeration](Newfolder/green_user_enum.gif)





**Bonus Objective:** Build on Objective #4 :XXS
![BonusXXS](Newfolder/green_bonus_xxs.gif)

Experiment to see if you can use XSS to: a) direct the user to a new URL, b) read cookie data, c) set cookie data.

* This exploit is basically the same as vulnerability for green #2. Through the feedback comment.

* In this case we use replace alert() statement with a window.location.assign(). I redirect the user to duckduckgo.



<hr>

<b><h3>Red</h3></b>
Vulnerability #1 Insecure Object Reference (IDOR)

![idor](Newfolder/red_user_enum.gif)


* In the 'find a salesperson' page, we directly change the id parameter in the url.

* Id's 10 and 11 were not supposed to be seen by everyone, but are accesible by simply changing the ID number in the url.



<hr>

<b><h3>Blue</h3></b> 
Vulnerability #1 SQL Injection

![sqli](Newfolder/blue_sqli.gif)

* I was able to use an SQL Injection exploit in the salesperson.php page.

* This exploit can be done via the url.

* The injection used was 'code(' OR 1=1'--)'

<hr>

### Notes

For about half an hour I did not know where to start.
However, the instructions for week 8 gave me an idea on where to begin, and reminded me on the attacks.  
The easiest exploit I found was enumeration, since the first step I took was to look at login errors, hoping I could get some 
errors that could lead me to SQLi.
