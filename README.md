# Blood-Parasite-Detection-yolov8
AI-Powered Detection of Blood Parasites in Microscopy Images using YOLOv8

Early-stage machine learning model to detect and classify bloodborne parasites (*Plasmodium* and *Trypanosome*) in microscopy images. This project is part of an initiative to explore AI-assisted diagnostics for infectious diseases, especially in resource-limited healthcare settings.

## Description

This project applies object detection using YOLOv8 to identify and distinguish between two blood parasites: *Plasmodium*, which causes malaria, and *Trypanosome*, which causes sleeping sickness. The current prototype serves as a proof of concept for integrating computer vision into diagnostic workflows in clinical labs or telepathology platforms.

The goal is to build toward a full pipeline with segmentation and clinical decision support applications, while remaining lightweight enough for scalable deployment in low-resource environments.

## Getting Started

### Dependencies

- Python 3.10+
- Google Colab (recommended)
- Required libraries:
  - `ultralytics`
  - `opencv-python`
  - `matplotlib`
  - `pandas`
  - `seaborn`

To install dependencies locally:
```bash
pip install -r requirements.txt
```
### Installing
1. Clone the repository:
```bash
git clone https://github.com/yourusername/blood-parasite-detection-yolov8.git
cd blood-parasite-detection-yolov8
```
2. Add your dataset in YOLO format under a data/ directory.
Make sure you follow the correct YOLO directory structure:
```bash
/data
  /images
    /train
    /val
  /labels
    /train
    /val
```
###Executing Program
1. To train the model:
```bash
yolo task=detect mode=train model=yolov8n.pt data=data.yaml epochs=50 imgsz=640
```
2. To predict on a new image:
```bash
yolo task=detect mode=predict model=runs/detect/train/weights/best.pt source=path_to_image.jpg
```
3. To evaluate:
```bash
yolo task=detect mode=val model=runs/detect/train/weights/best.pt data=data.yaml
```
