# Satellite/Aerial Imagery_Detection
Build a model capable of detecting and classifying objects from aerial imagery 

## Objective of this notebook
- The purpose of this notebook is to build model capable of detecting and classifying objects from aerial imagery
- The algorithm of choice here is YOLOV7 and we would be custom training YOLOV7 on an aerial imagery datatset
- Details of the **problem statement**  , **data set** , **data pre-processing & data splits,  **summary of the code/solution**  , **sample output/Prediction** from the program and **final result** of the project are listed in the sections to follow.

## Problem Statement 
Computer vision enables armed forces to optimise their missions, enhance the security of soldiers and protect citizens by using oject detection on satellite imagery to detect unusual activities at the borders.


## Data Description:
- Data Set: xView1 Dataset https://challenge.xviewdataset.org/data-explore 
- Total No Of classes = 60 - some examples include -> Small Aircraft,Cargo Plane,Pickup Truck,Container Ship,Oil Tanker,Helicopter,Crane Truck e.t.c
- Total No Of Image Files = 847
- Total no of Instances/Objects across all images= 6,01,937
 


## Domain:
  Defece Surveillance

## Summary of the Solution/Code:
The code aims at building a Custom CNN model.
- We begin by doing an Exploratory Data analyses and Visualisation on the images , refer **python worksheet /EDA/EDA_And_Preprocessing.ipynb**
- We then do the required pre-processing for the data to make it compatible with the model to be built.We also perform the data splits because we will not be using 16,000  images due to hardware constraints , we will perform a Train Data Split Size=6500 Records and Validation Data Split Size=1629 Records
- We then move on to Model building which will be a simple keras classifier model that has been converted to an object detector. Essentially it is a convolution neural network(in this case with a  base skeleton of MobileNet)which is pre-trained on a ImageNet DataSet who’s top layer have been replaced by two heads , namely a regression head and a classification head. This can be thought of as two parallel networks , one which does classification and the other that calculates the bounding box , each having its own loss function respectively. The combined loss of these functions is what the network strives to reduce with each epoch during the training.

    Architecture Diagram of the above model:
    ![image](https://user-images.githubusercontent.com/68383273/212604564-eaf2f89e-bba8-4a9a-aa59-ba5694875458.png)


- We then do  "Hyper parameter tuning" which involves going through multiple iterations while building the model to try different options for parameters such as  base skeleton n/w, top layers, optimizer and  image size
- The best model resulting from the above iterative process is chosen as the model refer **python worksheet /Custom Baseline Model/Final_Custom_Baseline_Model.ipynb**


## Sample Ouput/Prediction :
Here is a sample Ouput image to the program/model alongside the ground truth

![image](https://user-images.githubusercontent.com/68383273/191107674-7ea077b3-cb37-499e-bfd7-ad964f81a668.png)

## Result
- This model was able to obtain an accuracy of 0.70, IOU of 0.82 and mAp score of 0.592 .Refer **python worksheet /Custom Baseline Model/Calculate_mAp.ipynb** for mAp score calculation

## References & Guidance
- PGP GL/UAT study material 
- Capstone Mentor guidance

## Extension
- For this data set , we had the luxury of building a custom object localisation model because a single object exists in each image of this data set  & therefore we should start with the simplest model possible - a custom object localisation model
- Now as an extension to this worksheet , we could try conventional object detection models like YOLO and SSD to see  whether they were able to give us better scores and log the results.
-It would be interesting to see if using complex models like YOLO or SSD on this data set just ended up being an overkill

