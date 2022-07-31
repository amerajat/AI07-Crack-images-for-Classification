# AI07-Crack-images-for-Classification

## 1. Overview
Ther purpose of this project is to classify an images of concrete wall whether it has cracks or not. This project use the dataset from 	[Concrete Crack Images for Classification](https://data.mendeley.com/datasets/5y9wdsg2zt/2) and was created using Google Colab. The framewok used is Pandas, Scikit-learn and TensorFlow Keras. 

## 2. Methodology

### Data preprocessing

The data loaded is already in their classification file which is positive and negative crack folder. The images need to be process so as to build a more efficient data pipeline. The imges were resize to 100 x 100 and process to merge images into batches and into prefetch form as to increase efficiency in reading data. The data was splitted into the common split that is 70:30. Augmentation layer was used to increase generalization witht the random flipping and rotation.

### Model

This classification was handled by using transfer learning and the model that was used is ResNet50 as a Feature Extractor part for our model. The input layer is our augmentation layer where it will receive an image size of (100,100,3). As for the classification part of our model a global average pooling and dense layer are used as the classifier to output softmax activation function. The sofmax are used to predict the class of the input images.

![concrete crack images model](https://user-images.githubusercontent.com/92585515/182048076-cf4fa39a-216d-4019-a382-e44560596b8c.png)

The model was trained with epochs of 20 and batch size 32. Early stopping are applied to the model, and after reaches 0.9980 accuaracy and val_accuracy: 0.9986 the model was stopped at 3rd epochs.

![acc and val concrete crack images model](https://user-images.githubusercontent.com/92585515/182048301-f0618c85-96ce-4e7b-8d67-ccb8958b762a.png)

Evaluation of the model 

![loss and acc concrete crack images model](https://user-images.githubusercontent.com/92585515/182049112-c3d6c19a-8551-42f2-8e33-5c7f56d0c3db.png)

### Result

Example of images was used and the classification are shown below

![result_concrete crack images model](https://user-images.githubusercontent.com/92585515/182049177-03c7b60e-293b-4a07-91ed-ecde6d04c27e.png)


