# rawtherapee-dev

This repo can build an image of rawtherapee-dev and push it to the Github Container Registry.

<hr>

## Launching ghcr.io/kd6kxr/rawtherapee_docker-image

### Pre-requisites:
 
1. Install [Docker Desktop](https://www.docker.com/products/docker-desktop/)

2. Login to [Github Container Registry](https://ghcr.io) with your own Github `username` and a properly scoped `token`:

`docker login -u username -p token ghcr.io`

3. Download rawtherapee_docker-image:
```
$ docker pull ghcr.io/kd6kxr/rawtherapee_docker-image:latest
```

## Windows 11+:
- Pre-requisite: Install the [Linux Subsystem for Windows via the Microsoft Store](https://www.microsoft.com/store/productId/9P9TQF7MRM4R).
- Pre-requisite: Install the X11 Window System: [Xming](http://www.straightrunning.com/XmingNotes/)

1. Launch Xming by double-clicking the Xming icon.
##### In *Docker Desktop*:
3. Select the image in the Images tab and click *Run*.
4. Enter the volumes to map and the DISPLAY environment value `host.docker.internal:0`
<img src="https://raw.githubusercontent.com/kd6kxr/rtdev/main/mac-docker-options.png" alt="config options" width="550">

#### should result in an resizable RawTherapee window.

## On MacOS 11+:
Pre-requisite: Install the X11 Window System: [XQuartz](https://www.xquartz.org)
- In XQuartz app, set the Preferences>Security>Network Connections button to On.


1. Use terminal to launch an xterm window: `/opt/X11/bin/xterm`
2. In the xterm window, start the localhost listener:
```
xhost +localhost
/opt/X11/bin/Xquartz -depth 24-1 :0 -listen tcp &
```
##### In *Docker Desktop*:
3. Enter the volumes to map and the DISPLAY environment value `host.docker.internal:0`
<img src="https://raw.githubusercontent.com/kd6kxr/rtdev/main/mac-docker-options.png" alt="config options" width="550">

#### should result in an optimum-sized RawTherapee window.
<hr>

## Troubleshooting:

### if the screen is unresponsive at first
- you may need to first dismiss a partially hidden welcome splash screen on the first run of that container.
<img src="https://raw.githubusercontent.com/kd6kxr/rtdev/main/splash.png" alt="hidden splash screen" width="550">
