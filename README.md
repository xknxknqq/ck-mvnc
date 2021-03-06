# Collective Knowledge Workflows for Movidius Neural Compute Stick

[![logo](https://github.com/ctuning/ck-guide-images/blob/master/logo-powered-by-ck.png)](http://cKnowledge.org)
[![logo](https://github.com/ctuning/ck-guide-images/blob/master/logo-validated-by-the-community-simple.png)](http://cTuning.org)
[![License](https://img.shields.io/badge/License-BSD%203--Clause-blue.svg)](https://opensource.org/licenses/BSD-3-Clause)

# Introduction
This repository contains [Collective Knowledge workflows](http://cKnowledge.org/ai) 
to automate installation and execution of AI applications 
for [Movidius Neural Compute Stick](https://developer.movidius.com/start).

It also contains wrappers for YOLO object detection example 
from [this GitHub repository](https://github.com/gudovskiy/yoloNCS).

# Installing on Linux
```
$ sudo pip install ck
$ ck pull repo:ck-mvnc

$ ck install package --tags=lib,mvnc
$ ck install package --tags=caffemodel,yolo,tiny
$ ck install package --tags=demo,mvnc,yolo
```

##  Raspberry Pi notes

Note that Movidius Neural Compute Stick can run only on Raspbian Stretch or above. 
You can download this image for your RPi [here](https://www.raspberrypi.org/downloads/raspbian).

Since this OS version doesn't have integrated OpenCV support in Python 3, you will need
to answer "yes" to build OpenCV when installing MVNC package. It will take a very long
time (sometimes more than an hour) but it may be worth it.

# Running example with YOLO image classification
```
$ ck compile program:demo-mvnc-yolo
$ ck run program:demo-mvnc-yolo --cmd_key=classify-objects-in-images
```

# Running example with YOLO object detection from a webcam
```
$ ck compile program:demo-mvnc-yolo
$ ck run program:demo-mvnc-yolo --cmd_key=classify-objects-in-webcam
```

You can change webcam ID with width and height as following:
```
$ ck run program:demo-mvnc-yolo --cmd_key=classify-objects-in-webcam --env.SRC=1 --env.WD=800 --env.HT=600
```

# Running internal Movidius examples
```
$ ck run program:demo-mvnc-yolo --cmd_key=run-internal-movidius-examples
```

# Further reading about unified AI project

http://cKnowledge.org/ai
