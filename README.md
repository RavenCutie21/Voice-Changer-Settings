# A funny guide to W-Okada's RealTimeVoiceChangerClient and it's Settings, if your feelings get hurt easily cry about it.
Read this if you DO NOT trust me : https://docs.google.com/document/d/11eofqJXiHiVsLt_JjCwHROt_0OSryPFb1toyDBuLoXc/edit it is a different guide made my someone else, but it ALSO covers the installation and what version to pick.

Antasma's issues and fixes page : https://docs.google.com/document/d/1qlCm4LL3wdv8AQ0B5_Tp9OOseJmPHpzak9HPXLlIJlg/edit

Make sure to read the guide fully as i do have some error fixes randomly thrown about but most of it is at the very bottom for the serious ones

~~I have to add this since the guide above removed this for whatever reason~~ IT HAS BEEN ADDED BACK BUT JUST IN CASE IT STAYS HERE

VAC (Virtual-Audio-Cable by Muzychenko) - this virtual cable runs better than the one by SHITMEETER and you dont even have to change any settings, it has lower latency and a better audio quality

https://software.muzychenko.net/freeware/vac470lite.zip

This is not a one stop shop just my recommendations for what YOU the person reading this should use, depending on your hardware. But FIRST let's get some stuff out of the way

\\\\ DO NOT RUN AS ADMIN JUST BECAUSE ITS NOT WORKING, YOU MORE THAN LIKELY ARE JUST GOING TO RUN INTO MORE ERRORS \\\\ 
\\\\ RE-EXTRACTING THE INITIAL INSTALL FOLDER AND MOVING IT SO IT REPLACES ALL FILES IN YOUR CURRENT INSTALL FIXES A TON OF ISSUES \\\\ 
\\\\ IF YOU ARE GETTING ERROR CONNECTION REFUSED ON PORT 18888 DELETING STORED_SETTING.JSON CAN FIX THAT OR JUST RESTART YOUR ROUTER \\\\ 
\\\\ WHEN SWITCHING TO SERVER MODE FROM CLIENT MODE JUST RESTART YOUR APPLICATION THERES A LOW CHANCE DURING THE SWITCH WHERE IT ACTUALLY JUST DOESNT START \\\\ 
\\\\ FOR OTHER ERRORS GO TO THE VERY BOTTOM OF THE PAGE I HAVE TWO MORE LISTED \\\\

------------------
V12 of W-Okada's software is actually really good.

A) Passthrough which means you can just leave your mic on your virtual audio cable, and send your normal voice through it if you turn passthrough (red)

B) Monitoring now has a use on server mode, if you do want to hear yourself and dont want to throw off your word timing, set the gain now conveniently below monitoring down to like 0.1 you want it very very subtle.

------------------

What do I download? Make sure to use HuggingFace and read the downloads it appears in bottom left corner, with the full url of what you are about to click.

A) NVIDIA - onnxgpu-cuda

B) AMD or INTEL GPU - onnxdirectML version

C) CPU - doesnt matter both work

D) MAC - the only mac one

------------------

Before even starting find your start_http.bat file, right click it and create a shortcut, if you do not know how to create a shortcut, figure it out. Put that new shortcut on your desktop so you can easily access it, we will make a better version of this shortcut later that uses even less resources once everything is 100% working.

IF your GPU is not showing and you have an NVidia Graphics card make sure you have the NVIDIA Cuda Toolkit drivers installed, you can do a google search and find it.

If you are on AMD you should have the DirectML version of W-Okada's Realtime voice changer client installed. To tell the difference if you look at the GPU section, if theres a dropdown menu, thats the NVidia one, as of Version 11. If it says cpu, 0, 1, 2, 3, then you are on the correct AMD one. 

For AMD open your task manager (control+shift+escape) Press Performance, and you should see your GPU listed as GPU #, usually it will be 0, but sometimes it can be something else,

That number listed is what you would select inside of W-Okada's client to use your gpu.


# TUNE and the semi-worthless index

Tune is voice dependant so female to male you want a - tune, female to female you ideally dont have to change anything but you might have to depending on how soft your voice is in comparison.

The same can be said for males but its just reversed from above where soft becomes deep

now the truly worthless thing called index, there is ZERO benefit from using this, the only thing you really get is demerits, such as longer processing time, more cpu&gpu usage, lower quality, but if you absoluetely have to because your accent is very strong then that is really unfortunate as it does use significantly more resources. You only use the hard values of 0 or 1. 0 being off, and 1 being on. do not use anything in between, it really doesn't effect it by much unless its a hard value.


# Chunk Extra And F.0
Look at the images located in the folders above corresponding to what you have, for W-Okadas voice changer client itll give what i recommend as the starting point for Chunk + Extra.

but seriously....

NAVIGATE TO THE SCREENSHOT FOLDER IT LITERALLY GIVES YOU ALL OF THESE SETTINGS, F0 now has a folder explaining what each thing does in chart format.

NOTE: I do not have an AMD card so you wont see the cpu, 0, 1, 2, 3, boxes in my screenshot.

AMD users you have to have an ONNX model, and you HAVE to be using CREPE_TINY or CREPE_FULL for your gpu to even be used.

for both types of cards you play a little minigame of testing where you want to get as low of a chunk size as you can without any audio issues happening

# BUT ITS NOT USING MY GWAFFICS CARD >:(
FOR You NVIDIA cucks first, CUDA core usage does not appear on Task Manager usage, I can assure you, if you have your GPU selected it is being used.

For You AMD people literally the section before tells you how to make it use your GPU

But then you fucktards are saying "BUT ITS USING 50% OF MY CPU!@#! AND ONLY 5% OF MY GPU!" that.... is litearlly how it works, if its not using your cpu at all the program wouldnt even be open.

but it isnt supposed to be using half your cpu, which means you are running something too hard usually it is the EXTRA setting. So just.... LOWER IT. 

As an owner of a 3070 and an 11700F, it uses AT MOST 9% cpu usage while talking. and 0% gpu usage, (from calculations its more like 20% of dedicated vram usage so really its not that bad) according to Task Manager. You aren't having an issue, thats just how this fucking thing works. cry about it.

for intel arc, i have only seen one other person with it so i do not know if this is the case but i believe you just follow amd for this guide

# Audio
Reasons why I am listing the settings where they are as is, as it is a good middle ground that should work for majority of users, I will explain how to do the Audio Section now which is at the bottom no images are needed here if you can understand text you should be fine as images wont really matter as you can't see everything anyways.

What to pick

Server Mode : this is the option I recommend everyone to pick, it is faster and doesnt try to get reprocessed again

Client Mode : this mode is slower but can be your only hope if server mode just doesnt work for you

Sample Rate: Pick the sample rate of your audio devices in your windows sounds settings, to get there on windows 10 you right click the speakers icon in your task bar and hit sounds, on windows 11 you have to hit sound settings, then scroll to the bottom and hit advanced sound settings which would finally open the same window, overly complicated for no reason Microcuck.
44100 or 48000 are what you want to be using just make both of them match, on your recording and playback device.

You will need to have a Virtual Audio Cable of some sort in a moment.

When installing a virtual cable it will change your defaults for your window sounds settings, so you have to open the sounds panel and reselect your defaults back to your mic and headphones, hence why the one i recommended is still even better as itll offer to open it immediately.

Input : Choose (Wasapi) on the first dropdown box, if it doesnt work later when you do a sound test you will change this to (MME)
Second box for input: choose your Microphone, if you dont know what it is, when you were checking your sample rate it would have told you the name of the device.

Output : Make sure the first drop down matches the same as what you had from Input either being (Wasapi) or (MME)
Now heres where having a Virtual Audio Cable Matters, this is where you would choose your Virtual Audio Cable.

Monitor : Same thing with the first drop down box as previously stated
Pick your headphones on this for initial testing.


---------------------------------------------------

AMD folks, 
ONNX models are what you need to actually use your GPU, so you are going to have to convert your model to ONNX if you cant, cry. or make someone else do it for you. I certainly wont.

Note: during sound testing if switching to MME didnt work just go to client mode like i said it was your saving grace, but you would only choose your input and output device

# Does your Voice Sound like you are being electrofucked by Chinese Pop Rock Candy?

audiodg.exe to priority high and cpu affinity to a single cpu core (you have to do it every boot unless you get processlasso)

open task manager hit details

right click audiodg.exe and set whats listed above

as for the single cpu core make it an even number as thats your real cpu cores, so in my case i use 2 since i dont want it running on cpu 0 just my preference

This gets rid of any potential static happening as you are forcing it only use one core, if its on all cores and its cycling through as it normally does, it produces crackles, static, etc.

if you get ProcessLasso you can make the audiodg.exe setting continuously reapply every boot, otherwise you have to do it yourself every single time, suffer.


# But MOM how do i use it everywhere else!

To use on any other APP, your INPUT for that game or application will be

Your virtal audio cable, the one you selected as output above^

your output device does not change at all it stays your normal headphones or speakers

wow that was easy wasnt it!

# Special Needs Section for AUDIO

You are going to need Audio Suppression of some kind if you have constant background noise on your normal microphone. Just pick one below, I will list two options

NVIDIA Broadcast can work extremely well however on system reboots theres a 50% chance it just breaks your voice changer, the issue was specifically happening to me, if it doesnt for you then thats gucci, if it is though just get the next one.

Steelseries Sonar this is the one I use, has Clearcast built into it which is a really good noise suppression, its not as good as Broadcasts but anyone should be able to use it even if your system was built by the Obama Administration who fucked our school lunches by making it significantly worse quality

# Super High End GPU Owners I.E. 3060+
you should just be able to get away with 32 chunk and 16k extra with no issue at all, unless your game is gpu intensive then you raise the chunk to 80ish.

the giga 4090 chads can get away with basically anything but i still recommend 32 chunk as if its clear for a 3070 you should be fine no point in going lower anyways. 16k extra is working for me but your extra may be larger, it just will use more resources, think of it as a data cache that makes low latency function without sounding like Joe Biden

# special model section
yes it is possible to delete models, however not in the UI, you have to navigate to the folder called MODEL_DIR where your start_http.bat file is located, the mini sub folders inside of it starting from 0 ending at 199 (if you use the 200th slot 199 will appear) can just be deleted to remove a model. 

they will automatically remake themselves when you add a model in a slot that doesnt have a folder.

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

# Congratulations you are no longer a cuck and you should have a working setup!
any other stuff you have wrong ask AI Hub's discord server but it should be fully explained here unless its a weird issue.

# this section is just a general tip you dont have to do this AT ALL but it has removed any fps drops for me

UNDERVOLTING sounds scary but it isnt. it reduces temp and can get you more performance out of your card. read an actual guide on how to do it

but the quick explanation is use msi after burner, look up what your reference base clocks are, and lower your core clock down while looking at the curve editor until it hits that clock, then at around 950voltage which seems to work for 90% of cards you raise it back up to your boost speeds, obviously you want to know what those are too. 

i do cap my fps anyways obviously if you are running unlimited there will be some drops, but im running no drops now while before i was from the same cap i had set previously.

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


If it is something else please ask someone else, everything I know goes into this guide.

