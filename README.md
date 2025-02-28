## Dataset Information

Data set :- https://www.kaggle.com/datasets/paultimothymooney/chest-xray-pneumonia

## Description:

This dataset contains 5,232 chest X-ray images, categorized into three classes: "Normal," "Bacterial Pneumonia," and "Viral Pneumonia." The images come from pediatric patients aged 1 to 5 years and were quality-checked by medical professionals before being used for training.

## Structure:

The dataset is divided into three folders: train: 5,208 images test: 624 images val: 24 images

We modified the dataset to wrap the validation set into one training set of 5232 images. Additionally, we divided the dataset into three folder for each class.

## Classification Task

Our classification task involves categorizing X-ray images into three categories:

Normal
Bacterial Pneumonia
Viral Pneumonia
Hyperparameter Tuning:

We first trained a baseline model which achieved an accuracy of ~60%. However, it was overfitting. We then performed hyperparameter tuning to increase the accuracy and decrease overfitting. The number of filters in convolutional layers, filter size, pooling size, batch size, drop out rate, stride, the number of dense layers and their filter sizes, and type of activation function were tuned. The following set of hyperparameters gave the best validation accuracy (>=80%) :

num_filters = [32, 64] filter_size = 5 pool_size = 2 batch_size = 32 dropout = 0.5 stride = 2 dense_layers = [64] act_fun = 'elu'

## Grad-CAM Visualization:

To visualize what parts of the image our model was focusing on, Grad-CAM was put to use. It revealed that the model was mostly focusing on the parts of the lungs near the rib-cage.

## Fine-Tuning VGG16

To leverage the power of pre-trained models, we fine tuned VGG16 on the dataset and achieved a validation accuracy of >=90%.
