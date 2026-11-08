
# Microscopy Illumination Correction

**Comparative Analysis of Gaussian Smoothing and Polynomial Surface Fitting**

## Overview

Non-uniform illumination is a common problem in microscopy images, causing uneven brightness and making identical biological structures appear at different intensity levels. These variations can affect image quality, quantitative measurements, and the reliability of subsequent image analysis.

This project aims to correct non-uniform illumination in microscopy images using classical digital image processing techniques. Two illumination estimation methods are investigated and compared:

- **Gaussian-Based Illumination Estimation**
- **Polynomial Surface Fitting**

The methods will be evaluated under different illumination conditions to determine their effectiveness in improving brightness uniformity while preserving important image details.

## Objectives

The main objectives of this project are:

- Estimate non-uniform illumination patterns in microscopy images.
- Implement illumination correction using Gaussian smoothing and polynomial surface fitting.
- Generate synthetic illumination distortions, including vignetting and linear brightness gradients.
- Compare the correction methods using quantitative image quality metrics.
- Analyze the strengths and limitations of each method under different illumination conditions.

## Dataset

**Dataset:** BaSiCPy Microscopy Illumination Correction Dataset (Cell Culture Subset)

The dataset provides microscopy images for investigating illumination correction techniques.

Synthetic illumination distortions will also be applied to microscopy images to enable controlled experimental evaluation.

## Technologies

- **Programming Language:** Python
- **Libraries:** OpenCV, NumPy, scikit-image
- **Approach:** Classical Digital Image Processing (No AI/ML)

## Methodology

The proposed workflow consists of three main stages.

### 1. Image Preparation

- Load microscopy images.
- Convert images to grayscale or select an appropriate image channel.
- Normalize intensity values to the range [0, 1].
- Optionally introduce synthetic illumination distortions for evaluation.

### 2. Illumination Estimation

Two different methods will be implemented.

**Method A: Gaussian Smoothing**

A large-scale Gaussian filter is applied to estimate the smooth illumination background of the image.

**Method B: Polynomial Surface Fitting**

Background pixels or valid regions are sampled, and a low-order two-dimensional polynomial surface is fitted using least squares to estimate the illumination field.

### 3. Flat-Field Normalization

The estimated illumination field is used to correct the original image through flat-field normalization.

The correction model is:

**C = I / (L / mean(L) + ε)**

Where:

- **I:** Input image
- **L:** Estimated illumination map
- **C:** Corrected image
- **ε:** Small constant for numerical stability

## Experimental Plan

The experimental procedure includes:

1. Select original microscopy images as approximate reference images.
2. Apply synthetic illumination distortions such as vignetting and linear brightness gradients.
3. Estimate illumination fields using Gaussian smoothing and polynomial surface fitting.
4. Correct the distorted images using flat-field normalization.
5. Compare corrected images against their reference images using MAE, RMSE, and SSIM.
6. Analyze the performance of both methods under different illumination conditions.

## Expected Outcomes

The project is expected to:

- Improve illumination uniformity in microscopy images.
- Reduce artificial brightness variations.
- Preserve important biological image structures.
- Identify the strengths and limitations of Gaussian smoothing and polynomial surface fitting.
- Provide a quantitative comparison of classical illumination correction techniques.
# microscopy-illumination-correction
