# Setting Flightradar 24 and Flightaware simultaneously in a Raspberry pi. 

*On Raspberry pi zero + micro-usb_hub + USB-SDR + usb-wifi*

### Before start - make note 

1. Account Flightradar 24  <https://www.flightradar24.com>
2. Account Flightaware		<http://flightaware.com/>
3. GPS coordinated - <https://maps.google.com> 
4. Find altitud  <https://www.daftlogic.com/sandbox-google-maps-find-altitude.htm>

## Install and set up Flightradar24
No need to set up manually Rtl-sdr driver or Dump1090.  

Install flightradar24  
<https://www.flightradar24.com/raspberry-pi> 

``sudo bash -c "$(wget -O - http://repo.feed.flightradar24.com/install_fr24_rpi.sh)"``
Follow instructions in the screen.

Check 
http://raspberry.pi.ip:8754/

## Install Flightaware
<https://flightaware.com/adsb/piaware/install>

PiAware installation process :

```
wget http://flightaware.com/adsb/piaware/files/packages/pool/piaware/p/piaware-support/piaware-repository_3.1.0_all.deb
sudo dpkg -i piaware-repository_3.1.0_all.deb
sudo apt-get update
sudo apt-get install piaware
```

**dump1090 raw option is yes.**  
 
``nano /etc/fr24feed.ini``  

raw="yes"
   
Can also be set up in <http://x.x.x.x:8754/settings.html>  


Restart service `sudo service fr24feed restart`

Claim PiAware client on FlightAware.com   
<http://flightaware.com/adsb/piaware/claim>

