# Weapons Dataset

<strong>You can access our dataset by clicking [Download Weapons Dataset](https://docs.google.com/forms/d/1OFtJDJa2F9UX6XmD3Jvk8k2kpNvGHiwG90l5LC4ksdY)</strong>
 
# Dataset Details

we have prepared the dataset in two variants. First one is the X-Aligned Dataset and second one is the Angle-Oriented dataset but YOLO will only support the X-Aligned dataset. We will discuss both datasets one by one.

## 1) X-Aligned Dataset

This dataset consist of total 7801 images of weapons. There are two classes included in our dataset one is "Gun" and other is "Pistol". The given Dataset contain total 5512 instances of "Gun" and 3739 instances of "Pistol". We have prepared the different formats of this dataset because each model have its own format for training. 

The <strong>LabelImg</strong> tool is used for the preparation of annotation file. You can see the tool [HERE](https://github.com/tzutalin/labelImg).

The formats of different models are given below:

### I. YOLO Format

In YOLO labeling format, a `.txt` file with the same name is created for each image file in the same directory. Each `.txt` file contains the annotations for the corresponding image file, that is object class, object coordinates, height and width.

`<object-class> <x> <y> <width> <height>`

For each object, a new line is created.

Below is an example of annotation in YOLO format where the image contains two different objects.

```
0 45 55 29 67
1 99 83 28 44
 ```
 
The files will be shown like this:

<img src="https://github.com/tufailshah786/Weapons-Detection-with-YOLOV3/blob/main/yolo1.png" width="900" height="500"><br/><br/>

### II. Pascal-VOC Format
Pascal-VOC is an XML file, in Pascal-VOC we create a file for each of the image in the dataset. 

<strong>Pascal VOC Bounding box:(xmin-top left, ymin-top left,xmax-bottom right, ymax-bottom right).</strong>

<img src="https://github.com/tufailshah786/Weapons-Detection-with-YOLOV3/blob/main/pascal.png" width="400" height="500"><br/><br/>

Some of the key tags for Pascal VOC are explained below:
#### Folder:
Folder that contains the images
#### Filename:
Name of the physical file that exists in the folder
#### Size:
Contain the size of the image in terms of width, height and depth. If the image is black and white then the depth will be 1. For color images, depth will be 3
#### Object:
Contains the object details. If you have multiple annotations then the object tag with its contents is repeated. The components of the object tags are
* name
* pose
* truncated
* difficult
* bndbox
#### name:
This is the name of the object that we are trying to identify
#### truncated:
Indicates that the bounding box specified for the object does not correspond to the full extent of the object. For example, if an object is visible partially in the image then we set truncated to 1. If the object is fully visible then set truncated to 0
#### difficult:
An object is marked as difficult when the object is considered difficult to recognize. If the object is difficult to recognize then we set difficult to 1 else set it to 0
#### bounding box:
Axis-aligned rectangle specifying the extent of the object visible in the image.

### III. Faster R-CNN Format
The information of Faster R-CNN annotation information is saved in the `.txt` file (no space just comma between two values). Each row has the format like this: 
```
file_path,x1,y1,x2,y2,class_name

 ```
 Where file_path is the absolute file path for this image, (x1,y1) and (x2,y2) represent the top left and bottom right real coordinates of the original image, class_name is the class name of the current bounding box.

The information will be saved like this in the `.txt` file:

<img src="https://github.com/tufailshah786/Weapons-Detection-with-YOLOV3/blob/main/faster_txt.png" width="500" height="500"><br/><br/>
## 2) Angle-Oriented Dataset
This dataset consist of total 7801 images of weapons. There are two classes included in our dataset one is "Gun" and other is "Pistol". The given Dataset contain total 5512 instances of "Gun" and 3739 instances of "Pistol". We have also prepared the different formats of this dataset because each model have its own format of for training.

The <strong>roLabelImg</strong> tool is used for the prparation of annotation file. You can see the tool [HERE](https://github.com/cgvict/roLabelImg).
The XML file is generated through this tool which is shown below:

<img src="https://github.com/tufailshah786/Weapons-Detection-with-YOLOV3/blob/main/angle-oriented.png" width="400" height="500"><br/><br/>

Where <strong>(Cx,Cy)</strong> represent the centre point of the Bounding Box, <strong>"W"</strong> and <strong>"H"</strong> represent the width and height of the bounding box, and <strong>"Angle"</strong> represent the rotation of the Bounding Box.


