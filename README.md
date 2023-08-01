# An Asshole's guide to W-Okada's RealTimeVoiceChangerClient and it's Settings
Read this if you DO NOT trust me : https://docs.google.com/document/d/11eofqJXiHiVsLt_JjCwHROt_0OSryPFb1toyDBuLoXc/edit it is a different guide made my someone else, but it ALSO covers the installation and what version to pick.


This is not a one stop shop just my recommendations for what YOU the person reading this should use, depending on your hardware. But FIRST let's get some stuff out of the way

Before even starting find your start_http.bat file, right click it and create a shortcut, if you do not know how to create a shortcut, figure it out. Put that new shortcut on your desktop so you can easily access it, we will make a better version of this shortcut later that uses even less resources once everything is 100% working.

IF your GPU is not showing and you have an NVidia Graphics card make sure you have the NVIDIA Cuda Toolkit drivers installed, you can do a google search and find it.

If you are on AMD you should have the DirectML version of W-Okada's Realtime voice changer client installed. To tell the difference if you look at the GPU section, if theres a dropdown menu, thats the NVidia one, as of Version 11. If it says cpu, 0, 1, 2, 3, then you are on the correct AMD one. 

For AMD open your task manager (control+shift+escape) Press Performance, and you should see your GPU listed as GPU #, usually it will be 0, but sometimes it can be something else,

That number listed is what you would select inside of W-Okada's client to use your gpu.


# Chunk Extra And F.0
Look at the images located in the folders above corresponding to what you have, for W-Okadas voice changer client itll give what i recommend as the starting point for Chunk + Extra.

but seriously....

NAVIGATE TO THE SCREENSHOT FOLDER IT LITERALLY GIVES YOU ALL OF THESE SETTINGS

NOTE: I do not have an AMD card so you wont see the cpu, 0, 1, 2, 3, boxes in my screenshot.

AMD users you have to have an ONNX model, and you HAVE to be using CREPE_TINY or CREPE_FULL for your gpu to even be used.

for both types of cards you play a little minigame of testing where you want to get as low of a chunk size as you can without any audio issues happening

# BUT ITS NOT USING MY GWAFFICS CARD >:(
FOR You NVIDIA cucks first, CUDA core usage does not appear on Task Manager usage, I can assure you, if you have your GPU selected it is being used.

For You AMD people literally the section before tells you how to make it use your GPU

But then you fucktards are saying "BUT ITS USING 50% OF MY CPU!@#! AND ONLY 5% OF MY GPU!" that.... is litearlly how it works, if its not using your cpu at all the program wouldnt even be open.

but it isnt supposed to be using half your cpu, which means you are running something too hard usually it is the EXTRA setting. So just.... LOWER IT. 

As an owner of a 3070 and an 11700F, it uses AT MOST 9% cpu usage while talking. and 0% gpu usage, according to Task Manager. You aren't having an issue, thats just how this fucking thing works. cry about it.

# Audio
Reasons why I am listing the settings where they are as is, as it is a good middle ground that should work for majority of users, I will explain how to do the Audio Section now which is at the bottom no images are needed here if you can understand text you should be fine as images wont really matter as you can't see everything anyways.

What to pick

Server Mode : this is the option I recommend everyone to pick, it is faster and doesnt try to get reprocessed again

Client Mode : this mode is slower but can be your only hope if server mode just doesnt work for you

Sample Rate: Pick the sample rate of your audio devices in your windows sounds settings, to get there on windows 10 you right click the speakers icon in your task bar and hit sounds, on windows 11 you have to hit sound settings, then scroll to the bottom and hit advanced sound settings which would finally open the same window, overly complicated for no reason Microcuck.
44100 or 48000 are what you want to be using just make both of them match, on your recording and playback device.

You will need to have a Virtual Audio Cable of some sort in a moment.

Input : Choose (Wasapi) on the first dropdown box, if it doesnt work later when you do a sound test you will change this to (MME)
Second box for input: choose your Microphone, if you dont know what it is, when you were checking your sample rate it would have told you the name of the device.

Output : Make sure the first drop down matches the same as what you had from Input either being (Wasapi) or (MME)
Now heres where having a Virtual Audio Cable Matters, this is where you would choose your Virtual Audio Cable.

Monitor : Same thing with the first drop down box as previously stated
Pick your headphones on this for initial testing.


Now one last statement for you AMD folks,
ONNX models are what you need to actually use your GPU, so you are going to have to convert your model to ONNX if you cant, cry. or make someone else do it for you. I certainly wont.

Note: during sound testing if switching to MME didnt work just go to client mode like i said it was your saving grace, but you would only choose your input and output device

# Does your Voice Sound like you are being electrofucked by Chinese Pop Rock Candy?

audiodg.exe to priority high and cpu affinity to a single cpu core

open task manager hit details

right click audiodg.exe and set whats listed above

as for the single cpu core make it an even number as thats your real cpu cores, so in my case i use 2 since i dont want it running on cpu 0 just my preference

This gets rid of any potential static happening as you are forcing it only use one core, if its on all cores and its cycling through as it normally does, it produces crackles, static, etc.

if you get ProcessLasso you can make the audiodg.exe setting continuously reapply every boot, otherwise you have to do it yourself every single time, suffer.

# Special Needs Section for AUDIO

You are going to need Audio Suppression of some kind if you have constant background noise on your normal microphone. Just pick one below, I will list two options

NVIDIA Broadcast can work extremely well however on system reboots theres a 50% chance it just breaks your voice changer, the issue was specifically happening to me, if it doesnt for you then thats gucci, if it is though just get the next one.

Steelseries Sonar this is the one I use, has Clearcast built into it which is a really good noise suppression, its not as good as Broadcasts but anyone should be able to use it even if your system was built by the Obama Administration who fucked our school lunches by making it significantly worse quality



# FINALLY 
we get to testing, I will tell you audio issues that happen and how to fix them. 

From using the initial testing if you talk if your voice sounds perfectly clear you can move your chunk to the next smaller size until theres any issue, however for you smelly fucks who have an issue with the voice being choppy, you make your chunk size one larger.

You will repeat this process until you cant proceed any further, if you made it to 2048 extra for those smelly fucks you can try one final thing and pray it works and make your extra size one value larger, do not go any higher than this 16k value as you'll just have so much negative value that it wont even matter if you can run it.

For those good people who have there new Low Chunk size figured out where they can't go any lower, congratulations if you want to lower you COULD raise the extra like I said before to the 16k value, but it will use more CPU resources, for me a RTX 3070 user, I can get away with 32 chunk (i use 48 instead because anything longer than this has the same level of quality)

You want to be able to talk for at least 20 seconds non stop with absolutely no stuttering or words being cut off (on client mode this will happen if you turn any of the NOISE checkboxes on so just dont)

The very first sentence you say will always be fucked somehow so when you change a setting keep saying something like cuck until you hear it say it clear. then you can do your 20ish seconds of talking to see if it works, you will get tripped up in this testing phase as you are listening to what you say slightly delayed.

Finally you can remove the monitoring option if you like what you ended up with, so you dont have to listen to your ai voice anymore, as you are now a proud user of realtime voice with it being consistent.

Now let's make that secret sauce that allows RVC to use less resources, its not by a lot but it still matters.
we can now delete that original shortcut you have, or don't if you are a rebel.

Open up notepad and paste the next three lines into the file

Set WshShell = CreateObject("WScript.Shell") 

WshShell.Run chr(34) & "C:\PATH\TO\MMVCServerSIO\start_http.bat" & Chr(34), 0

Set WshShell = Nothing

change the Path to, parts into the actual path to the start_http.bat file. its different for everyone.

Save this file as a .vbs (refer to the VBS Image folder to see what the inside of the file will look like)

What this file does is make that black box that always launches, not show up when you run this. itll save 1% cpu usage but 1% is still something
Sometimes itll be more depending on how much resources it was using in task manager, for me it was trying to use 30% which now it doesnt use anything.

ONLY do the VBS file if you have everything set up and dont plan on changing anything. this means you have no need to even look at the black box for errors as its already working perfectly for you

note: So according to the AI HUB discord you allegedly need to have the file inside of the MMVCServerSIO folder where the start_http.bat file is to make it work

# Congratulations you are no longer a soyboy cuck and you have a working setup!
