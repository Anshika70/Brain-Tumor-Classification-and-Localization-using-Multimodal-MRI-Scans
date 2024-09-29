# Brain Tumor Classification and Localization using Multimodal MRI Scans with ResNet-101

## Table of Contents
- [Introduction](#introduction)
- [Dataset](#dataset)
- [Model Architecture](#model-architecture)
- [Installation](#installation)
- [Usage](#usage)
- [Results](#results)
- [Visualization](#visualization)

## Introduction
This project focuses on **brain tumor classification and localization** using **multimodal MRI scans** and deep learning techniques. The model is based on the **ResNet-101 architecture**, which has been adapted to perform both classification and localization of brain tumors from MRI images. This approach utilizes multiple MRI modalities (such as T1, T2, FLAIR, etc.) to enhance accuracy and precision.

The goal of the project is to classify different types of brain tumors and to localize the region of the tumor within the MRI scans, contributing towards aiding clinical diagnosis and treatment planning.

## Dataset
The dataset used in this project consists of multimodal MRI scans, including:
- T1-weighted images (T1)
- T2-weighted images (T2)
- Fluid-attenuated inversion recovery (FLAIR)
- Other MRI modalities (if available)

### Dataset Details:
- Each sample in the dataset includes MRI scans of a patient's brain, with labels for the type of tumor (e.g., glioma, meningioma, pituitary tumor, etc.).
- A segmentation mask is used for localization, marking the area where the tumor is present.
- The dataset is preprocessed before feeding it into the model to ensure uniformity and efficient training.

**Data Source**: The dataset may come from publicly available datasets like the **BRATS** (Brain Tumor Segmentation) dataset or any other MRI-based dataset available in medical imaging.

## Model Architecture
The core of the model is based on **ResNet-101**, a deep convolutional neural network known for its ability to handle complex image classification tasks efficiently due to its residual layers. The ResNet-101 model is fine-tuned for the following tasks:
1. **Classification**: To predict the type of brain tumor based on the MRI scans.
2. **Localization**: To predict the tumor’s location by generating a segmentation mask over the MRI images.

### Key Layers:
- **Residual Blocks**: Helps with deep learning by preventing vanishing gradients.
- **Global Average Pooling**: Used for classification.
- **Convolutional Layers for Segmentation**: Helps generate the tumor mask for localization.

## Installation
To set up this project on your local machine, follow the steps below:

1. Clone the repository:
    ```bash
    git clone https://github.com/your-username/Brain-Tumor-Classification-and-Localization.git
    cd Brain-Tumor-Classification-and-Localization
    ```

2. Install the necessary dependencies:
    ```bash
    pip install -r requirements.txt
    ```

3. Make sure to download the dataset and place it in the `/data` directory.

4. Preprocess the dataset if necessary:
    ```bash
    python preprocess.py
    ```

## Usage
Once the environment is set up and the data is prepared, you can train the model or run predictions as follows:

1. **Train the model**:
    ```bash
    python train.py
    ```

2. **Test the model**:
    ```bash
    python test.py
    ```

3. **Run inference on a new image**:
    ```bash
    python infer.py --input /path/to/mri_scan.png
    ```

### Key Scripts
- `train.py`: Used for training the model on the dataset.
- `test.py`: Evaluates the model on test data.
- `infer.py`: Runs inference for brain tumor classification and localization on new MRI images.

## Results
After training the ResNet-101 model, the following metrics were used to evaluate its performance:
- **Accuracy**: Overall classification accuracy of brain tumor types.
- **Dice Coefficient**: Evaluates the quality of the tumor localization (segmentation).
- **Precision/Recall/F1 Score**: Additional metrics to assess the classification task.

## Visualization
The project includes visualizations comparing the ground truth and predicted tumor localization on the MRI scans.

Here is an example of a **segmentation mask** produced by the model:
![Tumor Localization](./results/tumor_localization_example.png)

The model is also able to classify the type of brain tumor from MRI scans, displaying its predictions as:
- Glioma
- Meningioma
- Pituitary tumor, etc.

