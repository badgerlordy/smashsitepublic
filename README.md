# smashsitepublic

This is the public repository for the 'smashbet' website project.

The goal of this project was to create a website (webapp) that allowed for interactive betting of a fighting video game being streamed via Twitch (super smash brothers ultimate).
A Nintendo Switch is hooked up to a streaming PC for the video output. A custom Switch controller is wired(soldered) to the GPIO pins of a raspberry PI zero. This allows for remote control (from a PC) of the Switch.

The website is based on the Django framework and written in Python. With standard HTML, CSS, Javascript for the frontend.
The content is served to the users via Nginx and gunicorn. Along with asynchronus websockets (channels: https://channels.readthedocs.io/en/stable/) this allows the serving of many users at once, and can be scaled up.

There is a custom reader application that runs on the streaming PC. Located here: https://github.com/badgerlordy/smash-bros-reader
It 'reads' the screen to verify the game states (characters in the match,player names, score, who won). The reader application then sends this information to the frontend via RESTful API. 

The user is presented with the player names and characters for the match, and the teams they can bet on. They are then able to enter in the bet amount and lock it in before the pre-game timer runs out. 

