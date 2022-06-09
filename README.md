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

Oil spills in this study is based
on a work by Islam Abou
El-Magd et al. Which is
published in MDPI remote
sensing article.

Study area is near port Said in
Mediterranean sea
(31°30‘ N , 32°30‘ E).

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

Convert GeoTiff files to Jpeg
Transform a certain range of
backscatter
To reduce speckle noise of SAR
images we can apply lee filter
with differnet window sizes.

The input dimension of pre trained
models are usually 224*224 pixels.
So a resize step is needed.

After appling all the pre processings, we should categorize the images
based on the previous works and experience.

Three categories of spill and not spill and lookalikes are considered.


Input layer: RGB Image

Convolutional Layers: contain the learned kernels (weights), which
extract features that distinguish different images from one another.

