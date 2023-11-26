# wled-fuse
# WTF?
Happy holidays, If you're reading this the odds are you received one of my um, holiday cards? and have scanned the QR code on the back. This is some documentation for how to use WLED specifically in the context of this board.
# About WLED
WLED Is an open source RGB Pixel LED controller made by smart people on the internet. Information about the WLED project can be found here: [WLED Github Page]  (https://github.com/Aircoookie/WLED)
I make no claims about the reliability or color accuracy of WLED, however I think it's a really neat project and saved me having to even think about the software for this project (no thoughts, head empty, just solder LED and exist). WLED has some neat features that make it great for making fun LED toys. In no particular order:

 - Wifi Control with built in Web GUI
 - Built in controls and effects
 - Support for sACN (Referred to as E 1.51 for some reason)
 - Automatic wifi setup 

# How to connect
When the device boots, it attempts to connect to its last known wifi network. In most cases, when you first power up your board, it will not connect automatically. In this case, the board will create its own hotspot with the SSID **WLED-FUSE** in order to connect to the onboard hotspot, you will need to enter the default WLED password, **wled1234** you should then be automatically redirected to the WLED GUI which self hosts at **4.3.2.1** (which is a bit of a strange vanity IP, but I guess since they are the router they can do whatever they want) 

You can use the device like this with its built in AP mode, but your phone may be weird about being connected to wifi that doesn't go anywhere, so you may want to connect the board to a real wifi network. 

# Wifi Setup

### To connect your WLED module to your home Wifi:

**1.**  Click on the  _Config_  (gear) icon to edit your WLED module settings and choose 'Wifi Setup'.

**2.**  For most home networks, simply enter your Wifi network's name and network password. You can also change the mDNS address for your WLED module here. By default, I've made it **fuse.local** so once your device is connected, you should just be able to enter that into your browser and you're off to the races. 

**3.**  Click Save & Connect at the bottom of the page.

**4.**  Reconnect your device to your home's Wifi network.

**5.**  Check the device list in your router's user interface for the IP of the WLED device within your local network. Alternatively, the device will advertise itself with mDNS as **fuse.local** so in theory, just enter that in your address bar and it should take you to the GUI. Failing that, use the WLED app (free on the App Store, as it is able to discover WLED boards without knowing the IP! Have fun with the WLED software!

# WLED on your own
If you want to install WLED fresh, you can connect your board over USB-C to a computer and reinstall WLED from [this website](https://install.wled.me) which uses 'Web Serial' (which is a real web API for communicating with locally plugged in serial devices) to reprogram the board. It's WILD how easy they made this process. 

After flashing, only the 'F' will light up because WLED does not know about the other GPIO pins I used in my custom layout. As an exercise, I broke each letter out into its own 'pin' off the microcontroller [(Schematic for those interested)](https://github.com/mkohler99/wled-fuse/blob/main/Electronics/Drawings/Fuse%20LED%20Board%20Schematic.pdf), so in the LED settings you'll need to set up the following LED outputs:

 1. Pin 16 - 10 LEDs - Type WS281X - GRB
 2. Pin 17 - 10 LEDs - Type WS281X - GRB
 3. Pin 18 - 10 LEDs - Type WS281X - GRB
 4. Pin 19 - 11 LEDs - Type WS281X - GRB
 ==Fun Fact: The 'E' in the fuse logo has the most squares by one==

If you'd like to just reload my configuration file, you can find it linked [here.](https://github.com/mkohler99/wled-fuse/blob/main/Config/wled_cfg_fuse.json) You can upload a config file from the 'Security and Updates' tab at the bottom of the web GUI.
 
