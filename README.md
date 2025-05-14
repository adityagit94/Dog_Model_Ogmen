# Dog Face Landmark Detection

This repository contains the code and resources used for training a keypoint detection model to detect facial landmarks on dogs using YOLOv8 Pose Estimation. The task was part of an assignment requiring implementation of a deep learning model such as SSD, but YOLOv8 was chosen for its performance and simplicity in handling keypoint detection tasks.

## 📁 Dataset

- Labeled with **[Roboflow](https://universe.roboflow.com/adityas-workspace-7fc3f/dog-ogmen/browse?queryText=&pageSize=50&startingIndex=0&browseQuery=true)**
- Annotation type: **Keypoint Detection**
- Format: **YOLOv8 Pose**
- Classes: 1 (`dog`)
- Keypoints per image: 6 (forehead center, left/right eyes, nose, left/right ears)
- All bounding boxes and keypoints were **manually annotated**.

## Model

- 🚀 Model Used: **YOLOv8 (yolov8x-pose-p6 Model)** from [Ultralytics](https://github.com/ultralytics/ultralytics)
- 📈 Trained for 100 epochs using annotated dog images with facial keypoints.

**Directory structure:**
```
dog_dataset/
│
├── train/
├── valid/
├── test/
└── data.yaml
```

---

## 🚀 Model Architecture

I used [Ultralytics YOLOv8](https://github.com/ultralytics/ultralytics) for landmark (keypoint) detection.
