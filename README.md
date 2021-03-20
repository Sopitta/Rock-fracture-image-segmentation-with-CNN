# Rock fracture image segmentation with CNN

In this project, We used Unet for automatic fracture detection from rock fracture images. Both vanilla Unet architecture and Unet with pretrained weights 
from https://github.com/qubvel/segmentation_models.pytorch were explored.

## Creating Training set ##

![GTK Input](https://github.com/Sopitta/Rock-fracture-image-segmentation-with-CNN/blob/master/Image/GTK_input.PNG)

- The training images were extracted from 2D-map of fault and fracture traces in ArcMap [Skyttä, P., Ovaskainen, N., Nordbäck, N., Engström, J., Mattila, J., 2021. Fault-induced mechanical anisotropy and its effects on fracture patterns in crystalline rocks, Journal of Structural Geology. https://doi.org/10.1016/j.jsg.2021.104304] 

- The trainning set consists of 5024 RGB images of rock fracture crops and their BW masks/annotations. Both with dim 512 x 512

## Data Augmentation ##
- Affine transformation was applied (50 % percent probability of being applied) to the image batch during training for better generalization of the model. We used degrees = (-90,90), translate = (0.1,0.1), scale = (0.8,1.2), sheer = None)

## Example of Result ##

![Ori](https://github.com/Sopitta/Rock-fracture-image-segmentation-with-CNN/blob/master/Image/60_ori.png)       This is an original image 

![Mask](https://github.com/Sopitta/Rock-fracture-image-segmentation-with-CNN/blob/master/Image/60.png)             This is a mask image

![Predict](https://github.com/Sopitta/Rock-fracture-image-segmentation-with-CNN/blob/master/Image/60_bb_1.PNG)  This is interprted fractures (Accuracy 0.769/1 using dice coefficient)






