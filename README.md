# 2021 Purdue fall (2021.10~12)

Understanding the spatial distribution of the species of Red Cedar trees in the middle of the United States is vital for forestry and range management to restrict the spread of this species. Techniques to identify, locate, and mark this species can be used to calculate the cost to control the spread of this species.  
This research proposes a Machine Learning algorithm model to identify, locate and mark red cedar trees in a range land area by utilizing digital image processing. Haar cascade and You Only Look Once version 4 (YOLOv4) will be used to detect and red cedar will be detected in a seasonal difference with long term observation.  
This study has the potential to supplement future studies leading to the estimation of ground identification and volume from Unmanned Aerial Vehicle (UAV) imagery.
</br>
### Team Members
- Gayoung Kim (Kwangwoon University)
- Myungsup Kwak (Kwangwoon University)
- Somin An (Dankook University)
- Kyeongseo Choi (Dongguk University)
- Yaena Lee (Dongguk University)
- Evan Baker (Purdue University)
- Junhee Lee (Purdue University)
- Zhenyu Wan (Purdue University)
</br>

## Eastern Red Cedar, Juniperus Virginiana
Eastern Red Cedar, also known as Juniperus Virginiana, is a native evergreen tree that can be found in midcontinent forest–prairie transitional region and ecotone of North America. The expansion of eastern red cedar had an adverse effect on indigenous species across numerous states in America.
</br>

## Aim 
- Suggest a time-effective and economical method to detect red cedar usinag cameras instead of LiDAR and SAR. 
- Proposes a cost-effective method to detect the tree utilizing aerial images from the camera that is attached to a UAV. 

## Method
### 💡 Flowchart
![flowchart](https://user-images.githubusercontent.com/38778937/144263024-e2d19044-07fd-43b2-a485-e69223fe4d3e.png)

### 💡 Data Tagging
For annotation, video is divided into 10 frames per second and each frame is annotated as a tree tag with V7 tagging tool. The result of these tags is a polygon with a coordinate value of each vertex and bounding box.  

![data tagging](https://user-images.githubusercontent.com/38778937/144263692-de9642f6-f1f1-4172-b948-15ffe464a9f2.jpg)


### 💡 Haar Cascade
In general, Haar cascade detects features after making the image gray scale, but the target is a kind of tree, and to obtain advantage in detection in autumn and winter, color is also included in the feature. It extracts the features of an object and creates a xml file that trains its features. Haar cascade classifier provides xml file for detection. To train with Haar cascade, cascade Trainer GUI is used as a tool. It is a program that is used to train, test, and improve cascade classifier models with positive and negative images. Positive images are training materials for the classifier and negative images are images that don't contain the objects. Positive and negative images are relevant to the objects, but negative images should not include positive features.  
By preparing an image dataset manually, train data has been settled. Once the parameters are tuned and the training process is finished, an XML file will be created as a result. The XML file contains information as a classifier. And OpenCV provides a method for the Haar cascade named ‘detectMultiScale’. Then, it is tested with a new video to evaluate the output to analyze the accuracy of detection.

### 💡 YOLOv4
YOLOv4 is an object detection algorithm which is improved from the previous version. The majority object detectors based on CNN are used in specific systems, leading to reduced practicality of the algorithms. Darknet is used to train YOLOv4 object detectors. Detailed settings such as batch size, numbers of classes, etc. are configured to allow YOLOv4 to learn, making config files. The model is trained with the tree dataset using the config file. 

### 💡 Comparison 
The performance of two algorithms can be evaluated by using the F1 score, which is used as a classification evaluation metric for comparing these two algorithms. The F1 score consists of two factors, Recall and Precision. The definition of these two factors is described with 4 elements: True positive (TP), true negative (TN), false true (FT) and false positive (FP).  
With F1 score, the performance is also evaluated with FPS because YOLOv4 and Haar cascade can be processed in real time. 3-5 FPS or 10 FPS is required for FPS for real-time object detection speed is required. Speed of each algorithm can be compared to whether real-time processing can be conducted or not.  
Through this research, the recall and the precision of each algorithm are compared in figures and the difference in seasonal features will be studied. Furthermore, Haar cascade is usually used to detect facial features with significant recognition, so this paper can be reached to expand the scope by detecting another object.


