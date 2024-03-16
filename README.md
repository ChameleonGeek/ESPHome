# ESPHome
I have had to struggle through creating functional configurations for ESPHome devices in my Home Assistant setup.  HA and ESPHome are both terribly documented, so creating your own configurations requires lots of braiding poorly-written tuorials together and hoping.

I don't know if these will help anyone else, but I really hope so.

# How I develop and deploy
I am running a Home Assistant setup at home and at work.  Most of my development for work is actually done at home where I have an electronics bench.  I am really happy to have discovered that a configuration can support multiple wireless networks.  This way, I can develop and troubleshoot at home and seamlessly bring and install at work.  I don't even have to wait for the ESP to start the access point and change network credentials.

Since most of my configurations use the same board, the same networks, and I want them all to generate the access point and captive portal when needed, all of my configurations share the same included file.  That way, all I have to focus on is the unique parts of the configuration.  I included this include file as esp32-basic.yaml in this repo.

I prefer to define what pins I use for connecting to other devices in the substition section of the YAML file.  This way, all the pins I have to connect are in one place, making it really easy to wire everything up or make changes.
