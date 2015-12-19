# Plex Server for Raspberry Pi

Run a plex media server in Docker on the Raspberry Pi. Install [Hypriot OS](http://blog.hypriot.com/downloads), clone and run:

    docker-compose up -d

Note: The pi (including the pi 2) isn't powerful enough for transcoding but if you have media that will direct play on your client it works great! I've only tested this on the pi 2.

Updated: The pi2 is in fact powerful enough for transcoding, it turns out this is just for some reason blocked in the Plex base.

http://www.htpcguides.com/fix-plex-server-is-not-powerful-enough-on-raspberry-pi-2/

The repo is a fork of [greensheep/plex-server-docker-rpi][1] with the "Plex Media Server Not Powerful enough fix".  I have rebuilt the docker container
with the hack applied and successfully used the image to transcode 3 streams simtaneously on a Raspberry Pi 2.

Startinig from scratch, one only needs to follow 4 steps to get this working

1.  Download and burn one of the [Hypriot OS images][2] complete with Docker and Docker Compose (My tests were using Version 0.5 Will (beta), I will try a newer image at some point, but pretty certain they should work).

2.  SSH into the Pi using username/password pi/raspberry

3.  Clone the following github repository

    git clone https://github.com/bradleybossard/plex-server-docker-rpi.git

4.  Change into the directory and simple run the docker container in dameonized mode.  This will read the docker-compose file, download the docker image from dockerhub.com, and start the service while mapping the appropriate Plex config directories outside the container such that the docker container can be restarted and
these configs remain intact with each restart.

    cd plex-server-docker-rpi
    docker-compose up -d
  

[1]: https://github.com/greensheep/plex-server-docker-rpi
[2]: http://blog.hypriot.com/downloads/
