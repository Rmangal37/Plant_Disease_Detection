# 🌱 PlantGuard — AI Powered Plant Disease Detection & Treatment Advisor

PlantGuard is a deep learning–driven system that identifies plant leaf diseases with high accuracy and generates practical treatment recommendations using Generative AI.

Built to support farmers, researchers, and agri-tech solutions, the platform combines computer vision with intelligent language models to transform a simple leaf image into clear, actionable guidance.

---

## 📌 Project Overview

Plant diseases are one of the biggest threats to agricultural productivity. Early detection is critical, yet manual inspection requires expertise and time.

PlantGuard automates this process.

Upload a leaf image → detect the disease → receive AI-generated treatment advice in your preferred language.

### Key Highlights

* **Accuracy:** ~96–99%
* **Coverage:** 38 conditions (diseased + healthy)
* **Plant Species:** 14
* **Languages:** English, Hindi, Marathi
* **Interface:** Clean, user-friendly web application

---

## 🚀 What Makes PlantGuard Strong

* Deep learning model optimized for high performance without excessive computational cost
* Lightweight architecture suitable for scalable deployment
* Generative AI integration that converts predictions into farmer-friendly explanations
* Built with a practical, real-world use case in mind

This is not just a classifier. It is a decision-support tool.

---

## 🧠 System Architecture (High Level Flow)

1. User uploads a plant leaf image via the web app
2. Image is transformed (resize, normalize)
3. Trained **ResNet9** model predicts the disease
4. Prediction is sent to **Google Gemini**
5. Gemini generates treatment advice
6. Advice is optionally translated
7. Results are displayed instantly

---

## 🛠️ Tech Stack

| Component       | Technology        | Purpose                                          |
| --------------- | ----------------- | ------------------------------------------------ |
| Deep Learning   | PyTorch           | Training and building the ResNet9 neural network |
| Computer Vision | Torchvision, PIL  | Image preprocessing and transformations          |
| Frontend / App  | Streamlit         | Interactive web interface                        |
| GenAI           | Google Gemini API | Explanations, treatment advice, translation      |
| Model Format    | `.pth`, `.onnx`   | Saved weights with cross-platform potential      |
| Language        | Python            | Core development                                 |

---

## 📂 Project Structure

```
PlantGuard/
│
├── PlantGuard.py
├── plant_disease_detection.ipynb
├── model_test.ipynb
├── Kaggle/
│
├── models/
├── assets/
└── README.md
```

### Important Files

**PlantGuard.py**
The core application. Handles model loading, prediction pipeline, Streamlit UI, and Gemini API calls.

**plant_disease_detection.ipynb**
Training workspace. Includes dataset loading, architecture definition, GPU training, and weight export.

**model_test.ipynb**
Evaluation notebook used for accuracy measurement and confusion matrix analysis.

**Kaggle/**
Contains the “New Plant Diseases Dataset” used for training and validation.

---

## 🧠 Model Design

### ResNet9 — The Prediction Engine

Instead of using an oversized pre-trained network, PlantGuard uses a custom **ResNet9** architecture.

**Why this matters:**

* ~6.5 million parameters
* Faster training
* Lower compute requirements
* Strong performance for this dataset

**Core idea:**
Residual blocks introduce skip connections that allow gradients to flow through deeper layers, preventing the vanishing gradient problem and enabling richer feature learning.

The network progressively reduces spatial dimensions while increasing feature channels, helping it recognize subtle disease patterns.

---

## ⚡ Training Strategy — One Cycle Learning Rate

PlantGuard uses the **OneCycleLR policy**.

**How it works:**

* Start with a low learning rate
* Increase to a peak
* Gradually decrease

**Why it helps:**

* Acts as built-in regularization
* Encourages faster convergence
* Achieves high accuracy in fewer epochs (≈2 in this setup)

Efficient training without sacrificing performance.

---

## 🤖 Generative AI Integration

A raw prediction like *Tomato Early Blight* is not enough for most users.

PlantGuard turns predictions into guidance.

### Workflow:

Prediction → Prompt → Gemini → Explanation → Treatment Steps

Example prompt logic:

> Explain the disease “Tomato Early Blight” and provide practical treatment steps for farmers.

If Hindi or Marathi is selected, a secondary prompt translates the response.

Result: clear, accessible agricultural advice.

---

## ⚙️ Installation

### 1. Clone the Repository

```bash
git clone https://github.com/YOUR_USERNAME/PlantGuard.git
cd PlantGuard
```

---

### 2. Create Virtual Environment

**Windows**

```bash
python -m venv venv
venv\Scripts\activate
```

**Mac/Linux**

```bash
source venv/bin/activate
```

---

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

---

### 4. Configure Environment Variables

Create a `.env` file and add:

```
GEMINI_API_KEY=your_api_key_here
```

---

## ▶️ Running the Application

Launch the Streamlit app:

```bash
streamlit run PlantGuard.py
```

Open the provided local URL in your browser, upload a leaf image, and get predictions instantly.

---



## 🎯 Real World Use Cases

* Smart farming platforms
* Farmer assistance tools
* Agricultural research
* Crop monitoring systems
* Agri-tech startups

---

## 🔮 Future Improvements

* Mobile deployment for field usage
* Real-time camera detection
* Offline inference support
* Edge-device optimization
* Treatment recommendation database
* Weather-aware disease prediction

---

## 🤝 Contributing

Contributions are welcome.

1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Open a pull request

---

## 📜 License

MIT License 

---

## 👨‍💻 Author

**Ruchir Mangal**

GitHub:
[https://github.com/Rmangal37](https://github.com/Rmangal37)

---

⭐ If you found this project useful, consider giving it a star.
