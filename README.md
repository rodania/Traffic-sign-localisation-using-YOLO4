# Traffic sign localisation using YOLO4

<img src="./detecting_video.gif">

<!-- TABLE OF CONTENTS -->
<details open="open">
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#introduction">Introduction</a>
    </li>
    <li>
      <a href="#tools">Tools</a>
    </li>
    <li><a href="#data">Usage</a></li>
    <li><a href="#methodology">Methodology</a></li>
    <li><a href="#results">Results</a></li>
  </ol>
</details>

### Introduction
Sign recognition is a two part process. First process is to recognise there is a traffic sign on the road, and then localise it. The second is to find out which sign it is. The model here handles the first process; traffic sign localisation using YOLO4 model.

### Tools:
Python 3, Tensorflow, YOLO4, Pandas, Numpy, Google Colab

### Data:
The German Traffic Sign Detection Benchmark(GTSDB).
The dataset consists of 900 images in ppm format, 600 images for training and 300 for evaluation. The dataset should be downloaded in the same directory of darknet.

The annotation box should be converted tp be compatable with YOLO format. image preprocessing is available at "processing files for test IOU.ipynb"


### Methodology:
YOLO CNN is a convolutional neural network used to detect and classify objects by putting bounding boxes around detected objects. Such bounding box is the minimum sized rectangle, that contain the whole found object. YOLO works on the principle of Single Shot.

YOLO is trained to detect certain type of classes. To detect other classes, we need to retrain YOLO and do some changes in configuration files. Retraining process is transfer learning, it used the pretrained YOLO weights as starting point and then modify these weights to detect the customised object.

### Results

To measure the performance of object detection model, the concept of Intersection over Union (IoU) is used. IoU computes intersection over the union of the two bounding boxes; the bounding box for the ground truth and the predicted bounding box.

An IoU of 1 means that the predicted and the ground-truth bounding boxes are perfectly matched. By setting a threshold value for the IoU, we can determine whether the object detection is valid. 

To calculate mAP, I used the free script of Cartucho, available at this <a href="https://github.com/Cartucho/mAP">link</a>. The final results mAP is 94.98%.

detecting_video.gif
