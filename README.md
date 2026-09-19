# Safety Helmet Detection — YOLOv8

**AIRI Team PITB — AI Internship Task 1**

An end-to-end object detection system that detects **Helmet** and **No-helmet** cases in workplace/road-safety images, built using YOLOv8.

## Problem Statement

This project detects helmet and no-helmet cases in workplace or road-safety images. The system can help in basic safety monitoring by identifying people who are not wearing helmets.

**Classes:** helmet, no_helmet (2 classes — within the task's allowed range of 2–5 classes)

## Dataset

- Combined dataset in YOLOv8 format, split 70% train / 20% valid / 10% test
- Sourced and annotated via Roboflow, exported in YOLO format
- Classes: helmet, no_helmet

## Tools & Technologies

- Python, Google Colab, Google Drive
- YOLOv8 (Ultralytics)
- OpenCV, Matplotlib
- Roboflow (annotation & export)

## Project Structure

training_notebook.ipynb   - Full training, evaluation, inference pipeline
data.yaml                 - Dataset configuration
best.pt                   - Trained YOLOv8n model weights
final_results/            - Confusion matrix, PR/F1 curves, training curves
final_predictions_15/     - 15 sample prediction images (boxes + labels + confidence)
requirements.txt          - Python dependencies

## Model Training

- Model: YOLOv8n (pretrained on COCO)
- Epochs: 30
- Image size: 640
- Platform: Google Colab

## Evaluation

The trained model was evaluated on the held-out test set using Precision, Recall, mAP@0.5, and mAP@0.5:0.95. Confusion matrix and loss curves are available in final_results/.

## Inference

The model was run on unseen test images; sample outputs with bounding boxes, class labels, and confidence scores are available in final_predictions_15/.

## Error Analysis

A manual review of 10 representative predictions identified recurring issues: false negatives (missed objects, especially in crowded/small-object scenes), duplicate/overlapping detections, and occasional low-confidence or wrong-class predictions. Full details are documented in the notebook (Phase 10) and final report.

## How to Run

1. Open training_notebook.ipynb in Google Colab
2. Mount Google Drive and install dependencies: pip install -r requirements.txt
3. Update DATA_YAML path if needed
4. Run cells top to bottom (training cell can be skipped — trained weights are provided in best.pt)

## Author

Arisha Azhar — AIRI Team PITB AI Internship
