# 📚 AI Image Classifier

An end-to-end, high-performance web application that classifies academic paper abstracts into specific sub-disciplines of Mathematics and Computer Science. The system features a state-of-the-art fine-tuned **DeBERTa-v3-small** model adapted using Parameter-Efficient Fine-Tuning (**PEFT/LoRA**), served via a **FastAPI** backend, and presented through a modern, responsive **React (Vite)** frontend.

---

## 🚀 Key Features

* **Real-time Classification**: Instantly analyze and classify raw academic text into one of 11 distinct mathematical or computer science fields.
* **Confidence Scoring**: View the probability/confidence distribution score for the model's predictions.
* **LoRA PEFT Adaptation**: Utilizes Low-Rank Adaptation (LoRA) to adapt the DeBERTa-v3-small model efficiently with low memory footprint and high precision.
* **FastAPI Backend**: Clean, asynchronous API endpoints designed for high throughput inference.
* **Interactive React Frontend**: Interactive web interface featuring dark-mode styling, abstract input validation, and real-time prediction displays.

---

## 🛠️ Tech Stack

### Frontend
* **React 19** & **Vite** (Next-generation frontend tooling)
* **React Router Dom** (Single Page Application routing)
* Modern Vanilla CSS (Sleek dark-themed layout, custom glassmorphism)

### Backend
* **FastAPI** (Python web framework)
* **PyTorch** & **HuggingFace Transformers** (Inference engine)
* **PEFT (Parameter-Efficient Fine-Tuning)** (LoRA adapter injection)
* **Uvicorn** (ASGI server)

---

## 📂 Project Structure

```
Academic-Abstract-Classifier/
├── .gitignore                          # Root ignore configurations
├── .gitattributes                      # Git LFS tracking rules
├── README.md                           # Documentation
└── Academic Abstract Classifier/       # Main workspace folder
    ├── Academic Abstract Classifier.ipynb # Jupyter notebook used for fine-tuning
    ├── backend/
    │   └── app.py                      # FastAPI backend application
    ├── frontend/
    │   ├── package.json
    │   ├── vite.config.js
    │   ├── src/
    │   │   ├── App.jsx                 # Core routing setup
    │   │   ├── main.jsx
    │   │   └── pages/                  # HomePage, LoginPage, ClassifierPage
    │   └── ...
    ├── final_deberta_model/            # Fine-tuned LoRA adapters (weights)
    │   ├── adapter_config.json
    │   └── adapter_model.safetensors
    ├── data_visualization/             # Dataset analysis visualizations
    ├── test_tokenizer.py
    └── requirements.txt                # Python backend dependencies
```

---

## 🧠 Model Details

The classifier is based on **`microsoft/deberta-v3-small`**, fine-tuned on an academic dataset using LoRA (Low-Rank Adaptation) via HuggingFace's `peft` library. 

### Classification Classes (11 Categories)
1. **Commutative Algebra**
2. **Computer Vision and Pattern Recognition**
3. **Artificial Intelligence**
4. **Systems and Control**
5. **Group Theory**
6. **Computational Engineering, Finance, and Science**
7. **Programming Languages**
8. **Information Theory**
9. **Data Structures and Algorithms**
10. **Neural and Evolutionary Computing**
11. **Statistics Theory**

---

## 💻 Installation & Local Setup

### Prerequisites
* Python 3.9+
* Node.js 18+
* git

### 1. Setup the Backend API

1. Navigate into the workspace folder:
   ```bash
   cd "Academic Abstract Classifier"
   ```
2. Create and activate a python virtual environment:
   ```bash
   python -m venv .venv
   # On Windows:
   .venv\Scripts\activate
   # On macOS/Linux:
   source .venv/bin/activate
   ```
3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
4. Start the FastAPI server:
   ```bash
   python backend/app.py
   ```
   The backend server will run on `http://localhost:8000`.

### 2. Setup the Frontend App

1. In a new terminal, navigate to the frontend folder:
   ```bash
   cd "Academic Abstract Classifier/frontend"
   ```
2. Install Node packages:
   ```bash
   npm install
   ```
3. Run the React development server:
   ```bash
   npm run dev
   ```
   The frontend application will be hosted on `http://localhost:5173`.

---

## 🤝 Verification

Once both frontend and backend are running, navigate to `http://localhost:5173` in your browser. Go to the **Classifier** page, paste any abstract, and click **Classify** to run inferences.
