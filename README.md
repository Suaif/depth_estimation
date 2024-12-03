# Deep Learning for Image and Video Processing - Final Project

## Single Image Depth Estimation

### Academic Year: 2023-2024

**Author: Ismael Gómez Garrido (i6334270)**

### Project Overview
This project focuses on **Single Image Depth Estimation**, a challenging task in computer vision aimed at estimating the depth value for each pixel of an RGB image. Depth estimation algorithms are critical for applications in autonomous vehicles, robotics, augmented and virtual reality, and medical imaging. This report explores and compares different models and methodologies for depth estimation "in the wild," where images come with diverse structures and compositions.

### Table of Contents
1. [Introduction](#introduction)
2. [Related Work](#related-work)
3. [Data](#data)
   - NYU Depth V2
   - Depth in the Wild (DIW)
4. [Methodology](#methodology)
   - Data Preprocessing
   - Training Process
   - Model I: U-Net++
   - Model II: Transfer Learning with LR-ASPP
   - Metrics
5. [Experiments & Results](#experiments--results)
   - LR-ASPP
   - U-Net++
   - Comparison
6. [Conclusions & Possible Improvements](#conclusions--possible-improvements)
7. [References](#references)

### Introduction
**Single Image Depth Estimation** or **Monocular Depth Estimation** aims to estimate depth values for each pixel of an RGB image. This project involves training models to perform this estimation effectively using images with varying structures and elements, requiring a high level of generalization.

### Related Work
There has been substantial progress in monocular depth estimation. Early methods used superpixel grouping, while modern approaches leverage encoder-decoder architectures and, more recently, vision transformers and diffusion models.

### Data
Two datasets were used:
- **NYU Depth V2**: A widely-used benchmark dataset consisting of indoor scenes captured with RGB and Depth cameras.
- **Depth in the Wild (DIW)**: A challenging dataset with images gathered from Flickr, annotated only with relative depth between pairs of points.

### Methodology
- **Data Preprocessing**: Both datasets were resized to 200x200 resolution for computational efficiency.
- **Training Process**: Models were trained on NYU Depth V2 before fine-tuning with DIW, using pre-trained models to reduce training time.
- **Models**:
  - **U-Net++**: A widely-used architecture for semantic segmentation, adapted here for depth estimation.
  - **Transfer Learning with LR-ASPP**: A lightweight model leveraging MobileNetV3 for object detection and segmentation.
- **Metrics**: Mean Squared Error (MSE) was used for evaluating performance on NYU, while accuracy was used for DIW.

### Experiments & Results
The experiments compared the performance of the two models:
- **U-Net++** achieved better depth estimation results compared to **LR-ASPP**.
- **NYU Test MSE Loss**: LR-ASPP - 0.058, U-Net++ - 0.032
- **DIW Test Accuracy**: LR-ASPP - 58.4%, U-Net++ - 65.32%

### Conclusions & Possible Improvements
The significant difference in model performance was attributed to the larger number of parameters in U-Net++, which allowed it to capture more information. Future work could focus on comparing architectures with similar parameter counts or exploring vision transformers and diffusion models for improved results.

### References
- Oquab, M., et al. "DINOv2: Learning Robust Visual Features without Supervision." arXiv, 2023.
- Mertan, A., et al. "Single Image Depth Estimation: An Overview." Digital Signal Processing, 2021.
- And more (refer to the original report).

---

Feel free to adapt this README to match your preferences or add any additional sections.
