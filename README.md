
# 🐶 Dog Face Landmark Detection using YOLOv8 Pose

This project aims to detect facial landmarks on dogs using a deep learning model trained with YOLOv8 Pose. The dataset was annotated using Roboflow and includes labeled keypoints for dog facial features such as eyes, nose, and forehead.

---

## 📁 Dataset

- Labeled with **[Roboflow](https://universe.roboflow.com/adityas-workspace-7fc3f/dog-ogmen/browse?queryText=&pageSize=50&startingIndex=0&browseQuery=true)**
- Annotation type: **Keypoint Detection**
- Format: **YOLOv8 Pose**
- Classes: 1 (`dog`)
- Keypoints per image: 6 (forehead center, left/right eyes, nose, left/right brows)
- All bounding boxes and keypoints were **manually annotated**.

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

We use [Ultralytics YOLOv8](https://github.com/ultralytics/ultralytics) — specifically the `YOLOv8n-pose.pt` or similar — for landmark (keypoint) detection.

Model options:
- `yolov8n-pose.pt` - lightweight and fast
- `yolov8s/m/l-pose.pt` - more accurate but larger

---

## 🛠️ Installation

```bash
pip install ultralytics
```

(Optional: If using Colab, clone repo and unzip dataset)

---

## 🧠 Training

```python
from ultralytics import YOLO

# Load the model
model = YOLO("yolov8n-pose.pt")  # or yolov8s/m/l-pose.pt

# Train
model.train(
    data="path/to/data.yaml",
    epochs=50,
    imgsz=416,
    batch=8,
    name="dog_model"
)
```

Training logs and weights are saved to:
```
runs/pose/dog_model/
```

---

## 📊 Evaluation Results

After training:
```
Box Precision (P): ~0.0
Box Recall (R): ~0.0
Pose Precision (P): ~0.005
Pose mAP50: ~0.056
```

**Note:** Results suggest underfitting or poor data quality — improvements are listed below.

---

## 📈 Improvements Suggested

- ✅ Use a **larger and more diverse dataset**
- ✅ Make sure **keypoints are clearly visible** in all images
- ✅ Ensure all keypoints are labeled correctly (Roboflow has a quality check tool)
- ✅ Train longer (`epochs=100`)
- ✅ Try a larger model (`yolov8s-pose.pt` or `yolov8m-pose.pt`)

---

## 🖼️ Inference

```python
results = model.predict(source="path/to/image.jpg", conf=0.25, save=True)
```

Results will be saved in `runs/pose/predict/`.

---

## 📁 Outputs

Annotated image example (bounding box + keypoints):

![Example Output](path/to/output_image.jpg)

---

## 📄 License

This project is open-source under the MIT License.

---

## 👨‍💻 Author

Created for coursework on dog pose estimation using deep learning.  
Feel free to fork, extend or contribute!
