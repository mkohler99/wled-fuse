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
