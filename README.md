# faceMaskDetection-SSD-FasterRcnn-MosaicAug

![7](https://user-images.githubusercontent.com/27999714/137539103-859f0a81-a90c-4550-a44b-ca964bb0c2a2.png)


## Dataset
* https://www.kaggle.com/andrewmvd/face-mask-detection
* https://www.kaggle.com/wobotintelligence/face-mask-detection-dataset
* with_mask, without_mask, mask_weared_incorrect are the 3 class labels.

## Models
* SSD Single Shot MultiBox Detector - https://arxiv.org/abs/1512.02325
* Faste Rcnn - https://arxiv.org/abs/1506.01497

## Deep Learning FrameWork
* Pytorch

## Implementation Details
* The Main motivation in developing Facemask Detection is to deploy model in mobile Device and Heroku therefor i need to reduce the detection latency as low as possible.
Therefor i have given more emphasis on SSD Model with MobileNetV3 large as backbone. 
* I trained pytorch pretraind ssd_mobilenet_v3_large object detection model with heavy augmentation, given **0.38 MAP**. The Model was trained for above **100 epochs**. 
* The pretrained model separately trained with **Mosaic Augmentation** but i have trained for **40 EPOCHS** and got **0.39MAP**. Model performance can be further improved by for more epochs.

## Deployment
* Model is deployed to Heroku using Flask.
* Using REST API i have developed an android application, where user can capture picture from camera and can detect mask.
* Another android applicatoin is developed where The **Pytorch scripted model** is deployed on device.
* Check out the URLS below for above repos.

## Other Repo URLS
* Android Application using Heroku Rest API - https://github.com/green93/FaceMaskDetectionHerokuApiMVP
* Android Application using pytorch scripted model - https://github.com/green93/FaceMaskDetectionAndroidPytorch
* Heroku API Repo - https://github.com/green93/facemask-detection-heroku
* Rest API - https://facemask-detection-api.herokuapp.com/predict
