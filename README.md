# Arduino controlling a shocking collar.

This code is based on [Deviant Designs work](http://deviant-designs.co.uk/2019/03/29/arduino-controlled-shock-collar/)  

I only fixed timing issue, caused by sligtly different RF protocol of the new collar.

## Warning!

This project is to control a shock collar - a device traditionally used in "training" dogs and pets. while I cannot stop you from using it for this purpose, I condemn in the strongest possible terms the use of shock collars, and by extension, the use of this software to control shock collars, that are used on any entity that can feel pain that is unable to (i.e. non-human animals, human children) or does not (i.e. unwilling adults) consent to it's use on them.

This project uses commecial products that are intended for use on non-human animals, and involve electricity. I offer no guarantee that use outside (or within) the manifacturers intended use are safe and I reccomend you seek medical advice on the issue before use.

*Warning copied form [smouldery original repo](https://github.com/smouldery/shock-collar-control)*


## Hardware

* [Shocking Collar](https://www.aliexpress.com/item/Rechargeable-And-Waterproof-300-Meters-Remote-Electric-Shock-Anti-bark-Pet-Dog-Training-Collar-With-LCD/2052492035.html?channel=twinner)  
* [433 MHz transmitter](https://www.curiua.com/p/bqlzr-1-set-433mhz-rf-wireless-transmitter-und-empf-ngermodul-gr-n-pcb/0700443095464) - you can buy this, but I've tried 2 different version from Aliexpress and both are ok.
* An arduino, I've used a Mega2560 because was on my desk.

## How to use
Connect (on a breadbord, solder it, use hotglue, use jumpwire...) the pin 11 to the data pin of the trasmitter.  
Reset the collar as descripted on the collar instructions. The collar make a beep noise.  
Connect the pin 9 to GND. Now the collar emit a new beep noise. You are paired!
If you press/connect again the pin 9, the collar should vibrate.

Change the loop() function to do different mode and power settings.

If you have an SDR, you can grab a transmitted RF signal from the original remote, and extract the remote ID. If you change the const String key in the code with your remote ID, you can use both remote and arduino to control the collar.
