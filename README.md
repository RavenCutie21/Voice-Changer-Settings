# A guide for W-Okada's RealTimeVoiceChangerClient and an overview of it's Settings
This guide is written by: [Yuna](https://discord.com/users/824922747423031359)

# Other Links
[Pinned Guide in the AI Hub server #help-voice-changer channel](https://docs.google.com/document/d/11eofqJXiHiVsLt_JjCwHROt_0OSryPFb1toyDBuLoXc/edit )

[Antasma's issues and fixes page](https://docs.google.com/document/d/e/2PACX-1vQIwJ3MVidhgEaXwWFl0xpVonVOVfneaNVADd7-NMWFgPIsfWWhG8NNqzQMsXDIOGlBIfxscoIm2_6I/pub)


# The Basics
Make sure to read the guide fully

virtual cable i recommend but at the end of the day it doesnt matter
[VAC (Virtual-Audio-Cable by Muzychenko)](https://software.muzychenko.net/freeware/vac470lite.zip) - this virtual cable runs better than the one by [Voicemeeter](https://vb-audio.com/Cable/) and you dont even have to change any settings, it has lower latency and a better audio quality right out of the box

------------------

127.0.0.1 is localhost so it doesnt matter if people see it. same as if it starts with 192.168 or 10.0, its all the same thing. there is no point in worrying about showing it in a screenshot.

------------------

DO NOT RUN AS ADMIN JUST BECAUSE ITS NOT WORKING, YOU MORE THAN LIKELY ARE JUST GOING TO RUN INTO MORE ERRORS

------------------

RE-EXTRACTING THE INITIAL INSTALL FOLDER AND MOVING IT SO IT REPLACES ALL FILES IN YOUR CURRENT INSTALL FIXES A TON OF ISSUES

------------------

IF YOU ARE GETTING ERROR CONNECTION REFUSED ON PORT 18888 DELETING STORED_SETTING.JSON CAN FIX THAT OR JUST RESTART YOUR ROUTER

------------------

WHEN SWITCHING TO SERVER MODE FROM CLIENT MODE JUST RESTART YOUR APPLICATION THERES A LOW CHANCE DURING THE SWITCH WHERE IT ACTUALLY JUST DOESNT START

------------------

What do I download? Make sure to use HuggingFace and read the downloads, since it shows all 3 in one spot again, it appears in bottom left corner, with the full url of what you are about to click.

A) NVIDIA - onnxgpu-cuda

B) AMD or INTEL GPU - onnxdirectML version

C) CPU - doesnt matter both work

D) MAC - the only mac one obviously

------------------

Before even starting find your start_http.bat file, right click it and create a shortcut, if you do not know how to create a shortcut, figure it out. Put that new shortcut on your desktop so you can easily access it, we will make a better version of this shortcut later that uses even less resources once everything is 100% working.

if that does work do the following in the folder where start_http.bat is press "control+L" type "cmd" press "enter" type "start_http.bat" press "enter"

IF your GPU is not showing and you have an NVidia Graphics card make sure you have the NVIDIA Cuda Toolkit drivers installed, you can do a google search and find it.

If you are on AMD you should have the DirectML version of W-Okada's Realtime voice changer client installed. To tell the difference if you look at the GPU section, if theres a dropdown menu, thats the NVidia one, as of Version 11. If it says cpu, 0, 1, 2, 3, then you are on the correct AMD one. 

For AMD open your task manager (control+shift+escape) Press Performance, and you should see your GPU listed as GPU #, usually it will be 0, but sometimes it can be something else,

That number listed is what you would select inside of W-Okada's client to use your gpu.

# New Features added in Version 12

Passthru - When RED it sends your NORMAL mic into your OUTPUT, and DISABLES the voicechanger, when GREEN the voicechange is on like it was PRIOR to V12.

Monitoring now has a use on server mode, and it also appears in client mode, if you do want to hear yourself and dont want to throw off your word timing, set the gain now conveniently below monitoring down to like 0.3 you want it very very subtle.

# TUNE and index
Tune is voice dependant so female to male you want a - tune, female to female you ideally dont have to change anything but you might have to depending on how soft your voice is in comparison.

The same can be said for males but its just reversed from above where soft becomes deep

Index is only really beneficial if your Accent is HEAVY, or DOESN'T MATCH and you can't imitate the person's accent you want. But the cost is CPU usage, 300% more usage to be exact. I recommend using 0.


# Chunk Extra And F.0
Look at the images located in the folders above corresponding to what you have, for W-Okadas voice changer client itll give what i recommend as the starting point for Chunk + Extra.


NOTE: I do not have an AMD card so you wont see the cpu, 0, 1, 2, 3, boxes in my screenshot.

AMD users you have to have an ONNX model, and you HAVE to be using CREPE_TINY or CREPE_FULL for your gpu to even be used.

for both types of cards you play a little minigame of testing where you want to get as low of a chunk size as you can without any audio issues happening

# Graphics Card, and Why it's not being used
NVIDIA owners first, CUDA core usage does not appear on Task Manager usage, if you have your GPU selected it is being used, depending on your settings it'll be around 40% of your VRAM.

For AMD people the section before this explains how to make it use your gpu, reread it

Yes the program will still use your CPU, that's just how things work. The Extra Value is basically adding CPU usage for you.

DO NOT USE EXTRA ABOVE 32768, IDEALLY JUST USE 16384

As an owner of a 3070 and an 11700F, it uses AT MOST 9% cpu usage while talking. and 30% gpu usage from checking vram. with 64chunk 16384extra

for intel arc, i have only seen one other person with it so i do not know if this is the case but i believe you just follow AMD

# Audio
What to pick

Server Mode : this is the option I recommend everyone to pick, it is faster and doesnt try to get reprocessed again

Client Mode : this mode is slower but can be your only hope if server mode just doesnt work for you, or if you are using a DUAL computer setup.

Sample Rate: Pick the sample rate of your audio devices in your windows sounds settings, to get there on windows 10 you right click the speakers icon in your task bar and hit sounds, on windows 11 you have to hit sound settings, then scroll to the bottom and hit advanced sound settings which would finally open the same window, they made it overly complicated for no reason.
44100 or 48000 are what you want to be using just make both of them match, on your recording and playback device. 

Just an extra side note: some people have really good audio equipment and use over 48000 sample rate, you will not be able to use chunk sizes as low as others on 48000, that is because your audio data is exponentially larger based on your sample rate.

----------------------------------------------
You will need to have a Virtual Audio Cable of some sort in a moment.

When installing a virtual cable it will change your defaults for your window sounds settings, so you have to open the sounds panel and reselect your defaults back to your mic and headphones, hence why the one i recommended is still even better as itll offer to open it immediately.

Input : Choose (Wasapi) on the first dropdown box, if it doesnt work later when you do a sound test you will change this to (MME)
Second box for input: choose your Microphone, if you dont know what it is, when you were checking your sample rate it would have told you the name of the device.

Output : Make sure the first drop down matches the same as what you had from Input either being (Wasapi) or (MME)
Now heres where having a Virtual Audio Cable Matters, this is where you would choose your Virtual Audio Cable.

Monitor : Same thing with the first drop down box as previously stated
Pick your headphones on this if you want to listen to it


# Fix for increasing stability at lower latency

audiodg.exe to priority high and cpu affinity to a single cpu core (you have to do it every boot unless you get processlasso)

open task manager hit details

right click audiodg.exe and set whats listed above

as for the single cpu core make it an even number as thats your real cpu cores, so in my case i use 2 since i dont want it running on cpu 0 just my preference

This gets rid of any potential static happening as you are forcing it only use one core, if its on all cores and its cycling through as it normally does, it produces crackles, static, etc.

if you get [ProcessLasso](https://bitsum.com) you can make the audiodg.exe setting continuously reapply every boot, otherwise you have to do it yourself every single time, suffer.


# But how do I use it everywhere else!

To use on any other APP, your INPUT for that game or application will be

Your virtal audio cable, the one you selected as output above^

your output device does not change at all it stays your normal headphones or speakers

very very easy.

# Fix Section for Audio making noises on its own

You are going to need Audio Suppression of some kind if you have constant background noise on your normal microphone. Just pick one below, I will list four options

[NVIDIA Broadcast](https://www.nvidia.com/en-us/geforce/broadcasting/broadcast-app/) can work extremely well however on system reboots if you dont configure its defaults seperately from everything else it can just pick the virtual cable as its mic and not work. (to do so open sound settings, and scroll until you can press app volume and device preferences, find the input box for this application and press your actual microphone this fixes any issues with the voice changer breaking from my testing)

AMD Noise Suppression (this just appears in your amd driver software afaik) can also work but it lowers your audio quality a fair amount depending on the level of background noise bleed, too high of a sample rate will not work, you need 48000 afaik.

[Steelseries Sonar](https://steelseries.com/gg/sonar) this is the one I used to use, has Clearcast built into it which is a really good noise suppression, its not as good as Broadcasts but still way better than AMD's version anyone should be able to use it even if your system was built by the Obama Administration who fucked our school lunches by making it significantly worse quality

Finally the new (actually pretty old) method that I use, I use [Werman's RN Noise removal](https://github.com/werman/noise-suppression-for-voice), by injecting it into my microphone, with [Equalizer APO](https://sourceforge.net/projects/equalizerapo/). It sounds complicated but it doesnt even create another virtual input like all the others. It's noise suppression is equal to Nvidia Broadcasts, with LESS usage than steelseries sonar. You can watch a video for learning how to set this up or DM me if you really want to. 

In my opinion putting the VST's that you get from Werman RN Noise into this folder C:\Program Files\EqualizerAPO\VSTPlugins is far easier as your first time going to select a plugin will throw it there. Just remember when setting it up your chain will go as follows for APO, Device-your mic, any other plugins you want like preamp which is just gain control minus20 to positive20db, and finally the rn noise plugin, there will be a folder at the top called WermanSettings to show what i recommend as well as a voice clip showing off and on.

Stereo was the only one that worked for me but if Mono works, use that as its far more efficient.

# Higher End GPU Owners I.E. 3060+
you should just be able to get away with 48 chunk and 16k extra with no issue at all, unless your game is gpu intensive then you raise the chunk to 80 or 112+.

it is still case by case but as long as you did everything above even the audiodg stuff then you should be fine UNLESS you are using sample rates above 48000.

the giga 4090 chads can get away with basically anything but my recommendation would be 32 chunk as if its clear for a 3070 you should be fine no point in going lower anyways. 32k extra, think of extra as a data cache that makes low latency function without sounding like complete ass.

# model section
replacing a model does not delete it

yes it is possible to delete models, however not in the UI, you have to navigate to the folder called MODEL_DIR where your start_http.bat file is located, the mini sub folders inside of it starting from 0 ending at 199 (if you use the 200th slot 199 will appear) can just be deleted to remove a model. 

they will automatically remake themselves when you add a model in a slot that doesnt have a folder.

# FINALLY 
we get to testing, I will tell you audio issues that happen and how to fix them. 

From using the initial testing if you talk if your voice sounds perfectly clear you can move your chunk to the next smaller size until theres any issue, however if you still have an issue with the voice being choppy, you make your chunk size one size larger.

You will repeat this process until you cant proceed any further, if you made it to 2048 chunk, you can try one final thing and pray it works and make your extra size one value larger, do not go any higher than this 65k value as you'll just have so much more resources used.

For those good people who have there new Low Chunk size figured out where they can't go any lower, congratulations if you want to lower you COULD raise the extra like I said before to the 16k value, but it will use more CPU resources just do not exceed 65k extra, for me a RTX 3070 user, I can get away with 32 chunk (i use 48 instead because anything longer than this has the same level of quality for me)

You want to be able to talk for at least 20 seconds non stop with absolutely no stuttering or words being cut off (on client mode this will happen if you turn any of the NOISE checkboxes usually so just dont and get something else for noise suppression as stated before)

The very first sentence or word you say will always be fucked somehow so when you change a setting keep saying something like cuck until you hear it say it clear. then you can do your 20ish seconds of talking to see if it works, you will get tripped up in this testing phase as you are listening to what you say slightly delayed.

Finally you can remove the monitoring option if you like what you ended up with, so you dont have to listen to your ai voice anymore, as you are now a proud user of realtime voice with it being consistent.

# you do not need to proceed from this point on

Now let's make that secret sauce that allows RVC to use less resources, its not by a lot but it still does something.
we can now delete that original shortcut you have, or don't if you are a rebel.

Open up notepad and paste the next three lines into the file, make sure the file is ONLY 3 lines.

-----------------------------------------------------

Set WshShell = CreateObject("WScript.Shell") 

WshShell.Run chr(34) & "C:\Users\User\Desktop\MMVCServerSIO\start_http.bat" & Chr(34), 0

Set WshShell = Nothing

-----------------------------------------------------

change the Path to, parts into the actual path to the start_http.bat file. its different for everyone.

Save this file as a .vbs (refer to the VBS Image folder to see what the inside of the file will look like)

What this file does is make that black box that always launches, not show up when you run this. itll save 1% cpu usage but 1% is still something
Sometimes itll be more depending on how much resources it was using in task manager, for me it was trying to use 30% which now it doesnt use anything.

ONLY do the VBS file if you have everything set up and dont plan on changing anything. this means you have no need to even look at the cmd window for errors as its already working perfectly for you

note: you should have the file inside of the MMVCServerSIO folder where the start_http.bat file is to make it work, you can then make a shortcut of this and put it anywhere you want, 

mine goes in the startup folder since i want it to be running the moment i turn my computer on. to do so press win+e, control+L, type startup, press enter if you want it to appear in your windows start menu go back on folder by clicking the programs section in the top bar, and put the file there, or just put it on your desktop.

# Congratulations you should have a working setup with some good optimizations!
any other stuff you have issues with ask [AI Hub's discord server](https://discord.gg/aihub) but it should be covered in this guide unless its a weird issue.

# this section doesnt refer to the voice changer but can help for lessening FPS drops in game

UNDERVOLTING sounds scary but it isnt. it reduces temp and can get you more performance out of your card. read an actual guide on how to do it

but the quick explanation is use msi after burner, look up what your reference base clocks are, and lower your core clock down while looking at the curve editor until it hits that clock, then at around 950voltage which seems to work for 90% of cards you raise it back up to your boost speeds, obviously you want to know what those are too. 

i do cap my fps anyways obviously if you are running unlimited there will be some drops, but im running no drops now while before i was from the same cap i had set previously.

# Want to host on a seperate computer and still use it

You are gonna need to install it manually using either Docker or Anaconda.

After Installing and running it, No UI will open, that's the point of it. Now you want to find your Computers local IP address, you can figure out how to do that, but lets say it's

192.168.1.123... put that number in your browser on a computer you want to use it on, and put :18888 at the end which is basically what the normal install does already. Now if I'm correct since I haven't done this yet, I believe it would be Server for audio mode but it could very well just be client mode. I am going to assume it's Client where you would as the client should be the user and the server would be just the thing actually hosting it. But it should just work like a normal install from this point.

edit: so from my limited testing it seems like it is client mode you want to use, but it broke randomly after it was working so i wasnt able to fully find out

# random error stuff figured out

if this error appears:

Traceback (most recent call last):

  File "voice_changer\VoiceChanger.py", line 312, in switchModelType
  
  File "voice_changer\RVC\RVC.py", line 92, in init
  
  File "voice_changer\RVC\RVC.py", line 244, in prepareModel
  
  File "voice_changer\RVC\pipeline\PipelineGenerator.py", line 45, in createPipeline\
  
UnboundLocalError: local variable 'embedder' referenced before assignment

the fix is allegedly this:

open windows file explorer (Win+E)

press Control+L

type %appdata%

find the folder called "voice-changer-native-client"

delete it which fixes it for some people

obviously you would do so at your own risk

-------------------------------------------------------------------

if pressing the EXPORT to ONNX button results in a crash, its actually really easy to fix if you look at the command prompt window, it usually tells you your gpu is out of resources

so the quick easy fix is either 

A) making your chunk and extra a larger value by a significant amount and closing all background processes 

B) just running it on your cpu instead

-------------------------------------------------------------------

PIPELINE NOT INITIALIZED

Two Fixes are as follows

A) Third party antivirus can conflict and cause it to not start or

B) The more Likely one is the path to the file is too long, either put it on the root of your drive or directly on your desktop


