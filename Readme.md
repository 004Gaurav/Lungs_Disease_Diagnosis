# 🩻 X-ray Pneumonia Classifier (FastAPI + PyTorch)

## 🧠 Problem Statement

Pneumonia is a lung infection that causes inflammation in the air sacs (alveoli), leading to coughing, fever, and difficulty breathing.
Accurate and quick diagnosis using **X-ray images** can help doctors start treatment early and save lives.

This project builds a **Deep Learning API** using **PyTorch** and **FastAPI** that classifies X-ray images as:

* **Normal**
* **Pneumonia**

---

## 💡 Proposed Solution

We designed a **Convolutional Neural Network (CNN)** model in **PyTorch** that detects pneumonia from X-ray scans.
The trained model is deployed using **FastAPI**, which allows real-time image upload and prediction.

---

## 🧰 Tech Stack

| Layer                    | Tools / Frameworks         |
| ------------------------ | -------------------------- |
| **Programming Language** | Python 3.8+                |
| **Framework**            | FastAPI                    |
| **Deep Learning**        | PyTorch                    |
| **Image Processing**     | Pillow (PIL), Torchvision  |
| **Deployment**           | Local / Cloud (AWS, Azure) |
| **Version Control**      | Git & GitHub               |

---

## 🧬 Dataset Used

The dataset contains **chest X-ray images** categorized into:

* **Normal**
* **Pneumonia**

The data was provided for research purposes and used to train and test the CNN model for medical image classification.

---

## 🏗️ Project Structure

```
Xray_Pneumonia_Classifier/
│
├── xray/
│   ├── ml/
│   │   ├── model/
│   │   │   └── arch.py       # CNN architecture
│   │   ├── data_ingestion/
│   │   ├── data_transformation/
│   │   ├── model_training/
│   │   └── model_evaluation/
│   ├── logger.py
│   └── exception.py
│
├── app.py                    # FastAPI app
├── requirements.txt
├── xray_model.pth            # Trained model weights
└── README.md
```

---

## ⚙️ How to Run Locally

### Step 1. Clone the Repository

```bash
git clone https://github.com/<your-username>/xray-pneumonia-classifier.git
cd xray-pneumonia-classifier
```

### Step 2. Create and Activate a Virtual Environment

```bash
conda create -p env python=3.8 -y
conda activate ./env
```

### Step 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### Step 4. Run the FastAPI Application

```bash
uvicorn app:app --reload --port 8000
```

Now open your browser and go to:
👉 **[http://127.0.0.1:8000/docs](http://127.0.0.1:8000/docs)**

---

## 🧪 Testing the API

### Endpoint: `/predict`

Upload an X-ray image for classification.

**Example via Swagger UI:**

1. Visit `http://127.0.0.1:8000/docs`
2. Click on **`/predict`**
3. Upload an X-ray image (JPG/PNG)
4. Click **Execute**

**Response Example:**

```json
{
  "prediction_index": 1,
  "prediction_label": "Pneumonia"
}
```

---

## ☁️ Cloud Deployment (Optional)

You can deploy this project using:

* **AWS EC2**
* **Azure Web App**
* **Google Cloud Run**

Make sure to set your environment variables in your cloud settings:

```bash
AWS_ACCESS_KEY_ID=<your-key>
AWS_SECRET_ACCESS_KEY=<your-secret>
AWS_DEFAULT_REGION=<region>
```

---

## 🧩 Model Used

* **Custom CNN Model** (defined in `xray/ml/model/arch.py`)
* Trained using chest X-ray images
* Achieved high accuracy in detecting **Normal vs Pneumonia**

---

## 🔍 Example Architecture Diagram

![xray\_arch](https://user-images.githubusercontent.com/71321529/216753362-aeb34400-d21d-4b21-b2ce-63b86a47b594.jpg)

---

## 🩺 Future Improvements

* Add Grad-CAM for visualizing lung infection areas.
* Improve model generalization with larger datasets.
* Integrate with a user-friendly frontend (React or Streamlit).
* Add multi-class classification for other lung diseases.

---

## ✅ Conclusion

This project demonstrates how **Deep Learning + FastAPI** can power a real-time medical diagnostic API.
It provides a foundation for building intelligent healthcare tools to support faster and more accurate pneumonia screening.

