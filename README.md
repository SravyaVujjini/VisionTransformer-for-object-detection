## Vision Transformer for Object Detection

This repository contains an implementation of the Vision Transformer (ViT) architecture for object detection. The model is designed to detect objects in images and predict their 
bounding boxes and classes. The ViT architecture, originally proposed for image classification, is adapted here for object detection tasks.

### Below are the steps used in building the base model

1. Dataset Preparation
- Specify the dataset paths to the training images and annotations in the tomato_base_dir and related variables and implement a custom collate function to resize and preprocess the images.
  
2. Divide the Image into Patches
- Use the split_image_into_patches function to divide the input image into patches.
- Specify the patch size as a parameter to control the size of each patch.

3. 
