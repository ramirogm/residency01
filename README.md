# residency01


## Labs residency ideas

My interests:

- networked data
  - A fleet of.... 
- asynch stuff
  - processing data asynchronously, processing a stream
- AM/FM radio
  - SDR
- GPS
  - how does it work actually?


## Exploration


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


