# Welcome
<div align="center">
<img height="250" alt="logo" src="https://github.com/user-attachments/assets/a3ef47b8-0ed0-4e5a-b1c4-dd259e74dd2c" />


Multizone Audio router for windows with local API (Whole House Audio system)

</div>



# About

<div align="center">

CasChord is a Windows based audio routing software, designed to act as a whole home audio system using the cheapest hardware possible.

This application is compatible with any audio input or output that is normally visible to the windows sound manager, this includes virtual sound cards and mulitple identical audio devices.

## Basic Overview

The number of input sources and output zones is only limited to what Windows supports.

Supported inputs include those built into sound cards, mic in, line in and loopback.
Thrid-party virtual soundcards are also supported...

Input sources and output zones can be given custom names and or be hidden from main web user interface.

<img width="750"  alt="topography" src="https://github.com/user-attachments/assets/7d27b5de-2075-4a6f-8b60-bddd7126fd67" />


## Software Functions

The web ui or local API (documentaion included), are the main intended methods for user interaction. The Windows (Server side Software) does have a limited interface for inital configuration but the best user experience is using the aformentioned external interfaces.

### Win GUI
<img width="666"  alt="wingui" src="https://github.com/user-attachments/assets/ab4b10c4-ff15-4f9d-920e-066199c28226" />



The **Windows Gui** has the following features:



**Main Page:**  


- Input Device Selection: This is the audio source device, if it has a custom name set, that is what you will see..  
- Adjust Input Volume: This chnages the input volume for the source, using windows volume control api. Really it should always be set to 100% (set "always adjust input volume" in advanced, to true)
- Output Devices: Select all will enable all outputs...
- Output Devices cont..: These are your audio destinations, a.k.a your output zones. Each one is a distinct audio output device, you can select one or all at once.
- Master Volume: You can set individual zone volumes 0~100%, adjusting the Master Volume will snap all outputs to that setting.
- Start routing, stop routing, refresh: In the Windows GUI, you must first select an input and output, then click start, volume will ramp up slowly.. To add another output zone, routing needs to be stopped and started.. Refresh resets the interface selectors and stops routing.

**Advanced Tab:**  

- Enable Low Latancy Mode: Reduces lag from input to output.
- Buffer Size: This is the latancy added to the output stream, increase the number for slow systems, helps reduce stutter on slow machines.
- Always Adjust Input Volume: This, when enabled, will always set the input volume to 100%.
- Individual Output Delay: This is used to add latancy to outputs induvidually, useful for situations where you may have a usb audio device and a bluetooth audio device as grouped audio output zones. Adding latancy to sync up the sound.
  
**Device Names Tab**  

- This is where you can set custom names, like Record Player for an input, or Lounge Room for an output device.

**Web Server Tab**  

CasaChord comes bundled with its own HTTP webserver, to make life easier.

- Enable Web Server: Does what it says..
- Start With Application: Auto start server, great for headless systems.
- Enable mDns: This feature is hit and miss on Windows, but i left it in.. Basically, it should let you use a URL for connecting rather than host machines IP and port..
- Port Number: Set a port that youll append to the end of the host machines ip, for web gui access ie; 192.168.1.69:8008
- Current status: What you need to know to connect via local webgui
- Stop, Start: Stop and start webserver, may used cached settings.
- Apply and restart: Use this option for best results.

  

### Web GUI
<img width="487" alt="web_app" src="https://github.com/user-attachments/assets/aa90e083-d30b-46bc-bbe3-ee8056366a98" />


____

The web gui has client identification, allowing for users to create and set custom themes per client device.
Options related to server side application functions, like custom device names and volume controls are syncronised across all clients.

To avoid issues, only one client can control the interface at a time, all other clients are blocked with a message. To regain control, users simply have to press a single button.

<img width="615" height="436" alt="locked" src="https://github.com/user-attachments/assets/eace21aa-34be-43f9-bd99-4337d5917ecb" />

### Web Gui Admin


<img width="666"  alt="web admin" src="https://github.com/user-attachments/assets/0ec41ae2-2b02-4dc3-adbf-02c987daab77" />

