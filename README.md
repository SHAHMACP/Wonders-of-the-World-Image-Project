# 🌍 Wonders of the World - Image Recognition & Analysis
This project explores and analyzes images of the **12 Wonders of the World** using computer vision and basic data analytics techniques.

## 🏁 Project Overview

- 📸 Image Classification of Wonders
- 📊 Exploratory Data Analysis (EDA) - Annotations and Labelling
- 📂 Dataset organized by class
- 🤖 Model training and predictions
- 🧠 Visual analytics and screenshots included

---
## 🔹  **Create a New Project**
- Go to [Roboflow](https://app.roboflow.com/)
- Click **"Create New Project"**
- Choose:
  - Project name (e.g., Wonders of the World)
  - Project type: *Object Detection*, *Classification*, or *Segmentation*
  - Annotation type: *Bounding box*, *Polygon*, etc.
![image](https://github.com/user-attachments/assets/3fc0a0fd-f638-4737-ad32-ad7ae727ef5d)




## 🔹 **Upload Your Images**
- Drag and drop your image folder or upload them one-by-one.
- You can upload `.jpg`, `.png`, `.jpeg`, etc.
 ![image](https://github.com/user-attachments/assets/fc849376-1084-4d59-9c19-d78cd81c5a06)
 

## 🔹  **Start Annotating**

Labeling or annotating images is a **key step** in computer vision projects — it tells the model what it needs to learn from each image (like where the "Taj Mahal" is or which part is "Christ the Redeemer").

- Click **Annotate** tab.
- For **Object Detection**:
  - Draw **bounding boxes** around objects (like "Taj Mahal").
  - Enter the **label** (you can reuse existing or create new ones).
- For **Classification**:
  - Assign one label per image (no boxes needed).
   ![image](https://github.com/user-attachments/assets/ca62a1a0-8f13-41fb-a273-8c1a6eacdc57) 

#### 🔹  **Use Auto-Labeling (Optional)**
- Roboflow supports **AI-assisted labeling** using:
  - Pre-trained models
  - Custom models trained on your data
- Speeds up the annotation process.

#### 🔹 **Save and Review**
- Save annotations for each image.
- You can **filter**, **review**, and **edit** labels later.
- Ensure consistent labeling across your dataset.


### 💡 Annotation Best Practices


> 🟩 Use tight bounding boxes : Avoids capturing background noise
> 
> 🏷️ Consistent naming : Use the **same spelling** and **case** for labels
> 
> 🖼️ Label all relevant objects : Don’t leave out any object in an image
> 
> 🔍 Zoom in : Helps to annotate small or fine details 


### ✅ Benefits of Using Roboflow for Annotation

- Web-based (no installation)
- Fast annotation tools
- Auto-labeling support
- Clean dataset exports
- Built-in dataset versioning
- Supports collaboration
---

## 📥 After Labeling: Generate Dataset

Once labeling is done:
1. Click **"Generate Dataset"**
2. Choose your export format (YOLOv8, COCO, TensorFlow, etc.)
3. Download the annotated dataset

It will include:
```
images/
labels/
data.yaml (or equivalent config)
```

---



## 🧩 What is Train/Test/Valid Split?

When building a machine learning model (especially for images), your dataset is split into:


>  **Train**    : Used to teach the model (majority of data)
>    
> **Validation** : Used to tune model parameters & avoid overfitting.
> 
>  **Test** : Used to check how well the model performs on unseen data 


Roboflow offers an automatic split during dataset generation.

 **Note**: More training data generally improves accuracy, but validation and test data are crucial to measure how well your model generalizes.


### ⚙️ How to Do It in Roboflow

1. Go to your **Project Dashboard**.
2. Click **"Generate Dataset"**.
3. You'll see a slider where you can adjust:
   - Training %
   - Validation %
   - Test %
4. Roboflow will randomly (or smartly) assign images into those sets.
5. You can also **manually assign** images if needed (advanced tab).

![image](https://github.com/user-attachments/assets/bcf68160-57f3-4760-90b4-14fff044f9cd)


---

## Model Training

- Model: CNN (Keras/TensorFlow) or YOLOv8
- 80/20 split for training/testing
- Used `ImageDataGenerator` for augmentation

![image](https://github.com/user-attachments/assets/d50f6ffe-e92a-4cb5-baff-c4e750169fea)


---


## 🧼🌀 Image Preprocessing & Augmentation 


**Preprocessing** is the process of preparing raw images to make them suitable for training a machine learning model. It ensures consistency in the dataset.

 ✅ Common Preprocessing Techniques

> **Resizing**      : Makes all images the same dimensions (e.g., 416x416 or 640x640).
> 
> **Grayscale**     : Converts color images to black & white (if needed).
> 
> **Normalization** : Scales pixel values (e.g., from 0–255 to 0–1) for faster and stable training.
> 
> **Cropping**      : Focuses on key regions and removes irrelevant background.
> 
> **Removing noise**: Smoothens the image using filters (Gaussian blur, etc.).
> 

 📍 In Roboflow, preprocessing can be applied during **"Generate Dataset"** step.

🧰 Available preprocessing tools:
- Resize to square
- Auto-orient
- Convert to grayscale
- Filter corrupt or duplicate images


### 🔹 What is Augmentation?

**Augmentation** is the process of creating new training images from your existing images by applying random transformations. It increases the variety of data and helps the model generalize better.

 ✅ Common Augmentation Techniques


> **Flip (Horizontal/Vertical)**: Mirrors image
> 
> **Rotation**     : Rotates image (e.g., by 15° or 90°)
> 
> **Zoom**         : Randomly zooms into part of the image
> 
> **Brightness/Contrast Change** : Simulates different lighting
> 
> **Shear/Stretch**: Slants the image slightly
> 
> **Cutout**       : Randomly blacks out sections
> 
> **Noise Injection** : Adds random pixel noise
> 

![image](https://github.com/user-attachments/assets/68337554-914f-4270-8ab8-b7775320ee88)


### 🧠 Why Use Augmentation?


> Reduces Overfitting              : Model sees more variety
> 
> Mimics Real-World Conditions     : Brightness, orientation changes, etc.
> 
> Works better with small datasets : More training data from fewer examples
> 


### ⚙️ In Roboflow

- Go to **"Generate Dataset"**
- Choose **"Augmentations"**
- You can add:
  - Flip
  - Blur
  - Noise
  - Rotation
  - Hue/Saturation shifts
  - Mosaic & more
- You can also select how many **augmented copies** to create per image (e.g., 2x, 3x)

![image](https://github.com/user-attachments/assets/b2430f33-803d-4e93-976c-77525ae008e6)



Too much augmentation = unnatural data → may confuse the model. Choose smart combinations that resemble real-world variations.

---
## Dataset Analytics
![image](https://github.com/user-attachments/assets/696bb692-0d04-4b05-b704-25ffd59cb8f7)

---
![image](https://github.com/user-attachments/assets/93e72007-841d-4f89-b5a0-c9a859a23ea5)

---
## Predictions

![image](https://github.com/user-attachments/assets/a3e3158d-622f-4a28-ad0f-0bf3e07fe578)


- Predictions on unseen images

![image](https://github.com/user-attachments/assets/f2257eb2-8881-41c3-a913-343643026973)




---

## 🧠 Future Work

- Deploy model as web app using Streamlit or Flask
- Add more wonders or monuments

---

