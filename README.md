# rawtherapee-dev
This repo can build an image of rawtherapee-dev and push it to the Github Container Registry.

How to download the docker image:
```
$ docker pull ghcr.io/kd6kxr/rawtherapee_docker-image:latest
```



## Windows 11+:
- Pre-requisite: Install the [Linux Subsystem for Windows via the Microsoft Store](https://www.microsoft.com/store/productId/9P9TQF7MRM4R).
- Pre-requisite: Install the X11 Window System: [Xming](http://www.straightrunning.com/XmingNotes/)

1. Launch Xming by double-clicking the Xming icon.
##### Docker Desktop:
3. Select the image in the Images tab and click *Run*.
4. Enter the volumes to map and the DISPLAY environment value `host.docker.internal:0`
<img src="mac-docker-options.png"  width="550">


## On MacOS 11+:
Pre-requisite: Install the X11 Window System: [XQuartz](https://www.xquartz.org)
- In XQuartz app, set the Preferences>Security>Network Connections button to On.


1. Use terminal to launch an xterm window: `/opt/X11/bin/xterm`
2. In the xterm window, start the localhost listener:
```
xhost +localhost
/opt/X11/bin/Xquartz -depth 24-1 :0 -listen tcp &
```
3. Enter the volumes to map and the DISPLAY environment value `host.docker.internal:0`
<img src="mac-docker-options.png"  width="550">

#### Note: opening the Xquartz tcp listener in xterm results in an optimum-sized RawTherapee window.

Command Line:

```
docker run -it -rm -e DISPLAY=host.docker.internal:0 -v ~:/hi ghcr.io/kd6kxr/rawtherapee_docker-image:latest
```
