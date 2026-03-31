# Plant Disease Detection using Edge-Optimized Deep Learning

## Overview

Plant diseases significantly impact agricultural productivity and global food security. Early and accurate detection is crucial for minimizing crop losses.

This project presents a **lightweight deep learning model** for plant disease detection, specifically optimized for **edge devices (mobile/low-resource environments)**.

---

## Objective

* Detect and classify plant diseases from leaf images
* Achieve high accuracy with **low computational cost**
* Enable **real-time, on-device inference** without cloud dependency

---

## Core Technologies

### Deep Learning Model

* **MobileNetV3-Small (Modified)**
* Lightweight CNN architecture designed for mobile/edge devices

### Key Enhancement

* **Coordinate Attention (CA)**

  * Replaces traditional SE (Squeeze-and-Excitation)
  * Preserves spatial information (important for disease spots)

### Frameworks & Tools

* PyTorch (training)
* ONNX (deployment)
* NumPy, OpenCV (preprocessing)

---

## Dataset

* **PlantVillage Dataset**
* 54,000+ images
* 14 crop species
* 38 classes (healthy + diseased)

As shown in dataset samples (page 4), images include diverse leaf patterns and disease types 

---

## Model Architecture

* Base: MobileNetV3-Small
* Modified with:

  * Coordinate Attention (CA)
  * Depthwise separable convolutions
  * Inverted residual blocks

Architecture diagram (page 5) shows efficient feature extraction pipeline 

---

## Training Strategy

* Transfer Learning (ImageNet weights)
* Frozen feature extractor layers
* Trained classification head
* Optimizer: Adam
* Learning Rate Scheduler: ReduceLROnPlateau
* Early Stopping to prevent overfitting

---

## Results

* **Accuracy:** 98.37%
* **Precision:** 0.98
* **Recall:** 0.98
* **F1-score:** 0.98

Training & validation curves (page 7) show:

* Fast convergence
* Minimal overfitting
* Stable learning behavior 

---

## Model Comparison

| Model              | Parameters | Accuracy   |
| ------------------ | ---------- | ---------- |
| AlexNet            | 60M        | 97.82%     |
| GoogLeNet          | 5M         | 98.37%     |
| **Proposed Model** | **2.5M**   | **98.37%** |

Achieves same accuracy with **~24× fewer parameters** 

---

## Edge Deployment

* Model exported to **ONNX format**
* Enables:

  * Mobile deployment
  * Low-latency inference
  * No internet dependency

Designed for real-world agricultural usage in low-resource environments

---

## Key Insights

* Lightweight models can match heavy architectures
* Spatial attention (CA) improves disease localization
* Efficiency + accuracy trade-off is critical for real-world deployment

---

## Limitations

* Dataset collected in controlled conditions
* Real-world performance may vary (lighting, background noise)

---

## Future Work

* Test on real-field data
* Add disease severity prediction
* Deploy as mobile app / IoT system
* Improve robustness under varying conditions

---

## Authors

* Pratyush Negi
* University of Delhi

---

## Conclusion

This project demonstrates that **edge-optimized deep learning models** can achieve high accuracy while remaining computationally efficient, making them suitable for **real-world agricultural applications**.
