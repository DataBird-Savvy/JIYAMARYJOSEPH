# 🔍 Object Detection Using AI and Traditional CV Techniques

## 👩‍💻 Author Info

- **Name:** Jiya Mary Joseph  
- **Python Version:** Python 3.12.4

---

## 📘 Project Overview

This project demonstrates object detection using two approaches:

1. **AI-Based Approach**
2. **Non-AI (Traditional Computer Vision)**

It includes training a custom YOLO model using Roboflow, leveraging pretrained models, and applying classical image processing techniques.

---

## 🤖 AI-Based Approach

### ✅ Approach 1: Zero-shot Detection with Natural Language Models

- Used model providers that allow human-language prompts for object detection.
- Example: [GROQ](https://groq.com/) with the model `meta-llama/llama-4-scout-17b-16e-instruct`.

### ✅ Approach 2: Pretrained Lightweight YOLO

- Leveraged YOLO models from [Ultralytics](https://github.com/ultralytics/ultralytics).
- Lightweight and efficient for real-time inference.

### ✅ Approach 3: Fine-tuned YOLO with Custom Dataset

#### 🧪 Steps:

1. **Project Setup on Roboflow**
   - Created a new project.
   - Uploaded and labeled images.
   
2. **Dataset Versioning**
   - Performed train/val/test splits.
   - Skipped preprocessing.
   - Augmented images using:
     - Flip
     - Grayscale conversion
     - Rotation

3. **Model Training**
   - **On Roboflow Platform**
     - Used YOLOv11 as base model.
     - Early stopping applied based on validation loss.
   - **On Google Colab**
     - Exported dataset from Roboflow.
     - Trained using YOLOv8 from Ultralytics.

4. **Model Evaluation**

| Metric     | Value   |
|------------|---------|
| mAP        | 98%     |
| Precision  | 92%     |
| Recall     | 96.7%   |

> ![Model Evaluation Result](image.png)

---

## 🧠 Non-AI (Traditional CV) Approach

### 🛠️ Steps:

1. Convert image to **grayscale**.
2. Apply **Gaussian blur** to reduce noise.
3. Use **Otsu's thresholding** with binary inversion.
4. Apply **morphological operations** to isolate white pixels.
5. Perform **distance transform** to compute foreground areas.
6. Identify **sure foreground** and **sure background**.
7. Subtract both to find the **unknown region**.
8. Perform **marker labeling**: set background = 1, unknown = 0.
9. Apply **Watershed Algorithm**:
   - Treat image as a topographic surface.
   - Boundaries marked as `-1`.
10. Draw and count bounding boxes around detected objects.

---

## 📁 Project Structure

