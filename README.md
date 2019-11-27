# synthesis-hq


## Setting up the Raspberry Pi

### The List of Materials

- Raspberry Pi 4 Model B 4GB RAM
- 3.5" RPi Touchscreen LCD
- USB C charging cable

### Initial Raspberry Pi setup

Follow the great [tutorial at Desertbot.io](https://desertbot.io/blog/headless-raspberry-pi-4-ssh-wifi-setup)

remember to:

 - [ ] change default password
 - [ ] change hostname

### Configure UniFi Controller

follow the [official UniFi tutorial to add Unify source list](https://help.ubnt.com/hc/en-us/articles/220066768-UniFi-How-to-Install-and-Update-via-APT-on-Debian-or-Ubuntu)

then simply install the required packages:

```bash
sudo apt install openjdk-8-jre-headless

sudo apt update && sudo apt install unifi

```
based loosely on [this reddit thread](https://www.reddit.com/r/Ubiquiti/comments/cmg4aw/raspberry_pi_4_with_pi_hole_and_unifi_controller/)

after rebooting you should be able to access the UniFi Controller at `https://HOSTNAME.local:8443/`


**remember to access the controller via HTTPS, otherwise you will get an error**



### Enable LCD module

to enable the attached LCD:

```bash
sudo rm -rf LCD-show 

git clone https://github.com/goodtft/LCD-show.git 

chmod -R 755 LCD-show 

cd LCD-show/

sudo ./LCD35-show
```

to revert back to HDMI-connected monitor:

```bash
chmod -R 755 LCD-show 

cd LCD-show/ 

sudo ./LCD-hdmi
```

based on the [tutorial from TrickiKnow](https://trickiknow.com/raspberry-pi-3-complete-tutorial-2018-lets-get-started/)


