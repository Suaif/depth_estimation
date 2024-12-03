# Single Image Depth Estimation (20232024)

This project was part of the masters course: Deep Learning for Image and Video Processing at Maastricht University

### Project Overview
This project focuses on Single Image Depth Estimation (monocular depth estimation), which involves predicting the depth value for every pixel in an RGB image. This task is crucial in fields like autonomous vehicles, robotics, and augmented reality, and is particularly challenging due to the high variability in image structure and composition.

### Datasets
Two datasets were used:
- **NYU Depth V2**: A widely-used benchmark dataset consisting of 1449 indoor scenes captured with RGB and Depth cameras.
- **Depth in the Wild (DIW)**: A challenging dataset with 500,000 images gathered from Flickr, annotated only with relative depth between pairs of points.

### Methodology
- **Data Preprocessing**: Both datasets were resized to 200x200 resolution for computational efficiency.
- **Training Process**: Models were trained first on NYU Depth V2 and then fine-tuned with DIW.
- **Models**:
  - **U-Net++**: A widely-used architecture for semantic segmentation, adapted here for depth estimation.
  - **LR-ASPP (Little Reduced Atrous Spatial Pyramid Pooling)**: A lightweight model leveraging MobileNetV3 for object detection and segmentation.
- **Metrics**: Mean Squared Error (MSE) was used to evaluate performance on NYU, while accuracy was used for DIW.

### Experiments & Results
The experiments compared the performance of the two models:
- **U-Net++** achieved better depth estimation results in both datasets when compared to **LR-ASPP**.
- **NYU Test MSE Loss**: LR-ASPP - 0.058, U-Net++ - 0.032
- **DIW Test Accuracy**: LR-ASPP - 58.4%, U-Net++ - 65.32%

### Conclusions & Possible Improvements
The significant difference in model performance was attributed to the larger number of parameters in U-Net++, which allowed it to capture more information. 

Future work could focus on comparing architectures with similar parameter counts or exploring vision transformers and diffusion models for improved results.

### References
- W. Chen, et al. “Single-Image Depth Perception in the Wild" 2016.
- N. Silberman, D. Hoiem, P. Kohli, and R. Fergus, “Indoor Segmentation and Support Inference from RGBD Images.”
- Z. Zhou, et al. "UNet++: A Nested U-Net Architecture for Medical Image Segmentation." 2018.
- M. Sandler, “MobileNetV2: Inverted Residuals and Linear Bottlenecks" 2018
- And more (refer to the original report).
