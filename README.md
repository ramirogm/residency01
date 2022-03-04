# residency01

## Residency intro

During my first month on balena I'll be doing a residency on the balenaLabs team. This means that I can choose any project I want and have a month to develop it! The main goal of the project is to do the onboarding process ( get acquainted with the way things work around here ) in a fun and productive way. 

The first task is to decide what to work on. I have defined some restrictions or own goals about the project I'm about to start working on:

1) Must be something that is interesting to me
2) Doesn't have to result in a "product" of any kind
3) But I want to "finish" it, so I'd like to have a set of goals or stages and try to get as far as I can
4) It should be a way to learn the way the balena platform works: how to develop an app, maintain a fleet, what are the "reusable components" on the platform
5) Have something original: it may be a mashup of ideas, but not a clone of some other projects
6) Would be nice to include some hardware to use on a PI.


## Labs residency ideas

Ok, first: my interests:

I like to work ( or explore working ) on:

1) networked data, distributed computing
  - In balena terms, this could mean developing an app that makes sense to deploy to a fleet, as in a set of workers that are coordinated.
2) asynchronous processing, stream processing
  - processing data asynchronously, processing a stream as a way to both simplify complexity and provide scalability with a unified model. Somehow related to the one above

SDR related projects:

3) AM/FM radio
  - SDR: I have an SDR, but I haven't got time ( or just sat down ) to do anything besides some small toying with it
4) GPS
  - Would be good to understand how does it actually work, in terms of processing radio signals from sattelites. And how does the "interpolation" actually works? Everyone has a GPS on their phone or watch but how does this tiny device work?

## Exploration

Options 1 and 2 were discarded because I couldn't come up with a project that cover requisites 3 and specially 6.

I spent most of my time around exploring ideas for options 3 and 4: Using SDR ( what can I do with it ) and specially on AM/FM radio

I did some exploration on option 4 ( GPS ). But I think I would spend too much time understanding the way the protocol works, maybe copying from som implementation, and would be difficult to come with a plan ( req 3 ). 



### SDR

What can you do with SDR?

	You can do various different things using an SDR as follows:

	Receive broadcast radio
	Amateur radio
	Radio astronomy
	Track ships via AIS transmissions
	Track aircraft via Mode S transmissions
	Set up a DRM transmitter
		https://en.wikipedia.org/wiki/Digital_Radio_Mondiale
	Build a GSM network
	Experiment with LTE
	Learn how Global Navigation Satellite Systems work
		https://gnss-sdr.org/



## AM/FM Radio


Woudln't it be great to have a Raspberry Pi based AM/FM/SW radio?

- I could start with a Pi + a SDR dongle.
- Then connect the Pi to a speaker -> boom we have sound
- I could add a rotary switch ( now that I know how they're called ) to tune the radio and a potentiometer to control the volume
- I have several options for displays:
  - A simple frequency display with a 7-segment LED
  - A graphycal display that resembles an analog radio dial 


### Sources of ideas and notes:

A raspberry pi based radio
cabinet: get a hollowed out physical old radio
put a display on it
	Display library for node: https://github.com/normen/rpi-oled
	lego? https://www.raspberrypi.com/products/build-hat/
	lcd: https://thepihut.com/collections/raspberry-pi-screens/products/adafruit-blue-white-16x2-lcd-keypad-kit-for-raspberry-pi
	led + joystick! https://thepihut.com/collections/raspberry-pi-screens/products/adafruit-128x64-oled-bonnet-for-raspberry-pi-ada3531
	more displays on https://thepihut.com/pages/search-results?q=ssd1306&page_num=2
		like: 
enhance audio output: https://www.adafruit.com/product/1475
knob:
	https://www.adafruit.com/product/377
	from https://gist.github.com/savetheclocktower/9b5f67c20f6c04e65ed88f2e594d43c1

  It could play local AM and FM radio, AND also internet radio. All in one!
      we can apply filters
      we can do an "auto-tune" feature

## Aircraft tracker

mode-s aircraft tracker

		starting point: https://www.rtl-sdr.com/adsb-aircraft-radar-with-rtl-sdr/		
			This one works:
				https://github.com/MalcolmRobb/dump1090
					note that is a fork from the one antirez made
				Hint: If you're on a Debian system, you should check if you installed librtlsdr-dev. Not the rtl_sdr tools, not librtlsdr0, but librtlsdr-dev.
				Antenna		http://antirez.com/news/46
		another reference, a poster
			https://www.etsmtl.ca/Unites-de-recherche/Journee-Decouvertes/Edition-precedente/2013/Kiosque-1-2013/1F_Mode_S.pdf

				Eh a detailed post on 1090: https://www.satsignal.eu/raspberry-pi/dump1090.html

				How to add a station to flightaware: https://flightaware.com/adsb/piaware/build

				buy antenna https://shop.jetvision.de/epages/64807909.sf/en_GB/?ObjectPath=/Shops/64807909/Products/67121


		this is for ships
			https://www.rtl-sdr.com/rtl-sdr-tutorial-cheap-ais-ship-tracking/

It's been already done! :/
https://github.com/ketilmo/balena-ads-b


## find lost items using apple tags or similar clone

apple tags clone to locate stuff/toys lost in the house
	with aliens motion detector UI
	http://www.virtualfrontiers.co.uk/motion%20tracker.htm


## GPS

GPS
	there was a guy somewhere who created its own GPS from Radio
	seems complex
	GPS + SDR
		https://www.rtl-sdr.com/rtl-sdr-tutorial-gps-decoding-plotting/
		https://github.com/happysat/Setup-Meteor-M-N2-N2-2-with-LRPT-Decoder-and-MeteorGIS/blob/main/README.md




## RANDOM NOTES


Well on the balenaOS I don't have apt-get or anything like that, so I'm trying to run on the intel nuc which has linux and then try to build the image


balenaSound

ross porter has plans for wood case



### My hardware


https://www.amazon.com/gp/product/B0747PX3NZ/ref=ppx_yo_dt_b_asin_title_o03_s00?ie=UTF8&psc=1

Nooelec NESDR Smart HF Bundle: 100kHz-1.7GHz Software Defined Radio Set for HF/UHF/VHF Including RTL-SDR, Assembled Ham It Up Upconverter, Balun, Adapters

Manufacturer	Nooelec Inc.
ASIN	B0747PX3NZ
Item model number	NooElec NESDR SMArt HF Bundle

NE SDR natively covers 25 MHz to 1.7 GHz. You need to use the upconverter to receive below 25 MHz. You also need to put a -125 Mhz offset in the SDR software. Once you do you can receive HF Ham Stuff and shortwave.


ON the NUC:
rtl_tcp -a 192.168.0.3


qcrx on the mac: 
Use the device argument 'rtl_tcp=192.168.0.3:1234' in OsmoSDR (gr-osmosdr) source
to receive samples in GRC and control rtl_tcp parameters (frequency, gain, ...).

This worked on mac 10.12; newers need a more modern version
https://github.com/gqrx-sdr/gqrx/releases/tag/v2.11.1



