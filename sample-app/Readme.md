# Pedestrian Tracker C++ Demo

Implementation of a pedestrian tracking demo. 
This demos is included in OpenVINO package.
Source code: https://github.com/opencv/open_model_zoo/tree/master/demos/pedestrian_tracker_demo

## Video

For this sample you can use the following Pexel public video: 
https://www.pexels.com/video/a-day-at-the-mall-1338598/

Download it inside the video folder.

## Build the Docker image

```bash
docker build -t sample-app
```

## Run the container

### Enable X

Since this sample application uses the display to show the output, we need to share the host display with the guest container. 

The X server on the host should be enabled for remote connections: 

```bash
xhost + 
```

### Run the container

```bash
docker run --net=host --env="DISPLAY" --volume="$HOME/.Xauthority:/root/.Xauthority:rw" -ti sample-app /bin/bash
```

## Run the sample application

```bash
~/omz_demos_build/intel64/Release/pedestrian_tracker_demo \
  -i /app/videos/video1.mp4 \
  -m_det /app/models/intel/person-detection-retail-0013/FP32/person-detection-retail-0013.xml \
  -m_reid /app/models/intel/person-reidentification-retail-0031/FP32/person-reidentification-retail-0031.xml  \
  -d_det CPU
```

Where: 
* video1.mp4 is the name of our video
* person-detection-retail-0013 and person-reidentification-retail are the two models this sample uses



