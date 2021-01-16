## object_detection_using_ssd

### AIM
To perform Object Detection using SSD 

### SSD:

SSD (Single Shot Detector) is reviewed. By using SSD, we only need to take one single shot to detect multiple objects within the image, while regional proposal network (RPN) based approaches such as R-CNN series that need two shots, one for generating region proposals, one for detecting the object of each proposal. Thus, SSD is much faster compared with two-shot RPN-based approaches.

### 1.MultiBox Detector
<img src="img1.png">
SSD: Multiple Bounding Boxes for Localization (loc) and Confidence (conf)

->After going through a certain of convolutions for feature extraction, we obtain a feature layer of size m×n (number of locations) with p channels, such as 8×8 or 4×4 above. And a 3×3 conv is applied on this m×n×p feature layer.
->For each location, we got k bounding boxes. These k bounding boxes have different sizes and aspect ratios. The concept is, maybe a vertical rectangle is more fit for human, and a horizontal rectangle is more fit for car.
->For each of the bounding box, we will compute c class scores and 4 offsets relative to the original default bounding box shape.
Thus, we got (c+4)kmn outputs.

“SSD: Single Shot MultiBox Detector”. But the above it’s just a part of SSD.

### 2.SSD Network Architecture
<img src="img2.png">
To have more accurate detection, different layers of feature maps are also going through a small 3×3 convolution for object detection as shown above.

