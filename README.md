# Satellite/Aerial Imagery_Detection
Build a model capable of detecting and classifying objects from a Satellite/Aerial/Overhead Imagery Data.

## Objective of this notebook
- The purpose of this notebook is to build model capable of detecting and classifying objects from aerial imagery
- The algorithm of choice here is YOLOV7 and we would be custom training YOLOV7 on an aerial imagery datatset
- Details of the **Problem Statement**  , **Data Set** , **Data Pre-processing & Splits**,  **Architecture/Algorithm** , **Summary of the Code/Solution**  , **Sample Output/Prediction** from the program and **Final Result** of the project are listed in the sections to follow.

## Problem Statement 
Computer vision enables armed forces to optimise their missions, enhance the security of soldiers and protect citizens by using oject detection on satellite imagery to detect unusual activities at the borders.


## Data Description:
- Data Set: xView1 Dataset https://challenge.xviewdataset.org/data-explore 
- Total No Of classes in the entire dataset = 60 - some examples include are Small Aircraft,Cargo Plane,Pickup Truck,Container Ship,Oil Tanker,Helicopter,Crane Truck e.t.c
- Total No Of Image Files = 847
- Total no of Instances/Objects across all images= 6,01,937
 
## Domain:
  Defence Surveillance

## Data Pre-processing & Splits:
- The xView dataset contains labels in the format of a geoJSON file. As part of the pre-processing , we converted the the labels from geoJSON(xView_train.geojson) format to YOLOV7 label format.
- YOLOV7 has a specific label format wherein there will be one label file for each image file and the format of the label file will be as follows
 class|xcenter|ycentre|width|height for each bounding box in that image and labels were generated in this format
 - A subset of data was taken catering to the follwoing  4 classes
![image](https://user-images.githubusercontent.com/68383273/230113892-a94c529d-eb3b-4885-a4fe-64e434f8e5cb.png)
 - The Train and Validation splits were done in a 80:20 split respectively and the details are as follows
 ![image](https://user-images.githubusercontent.com/68383273/230113508-395c797f-0d8f-414d-956c-09fd5a5aff95.png)
 
 
 ## Architecture/Algorithm:
 YOLOV7 by https://github.com/WongKinYiu/yolov7

## Summary of the Solution/Code:
The code aims at custom training YOLOV7 on the xView dataset
- In this notebook we first Explore/Sanity test on  YOLOV7  API as is and run some general inferences to validate setup
- We then Custom Train this YOLOV7 API on XView Data for 151 epochs
- We log the mAp score and F1 scores
- Run inferences on some images from validation split

## Sample Ouput/Prediction :
Here is a couple of sample Ouput images from  the program/model .

![image](https://user-images.githubusercontent.com/68383273/230123824-a8c0de0d-d6de-4cbb-ab1f-52b27ae4b1a1.png)

![image](https://user-images.githubusercontent.com/68383273/230122485-634bd05b-5303-4509-8830-b254895de942.png)



## Result

![image](https://user-images.githubusercontent.com/68383273/230117826-11cf8763-d2ce-420b-a9d8-c84814b41e40.png)

![image](https://user-images.githubusercontent.com/68383273/230119006-140a54ed-4743-4200-9489-6bd10fe6eddc.png)

## Extension
- Some classes performed well while some very poorly .Classes such as small aircraft & helicopter performed poorly compared to Passenger/Cargo flight class.
- Excerpt from final report below
 
![image](https://user-images.githubusercontent.com/68383273/230119658-d569cf23-c85d-4306-8ea9-61e18ee5d201.png)

 
## References & Guidance
- https://challenge.xviewdataset.org/data-explore
- https://github.com/ultralytics/xview-yolov3
- https://medium.com/picterra/the-xview-dataset-and-baseline-results-5ab4a1d0f47f

