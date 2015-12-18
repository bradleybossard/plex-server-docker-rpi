# Plex Server for Raspberry Pi

Run a plex media server in Docker on the Raspberry Pi. Install [Hypriot OS](http://blog.hypriot.com/downloads), clone and run:

    docker-compose up -d

Note: The pi (including the pi 2) isn't powerful enough for transcoding but if you have media that will direct play on your client it works great! I've only tested this on the pi 2.

Updated: The pi2 is in fact powerful enough for transcoding, it turns out this is just for some reason blocked in the Plex base.

http://www.htpcguides.com/fix-plex-server-is-not-powerful-enough-on-raspberry-pi-2/

The repo is a fork of [greensheep/plex-server-docker-rpi][1] with the "Plex Media Server Not Powerful enough fix".  I have successfully used the image at


[1]: https://github.com/greensheep/plex-server-docker-rpi
