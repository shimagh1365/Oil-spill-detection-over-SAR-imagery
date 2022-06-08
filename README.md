# Oil-spill-detection-over-SAR-imagery

Introduction

Oil spills are generally characterized as the release of liquid
petroleum hydrocarbons into the environment due to human
activities.

Diverse studies have highlighted the usefulness of Synthetic Aperture
Radar images (SAR) obtained by satellites for the detection of oil
spills.

Due to large amount of satellite images, we can use machine learning
techniques or deep learning models to monitor sea conditions
automatically.

Ground Truth & Study Area

Oil spills in this study is based
on a work by Islam Abou
El-Magd et al. Which is
published in MDPI remote
sensing article.

Study area is near port Said in
Mediterranean sea
(31°30‘ N , 32°30‘ E).

Google Earth Engine (GEE)

To reduce download size and
processing time, we can use
google earth engine.

Sentinel 1 images with relative
orbit number of 160 from 2014
to 2021 is croped to ROI and
saved to google drive in geoTiff
format.

Some of the preprocessing steps
such as calibrations, is already
done on GEE datasets

Pre Processing

Convert GeoTiff files to Jpeg

Transform a certain range of
backscatter

Pre Processing

To reduce speckle noise of SAR
images we can apply lee filter
with differnet window sizes.

One example is shown below
with 9*9 window size.

Noise reduction is more visible
after resizing the images.

Pre Processing

The input dimension of pre trained
models are usually 224*224 pixels.
So a resize step is needed.

As mentioned before the effect of
lee filter is clear after resizing.
Categorizing

After appling all the pre processings, we should categorize the images
based on the previous works and experience.

Three categories of spill and not spill and lookalikes are considered.

Convolutional Neural Network (CNN)

A class of deep neural networks

Most commonly applied to analyzing visual imagery

Image classification & Image segmentation
CNN Layers

Input layer: RGB Image

Convolutional Layers: contain the learned kernels (weights), which
extract features that distinguish different images from one another.

Padding

Kernel size

Stride

Pooling Layers: gradually decreases the spatial extent of the network.

Flatten Layer: converts a three-dimensional layer in the network into a
one-dimensional vector to fit the input of a fully-connected layer for
classification.

Data

Scenario 1 Table

Category/Type

Training

Validation

Test

Total

Spill

43

6

3

52

Not spill

70

20

10

100

Total

113

26

13

152

Scenario 2 Table

Category/Type

Training

Validation

Test

Total

Spill

43

6

3

52

Not spill

77

22

12

111

Total

120

28

15

163

6 Year of Sentinel 1 SAR images

Categorised in 3 classes ( spill & water & lookalikes)

Two scenario of classification investigated

Scenario 1: water & oil spills

Scenario 2: water and lookalikes as not spill & oil spills as spill

Google Colab

allows you to write and execute Python in your browser

Zero configuration

Free access to GPUs

Easy sharing

Pre Trained Model

Transfer learning: use a pre-trained model
on a different simillar dataset

Fine-tuning: use parts of the pre-trained
model and train some other parts of it, for
another dataset

Fine Tunning Pre Trained Models

Removed the dense layer and
replaced it with a 2 class
dense layer in all models.

Fine tuned models are:

VGG-16

ResNet50 V2

MobileNet

Inception V3
Conclusion

Training the model with lookalikes as notspill class increases all the
test accuracies.

Highest accuracies in test data is for InceptionV3 model in both
scenaios.

Repetition of 100% test accuracy is highest in InceptionV3 model (4
out of 10 trainings).

Stability of the training and validation accuracies is higher in VGG-16
model.







