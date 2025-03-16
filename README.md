
# Warehouse Detection Project

## Overview
This project focuses on detecting various objects within a warehouse environment using the YOLO (You Only Look Once) object detection model. The dataset consists of multiple classes such as boxes, carts, crates, fire extinguishers, forklifts, fuse boxes, KLT bins, and pallets. The training process was conducted using the `YOLO11n` model with 50 epochs, resulting in high accuracy and performance metrics.

## Dataset Details

### Classes
The dataset includes the following classes:
- box
- cart
- crate
- fire_extinguisher
- forklift
- fuse_box
- klt_bin
- pallet

### Distribution of Images
#### Training Set
| Class             | Number of Images |
|-------------------|------------------|
| box               | 1472             |
| cart              | 1873             |
| crate             | 4287             |
| fire_extinguisher | 734              |
| forklift          | 1103             |
| fuse_box          | 4363             |
| klt_bin           | 5312             |
| pallet            | 337              |

#### Validation Set
| Class             | Number of Images |
|-------------------|------------------|
| box               | 120              |
| cart              | 169              |
| crate             | 381              |
| fire_extinguisher | 67               |
| forklift          | 77               |
| fuse_box          | 396              |
| klt_bin           | 481              |
| pallet            | 25               |

#### Test Set
| Class             | Number of Images |
|-------------------|------------------|
| box               | 75               |
| cart              | 106              |
| crate             | 259              |
| fire_extinguisher | 39               |
| forklift          | 52               |
| fuse_box          | 251              |
| klt_bin           | 307              |
| pallet            | 19               |

## Training Process

### Model Configuration
- **Model**: YOLO11n
- **Training Data**: `/content/Indoor-1/data.yaml`
- **Epochs**: 50
- **Image Size**: 700x700
- **Batch Size**: 16
- **Device**: GPU (Tesla T4)
- **Project Name**: `warehouse_detection`

### Training Results
The training process completed in approximately 1.978 hours. The final results are summarized below:

- **Box Loss**: 0.5799
- **Class Loss**: 0.3367
- **DFL Loss**: 0.812
- **Instances**: 146
- **Size**: 704

### Performance Metrics
- **Precision**: 0.913
- **Recall**: 0.796
- **mAP50**: 0.842
- **mAP50-95**: 0.693

### Class-wise Performance
| Class             | Precision | Recall | mAP50 | mAP50-95 |
|-------------------|-----------|--------|-------|----------|
| all               | 0.913     | 0.796  | 0.842 | 0.693    |
| box               | 0.95      | 0.933  | 0.965 | 0.866    |
| cart              | 0.843     | 0.663  | 0.742 | 0.57     |
| crate             | 0.959     | 0.967  | 0.983 | 0.865    |
| fire_extinguisher | 0.919     | 0.744  | 0.816 | 0.514    |
| forklift          | 0.991     | 1.0    | 0.995 | 0.97     |
| fuse_box          | 0.832     | 0.415  | 0.469 | 0.251    |
| klt_bin           | 0.786     | 0.504  | 0.639 | 0.368    |
| pallet            | 0.965     | 0.94   | 0.971 | 0.876    |
| sign              | 0.975     | 1.0    | 0.995 | 0.955    |

## Visualizations

### Confusion Matrix Normalized
The confusion matrix provides insights into the classification performance of the model. Each cell represents the proportion of instances that were predicted to belong to a particular class when they actually belonged to another class.

### Training and Validation Metrics
These graphs show the evolution of various metrics during the training process, including losses, precision, recall, and mAP scores. The smooth lines represent smoothed versions of the raw data points.

## Usage

To use this model, follow these steps:
1. Clone the repository.
2. Install the necessary dependencies.
3. Load the trained model weights from `runs/detect/warehouse_detection/weights/best.pt`.
4. Use the model to detect objects in new images or videos.

## Conclusion
This project demonstrates the effectiveness of the YOLO11n model in detecting various objects within a warehouse environment. The high precision, recall, and mAP scores indicate that the model performs well across different classes. Future work could involve further fine-tuning the model and expanding the dataset to improve performance even more.
