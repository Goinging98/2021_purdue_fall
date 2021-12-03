# 🎄 Detecting Red Cedar tree by Haar Cascade and YOLOv4 with Seasonal Comparison 

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

## Problem Statement
Eastern Red Cedar, also known as Juniperus Virginiana, is a native evergreen tree that can be found in midcontinent forest–prairie transitional region and ecotone of North America. The expansion of eastern red cedar had an adverse effect on indigenous species across numerous states in America.  
For instance, the state of Oklahoma is losing 278,130 acres per year from the invasion of juniper species. As a result of losing precious land resources to this species, the expansion of the trees has a negative effect on the local economy. The introduction of eastern red cedar also decreases biodiversity.  
Therefore, detecting red cedar is required before the tree matures and is widely spread.  
</br>

## Aim and Novelty 
- Suggest a time-effective and economical method to detect red cedar usinag cameras instead of LiDAR and SAR. 
- Proposes a cost-effective method to detect the tree utilizing aerial images from the camera that is attached to a UAV. 
- Considering the seasonal difference of the appearance of forests, the shoot was conducted twice
  -  October : when all the trees are green
  -  November : when leaves on deciduous trees change color or fall down
</br>

## Method
### 💡 Flowchart
![flowchart](https://user-images.githubusercontent.com/38778937/144263024-e2d19044-07fd-43b2-a485-e69223fe4d3e.png)

### 💡 Data Tagging
For annotation, video is divided into 10 frames per second and each frame is annotated as a tree tag with V7 tagging tool. The result of these tags is a polygon with a coordinate value of each vertex and bounding box.  

![data tagging_side](https://user-images.githubusercontent.com/38778937/144276628-07991c13-c5db-4549-9b57-ece8a90506f8.jpg)

### 💡 Environment Setting
1. Install Docker on Ubuntu 20.04 LTS
2. Build Two Dockerfiles for each algorithm
    - YOLOv4 : OpenCV 4.5.4 + Darknet + Jupyter Notebook
    - Haar Cascade : OpenCV 4.5.4 + Jupyter Notebook
3. Haar Cascade
    - Training
      - Prepared : OpenCV 3.4, Jupyter Notebook, vector file, Positive Images, Positive text files, Negative Images, Negative text file
      - Result : cascade classifier XML file
    - Testing
      - Prepared : OpenCV 4.5.4, Jupyter Notebook, Trained XML file, Testing video (never used in training)
      - Result : Visualized result with bounding box
4. YOLOv4
    - Training
      - Prepared : OpenCV 4.5.4, Darknet, Image frames, Text files with coordinate value of bounding box, Config file
      - Result : YOLOv4 Weight file
    - Testing
      - Prepared : Darknet, YOLOv4 Weight file, Testing video (never used in training)
      - Result : Visualized result with bounding box


