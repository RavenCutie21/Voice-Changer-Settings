# A guide for [W-Okada's RealTimeVoiceChangerClient](https://github.com/w-okada/voice-changer/blob/master/README_en.md) and an overview of it's Settings
This guide is written by: [Yuna](https://discord.com/users/824922747423031359)

# Other Links
[Original Guide](https://docs.google.com/document/d/11eofqJXiHiVsLt_JjCwHROt_0OSryPFb1toyDBuLoXc/edit )

[Antasma's Error Fixes](https://docs.google.com/document/d/e/2PACX-1vQIwJ3MVidhgEaXwWFl0xpVonVOVfneaNVADd7-NMWFgPIsfWWhG8NNqzQMsXDIOGlBIfxscoIm2_6I/pub)

Anything below this are just cool tech, I will not help with, you can create posts on the Github pages it links to.

[SociallyIneptWeeb's AI Cover Gen](https://github.com/SociallyIneptWeeb/AICoverGen)

[Sharmah's Realtime Translator & Subtitler](https://github.com/Sharrnah/whispering-ui)

[0Xiaohei0's Realtime Voice Converter EN to JP](https://github.com/0Xiaohei0/VoiceToJapanese)

# Quick Navigation click any blue text to jump

[Quick Settings](https://github.com/YunaOneeChan/Voice-Changer-Settings#tldr-tweak-afterwards-there-is-no-perfect-settings)

[Virtual Cables](https://github.com/YunaOneeChan/Voice-Changer-Settings/tree/main#virtual-cables)

[What Version to Download](https://github.com/YunaOneeChan/Voice-Changer-Settings/tree/main#what-version)

[Before Starting](https://github.com/YunaOneeChan/Voice-Changer-Settings/tree/main#before-starting)

[Tune & Index Explanation](https://github.com/YunaOneeChan/Voice-Changer-Settings/tree/main#tune-and-index)

[Chunk, Extra, & F0](https://github.com/YunaOneeChan/Voice-Changer-Settings/tree/main#chunk-extra--f0)

[Graphics Card Troubleshooting](https://github.com/YunaOneeChan/Voice-Changer-Settings/tree/main#graphics-card-not-showing-up-or-not-being-utilized)

[Audio](https://github.com/YunaOneeChan/Voice-Changer-Settings/tree/main#audio)

[Audiodg Optimizations](https://github.com/YunaOneeChan/Voice-Changer-Settings/tree/main#audiodgexe-optimizations)

[Using Elsewhere](https://github.com/YunaOneeChan/Voice-Changer-Settings/tree/main#using-the-voicechanger-elsewhere)

[Noise Suppression](https://github.com/YunaOneeChan/Voice-Changer-Settings/tree/main#noise-suppression)

[Model Deletion & Updating](https://github.com/YunaOneeChan/Voice-Changer-Settings/tree/main#noise-suppression)

[Testing](https://github.com/YunaOneeChan/Voice-Changer-Settings/tree/main#testing)

[Discord Settings](https://github.com/YunaOneeChan/Voice-Changer-Settings/tree/main#discord-settings)

[Launching on Mac](https://github.com/YunaOneeChan/Voice-Changer-Settings/tree/main#opening-on-mac)

[Undervolting for Gamers](https://github.com/YunaOneeChan/Voice-Changer-Settings/tree/main#the-gamers)

# TLDR tweak afterwards, there is no "PERFECT" settings

Gain is personal preference but lowering input also reduces any extra background noise leakage that you may happen to have even with a Noise Suppressed Mic.

Crepe_Tiny is the lightest good sounding one within 1% of dio so you can probably ignore but it stays for now, next best being RMVPE, you can now ignore CREPE_FULL in it's entirety. 

NVIDIA: f0-RMVPE/CREPE_TINY,Chunk 112,Extra4096-16384,Tune Voice dependant but range is -12 to +12,Index 0 or 1,Gain In0.7 Out1.4,Model type any

![Nvidia](https://github.com/YunaOneeChan/Voice-Changer-Settings/blob/main/Quick%20Settings%20Images/Nvidia%20Settings.png)


AMD/INTEL: f0-CREPE_TINY/RMVPE,Chunk 112,Extra4096-16384,Tune Voice dependant but range is -12 to +12,Index 0 or 1,Gain In0.7 Out1.4,Model type ONNX

![Amd/Intel](https://github.com/YunaOneeChan/Voice-Changer-Settings/blob/main/Quick%20Settings%20Images/AMD%20and%20Intel%20GPU%20Settings.png)


CPU: f0-Harvest/Dio,Chunk 448,Extra8192,Tune Voice dependant but range is -12 to +12,Index 0 or 1,Gain In0.7 Out1.4,Model type any

![CPUl](https://github.com/YunaOneeChan/Voice-Changer-Settings/blob/main/Quick%20Settings%20Images/CPU%20settings.png)

Colab: f0-CREPE_TINY/RMVPE,Chunk MAXED,Extra4096,Tune Voice dependant but range is -12 to +12,Index 0 or 1,Gain In0.7 Out1.4,Model type any

![Colab](https://github.com/YunaOneeChan/Voice-Changer-Settings/blob/main/Quick%20Settings%20Images/Colab%20settings.png)

M1 Mac(WIP Section): f0-Harvest, I assume RMVPE should be fine due to previous results,Chunk 448,Extra 131072 maybe 65536,Tune Voice dependant but range is -12 to +12,Index 0 or 1,Gain In0.7 Out1.4,Model type PTH, ONNX seems to have infinite res gaining bug, atleast for the one user found using it.

![Mac](https://github.com/YunaOneeChan/Voice-Changer-Settings/blob/main/Quick%20Settings%20Images/Mac%20Settings.png)

Input: Noise Suppressed Mic

Output: Virtual Cable

Monitor: Headphones

Monitor Gain 0.5

Passthru GREEN = WORKING VOICE CHANGER

Passthru RED = NO MORE WORKING VOICE CHANGER



# Virtual Cables

Recommended: [VAC (Virtual-Audio-Cable by Muzychenko)](https://software.muzychenko.net/freeware/vac470lite.zip) - this virtual cable is called Line 1 on In/Output 

[Voicemeeter](https://vb-audio.com/Cable/) - this virtual cable is the voicemeeter one, Input is called VB Cable Output, while output is reveresed.

Mac only cable [Blackhole Virtual Audio Cable](https://existential.audio/blackhole/), But [Voicemeeter](https://vb-audio.com/Cable/) one works as well

# What Version

What do I download? Make sure to use HuggingFace and read the downloads, since it shows all 3 in one spot again, it appears in bottom left corner, with the full url of what you are about to click.

Links will update to the LATEST version every week.

A) NVIDIA/CPU - [onnxgpu-cuda](https://huggingface.co/wok000/vcclient000/resolve/main/MMVCServerSIO_win_onnxgpu-cuda_v.1.5.3.12a.zip)

B) AMD or INTEL ARC - [onnxdirectML version](https://huggingface.co/wok000/vcclient000/resolve/main/MMVCServerSIO_win_onnxdirectML-cuda_v.1.5.3.12a.zip) - do know that the DIRECTML version is EXPERIMENTAL, if it doesn't fully work that is why, just check if your GPU supports onnxruntime, if it does you are extremely likely to be able to use this.

C) [Collab version](https://github.com/w-okada/voice-changer/blob/master/Realtime_Voice_Changer_on_Colab.ipynb) still probably better than running on CPU, your settings are 2048 chunk 4096 extra crepe_tiny, anything else and it sucked really bad for me

D) MAC - [the only mac one obviously](https://huggingface.co/wok000/vcclient000/resolve/main/MMVCServerSIO_mac_onnxcpu-nocuda_v.1.5.3.12a.zip)

# Before Starting

You need to extract the MMVCServerSIO folder and put it somewhere else, ideally your Desktop, or the root of your Drive. 

Find your start_http.bat file, right click it and create a shortcut; Put that new shortcut on your desktop so you can easily access it.. if the cmd window instantly closes the next line is for you, else ignore it.

In the folder where start_http.bat is press "control+L" type "cmd" press "enter" (if this doesnt open a CMD with the path of your folder showing, use the cd command to navigate to that folder) type "start_http.bat" press "enter"

If it seems like its stuck at any point in the future when running click in the CMD window and press enter

This will install almost all dependencies and make the voice changer run, you will always open the file referrenced above to start the voice changer.

Nvidia users will have the onnxgpu-cuda version

If you have an AMD or Intel GPU you should have the onnxdirectML-cuda version of W-Okada's Realtime voice changer client installed. To tell the difference if you look at the GPU section, if theres a dropdown menu, thats the NVidia one, as of Version 11. If it says cpu, 0, 1, 2, 3, then you are on the AMD&Intel one. 

For AMD&Intel if you have more than One GPU in your rig, open your task manager (control+shift+escape) Press Performance, and you should see your GPU listed as GPU #, select the correct number for the GPU you want to use, otherwise leave it 0 if yo uhave only one card


# TUNE and index
Tune is voice dependant so female to male you want a - tune, female to female you ideally dont have to change anything but you might have to depending on how soft your voice is in comparison.

The same can be said for males but its just reversed from above where soft becomes deep

Index is only really beneficial if your Accent is HEAVY, or DOESN'T MATCH and you can't imitate the person's accent you want. But the cost is CPU usage, 300% more usage to be exact. I recommend using 0.


# Chunk, Extra, & F.0
Chunk, the lower this is the less latency you have for the voice to come out, but the lower the quality becomes each time, you find the one where it doesn't have any audio glitches, i.e. stuttering, repeating words, cutting in and out, or laggy

Extra start with 4096 while testing your chunk values, but this hold past data, to incraese stability even more, at the cost of more resources. The larger this value is the more resources it uses, I would say there is zero point in going higher than the 32768 value. when you increase this you can sometimes also get lower and lower chunk values while boosting clarity.

F.0, depending on what GPU you have or lack there of, depends on what you use here. 

Nvidia: Ideally you use RMVPE, but if you have an older card it can cause it to be laggy, so you refer to AMD/Intel

AMD/Intel: You ONLY have 2 options for this CREPE_FULL and CREPE_TINY, reason being you need to follow specific steps to make your GPU work unfortunately.

CPU: DIO or Harvest, nothing else matters for you.

What I would pick for AMD/INTEL and CPU, Crepe_Tiny or Dio as they are the lightweight ones meaning you should be able to run it at lower latencies.


# Graphics Card not showing up, or not being utilized

IF your GPU is not showing and you have an NVidia Graphics card make sure you have the [NVIDIA Cuda Toolkit drivers](https://developer.nvidia.com/cuda-downloads) 

NVIDIA owners, CUDA core usage does not appear on Task Manager usage normally, if you have your GPU selected it is being used, depending on your settings it'll be around 40% of your VRAM, other times it'll sometimes show up even if it's not actually meant to

For AMD&Intel you need to use the correct F0, as well as export your Model to ONNX, and reupload it as the ONNX file.

Yes the program will still use your CPU, that's just how things work. The Extra Value is basically adding CPU usage for you.

# Audio
What to pick

Server Mode : this is the option I recommend everyone to pick, it is faster and doesnt try to get reprocessed again, and you get to pick the driver you use

Client Mode : this mode is slower than server mode, it also uses the "Chrome Browser" version of accessing your mic, so if you use something like EQAPO (explained later) it won't register the changes you did, or if you are using a DUAL computer setup you then have to use it.

Sample Rate (S.R): Pick the sample rate of your audio devices in your windows sounds settings, to get there on windows 10 you right click the speakers icon in your task bar and hit sounds, on windows 11 you have to hit sound settings, then scroll to the bottom and hit advanced sound settings which would finally open the same window, they made it overly complicated for no reason.
44100 or 48000 are what you want to be using for most people. If you have good equipment like a Shure SM7B, it'll more likely be 192000 sample rate.

S. Threshhold: The minimum required sound for it to start converting audio, if you raise IN Gain at the top nothing you do here will matter. I have it set halfway but it's personal preference and doesn't really change much.

----------------------------------------------
You will need to have a Virtual Audio Cable now

When installing a virtual cable it will change your defaults for your window sounds settings, so you have to open the sounds panel and reselect your defaults back to your mic and headphones, hence why the one i recommended is still even better as itll offer to open it immediately.

Input : Choose (Windows Wasapi) on the first dropdown box, if it doesnt work when you do a sound test you will change this to (MME)

Second box for input: choose your Microphone, if you dont know what it is, when you were checking your sample rate it would have told you the name of the device.

Output : Make sure the first drop down matches the same as what you had from Input either being (Windows Wasapi) or (MME)

This is where you pick your Virtual Audio Cable from way earlier from the name's I said prior

Monitor : Same thing with the first drop down box as previously stated, but now you pick your headphones if you want to monitor audio.

There is a mini gain slider, that controls how loud you hear your voice, I recommend something subtle like 0.5 or less so you don't get tripped up when you talk.

# Audiodg.exe Optimizations

open task manager hit details

right click audiodg.exe and set Priority to HIGH

right click it again and press set affinity and only have CPU 2 picked.

as for the single cpu core an even number as thats your real cpu core, so in my case i use 2 since i dont want it running on cpu 0 this is just my preference and what has always worked for me.

This gets rid of any potential static happening as you are forcing it only use one core so it's not getting any lag from jumping between different ones, on all cores and its cycling through as it normally does, it produces crackles, static, etc. when its this way at extremely low latency.

if you get [ProcessLasso](https://bitsum.com) you can make the audiodg.exe setting continuously reapply every boot, otherwise you have to do it yourself every single time,

# Using the voicechanger elsewhere
To use on any other APP, your INPUT for that game or application will be

Your [virtal audio cable](https://github.com/YunaOneeChan/Voice-Changer-Settings/tree/main#virtual-cables), the one you selected previously in the audio section

your output device does not change at all it stays your normal headphones or speakers

very very easy.

# Noise Suppression
Yes this removes the voice model speaking on its own, as long as you pick any option it will just work, the 4th one however only works in server mode, the rest work on Client and Server.

You are going to need Audio Suppression of some kind if you have constant background noise on your normal microphone. Just pick one below, I will list four options

[NVIDIA Broadcast](https://www.nvidia.com/en-us/geforce/broadcasting/broadcast-app/) can work extremely well however on system reboots if you dont configure its defaults seperately from everything else it can just pick the virtual cable as its mic and not work. (to do so open sound settings, and scroll until you can press app volume and device preferences, find the input box for this application and press your actual microphone this fixes any issues with the voice changer breaking from my testing)

AMD Noise Suppression (this just appears in your amd driver software afaik) can also work but it lowers your audio quality a fair amount depending on the level of background noise bleed, too high of a sample rate will not work, you need 48000 afaik.

Recommended Method: [Steelseries Sonar](https://steelseries.com/gg/sonar) this is the one I used to use, has Clearcast built into it which is a really good noise suppression, its not as good as Broadcasts but still way better than AMD's version anyone should be able to use it even if your system was built by the Obama Administration who fucked our school lunches by making it significantly worse quality

Final Method: Do not use if you use Client Mode 

VST Plugins injected into your mic [Werman's RN Noise removal](https://github.com/werman/noise-suppression-for-voice) or [Goyo's AI Voice Seperator](https://goyo.app), using [Equalizer APO](https://sourceforge.net/projects/equalizerapo/). 

In my opinion putting the VST's that you get from Werman RN Noise or the installer of Goyo into this folder C:\Program Files\EqualizerAPO\VSTPlugins is far easier as your first time going to select a plugin will throw it there. Just remember when setting it up your chain will go as follows for APO, Device-your mic, any other plugins you want like preamp which is just gain control minus20 to positive20db, and finally the rn noise plugin, there will be a folder at the top called WermanSettings to show what i recommend as well as a voice clip showing off and on.

Stereo was the only one that worked for me on Werman but it uses more resources (hard to tell), if Mono works, use that as its far more efficient. Goyo works on mono & stereo for me. 

# model deletion and or updating
replacing a model does not delete it

yes it is possible to delete models, however not in the UI, you have to navigate to the folder called MODEL_DIR where your start_http.bat file is located, the mini sub folders inside of it starting from 0 ending at 199 (if you use the 200th slot 199 will appear) can just be deleted to remove a model. 

they will automatically remake themselves when you add a model in a slot that doesnt have a folder.

As a Just in case before updating backup the ENTIRE model_dir folder or move it else where, since it holds majority of settings, but it shouldn't get replaced when updating so you should be fine.


# Testing
While testing the only important thing to pay attention to are the Chunk/Extra. Just make sure you already changed your Tune and saved what you think sounds closest to the voice you are using.

You will do an audio test, if there is any sort of lag or stuttering that means your chunk is too low, or not using enough EXTRA, Ideally do not exceed 32768 extra as CPU resource usage is exponential from this setting

If it is perfectly clear you can try lowering your chunk more until you get an acceptable latency, else raise it

That's all you do in a loop there will be a point you can't proceed anymore and those are your perfect settings, unless you play something thats extremely intensive on your system then you have to tweak it a little bit.

# you do not need to proceed from this point on

Potentially lower Voice Changer client resource usage, its not by a lot but it still does something.
we can now delete that original shortcut you have, or don't if you are a rebel.

Open up notepad and paste the next three lines into the file, make sure the file is ONLY 3 lines.

-----------------------------------------------------

Set WshShell = CreateObject("WScript.Shell") 

WshShell.Run chr(34) & "C:\PATH\TO\MMVCServerSIO\start_http.bat" & Chr(34), 0

Set WshShell = Nothing

-----------------------------------------------------

change the Path to, part into the actual path to the start_http.bat file. its different for everyone depending on where you put it.

Save this file as a .vbs (refer to the VBS Image folder to see what the inside of the file will look like)

What this file does is make that black box aka CMD that always launches, not show up when you run this. itll save 1% cpu usage but 1% is still something
Sometimes itll be more depending on how much resources it was using in task manager, for me it was trying to use 30% which now it doesnt use anything.

ONLY do the VBS file if you have everything set up and dont plan on changing anything. this means you have no need to even look at the cmd window for errors as its already working perfectly for you

note: you should have the file inside of the MMVCServerSIO folder where the start_http.bat file is to make it work, you can then make a shortcut of this and put it anywhere you want, 

mine goes in the startup folder since i want it to be running the moment i turn my computer on. to do so press win+r, type startup, press enter if you want it to appear in your windows start menu go back on folder by clicking the programs section in the top bar, and put the file there, or just put it on your desktop.

# Congratulations you should have a working setup with some good optimizations!
any other stuff you have issues with ask [AI Hub's discord server](https://discord.gg/aihub) but it should be covered in this guide unless its a weird issue.

# Discord Settings
Reference images will be listed at the end for most of whats listed here

I am going to go through all of the Discord Voice & Video settings and tell you what you change for the voice changer to have the least problems.

Input Mode: Voice Activity, unless you want to Hold your PTT key longer than you are used to

Input sensitivity uncheck and manually set it to something like -75db or -65db

Echo Cancellation : Turn this off, when testing in voice & video it causes your voice to cut in and out, and its arguably useless anyways.

Noise Suppression : Standard or None. I prefer None since I do all of my own noise supression anyways.

Automatic Gain : Personal Preference but Off is what I prefer.

Audio Subsystem : for the least issues Legacy, otherwise just stick to Standard. It doesn't make that much of a difference

![One](https://github.com/YunaOneeChan/Voice-Changer-Settings/blob/main/Discord%20Settings/discord%20settings%201.png)
![Two](https://github.com/YunaOneeChan/Voice-Changer-Settings/blob/main/Discord%20Settings/discord%20settings%202.png)
![Three](https://github.com/YunaOneeChan/Voice-Changer-Settings/blob/main/Discord%20Settings/discord%20settings%203.png)


# Opening on Mac
One thing to know is INTEL Mac's DO NOT WORK AT ALL.

It is launched as follows.

Unzip the downloaded file.

Next, run MMVCServerSIO by hold down the control key and clicking it (or right-click to run it). If a message appears stating that the developer cannot be verified, run it again by holding down the control key and clicking it (or right-click to run it). The terminal will open and the process will finish within a few seconds.

Next, execute the startHTTP.command by holding down the control key and clicking on it (or you can also right-click to run it). If a message appears stating that the developer cannot be verified, repeat the process by holding down the control key and clicking on it (or perform a right-click to run it). A terminal will open, and the launch process will begin.

In other words, the key is to run both MMVCServerSIO and startHTTP.command. Moreover, you need to run MMVCServerSIO first.

[Or refer to this video slightly below this section it linkes you to in W-Okadas github page called m1_mac, It is probably outdated but its the only one i can find](https://github.com/w-okada/voice-changer/blob/master/README_en.md#software-signing)


# The Gamers

UNDERVOLTING sounds scary but it isnt. it reduces temp and can get you more performance out of your card. read an actual guide on how to do it

but the quick explanation is use msi after burner, look up what your reference base clocks are, and lower your core clock down while looking at the curve editor until it hits that clock, then at around 950voltage which seems to work for 90% of cards you raise it back up to your boost speeds, obviously you want to know what those are too. 

i do cap my fps anyways obviously if you are running unlimited there will be some drops, but im running no drops now while before i was from the same cap i had set previously.

