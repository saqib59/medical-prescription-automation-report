# Medicine Prescription Automation

Automated recognition of handwritten doctor prescriptions using Optical Character Recognition (OCR) and a Convolutional Neural Network (CNN), deployed as a web application.

## Overview

Doctors' handwritten prescriptions are often hard for patients to read, leading to confusion about medicine names, dosages, and intake schedules. This project uses deep learning and image processing to automatically recognize handwritten medicine names from a prescription image and convert them into clear, readable digital text.

## How It Works

1. **Image Pre-processing** – captured prescription images are resized, converted to grayscale, and cleaned up (binarization, thresholding, dilation) to remove noise.
2. **Line & Word Segmentation** – contour detection is used to isolate individual lines, then individual words, from the prescription image.
3. **Feature Extraction** – each word image is processed and prepared for the recognition model.
4. **Character/Word Recognition** – a custom-trained CNN (built with TensorFlow/Keras) predicts the medicine name from the processed image.
5. **Web Interface** – a Flask-based web app lets users upload/crop a prescription image and view the predicted medicine name.

## Dataset

- ~300 real handwritten prescriptions collected from local doctors (Sindh Government Hospital, Karachi, and other contributors).
- Images labeled with the correct medicine name to build a custom image dataset (`X`) and label file (`Y`).
- Data augmentation applied to increase dataset size and improve model generalization.

## Model

- Custom CNN architecture with multiple convolutional, max-pooling, and batch-normalization layers, followed by dense layers with ReLU/Softmax activations.
- Loss: `sparse_categorical_crossentropy` | Optimizer: `Adam` | Metric: `accuracy`
- **Training accuracy:** ~90% | **Validation accuracy:** ~70%

## Tech Stack

- **Language:** Python
- **Deep Learning:** TensorFlow, Keras
- **Image Processing:** OpenCV
- **Web Framework:** Flask
- **Frontend:** HTML, Bootstrap, CSS, JavaScript
- **Deployment:** Heroku

## Project Structure (suggested)

```
├── dataset/              # Collected prescription images & labels
├── preprocessing/        # Image pre-processing & segmentation scripts
├── model/                # CNN training, evaluation & saved model
├── app/                  # Flask application (routes, templates, static files)
├── requirements.txt
└── README.md
```

## Future Scope

- Mobile application for on-the-go prescription scanning
- Larger, more diverse handwriting dataset for improved accuracy
- Extension to help improve handwriting recognition for children's learning

## Authors

- Saqib Ali
- Shahzad Ahmed
- Shahzaib Siddiqui

**Supervisor:** Prof. Farhan Ahmed Siddiqui — Department of Computer Science, University of Karachi (UBIT)

## License

This project was developed as a Final Year Project (BS Software Engineering, 2022) and is shared for educational/portfolio purposes.
