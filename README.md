## Project Overview

This project integrates **image classification** and **object detection** into a single end-to-end pipeline, primarily focused on identifying and classifying vehicles under varying weather and lighting conditions. It utilizes:

1. **ResNet50-based Classification**  
   - Two separate models determine:
     - **Weather**: “Rainny” vs. “Sunny”  
     - **Time of Day**: “Day” vs. “Night”

2. **YOLO-based Object Detection**  
   - Multiple YOLO models (e.g., YOLOv8, YOLOv10x, YOLOv11n) are individually trained on different environments (Sunny Day, Sunny Night, Rainny Day, Rainny Night).
   - An **ensembling** strategy combines the output of multiple YOLO models for higher accuracy.
   - A **unified YAML configuration** merges all datasets, enabling a single YOLO model to handle diverse conditions in one go.

**Key highlights**:
- **Memory Management**: Automatically clears GPU caches to optimize training in a Kaggle environment.
- **Data Handling**: Organizes and labels images using Pandas DataFrames, with Keras `ImageDataGenerator` performing data augmentation.
- **Evaluation & Visualization**:  
  - Produces confusion matrices and classification reports for the ResNet models.  
  - Uses mean Average Precision (mAP) metrics for YOLO models and displays detection results with bounding boxes via OpenCV and Matplotlib.  

Overall, this project demonstrates a robust workflow that goes from data preparation and labeling all the way to advanced training and evaluation of both classification and detection models, making it a comprehensive resource for multi-condition vehicle detection and classification tasks.

