# Vehicle Counting using YOLOv8

## Overview
This project implements a vehicle counting system using YOLOv8, a state-of-the-art object detection model. The system is trained to detect and classify vehicles into two categories: cars and trucks.

## Features
- Custom training of YOLOv8 model for vehicle detection
- Real-time inference on video streams
- Performance evaluation on validation and test sets
- Data augmentation techniques for improved model generalization


## Setup and Installation
1. Clone this repository:
   ```
   git clone https://github.com/your-username/vehicle-counting-yolov8.git
   cd vehicle-counting-yolov8
   ```

2. Install the required packages:
   ```
   pip install ultralytics==8.0.20 roboflow
   ```

3. Set up your Roboflow account and obtain an API key.

## Dataset
The dataset used in this project is structured as follows:
- Training set: 128 images
- Validation set: 29 images
- Test set: 15 images

The dataset is organized in YOLO format and includes annotations for cars and trucks.

## Usage
1. To train the model:
   ```
   yolo task=detect mode=train model=yolov8s.pt data=/path/to/data.yaml epochs=25 imgsz=800
   ```

2. To validate the model:
   ```
   yolo task=detect mode=val model=/path/to/best.pt data=/path/to/data.yaml
   ```

3. To run inference:
   ```
   yolo task=detect mode=predict model=/path/to/best.pt conf=0.25 source=/path/to/images
   ```

## Results
After training for 25 epochs, the model achieved the following performance on the test set:
- mAP50: 0.981
- mAP50-95: 0.543
- Precision: 0.924
- Recall: 0.913

Class-wise performance:
- Car: mAP50 = 0.973, mAP50-95 = 0.473
- Truck: mAP50 = 0.989, mAP50-95 = 0.613

## Model Architecture
The project uses a YOLOv8s model with the following specifications:
- Layers: 168
- Parameters: 11,126,358
- GFLOPs: 28.4

## Acknowledgments
- This project uses the Ultralytics YOLOv8 implementation.
- Dataset management and augmentation were done using Roboflow.

## Contributing
Contributions to this project are welcome. Please fork the repository and submit a pull request with your changes.
