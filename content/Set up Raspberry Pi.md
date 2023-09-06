# How to set up a [[Raspberry pi]]

## 1. Get the Operating system
- On your computer, navigate to 
[www.raspberrypi.com/software/operating-systems/](https://www.raspberrypi.com/software/operating-systems/)
- Download the [[image file]] for [[raspberry pi os]]. Get the version with desktop and recommended software as you might need additional software on the pi. 

>[!INFO]
>The "image" file in this context isn't an image as in a rectangular pixel grid. The term "image" is used to precise it is an exact copy. 
>The os in question is alrady compiled, is configured to work on your raspberry and has a number of programs preinstalled. 
>An "image" or "snapshot" of that state was taken and that is what you download.

## 2. Get software to install the OS
- Download the etcher utility from 
[www.balena.io/etcher/.](https://www.balena.io/etcher/)

> [!INFO]
> Etcher is a simple [[electron app]] that will let you flash your .img.xz os file to your SD card.

## 3. Install the os on an SD card 
- From Etcher, choose your zip file and the SD card you wish to flash and use as startup disk for your pi. 
- Flash it. Your SD card now contains Raspberry pi os. 

## 4. Configure your pi
- Insert the [[SD card]] into your pi.
- Hook up the [[usb]] c cable from your pi to a usb port on the screen or computer tower. 

> [!INFO]
> If you get a "low voltage" warning notification, try powering the pi from a better source, such as a phone [[fast-charge brick]]

Now plug the [[hdmi]] cable into the micro hdmi port on the pi and the full-size hdmi port on the screen. Select the hdmi input from the screen menu. 
- Your raspberry pi should boot up by itself once plugged into a power source.
- At [[boot]] from the SD card, follow the on screen set up instructions. 
- At the [[network|networking]] setup screen, to connect to the [[internet]], simply choose the eduroam network or your personal wifi hotspot from your phone. 

> [!info] quick tip 
> You could connect your raspberry to the computer towers with an [[rj45]] cable and configure the proxy to access the internet through the university's network, but that is unnecessary. 

``` bash
	export http_proxy="http://proxy.iut-orsay.fr:3128"
	export https_proxy="http://proxy.iut-orsay.fr:3128" 
	export no_proxy=" localhost, 127.0.0.1" 
	xhost local:root 
	sudo /usr/local/bin/partage-connexion.sh 
	setxkbmap fr 
	date MMDDHHmmAA // MM = Mois, DD = Jours, HH = Heures, mm = Minutes, AA = Années 
	export | grep -i proxy 
	sudo raspi-config 
	chmod u+x marionnet_from_scratch.txt 
	./marionnet_from_scratch.txt 
```

- Open the terminal, type and run ```sudo apt-get update```

## Congratulations, you have a working raspberry pi. 

---
#tutorial 