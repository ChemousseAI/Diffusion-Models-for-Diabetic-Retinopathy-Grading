# Diffusion-Models-for-Diabetic-Retinopathy-Grading


📄 Published Research Paper

[![Paper](https://img.shields.io/badge/Paper-PDF-red)](#)
[![Python](https://img.shields.io/badge/Python-3.10+-blue)](#)
[![PyTorch](https://img.shields.io/badge/PyTorch-2.x-orange)](#)
[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](LICENSE)

🏥 Medical Imaging | 🧠 Deep Learning | 🎨 Diffusion Models

This repository contains the official implementation of our published work: "**Enhancing Diabetic Retinopathy Grading with Advanced Diffusion Models**" (*this work has been published in 28 July 2024*)

link: https://link.springer.com/chapter/10.1007/978-981-97-3559-4_17


The paper's framework consists of two main components: data generation and classification. 

<img width="4100" height="660" alt="mermaid-diagram" src="https://github.com/user-attachments/assets/c6516d5a-3a68-435b-af3e-72d5a5681d1a" />


## Overview

Medical image classification is often hindered by limited and imbalanced datasets. This project investigates the use of advanced diffusion models as a data augmentation strategy for diabetic retinopathy grading.

Using the IDRiD dataset, we compare traditional image augmentation techniques against diffusion-based augmentation and evaluate their impact on two deep learning classifiers: a custom CNN and a fine-tuned ResNet-50.

Our findings demonstrate that diffusion-generated retinal images improve classification performance and reduce overfitting, particularly in underrepresented classes.



## Problem Statement

Deep learning systems have demonstrated remarkable performance in medical image analysis. However, their success heavily depends on the availability of large, balanced, and accurately annotated datasets.

In diabetic retinopathy grading, obtaining such datasets is challenging because:

* Medical image collection and annotation are expensive and time-consuming.
* Expert clinical labeling is required.
* Public datasets are often limited in size.
* Severe class imbalance exists, particularly for advanced disease stages.

Traditional augmentation techniques such as flipping, rotation, and brightness adjustment increase the number of training samples but do not introduce new pathological patterns. Consequently, models remain vulnerable to overfitting and often struggle to generalize to underrepresented classes.

This work explores whether diffusion models can generate realistic retinal images that enrich the training distribution and improve classification performance.



## Methodology

### Dataset

Experiments were conducted on the **IDRiD (Indian Diabetic Retinopathy Image Dataset)**, which contains retinal fundus photographs annotated according to five diabetic retinopathy severity grades (0–4).

* 516 retinal fundus images
* Resolution: 4288 × 2848
* Five diabetic retinopathy severity grades (0–4)
* Train/Test split:

  * Training: 413 images
  * Testing: 103 images

The dataset is highly imbalanced, motivating the use of data augmentation techniques.

<img width="531" height="420" alt="image" src="https://github.com/user-attachments/assets/13811a32-c01a-4293-a254-53eb6eb0865d" />


### Data Augmentation Strategies

Two augmentation pipelines were compared:

#### 1. Traditional Augmentation

* Horizontal flipping
* Vertical flipping
* Brightness/intensity transformations

These methods generate variations of existing images while preserving their original visual content.

<img width="1099" height="259" alt="image" src="https://github.com/user-attachments/assets/af086534-df95-49da-9015-4ec4eeecce6c" />


#### 2. Diffusion-Based Augmentation

A diffusion-model-driven image-to-image generation pipeline was employed to synthesize new retinal images while preserving disease-specific characteristics.

The generated samples were used to:

* Balance the class distribution
* Increase dataset diversity
* Introduce novel visual variations that cannot be achieved through standard transformations

After augmentation, the dataset was balanced across all severity grades, resulting in approximately equal representation for each class.

### Classification Models

Two deep learning classifiers were evaluated:

#### Custom CNN

* Three convolutional blocks
* Batch normalization
* Fully connected layers with dropout regularization
* Adam optimizer

#### Fine-Tuned ResNet-50

* Pretrained on ImageNet
* Transfer learning framework
* Final classification layers replaced and fine-tuned for DR grading

Both models were trained under identical conditions using either traditionally augmented data or diffusion-augmented data.

<img width="1700" height="560" alt="image" src="https://github.com/user-attachments/assets/f23f5f85-4964-424e-b9fc-080b2f593fd3" />

## Generated Images Section

* Original retinal images:

  <img width="1266" height="323" alt="image" src="https://github.com/user-attachments/assets/4a3c37a9-e3cc-45ec-925c-2bc1aa7fb4ef" />

  
* Generated retinal images by Diffusion model:

  <img width="1266" height="323" alt="image" src="https://github.com/user-attachments/assets/3ad0c939-bfdd-43a0-ac24-5148bcaef506" />




## Results

### Performance Comparison


| Model                               | Accuracy   |
| ----------------------------------- | ---------- |
| CNN + Traditional Augmentation      | 38.83%     |
| CNN + Diffusion Augmentation        | 44.66%     |
| ResNet50 + Traditional Augmentation | 41.74%     |
| ResNet50 + Diffusion Augmentation   | **53.40%** |



### Key Findings

✅ Diffusion-based augmentation consistently improved diabetic retinopathy grading performance.

✅ Diffusion models improved classification performance.

✅ Diffusion augmentation reduced overfitting.

✅ ResNet-50 achieved the best result, reaching **53.40% accuracy**.

✅ Synthetic retinal images reduced overfitting and improved model generalization.

✅ Minority disease grades benefited from better representation and recall.

✅ Demonstrated the effectiveness of diffusion models as a data augmentation strategy for medical imaging.


These results demonstrate that diffusion models can provide richer and more informative training samples than conventional augmentation techniques.



## Impact

This work highlights the potential of diffusion models as a powerful data augmentation tool for medical imaging applications.

### Scientific Impact

* Demonstrates the applicability of modern diffusion models in ophthalmology.
* Provides evidence that generative AI can improve diagnostic model training in low-data environments.
* Contributes to the growing body of research on synthetic medical image generation.

### Clinical Impact

* Supports the development of more robust automated diabetic retinopathy screening systems.
* Helps address data scarcity and class imbalance in medical datasets.
* May improve early detection of vision-threatening retinal diseases through better-performing AI models.

### Future Directions

Future research may investigate:

* Larger-scale diffusion-generated datasets.
* Domain-specific medical diffusion models.
* Multi-modal augmentation strategies.
* Integration with newer vision architectures.
* Evaluation on additional retinal imaging datasets.



## Why This Project Matters

Medical datasets are difficult and expensive to collect and annotate. Diffusion models provide a promising approach for generating realistic synthetic data that can improve model generalization and reduce the impact of class imbalance.

This work demonstrates how modern generative AI techniques can be applied to solve practical challenges in medical image analysis.

---
# Citation Section

```bibtex
@inproceedings{ouissam2025prodnet,
  title={ProdNet: A Lightweight Network for Fast Discovery of Matrix Multiplication Algorithms},
  author={Ouissam Lakas, Badia and Berdjouh, Chemousse and Bounane, Khadra and Lamine Kherfi, Mohammed and Aiadi, Oussama and Brahim Belhouari, Samir},
  booktitle={International Conference on Intelligent Systems and Pattern Recognition},
  pages={95--108},
  year={2025},
  organization={Springer}
}
```

---
Free PDF: https://drive.google.com/file/d/1fQWRAKs7mhNk2_jM2068IROaBr8bQ8aa/view?usp=sharing
