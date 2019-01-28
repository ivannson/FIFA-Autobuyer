# FIFA-Autobuyer
Automatically buying players on FIFA Web App with Python

# Required:
Chrome browser
webbot library (https://github.com/nateshmbhat/webbot) - does the clicking
tkinter - does the buttons


# How it works 
Clicking 'Go to FUT Web App' opens a new Chrome window and goes to https://www.easports.com/fifa/ultimate-team/web-app/#

Clicking 'Login' clicks.... You can guess what it clicks

Clicking 'Input Email and Password' inputs your email and password for your Origin account. These have to be specified in the 'credentials' function. Then the bot clicks 'Send Verification Code' which you have to type in manually. 
If you don't want to specify your email and password in the code you can do this step manually. 

To start buying players, go to the 'Transfers' tab, find a player that you need, and specify the Max Buy Now price and the minimum buy/buy now prices too.
It is important to have tolerance because the bot changes the prices slightly (by clicking +/- on the price) in order for the list of players to be refreshed. so if your specified price is 10,000, it will be chaninging between 10,250 and 10,000. This keeps the account from getting banned as it simulates human behaviour. 

## How many times does the bot try to snipe a player?
Each time the 'Start Sniping' putton is pressed, a random number between 30 and 70 is generated. This is how many attempts at buying a player can be made. These numbers can be changed in the snipe() function. It is worth noting, that the higher the upper bound is, the less safe it is to do (more likelihood of the game asking you to verify that you are a human). 

After each attempt the script stops for a random amount of time (between 0.3s and 1s) before sniping again. This is again an attempt to simulate human behaviour and fool the bot detection algorithm by introducing randomness (same as with the number of attempts). This can be changed in the last line of the snipe() function. 

If a verification process is triggered, the bot clicks some button that redirects it to the EA website (I don't know what it clicks exactly). To stop it from carrying on clicking, the change in the URL is detected and the sniping function is interrupted. If that happens, manually click 'Go back' button in Chrome and solve the puzzle.
To minimise the chance of verification being triggered, after each time (or every other time) the sniping process has finished, go to another tab in the menus, and then back to transfers.


# Note 
This is a small project that I spent a few hours on, so it is by no means bug free. Errors do occur where the bot starts clicking in the wrong place which causes it to jump around in the menus. This usually happens because the required button was not available, so the bot clicked 'the next best thing'. So if you do use it, watch what the bot is doing, do not leave it on for hours and go to bed.

This was designed as a proof of concept, and it is not advised to use it for personal gain.
