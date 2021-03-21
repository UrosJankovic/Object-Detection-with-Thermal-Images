## Object Detection with Thermal Images
My thesis studies that reasearch object detection on thermal images, as well as comparing the thermal and RGB images detection.
## Requirements
Python 3.8 or later with all requirements.txt dependencies installed, including torch>=1.7. To install run:
```
$ pip install -r requirements.txt
```
## Instructions
- KAIST Multispectral Pedestrian Dataset is available [here](https://soonminhwang.github.io/rgbt-ped-detection/data/)
- Download the annotations in .vbb format and convert to Darknet txt or download txt directly
 ```
$ curl -LO http://multispectral.kaist.ac.kr/pedestrian/data-kaist/annotations.zip
 ```
- Tree folder looks like this:
```
├── KAIST_dataset
│   ├── images
│   ├── labels
├── app
│   ├── __pycache__
│   ├── data
│   ├── detect.py
│   ├── hubconf.py
│   ├── models
│   ├── runs
│   ├── test.py
│   ├── train.py
│   ├── utils
│   ├── wandb
│   └── weights
```
- In images there should be two directories 'train' and 'val', and the same should be in labels.

- Running the code:
```
$ ./train.py --img-size 416 --batch 16 --epochs 50 --data data/kaist.yaml --cfg cfg/yolov3.yaml --weights weights/yolov3.pt
```
```
$ ./test.py --img-size 416 --cfg cfg/yolov3.yaml --weights weights/yolov3.pt --data data/kaist.yaml
```

## Results

### Thermal images object detection

<img src ="https://github.com/UrosJankovic/Object-Detection-with-Thermal-Images/blob/master/data/results/resultsThermal.png" width="500">

### RGB images object detection

<img src = "https://github.com/UrosJankovic/Object-Detection-with-Thermal-Images/blob/master/data/results/resultsThermal.png" width="500">
