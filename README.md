# Skin-Cancer-Detection
A deep learning project for skin cancer detection using tensorflow.

Given a dataset of skin cancer images, this project classifies skin cancer tumors into either benign or malignant.

The model is fit into the dataset then trained to identify whether a tumor is benign or malignant.

Below is an image of a benign tumor,

![Screenshot 2022-12-20 160134](https://user-images.githubusercontent.com/78556152/208673808-01551a4a-d57f-4e5d-9f31-f75e1eab8b47.png)

Malignant tumor.

![malig](https://user-images.githubusercontent.com/78556152/208674041-0d6a73ab-d9f6-4a65-8ba7-732c0fa666b6.jpg)

## Splitting into Training and Validation

Some parameters are first defined for the loader:

batch size set to 32,

Image height set to 180 and 

Image width set to 180.

The dataset is split into training set and validation set with 80% given to training set and 20% given to validation for better learning.

## Classes

There are two classes; benign class and malignant class as shown below

![Screenshot 2022-12-20 161200](https://user-images.githubusercontent.com/78556152/208675418-a31538b4-dd5e-4dd0-bd16-0cb928e032ce.png)


Here are some images from our dataset

![Screenshot 2022-12-20 161605](https://user-images.githubusercontent.com/78556152/208676083-ffc05990-11b0-406d-8976-d1d9ead1d654.png)
![Screenshot 2022-12-20 161527](https://user-images.githubusercontent.com/78556152/208676094-cf12a794-ebe2-4624-9a68-e8663c2c2873.png)


## Keras Model

The dataset is first configured for performance with two functions

data.cache() and 

data.prefetch().

RGB channel values are standardized to [0,1] range using tf.keras.Rescalling

The model is then created and compiled. Here is the model summary

![Screenshot 2022-12-20 162055](https://user-images.githubusercontent.com/78556152/208676964-aa391c04-8904-42f5-b7a5-1c5a9691b096.png)

## Training the Model

The model is trained with 10 epochs as shown below

![Screenshot 2022-12-20 162511](https://user-images.githubusercontent.com/78556152/208677677-784e49cd-d26c-43bf-87b9-30dc238f4a1f.png)

As seen in the image above, the results are great given a good training and validation accuracy.

## Visualizing Training Results

Plots on accuracy and loss are created for training and validation sets.

![Screenshot 2022-12-20 162835](https://user-images.githubusercontent.com/78556152/208678247-cd489552-1ebe-4bba-bd8c-bf52a6fffada.png)

The results look great with the training and validation accuracies being on close margins. However, adding augmentation technique and a Dropout layer to our model makes it even much remarkable.


## Predicting on New Data

When a new image is given to the model for prediction, it classifies it correctly in the right class

![Screenshot 2022-12-20 164019](https://user-images.githubusercontent.com/78556152/208680556-804d88af-c69b-443a-82cd-6dba7969ad1f.png)


## Saving the model

The model is saved and served with tensorflow serving in docker during deployment

![Screenshot 2022-12-20 164214](https://user-images.githubusercontent.com/78556152/208680895-1be8814b-e5d4-4c67-8af7-215e437c4677.png)
