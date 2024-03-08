## Vision Transformer for Object Detection

This repository contains an implementation of the Vision Transformer (ViT) architecture for object detection. The model is designed to detect objects in images and predict their 
bounding boxes and classes. The ViT architecture, originally proposed for image classification, is adapted here for object detection tasks.

### Below are the steps used in building the base model

#### 1. Dataset Preparation 
- Specifed the dataset paths to the training images and annotations in the tomato_base_dir and related variables and implemented a custom collate function to resize and preprocess the images.
- This is the dataset used in the basemodel. (https://universe.roboflow.com/object-detection-i2phe/tomato1-kggoq/dataset/1)
  
#### 2. Divide the Image into Patches
- Used the split_image_into_patches function to divide the input image into patches.
- Specifed the patch size as a parameter to control the size of each patch.

![image](https://github.com/SravyaVujjini/VisionTransformer-for-object-detection/assets/121740546/9dcc8a93-01a7-47c7-9d94-4f85db9aee32)


#### 3. Project Flattened Patches to Embedding Dimension
- Implemented the embed_patches function.
- Used a linear layer (nn.Linear) to project the flattened patches to the desired embedding dimension.
- Applied the linear layer to the flattened tensor.

#### 4. Encoder Block with Multi-Head Attention and Fully Connected Network
- Defined the EncoderBlock class.
- Utilized Layer Normalization, Multi-Head Attention, and a Feed-Forward Network (FFN) with residual connections.
- Implemented the forward method to process input through these components.

#### 5. MLP Classifier Head
- Implement the MLPClassifier class for image classification comprising of fully connected layers with ReLU activation for the classification task.
- Outputs the probabilities for each class.

#### 6. MLP Head for Object Detection
- Utilized MLPHead for object detection comprising of fully connected layers with GELU activation and dropout for regularization.
- The final layer outputs four values representing bounding box coordinates.

### Below is the base model architecture

![image](https://github.com/SravyaVujjini/VisionTransformer-for-object-detection/assets/121740546/be6ff1d9-5209-488d-8baf-96fad4b40312)
