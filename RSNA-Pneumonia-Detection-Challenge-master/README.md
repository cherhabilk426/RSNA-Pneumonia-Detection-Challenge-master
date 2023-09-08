Faster R-CNN for RSNA-Pneumonia-Detection-Challenge Dataset by Keras
Introduction


In this competition, you’re challenged to build an algorithm to detect a visual signal for pneumonia in medical images. Specifically, your algorithm needs to automatically locate lung opacities on chest radiographs.


The original code of Keras version of Faster R-CNN I used was written by yhenon (resource link: GitHub .) He used the PASCAL VOC 2007, 2012, and MS COCO datasets


We have modified the problem statement for our personal learning purpose 
We consider only those images which has lables coordinate in stage_2_train_labels.csv 

For me, I just used the  RSNA-Pneumonia-Detection-Challenge Dataset for lungs capacity . I applied configs different from his work to fit my dataset and I removed unuseful code.

#Project Structure


dcm to jpg .ipynb  is the file to tranfom .dcm to jpg images in train and test floder 

preposessing.ipynb is the file to preprocessing the  (stage_2_train_labels.csv ) we have drop the values which doesnot conatin any coordinate values ( 0004cfab-14fd-4e49-80ba-63a80b6bddd6,,,,,0 ) I run this part by my own computer because of no need for GPU computation.


frcnn_train_vgg.ipynb is the file to train the model. The configuration and model saved path are inside this file. frcnn_test_vgg.ipynb is the file to test the model with test images and calculate the mAP (mean average precision) for the model. 


Prerequisites
Linux or OSX with GTX 1650 with 4 gb ram 
CUDA 10.1, keras, Python 3.6

skimage, matplotlib, sklearn, tqdm

for training we have used GTX 1650 with 4 gb ram and for 40 epoch it's taken 60 hours approx and  MPA score is 0.16 due to less amount of data and base model (vgg-16 ) is not trained on such type of x ray image 


Base Model Vgg16 

Its a one stage  faster rcnn tranning  model 



download the pretrain model https://drive.google.com/open?id=1ETaNh2xfvJLscfSVPMjCfOLIEtFpCj60

dowload the config file https://drive.google.com/open?id=1Vo9c1jbMnSDDOdRSrYAOSreczWHCFq3T






You can dowload the data set from kaggle compition 
https://www.kaggle.com/c/rsna-pneumonia-detection-challenge


Evaluation
The training loss on the region proposal network and the Faster R-CNN core network is shown below. The results are evaluated on the mean average precision at the different intersection over union (IoU) thresholds. 

![x ray](https://user-images.githubusercontent.com/45600643/73590123-a80f9280-4504-11ea-890e-b8b9630ac0cd.png)

![x ray_2](https://user-images.githubusercontent.com/45600643/73590132-b52c8180-4504-11ea-906c-7c2e1f395ac8.png)



Results 

![download](https://user-images.githubusercontent.com/45600643/73592380-ba4afa00-451f-11ea-859a-3f10f3b0f365.png)




