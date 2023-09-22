# A guide for [W-Okada's RealTimeVoiceChangerClient](https://github.com/w-okada/voice-changer/blob/master/README_en.md) and an overview of it's Settings
This guide is written by: [Raven](https://discord.com/users/824922747423031359)

Anyone CAN DM me by clicking my name to be direct linked to my discord account; 

[@ravencutie21](https://discord.com/users/824922747423031359)

If you have any new information specifically Mac based ones, I.E. settings that have worked for you, please dm me so it can be added to the guide, so we can all have something that works together.

# Other Links
[Original Guide](https://docs.google.com/document/d/11eofqJXiHiVsLt_JjCwHROt_0OSryPFb1toyDBuLoXc/edit ) I consider this as OUTDATED now, but it does have some useful things like how to set up Voicemeeters Virtual Cable.

[Antasma's Error Fixes](https://docs.google.com/document/d/e/2PACX-1vQIwJ3MVidhgEaXwWFl0xpVonVOVfneaNVADd7-NMWFgPIsfWWhG8NNqzQMsXDIOGlBIfxscoIm2_6I/pub)

Anything below this are just cool tech, I will not help with, you can create posts on the Github pages it links to.

[SociallyIneptWeeb's AI Cover Gen](https://github.com/SociallyIneptWeeb/AICoverGen)

[Sharmah's Realtime Translator & Subtitler](https://github.com/Sharrnah/whispering-ui)

[0Xiaohei0's Realtime Voice Converter EN to JP](https://github.com/0Xiaohei0/VoiceToJapanese)

# Quick Navigation click any blue text to jump

[Quick Settings](https://github.com/YunaOneeChan/Voice-Changer-Settings/tree/main#tldr-there-are-no-perfect-settings)

[Virtual Cables](https://github.com/YunaOneeChan/Voice-Changer-Settings#virtual-cables)

[What Version to Download](https://github.com/YunaOneeChan/Voice-Changer-Settings#what-version-to-download)

[Updating](https://github.com/OneeChan/Voice-Changer-Settings#updating)

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

# TLDR there are no "PERFECT" settings

My Settings with a 3070 are as follows : 0.7in gain, 2.5out gain, sup2 box checked, rmvpe, s.thresh 0.00025, 96 chunk, 16384 extra, client, sonar mic, line 1, sonar chat, 0.1gain for monitor, advanced REST, 0.2-0.8, 300 trancate, off silencefront, 0.5 protect, low rvc qual, skip passthru confirm no, with audiodg.exe stuff in its own section, my audio peaks at -12db, below are what i recommend for everyone else.
* Just Use Client Mode, the only benefit server mode is slightly lower latency, client mode is just significantly easier to get set up

quick explanation in dummy terms + quick link to advanced settings
* First Option / Second Option
* Lowest - Highest
* [ADVANCED SETTINGS](https://github.com/YunaOneeChan/Voice-Changer-Settings#advanced-settings)

Same for everyone
* Tune is Voice dependant but range is usually -12 to +12
* Index 0 is ideal until bug is fixed with 3-5x cpu usage, 
* You don't have to touch gain stuff, but try aiming for your normal mic in OBS to be in the range of -23db to -10db when talking normally, if its not then raise gain a bit in the voice changer. you dont need to crank it at all the way up. If it is, and you are bleeding a bit of noise still even after noise suppression do 0.7in and 1.4out. 98% of normal volume but should remove the rest of the noise
* You want to have this on an SSD or an NVME drive, you also want to have a good CPU as this is actually the main bottleneck after not having enough vram. if you are atleast 8gb of vram you are find to use this while playing games.
* If you want this on another drive, use SYMLINK and put it on your C Drive so it doesn't error out.

NVIDIA: f0-RMVPE/CREPE_TINY, Chunk 112, Extra4096-16384, Model type any

![Nvidia](https://github.com/YunaOneeChan/Voice-Changer-Settings/blob/main/Quick%20Settings%20Images/Nvidia%20Settings.png)


AMD/INTEL: f0-RMVPE_ONNX/CREPE_TINY,Chunk 112,Extra4096-16384, Model type ONNX

![Amd/Intel ARC](https://github.com/YunaOneeChan/Voice-Changer-Settings/blob/main/Quick%20Settings%20Images/AMD_ARC_Settings.png)


CPU: f0-Dio/Harvest, Chunk 448, Extra4096-8192, Model type any

![CPUl](https://github.com/YunaOneeChan/Voice-Changer-Settings/blob/main/Quick%20Settings%20Images/reCPU%20settings.png)

Colab NO INDEX & Kaggle (t4) : f0-RMVPE_ONNX, Chunk 96 is the lowest you can go,Extra16384, Model type PTH

Colab WITH INDEX & Kaggle (t4) : Chunk 112 is the lowest you can go, Extra8192

Please follow the dark mode screenshot for [Advanced Settings](https://github.com/YunaOneeChan/Voice-Changer-Settings#advanced-settings), it's what you would run on a DUAL PC setup and Colab

Screenshots are, NOT Using Index TOP, Using Index BOTTOM

![Colab](https://github.com/YunaOneeChan/Voice-Changer-Settings/blob/main/Quick%20Settings%20Images/Colab_No_Index.png)
![Colab](https://github.com/YunaOneeChan/Voice-Changer-Settings/blob/main/Quick%20Settings%20Images/Colab_Index.png)

Using Kaggle means you have 30 hours PER WEEK, of Gpu usage, it runs even when it is NOT being used, so remember to unselect it when you are done using it.

Kaggle P100 GPU : f0-RMVPE_ONNX, Chunk 48 is the lowest you can go if no index but 64 is preferred since you never need to change, Extra8192, any model works

![Kaggle](https://github.com/YunaOneeChan/Voice-Changer-Settings/blob/main/Quick%20Settings%20Images/kagglep100.png)

M1 Mac(WIP Section): f0-Harvest/RMVPE_ONNX/CREPE_TINY, Chunk 448,Extra 131072 maybe 65536, Model type PTH, ONNX seems to have infinite res gaining bug as of August 17th, 2023.

If you are a Mac user please ADD and DM me with what Mac you have and what settings you have got working so this can be complete [@ravencutie21](https://discord.com/users/824922747423031359)

![Mac](https://github.com/YunaOneeChan/Voice-Changer-Settings/blob/main/Quick%20Settings%20Images/Mac%20Settings.png)

M2 Max Mac (also wip): f0-RMVPE/RMVPE_ONNX/CREPE_TINY, Chunk 256, Extra 65536, model type PTH

![Mac2](https://github.com/YunaOneeChan/Voice-Changer-Settings/blob/main/Quick%20Settings%20Images/m2max%20mac.png)

Voice changer settings for audio
* Just use Client Mode it's far easier to set up, no think monke brain, but Server settings are listed as well if you do want the lower latency.


CLIENT:
* Input: Your Microphone
* Output: Virtual Cable (Line 1 or VB-Audio Virtual Cable INPUT)
* Monitor: Headphones
* Monitor Gain 0.3 (this is personal preference)
* feel free to turn on SUP2 box above f0 det if you do have a little background noise, sup1 and echo don't need to be used at all, sup2 is just better:tm:
* set your S. Threshhold to be something low 1/4th of the bar is fine.


Server
* S.R. match this to your windows sample rate otherwise no audio gets produced (if Sonar its 48000)
* Input: Your Noise Supressed Microphone (Windows WASAPI Steelseries Sonar Mic) (MME Broadcast or MME AMD mic)
* Output: Virtual Cable (Line 1 or VB-Audio Virtual Cable INPUT) (match with driver from above
* Monitor: Headphones (match with driver from above again, if using sonar, use CHAT here)
* Monitor Gain 0.2 (this is personal preference)



Anywhere else that you want to use the voice changer 

* Input: Virtual Cable, on some older games you may need to set your default in the windows sound settings to be the virtual cable, like TF2 for example.
* Output: your headphones.

If your audio is crackling everywhere refer to : [Audiodg Optimizations](https://github.com/YunaOneeChan/Voice-Changer-Settings#audiodgexe-optimizations)

If your audio is only crackling in discord refer to : [Discord Settings](https://github.com/YunaOneeChan/Voice-Changer-Settings#discord-settings)


Passthru GREEN for working voicechanger, Passthru RED for normal mic

### Don't use Okada's voice changer? No problem I'll quickly explain what to do and not to do on RVC's version of it.

* Select your PTH and Index, you do not need to use ONNX at all here for anyone AFAIK. 
* Choose your Input and Output device, use MME, as I could not get anything else to work for whatever reason, but it's fine as MME should work for everyone
* Respone Threshhold, Set it to -60 all the way up to -50, everyone should trigger it at -60 with normal talking
* Pitch settings, this is where you adjust based on your voice, find whatever you want
* Wao an Index slider? That actually doesn't have a bug? Use whatever you like here.
* Loudness factor, this is Gain Control, if you do not see it that's because you are using the old prebuilt binary from 0813, install it manually and you'll see it.
* Sample Length this is similar to chunk in Okada's. Add a 0 to the end of whatever you pick and that's what it is in MS, play around with this while testing in audacity (when you adjust it you'll need to hit start conversion again)
* Number of CPU processes can be skipped as you should be using RMVPE, but if you are a psycho you can use harvest and play around with this
* Fade Length, I could not find out what this does, by default its on 0.04, or on the prebuilt its 0.15, so use that as a range and I guess figure out what you think sounds or works the best.
* Extra Inference time, this is basically Extra, but it's also a fall back in case you randomly get a massive load on GPU, it'll be the maximum time it'll take, by Default its 2.00, What i picked is 3.45, and it's also what a lot of AMD users pick in the CN and JP communities, but generally if you have an old card like 1600series or older, use 2.00, if its newer than that 3.00 is fine.
* Input Noise Reduction, Please DO NOT use this, it seems to be bugged when building yourself and causes audio to slowly get quieter and quieter.
* Output Noise Reduction on the other hand is actually fine to use if you want to, It really doesn't make a difference at the end of the day.

# Virtual Cables

Recommended: [VAC (Virtual-Audio-Cable by Muzychenko)](https://software.muzychenko.net/freeware/vac470lite.zip) - this virtual cable is called Line 1 on In/Output 

[Voicemeeter](https://vb-audio.com/Cable/) - this virtual cable is the voicemeeter one, Input is called VB Cable Output, while output is reveresed.

Mac only cable [Blackhole Virtual Audio Cable](https://existential.audio/blackhole/), But [Voicemeeter](https://vb-audio.com/Cable/) one works as well

# What Version to Download

What do I download? Don't worry I made this simple, just click either Latest or Stable depending on your Graphics card.

If you don't have at least 4gb of VRAM I would highly recommend just going with the Colab Version, as it will definitely run better. 

The First Link of all sections will be the LATEST STABLE, the second link will be if the first is buggy for you

A) NVIDIA/CPU - [Version 13 gpu-cuda](https://huggingface.co/wok000/vcclient000/resolve/main/MMVCServerSIO_win_onnxgpu-cuda_v.1.5.3.13.zip) or [Version 12 gpu-cuda](https://huggingface.co/wok000/vcclient000/blob/main/MMVCServerSIO_win_onnxgpu-cuda_v.1.5.3.12.zip)

B) AMD or INTEL ARC - [Version 13 directml](https://huggingface.co/wok000/vcclient000/resolve/main/MMVCServerSIO_win_onnxdirectML-cuda_v.1.5.3.13.zip) or [Version 12 directml](https://huggingface.co/wok000/vcclient000/blob/main/MMVCServerSIO_win_onnxdirectML-cuda_v.1.5.3.12.zip)

note the directml version is EXPERIMENTAL, if it doesn't fully work that is why, just check if your GPU supports onnxruntime, if it does you are extremely likely to be able to use this.

C1) [Colab version](https://colab.research.google.com/github/w-okada/voice-changer/blob/master/Realtime_Voice_Changer_on_Colab.ipynb) EXTREMELY good now, 400ms of latency without index, comparable to using NVIDIA, if you added it to your Drive, you have to delete and the files it makes and redownload them to update as far as I can tell.

C2) [Kaggle Version](https://www.kaggle.com/code/rafacasari/wokada-voice-changer) same as colab just somewhere else if using T4s, Even better if you use P100. P100 = 200ms of latency, T4 = 400ms due to different chunks. Kaggle is limited to 30 hours of GPU usage PER week, remember to unselect the GPU after you are done otherwise it will still use your time.

D) MAC - [Version 13 Mac](https://huggingface.co/wok000/vcclient000/resolve/main/MMVCServerSIO_mac_onnxcpu-nocuda_v.1.5.3.13.zip) or [Version 12 Mac](https://huggingface.co/wok000/vcclient000/blob/main/MMVCServerSIO_mac_onnxcpu-nocuda_v.1.5.3.12.zip)

E) Intel Mac users - unsupported refer to C

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

* win10: In the folder where start_http.bat is press "control+L" type "cmd" press "enter" (if this doesnt open a CMD with the path of your folder showing, use the cd command to navigate to that folder) type "start_http.bat" press "enter"
* win11: right click anywhere in folder you should see "Open in Terminal" press it, type "start_http.bat" 

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

Silence front turned off for Dark Mode SS, it auto turns back on which is dumb, but thats how it is

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
















# Common GPU Chart for known working settings > WIP
### these are not perfect, as it depends on what you are doing but should give you something that just works right away.
If your GPU is not listed start with this if its a Newer Card aka released in the Last 4 years and has atleast 8gb of Vram
Chunk: 96, Extra, 16384
If you have less then 8gb of vram and your card is older than 4 years use this, 4gb is the minimum you should have.
Chunk: 192, Extra 8192

AMD
500 series cards - 256+ Chunk 8192 Extra
580 - 192+ Chunk 8192 Extra
6xxx XT cards - 128+ Chunk 16384 Extra
7xxx XT cards - 112+ Chunk 16384 Extra


NVIDIA 8gb+
Any 40 series card - 96+ Chunk 16384 Extra
Any 30 series card - 96+ Chunk 16384 Extra
Any 20 series card - 128+ Chunk 8192 Extra
Any 10 series card - 128+ Chunk 8192 Extra
Any 16 series card - 128+ Chunk 8192 Extra

NVIDIA 4gb+
256+ Chunk 8192 Extra

Laptop Variant Cards, refer to the previous gen of desktop in the chart above.
