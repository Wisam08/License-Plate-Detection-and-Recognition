# 🚗 License Plate Detection and Recognition



This project performs automatic license plate detection and OCR-based recognition from videos using a fine-tuned YOLOv8 model and EasyOCR. It includes custom logic for text correction, format validation, and temporal stabilization to improve the accuracy and consistency of detected license plates across video frames.

> 📽️ Inspired by [this tutorial](https://www.youtube.com/watch?v=9KnARRqbkzY&list=PLPTV0NXA_ZSgmWYoSpY_2EJzPJjkke4Az&index=27) on YouTube.

---

## 📸 Sample Output

Here is an example of detected license plates:
<img width="1547" height="861" alt="Github pic" src="https://github.com/user-attachments/assets/76150e83-daa2-461e-8612-e8df68f5b593" />

## 🧠 Features

- ✅ Fine-tuned YOLOv8 model for license plate detection.
- ✅ EasyOCR for recognizing text from license plates.
- ✅ Text correction for common OCR misreads (e.g., `0` → `O`, `5` → `S`).
- ✅ Regex validation for Indian license plate format.
- ✅ Temporal smoothing using history-based majority voting.
- ✅ Annotated output video with bounding boxes and overlaid text.

---

## 📌 Expected Plate Format

Supports Indian number plate format (example: `MH12ABC1234` simplified to `MH12ABC`):

```regex
^[A-Z]{2}[0-9]{2}[A-Z]{3}$
```


📦 License-Plate-Recognition-YOLOv8
```
│
├── license_plate_best.pt           # YOLOv8 trained model (not included, add manually)
├── vehicle_video.mp4               # Input test video (you can replace this)
├── output_with_licensev3.mp4       # Output annotated video (auto-generated)
├── yolo_ocr.py                     # Main script
└── README.md                       # This file
