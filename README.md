![Darknet Logo](http://pjreddie.com/media/files/darknet-black-small.png)

# YOLO v2&v3 with RTMP enabled
You only look once (YOLO) is a state-of-the-art, real-time object detection system.

This repository is forked from `https://github.com/AlexeyAB/darknet`

AlexeyAB version enable Window support and some options that I don't need to do again. 

This repository extend YOLO to running on RTMP streaming.

## Why I create this
At first move I would like to make my device having YOLO ability, so I plan to do this streaming in/out to get YOLO result.

However the streaming delay is too high to accept( more than 10 seconds).

Now it is another YOLO with RTMP input and output result.

## Build Requirements
* requirement to build Darknet
* OpenCV enabled
* cuDNN enabled
* GPU enabled

## How to use

#### Example of usage in console

* darknet detector demo cfg/coco.data cfg/yolov3.cfg yolov3.weights -dont_show -rtmp_fps 15 -rtmp_bps 2000000 rtmp://**YOUR.RTMP/SOURCE**

* darknet rtmp ouput url is fixed in src/demo.c. modify "output_url" manually before build the code.

#### DEMO Environment
1. RTMP server : https://github.com/arut/nginx-rtmp-module
2. RTMP client : [VLC](https://www.videolan.org/vlc/index.html)
3. RTMP source : [OBS](https://obsproject.com)
    * output resolution : 852x480
    * FPS: 15

*OBS send streaming to RTMP server, server will call darknet(YOLO) to process.
darknet(YOLO) will render to another rtmp streaming.
VLC open the streaming.*

<img src='https://github.com/MarcoBay/darknet-rtmp/raw/master/graphic/vlcsnap-1.png?raw=true' width='473' alt='Demo1'>

<img src='https://github.com/MarcoBay/darknet-rtmp/raw/master/graphic/vlcsnap-2.png?raw=true' width='473' alt='Demo2'>

<img src='https://github.com/MarcoBay/darknet-rtmp/raw/master/graphic/vlcsnap-3.png?raw=true' width='473' alt='Demo3'>


