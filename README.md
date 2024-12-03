# depth_estimation
Single Image Depth Estimation

Overview

This project focuses on Single Image Depth Estimation (monocular depth estimation), which involves predicting the depth value for every pixel in an RGB image. This task is crucial in fields like autonomous vehicles, robotics, and augmented reality, and is particularly challenging due to the high variability in image structure and composition.

Datasets Used

NYU Depth V2: A dataset containing 1449 indoor RGB images with depth maps, used for initial training.

Depth in the Wild (DIW): A dataset of 500,000 images with depth relationships between point pairs, which adds a significant challenge to depth estimation due to its variability.

Methodology

The approach involves data preprocessing to resize images for efficient training and the use of transfer learning to overcome computational constraints. Two models were implemented:

U-Net++: A popular encoder-decoder architecture used for semantic segmentation, pretrained with ResNeXt50 weights.

LR-ASPP: A lightweight architecture combining MobileNetV3 and Atrous Spatial Pyramid Pooling to improve feature extraction efficiency.

Results

U-Net++ outperformed LR-ASPP in both datasets, achieving lower loss and higher accuracy in depth prediction.

NYU Dataset: U-Net++ achieved a lower Mean Squared Error (MSE) of 0.032 compared to LR-ASPP's 0.058.

DIW Dataset: U-Net++ achieved a test accuracy of 65.32%, while LR-ASPP achieved 58.4%.

Conclusions

The number of parameters played a key role in the performance difference between the models. U-Net++ was able to better capture depth information, while LR-ASPP struggled due to its smaller size. Future work includes testing models with similar parameter counts or experimenting with vision transformers and diffusion models for further improvement.

How to Run the Project

Clone the repository:

git clone <repository-url>

Navigate to the project directory:

cd single_image_depth_estimation

Install the required dependencies:

pip install -r requirements.txt

Run the training script:

python train.py

Dependencies

Python 3.8+

PyTorch

NumPy

OpenCV

scikit-learn

License

This project is licensed under the MIT License - see the LICENSE file for details.

