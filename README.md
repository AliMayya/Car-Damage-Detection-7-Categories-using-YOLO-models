# Car-Damage-Detection-7-Categories-using-YOLO-models
This project aims to effectively detect seven different types of car damages
# CarDefectDetection
**Prepared by:**
**Dr. Ali Mayya** (Model preparation, dataset creation and annotation, training, evaluation, and writing)

**Eng Ali Altrkbi** (Dataset collection, training, App design and implementation)

## Table of Contents
- [Part 1 Backend](#part-1-backend)
- [Model creation, training, and evaluation code](#model-creation-training-and-evaluation-code)
- [Evaluation results](#evaluation-results)
- [Test samples](#test-samples)
- [Test samples from Internet](#test-samples-from-internet)
- [Validation curves](#validation-curves)
- [Part2 frontend APP](#part2-frontend-app)
- [Limitation and Future work](#limitation-and-future-work)

## Part 1 Backend
Mission: Design and implement advanced image-based models that detects 7 types of vehicle damage. 
Main Architecture: YOLOV8S, YOLOV12S, YOLOV12N (without pretrained weights)
1.	Collect Dataset:
o	Self-collected images of vehicle damages:

  	a) Number of images: 2090
  	
  	b) Number of annoations: 5507
  	
o	Classes:
1. Bumper detachment: 653
2. Dent  : 941
3. Damaged car body: 165
4. Damaged tire: 240
5. Damaged headlight/taillight: 500
6. Broken glass/windshield: 469
7. Scratch/scrape: 2539
   
Examples:

![image](https://github.com/user-attachments/assets/46800e25-98f4-42f0-a840-b9aa3897e2a4)

![image](https://github.com/user-attachments/assets/dbe3de2e-605f-4a4c-89ec-5d961545564e)


2. Annotate dataset:
   We utilize LabelImg to annotate images using bounding boxes.
        labelImg . classes.txt
   Annotation in LabelImg example:
   
   ![image](https://github.com/user-attachments/assets/d0cd9013-66f3-47c1-ac52-50bb28ce0fc4)

   ![image](https://github.com/user-attachments/assets/36055250-4e8a-492f-a371-a1056309aeba)

   ![image](https://github.com/user-attachments/assets/e351a8b0-f2e0-48dd-9f3c-708b49851f25)



  # Dataset images and labels will be available on demand
   
4. Save images and Labels into two separate folders ("Images", "Labels")
   
5. Create YOLOV core models
   
   5-1- YOLOV8S
   
   5-2- YOLOV12S
   
   5-3- YOLOV12N
   
7. Train models:

   a) Split dataset into training, validation and test

   b) Apply data augmentation to training set

   c) Cretae models and choose training parameters

   d) Train models
  YOLOV12N architecture:
![image](https://github.com/user-attachments/assets/0aae28bd-7ac8-47a1-a5a2-faadb4087b52)

   
9. Evaluate the trained model using both validation and test sets
   
## Model creation, training, and evaluation code
Code file: Car_damage_detection_7_classes_YOLOV12n.ipynb
Output trained model file: carDamageDetectYOLOV12n.pt

## Evaluation results
**Validation set:**

![image](https://github.com/user-attachments/assets/67362cb3-961d-4a1d-a7ab-6dce7e030f0f)


**Test Set:**

![image](https://github.com/user-attachments/assets/1928a991-7dc5-4f76-8ded-21bff6208a2b)


## Test samples
Test sample1:

![image](https://github.com/user-attachments/assets/e070f0b9-d560-4591-89df-61add2010e85)


Test sample2:

![image](https://github.com/user-attachments/assets/e3a0c9de-3542-4ab6-b754-4a92de6788f7)


Test sample3:

![image](https://github.com/user-attachments/assets/d2b751ae-f1ad-4c85-a5f8-2c2dca978b95)


Test sample4:

![image](https://github.com/user-attachments/assets/c5ebfa9e-57bc-4e15-a21b-e278572c9e46)


Test sample5:

![image](https://github.com/user-attachments/assets/02c3cb57-02f2-4ddb-9a64-b7269108a4ec)


Test sample6:

![image](https://github.com/user-attachments/assets/575ea8be-f946-4ad8-8412-a28171ca77f3)


Test sample7:

![image](https://github.com/user-attachments/assets/6d1a1bd7-bef3-4ccd-935e-e497a1f6967a)


## Test samples from Internet

![image](https://github.com/user-attachments/assets/617d9b78-8586-4149-b27a-9d5628907063)


![image](https://github.com/user-attachments/assets/0ed6ff65-251d-4586-b2c1-ea88ab8683e7)


![image](https://github.com/user-attachments/assets/f3333264-9c45-440c-ac83-6dc259570bb0)


![image](https://github.com/user-attachments/assets/1c32e01c-bf53-4e8d-842c-6a9cf0cdd416)


![image](https://github.com/user-attachments/assets/9a39e6c3-0dad-4af1-8fcb-ba46e7c82d4b)


![image](https://github.com/user-attachments/assets/13003a01-33fb-4bc8-9792-8ebd6305836a)


![image](https://github.com/user-attachments/assets/09140efc-7f84-440b-b080-b8b74fa2b16c)


## validation curves

![image](https://github.com/user-attachments/assets/7802519e-ccac-452a-8a42-3b98dc72cbc8)


**Confusion Matrix**

![download](https://github.com/user-attachments/assets/97404a6f-7d85-40d3-b092-3e641b87804d)

**Precision, Recall, mAP50 Curves**

![image](https://github.com/user-attachments/assets/fb7c0429-1771-4144-921b-4476eeecff16)

![image](https://github.com/user-attachments/assets/845d41f1-4882-4542-8f7f-bded2561d5fd)

## Part2 frontend APP
## Quick Start

1. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

2. **Run the application**:
   ```bash
   python app.py
   ```

3. **Open in browser**: `http://localhost:8000`

## Requirements

- Python 3.10
- YOLO model : `YOLOV8s`,`YOLOV12s`

## API Usage

### Upload and Detect
```bash
curl -X POST "http://localhost:8000/detect" \
     -F "file=@your_image.jpg"
```

## API Documentation

- **Swagger UI**: `http://localhost:8000/docs`
- **ReDoc**: `http://localhost:8000/redoc`

## Project Structure

```
webapp/
├── app.py                           # FastAPI application
├── static/index.html               # Web interface  
├── CarDamageDetectYOLOV8 (2).pt   # YOLOv8 model
├── CarDetectYOLOV12.pt            # YOLOv12 model
└── requirements.txt               # Dependencies
```











