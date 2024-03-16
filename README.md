# ESPHome
I have had to struggle through creating functional configurations for ESPHome devices in my Home Assistant setup.  HA and ESPHome are both terribly documented, so creating your own configurations requires lots of braiding poorly-written tuorials together and hoping you understood what the author was doing well enough to adapt their code.

I don't know if these will help anyone else, but I really hope so.

# How I develop and deploy
I am running a Home Assistant setup at home and at work.  Most of my development for work is actually done at home where I have an electronics bench.  I am really happy to have discovered that a configuration can support multiple wireless networks.  This way, I can develop and troubleshoot at home and seamlessly bring and install at work.  I don't even have to wait for the ESP to start the access point and change network credentials.

I work at a dance school, and the teachers and students like to use lots of different lights in the classrooms.  Because of this, many of my configurations are focused on controlling different types of lights.  The lights were purchased based on price rather than ease of integration into a Home Assistant environment.  I've learned how to control lights via simple binary relays (switching AC and DC), DC solid state relays that can provide limited dimming, infrared remote control codes and bluetooth, and addressable LEDS (both WS2811 and WS2812).  Cost is more important than time with many of these configurations, so most are combinations of the ESP32 and different discreet components rather than fully configured off the shelf devices. 

Since most of my configurations use the same board (Wemos D1 Mini ESP32-WROOM), the same networks, and I want them all to generate the access point and captive portal when needed, all of my configurations share the same included file.  That way, all I have to focus on is the unique parts of the configuration.  I included this include file as esp32-basic.yaml in this repo.

I prefer to define what pins I use for connecting to other devices in the substition section of the YAML file.  This way, all the pins I have to connect are in one place, making it really easy to wire everything up or make changes.

I am running Home Assistant on a Raspberry Pi 3B both at home and at work.  The Pi is more than capable of running all aspects of HA I've wanted except for compiling the firmware for the ESP devices.  Because of this, I'm compiling the code and flashing the devices with a laptop instead of the HA host Pi.
