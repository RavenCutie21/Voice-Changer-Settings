# RVC-Settings
My settings for W-Okada's Realtime voice changer client.


This is not a one stop shop just my recommendations for what YOU the person reading this should use, depending on your hardware. But FIRST let's get some stuff out of the way

Before even starting find your start_http.bat file, right click it and create a shortcut, if you do not know how to create a shortcut, figure it out. Put that new shortcut on your desktop so you can easily access it, we will make a better version of this shortcut later that uses even less resources once everything is 100% working.

IF your GPU is not showing and you have an NVidia Graphics card make sure you have the NVIDIA Cuda Toolkit drivers installed, you can do a google search and find it.

If you are on AMD you should have the DirectML version of W-Okada's Realtime voice changer client installed. To tell the difference if you look at the GPU section, if theres a dropdown menu, thats the NVidia one, as of Version 11. If it says cpu, 0, 1, 2, 3, then you are on the correct AMD one. 

For AMD open your task manager (control+shift+escape) Press Performance, and you should see your GPU listed as GPU #, usually it will be 0, but sometimes it can be something else,

That number listed is what you would select inside of W-Okada's client to use your gpu.


I will embed the images later for now refer to the screenshots in the folders...

NOTE: I do not have an AMD card so you wont see the cpu, 0, 1, 2, 3, boxes.

Reasons why I am listing the settings where they are as is, as it is a good middle ground that should work for majority of users, I will explain how to do the Audio Section now which is at the bottom no images are needed here if you can understand text you should be fine as images wont really matter as you can't see everything anyways.

What to pick
Server Mode : this is the option I recommend everyone to pick, it is faster and doesnt try to get reprocessed again
Client Mode : this mode is slower but can be your only hope if server mode just doesnt work for you

Sample Rate: Pick the sample rate of your audio devices in your windows sounds settings, to get there on windows 10 you right click the speakers icon in your task bar and hit sounds, on windows 11 you have to hit sound settings, then scroll to the bottom and hit advanced sound settings which would finally open the same window, overly complicated for no reason Microcuck.
44100 or 48000 are what you want to be using just make both of them match, on your recording and playback device.

You will need to have a Virtual Audio Cable of some sort in a moment,
Input : Choose (Wasapi) on the first dropdown box, if it doesnt work later when you do a sound test you will change this to (MME)
Second box for input: choose your Microphone, if you dont know what it is, when you were checking your sample rate it would have told you the name of the device.

Output : Make sure the first drop down matches the same as what you had from Input either being (Wasapi) or (MME)
Now heres where having a Virtual Audio Cable Matters, this is where you would choose your Virtual Audio Cable.

Monitor : Same thing with the first drop down box as previously stated
Pick your headphones on this for initial testing.


Now one last statement for you AMD folks,
ONNX models are what you need to actually use your GPU, so you are going to have to convert your model to ONNX if you cant, cry. or make someone else do it for you. I certainly wont.

Note: during sound testing if switching to MME didnt work just go to client mode like i said it was your saving grace, but you would only choose your input and output device


FINALLY we get to testing, I will tell you audio issues that happen and how to fix them. 

From using the initial testing if you talk if your voice sounds perfectly clear you can move your chunk to the next smaller size until theres any issue, however for you smelly fucks who have an issue with the voice being choppy, you make your chunk size one larger.

You will repeat this process until you cant proceed any further, if you made it to 2048 extra for those smelly fucks you can try one final thing and pray it works and make your extra size one value larger, do not go any higher than this 16k value as you'll just have so much negative value that it wont even matter if you can run it.

For those good people who have there new Low Chunk size figured out where they can't go any lower, congratulations if you want to lower you COULD raise the extra like I said before to the 16k value, but it will use more CPU resources, for me a RTX 3070 user, I can get away with 32 chunk (i use 48 instead because anything longer than this has the same level of quality)

You want to be able to talk for at least 20 seconds non stop with absolutely no stuttering or words being cut off (on client mode this will happen if you turn any of the NOISE checkboxes on so just dont)

The very first sentence you say will always be fucked somehow so when you change a setting keep saying something like cuck until you hear it say it clear. then you can do your 20ish seconds of talking to see if it works, you will get tripped up in this testing phase as you are listening to what you say slightly delayed.

Finally you can remove the monitoring option if you like what you ended up with, so you dont have to listen to your ai voice anymore, as you are now a proud user of realtime voice with it being consistent.

