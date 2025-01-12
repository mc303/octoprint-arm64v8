# OctoPrint-docker [![Build Status](https://travis-ci.org/mc303/OctoPrint-arm64v8.svg?branch=master)](https://travis-ci.org/mc303/OctoPrint-arm64v8)

This repository contains everything you need to run [Octoprint](https://github.com/foosel/OctoPrint) in a arm64v8 docker environment.

# Getting started

```
git clone https://github.com/OctoPrint/docker.git octoprint-docker && cd octoprint-docker

# search for you 3D printer serial port (usually it's /dev/ttyUSB0 or /dev/ttyACM0)
ls /dev | grep tty

// edit the docker-compose file to set your 3D printer serial port
vi docker-compose.yml

docker-compose up -d
```

You can then go to http://localhost:5000

You can display the log using `docker-compose logs -f`

## Without docker-compose
```
docker run -d -v ./config:/home/octoprint/.octoprint --device /dev/ttyACM0:/dev/ttyACM0 -p 5000:5000 --name octoprint octoprint/octoprint
```

# Additional tools

## FFMPEG

Octoprint allows you to make timelapses using an IP webcam and ffmpeg. It is installed in `/opt/ffmpeg`
