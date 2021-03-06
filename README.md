# JetsonNano_Certificate

## What Does This Program Do?
This program used the imagenet network that was provided in the Nvidia Jetson Nano Hello AI World tutorial to train the AI to recognize human face and whether the person in front of the camera is wearing a mask. If human is detected but no mask is detected, then the program will trigger a warning message to whoever may concern.

For example, implementing this program at the entrance of a building. The securities can receive and monitor the messages that there is a person entering the building without wearing mask.

## Prerequisite
NVIDIA Jetson Nano Developer Kit\
USB Web Camera (Raspberry Pi Camera V2 may also works, but the code in this repo is for USB camera only)\
NVIDIA JetPack 4.2.1 or later\
Basic knowledge regarding Jetson and Linux and docker environment from Hello AI World Tutorial(https://github.com/dusty-nv/jetson-inference)

## Installation
1. Set up the jetson-inference\
You can set up the jetson-inference following this tutorial https://github.com/dusty-nv/jetson-inference

2. Get to the right directory\
$ cd ~/jetson-inference/python/training/classification/

3. Install this application and the dependent modules\
$ git clone https://github.com/Cyuaz/JetsonNano_Certificate

4.Merge the files you just cloned from github to the classification folder

## How To Use
1. Go to the jetson-inference\
$ cd ~/jetson-inference

2. Run the docker\
$  docker/run.sh --volume ~/jetson-inference/python/training/classification:/jetson-inference/python/training/classification

3. Go to the directory\
$ cd /jetson-inference/python/training/classification

4. Run the program\
$  python3 mask_recognition.py --model=models/mask/resnet18.onnx --input_blob=input_0 --output_blob=output_0 --labels=data/mask/labels.txt /dev/video0

Note: The first time to run anything camera related is gonna take about 5 minutes to initialize. Don't kill the program just because you think it is acting weird.


