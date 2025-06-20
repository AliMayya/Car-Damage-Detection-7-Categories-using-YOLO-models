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



   Dataset images and labels are located in Dataset.rar file
   
4. Save images and Labels into two separate folders ("Images", "Labels")
   
5. Create YOLOV8 core model
   
6. Train model using the training set and apply the augmentation operations during training
   
7. Evaluate the trained model using both validation and test sets
   
## Model creation, training, and evaluation code
Code file: CarDefectsDetectionYOLOV8.ipynb
Output trained model file: carDamageDetectYOLOV8.pt

## Evaluation results
**Validation set:**

![image](https://github.com/user-attachments/assets/bade578c-2d0f-4512-865a-b00008a2739a)


**Test Set:**

![image](https://github.com/user-attachments/assets/c5742c6c-52fd-450b-9cca-b240f2e8fe1f)

## Test samples
Test sample1:

![image](https://github.com/user-attachments/assets/9062be5a-d4fc-48ba-a179-00a3bc95214e)
