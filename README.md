# 2021 Purdue fall (2021.10~12)

Understanding the spatial distribution of the species of Red Cedar trees in the middle of the United States is vital for forestry and range management to restrict the spread of this species. Techniques to identify, locate, and mark this species can be used to calculate the cost to control the spread of this species.  
This research proposes a Machine Learning algorithm model to identify, locate and mark red cedar trees in a range land area by utilizing digital image processing. Haar cascade and You Only Look Once version 4 (YOLOv4) will be used to detect and red cedar will be detected in a seasonal difference with long term observation.  
This study has the potential to supplement future studies leading to the estimation of ground identification and volume from Unmanned Aerial Vehicle (UAV) imagery.
</br></br>

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




### 💡 YOLOv4

