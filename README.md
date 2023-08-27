# A guide for [W-Okada's RealTimeVoiceChangerClient](https://github.com/w-okada/voice-changer/blob/master/README_en.md) and an overview of it's Settings
This guide is written by: [Yuna](https://discord.com/users/824922747423031359)

Anyone CAN DM me by clicking my name to be direct linked to my discord account; 

@YunaOneeChan

If you have any new information specifically Mac based ones, I.E. settings that have worked for you, please dm me so it can be added to the guide, so we can all have something that works together.

# Other Links
[Original Guide](https://docs.google.com/document/d/11eofqJXiHiVsLt_JjCwHROt_0OSryPFb1toyDBuLoXc/edit ) I consider this as OUTDATED now, but it does have some useful things like how to set up Voicemeeters Virtual Cable.

[Antasma's Error Fixes](https://docs.google.com/document/d/e/2PACX-1vQIwJ3MVidhgEaXwWFl0xpVonVOVfneaNVADd7-NMWFgPIsfWWhG8NNqzQMsXDIOGlBIfxscoIm2_6I/pub)

Anything below this are just cool tech, I will not help with, you can create posts on the Github pages it links to.

[SociallyIneptWeeb's AI Cover Gen](https://github.com/SociallyIneptWeeb/AICoverGen)

[Sharmah's Realtime Translator & Subtitler](https://github.com/Sharrnah/whispering-ui)

[0Xiaohei0's Realtime Voice Converter EN to JP](https://github.com/0Xiaohei0/VoiceToJapanese)

# Quick Navigation click any blue text to jump

[Quick Settings](https://github.com/YunaOneeChan/Voice-Changer-Settings#tldr-tweak-afterwards-there-is-no-perfect-settings)

[Virtual Cables](https://github.com/YunaOneeChan/Voice-Changer-Settings#virtual-cables)

[What Version to Download](https://github.com/YunaOneeChan/Voice-Changer-Settings#what-version-to-download)

[Updating](https://github.com/YunaOneeChan/Voice-Changer-Settings#updating)

[Starting Out](https://github.com/YunaOneeChan/Voice-Changer-Settings#starting-out)

[Tune & Index Explanation](https://github.com/YunaOneeChan/Voice-Changer-Settings#tune-and-index)

[Chunk, Extra, & F0](https://github.com/YunaOneeChan/Voice-Changer-Settings#chunk-extra--f0)

[Graphics Card Troubleshooting](https://github.com/YunaOneeChan/Voice-Changer-Settings#graphics-card-not-showing-up-or-not-being-utilized)

[Audio](https://github.com/YunaOneeChan/Voice-Changer-Settings#audio)

[Advanced Settings](https://github.com/YunaOneeChan/Voice-Changer-Settings#advanced-settings)

[Audiodg Optimizations](https://github.com/YunaOneeChan/Voice-Changer-Settings#audiodgexe-optimizations)

[Using Elsewhere](https://github.com/YunaOneeChan/Voice-Changer-Settings#using-the-voicechanger-elsewhere)

[Noise Suppression](https://github.com/YunaOneeChan/Voice-Changer-Settings#noise-suppression)

[Model Deletion & Updating](https://github.com/YunaOneeChan/Voice-Changer-Settings#noise-suppression)

[Testing](https://github.com/YunaOneeChan/Voice-Changer-Settings#testing)

[Discord Settings](https://github.com/YunaOneeChan/Voice-Changer-Settings#discord-settings)

[Launching on Mac](https://github.com/YunaOneeChan/Voice-Changer-Settings#opening-on-mac)

[Undervolting for Gamers](https://github.com/YunaOneeChan/Voice-Changer-Settings#the-gamers)

# TLDR tweak afterwards, there is no "PERFECT" settings

Gain is personal preference but lowering input also reduces any extra background noise leakage that you may happen to have even with a Noise Suppressed Mic.

Crepe_Tiny is the lightest good sounding one within 1% of dio so you can probably ignore but it stays for now, next best being RMVPE (onnx if AMD/IntelArc), you can now ignore CREPE_FULL in it's entirety. 

quick explanation in dummy terms + quick link to advanced settings
* First Option / Second Option
* Lowest - Highest
* [ADVANCED SETTINGS](https://github.com/YunaOneeChan/Voice-Changer-Settings#advanced-settings)

NVIDIA: f0-RMVPE/CREPE_TINY,Chunk 112,Extra4096-16384,Tune Voice dependant but range is -12 to +12,Index 0 or 1,Gain In0.7 Out1.4,Model type any

![Nvidia](https://github.com/YunaOneeChan/Voice-Changer-Settings/blob/main/Quick%20Settings%20Images/Nvidia%20Settings.png)


AMD/INTEL: f0-RMVPE_ONNX/CREPE_TINY,Chunk 112,Extra4096-16384,Tune Voice dependant but range is -12 to +12,Index 0 or 1,Gain In0.7 Out1.4,Model type ONNX

![Amd/Intel ARC](https://github.com/YunaOneeChan/Voice-Changer-Settings/blob/main/Quick%20Settings%20Images/AMD_ARC_Settings.png)


CPU: f0-Dio/Harvest,Chunk 448,Extra4096-8192,Tune Voice dependant but range is -12 to +12,Index 0 or 1,Gain In0.7 Out1.4,Model type any

![CPUl](https://github.com/YunaOneeChan/Voice-Changer-Settings/blob/main/Quick%20Settings%20Images/reCPU%20settings.png)

Colab NO INDEX: f0-RMVPE_ONNX,Chunk 96 is the lowest you can go,Extra16384,Tune Voice dependant but range is -12 to +12,Index 0-1,Gain In0.7 Out1.4,Model type PTH, no idea why ONNX is performing worse for me but you can try it out yourself. 

Colab WITH INDEX: f0-RMVPE_ONNX,Chunk 112 is the lowest you can go,Extra8192,Tune Voice dependant but range is -12 to +12,Index 0-1,Gain In0.7 Out1.4,Model type PTH, no idea why ONNX is performing worse for me but you can try it out yourself. 

Please follow the dark mode screenshot for [Advanced Settings](https://github.com/YunaOneeChan/Voice-Changer-Settings#advanced-settings), it's what you would run on a DUAL PC setup and Colab

Screenshots are, NOT Using Index TOP, Using Index BOTTOM

![Colab](https://github.com/YunaOneeChan/Voice-Changer-Settings/blob/main/Quick%20Settings%20Images/Colab_No_Index.png)
![Colab](https://github.com/YunaOneeChan/Voice-Changer-Settings/blob/main/Quick%20Settings%20Images/Colab_Index.png)

M1 Mac(WIP Section): f0-Harvest/RMVPE_ONNX/CREPE_TINY,Chunk 448,Extra 131072 maybe 65536,Tune Voice dependant but range is -12 to +12,Index 0 or 1,Gain In0.7 Out1.4,Model type PTH, ONNX seems to have infinite res gaining bug as of August 17th, 2023.

If you are a Mac user please ADD and DM me with what Mac you have and what settings you have got working so this can be complete @YunaOneeChan

![Mac](https://github.com/YunaOneeChan/Voice-Changer-Settings/blob/main/Quick%20Settings%20Images/Mac%20Settings.png)



Input: Noise Suppressed Mic (ideally sonar or NVIDIA/AMD's noise suppression if CLIENT audio)

Output: Virtual Cable (Line 1 or VB-Audio Virtual Cable INPUT)

Monitor: Headphones

Monitor Gain 0.5 (this is personal preference if you plan on monitoring to see if it's working, you would want something quieter so you don't get tripped up from hearing what you said repeated back)

Passthru GREEN for working voicechanger, Passthru RED for normal mic



# Virtual Cables

Recommended: [VAC (Virtual-Audio-Cable by Muzychenko)](https://software.muzychenko.net/freeware/vac470lite.zip) - this virtual cable is called Line 1 on In/Output 

[Voicemeeter](https://vb-audio.com/Cable/) - this virtual cable is the voicemeeter one, Input is called VB Cable Output, while output is reveresed.

Mac only cable [Blackhole Virtual Audio Cable](https://existential.audio/blackhole/), But [Voicemeeter](https://vb-audio.com/Cable/) one works as well

# What Version to Download

What do I download? Don't worry I made this simple, just click either Latest or Stable depending on your Graphics card.

If you don't have at least 4gb of VRAM I would highly recommend just going with the Colab Version, as it will definitely run better. 

The First Link of all sections will be the LATEST, the second link will be the MOST STABLE until further testing is done.

A) NVIDIA/CPU - [Version 13 latest](https://huggingface.co/wok000/vcclient000/resolve/main/MMVCServerSIO_win_onnxgpu-cuda_v.1.5.3.13.zip) or [Version 12 stable](https://huggingface.co/wok000/vcclient000/blob/main/MMVCServerSIO_win_onnxgpu-cuda_v.1.5.3.12.zip)

B) AMD or INTEL ARC - [Version 13 directml](https://huggingface.co/wok000/vcclient000/resolve/main/MMVCServerSIO_win_onnxdirectML-cuda_v.1.5.3.13.zip) or [Version 12 directml](https://huggingface.co/wok000/vcclient000/blob/main/MMVCServerSIO_win_onnxdirectML-cuda_v.1.5.3.12.zip)

note the directml version is EXPERIMENTAL, if it doesn't fully work that is why, just check if your GPU supports onnxruntime, if it does you are extremely likely to be able to use this.

C) [Colab version](https://colab.research.google.com/github/w-okada/voice-changer/blob/master/Realtime_Voice_Changer_on_Colab.ipynb) EXTREMELY good now, 400ms of latency without index, comparable to using NVIDIA, if you added it to your Drive, you have to delete and the files it makes and redownload them to update as far as I can tell.

D) MAC - [Version 13 Mac](https://huggingface.co/wok000/vcclient000/resolve/main/MMVCServerSIO_mac_onnxcpu-nocuda_v.1.5.3.13.zip) or [Version 12 Mac](https://huggingface.co/wok000/vcclient000/blob/main/MMVCServerSIO_mac_onnxcpu-nocuda_v.1.5.3.12.zip)

Mac users please DM if you find any better settings, as I only found one person with one so far and that was his.

# Updating

When updating delete everything EXCEPT the following

* model_dir folder
* your shortcut to start_http.bat
* VBS script if you made it to have no cmd prompt appear.

Just remember to change your extra, chunk, and audio settings back to one value higher than revert as sometimes it'll display the wrong values.

Yes, this also includes the S.R. for server mode if you are using it.


# Starting Out

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

AMD/Intel: You have 2 options for this CREPE_TINY and RMVPE, you still need to use ONNX models

CPU: DIO or Harvest, nothing else matters for you.


# Graphics Card not showing up, or not being utilized

IF your GPU is not showing and you have an NVidia Graphics card make sure you have the [NVIDIA Cuda Toolkit drivers](https://developer.nvidia.com/cuda-downloads) 

NVIDIA owners, CUDA core usage does not appear on Task Manager usage normally, if you have your GPU selected it is being used, depending on your settings it'll be around 40% of your VRAM, other times it'll sometimes show up even if it's not actually meant to

For AMD&Intel you need to use the correct F0, as well as export your Model to ONNX, and reupload it as the ONNX file.

Yes the program will still use your CPU, that's just how things work. The Extra Value is basically adding CPU usage for you.

# Audio
What to pick

Server Mode : this is the option I recommend everyone to pick, it is faster and doesnt try to get reprocessed again, and you get to pick the driver you use

Client Mode : this mode is slower than server mode by 40ms total, it also uses the "Chrome Browser" version of your mic, so if you use something like EQAPO (explained later) it won't register the changes you did, or if you are using a DUAL computer setup or Colab you then have to use this.

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

# Advanced Settings

These are my Advanced Settings, feel free to copy them, but I really don't advise changing them that much unless you know what you are doing. Sometimes I change Trancate back to 100. Either screenshot is fine, but bottom one is definitely more so towards dual PC, but still works extremely well on a single one.

![Screenshot](https://github.com/YunaOneeChan/Voice-Changer-Settings/blob/main/Quick%20Settings%20Images/My%20Advanced%20Settings.png)

![Screenshot2](https://github.com/YunaOneeChan/Voice-Changer-Settings/blob/main/Quick%20Settings%20Images/Advancedv2.png)

# Audiodg.exe Optimizations

open task manager hit details

right click audiodg.exe and set Priority to HIGH

right click it again and press set affinity and only have CPU 2 picked.

as for the single cpu core an even number as thats your real cpu core, so in my case i use 2 since i dont want it running on cpu 0 this is just my preference and what has always worked for me.

This gets rid of any potential static happening as you are forcing it only use one core so it's not getting any lag from jumping between different ones, on all cores and its cycling through as it normally does, it produces crackles, static, etc. when its this way at extremely low latency.

if you get [ProcessLasso](https://bitsum.com) you can make the audiodg.exe setting continuously reapply every boot, otherwise you have to do it yourself every single time,

# Using the voicechanger elsewhere
To use on any other APP, your INPUT for that game or application will be

Your [virtal audio cable](https://github.com/YunaOneeChan/Voice-Changer-Settings#virtual-cables)

your output device does not change at all it stays your normal headphones or speakers

in the voice changer like it was said previously will have to select it as output or monitor to be outputting sound into it.

very very easy.

You can refer to the Discord Settings section to see an image of what it would look like for any app you would want to use it on.

# Noise Suppression
Yes this removes the voice model speaking on its own, as long as you pick any option it will just work, the 4th one however only works in server mode, the rest work on Client and Server.

You are going to need Audio Suppression of some kind if you have constant background noise on your normal microphone. Just pick one below, I will list four options

[NVIDIA Broadcast](https://www.nvidia.com/en-us/geforce/broadcasting/broadcast-app/) can work extremely well however on system reboots if you dont configure its defaults seperately from everything else it can just pick the virtual cable as its mic and not work. (to do so open sound settings, and scroll until you can press app volume and device preferences, find the input box for this application and press your actual microphone this fixes any issues with the voice changer breaking from my testing)

AMD Noise Suppression (this just appears in your amd driver software afaik) can also work but it lowers your audio quality a fair amount depending on the level of background noise bleed, too high of a sample rate will not work, you need 48000 afaik.

Recommended Method: [Steelseries Sonar](https://steelseries.com/gg/sonar) this is the one I used to use, has Clearcast built into it which is a really good noise suppression, its not as good as Broadcasts but still way better than AMD's version anyone should be able to use it even if your system was built by the Obama Administration who fucked our school lunches by making it significantly worse quality

Final Method: Do not use if you use Client Mode 

VST Plugins injected into your mic [Werman's RN Noise removal](https://github.com/werman/noise-suppression-for-voice) or [Goyo's AI Voice Seperator](https://goyo.app), using [Equalizer APO](https://sourceforge.net/projects/equalizerapo/). 

^ these plugins are kinda intensive for older hardware so do the more optimized version farther down using reaplugs and atkexpander. all of this is completely free, you just got to figure out your own settings for it all. If you are a nice individual ill coach you through the entire thing but probably not #toolazy


In my opinion putting the VST's that you get from Werman RN Noise or the installer of Goyo into this folder C:\Program Files\EqualizerAPO\VSTPlugins is far easier as your first time going to select a plugin will throw it there. Just remember when setting it up your chain will go as follows for APO, Device-your mic, any other plugins you want like preamp which is just gain control minus20 to positive20db, and finally the rn noise plugin, there will be a folder at the top called WermanSettings to show what i recommend as well as a voice clip showing off and on.

Stereo was the only one that worked for me on Werman but it uses more resources (hard to tell), if Mono works, use that as its far more efficient. Goyo works on mono & stereo for me. 

Now the SAFEST way of using EQAPO, you will get [REAPLUGS](https://www.reaper.fm/reaplugs/), and you will get an expander I use [ATKEXPANDER](https://www.kvraudio.com/product/atkexpander-by-matthieu-brucher) in this screenshot

![APO](https://github.com/YunaOneeChan/Voice-Changer-Settings/blob/main/WermanSettings/safe%20noise%20reduction.png)

You will have to manually edit your settings yourself as I do not show it, but there are guides on how to do that, you just have to look around yourself. This screenshot is a very efficient way of doing it with GAIN STAGING.

DISCLAIMER: GOYO IS CPU INTENSIVE AND CAN CAUSE SOUND BREAKING ON YOUR SYSTEM, RN NOISE IS THE FAR SAFER OPTION BUT EVEN THAT CAN DO THE SAME THING, IT IS HIGHLY RECOMMENDED THAT YOU JUST USE SONAR INSTEAD

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

Please refer to Okada's documentation as it will have more on it, this is just how to get it opened. 


# The Gamers

UNDERVOLTING sounds scary but it isnt. it reduces temp and can get you more performance out of your card. read an actual guide on how to do it

but the quick explanation is use msi after burner, look up what your reference base clocks are, and lower your core clock down while looking at the curve editor until it hits that clock, then at around 950voltage which seems to work for 90% of cards you raise it back up to your boost speeds, obviously you want to know what those are too. 

i do cap my fps anyways obviously if you are running unlimited there will be some drops, but im running no drops now while before i was from the same cap i had set previously.

-------------------------------------
# Heres a Guide on how to make your normal mic sound better using Equalizer APO

https://github.com/YunaOneeChan/Sounding-Good-With-APO

It's very basic currently and doesn't cover the actual EQ part of it, but it gives a general use template, with only two things you change yourself. One is for removing a ton of background noise, the other is the actual eq part as every voice is different.
