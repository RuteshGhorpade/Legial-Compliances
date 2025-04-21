# 🧠 Legial Compliances - AI-based Legal Document Classifier

This project is an AI-powered web application that classifies **legal documents** into categories (e.g., contracts, agreements) and generates a **summary** using NLP models.

It supports:
- 🧾 **OCR extraction** from PDF files using Tesseract
- 📊 **Document classification** using Logistic Regression & TF-IDF
- ✂️ **Summarization** using Hugging Face's T5 model

---

## 📁 Project Structure

```
Legial-Compliances/
├── backend/
│   └── model/                  # Trained classifier & vectorizer
├── data/
│   └── CONTRACT_TYPES/         # Training data (organized by folder)
├── static/
│   ├── uploads/                # Uploaded PDFs
├── templates/
│   └── index.html              # Upload form
├── app.py                      # Flask backend
├── utils.py                    # OCR, summarization, classification
├── train.py                    # Model training
├── requirements.txt            # Python dependencies
├── .env                        # Tesseract & Poppler config
└── README.md                   # You're here!
```

---

## ⚙️ Installation & Setup

### 1. Clone the Repo

```bash
git clone https://github.com/RuteshGhorpade/Legial-Compliances.git
cd Legial-Compliances
```

### 2. Create & Activate a Virtual Environment

```bash
python -m venv venv
# Windows
venv\Scripts\activate
# macOS/Linux
source venv/bin/activate
```

### 3. Install Python Dependencies

```bash
pip install -r requirements.txt
```

### 4. Install External Tools

- ✅ **[Tesseract OCR](https://github.com/tesseract-ocr/tesseract)**
- ✅ **[Poppler for PDF to Image conversion](http://blog.alivate.com.au/poppler-windows/)**

Make sure to add both to your system path, and update the `.env` file.

---

## 🧪 Setup `.env` File

Create a `.env` file in the root directory:

```
POPPLER_PATH=C:\path\to\poppler\bin
```

Adjust path for your system.

---

## 🏋️‍♂️ Train the Model (Optional)

To train or retrain the classifier on your own dataset:

```bash
python train.py
```

Your dataset should be placed inside the `data/CONTRACT_TYPES/` folder with this format:

```
data/
└── CONTRACT_TYPES/
    ├── Employment/
    │   ├── file1.txt
    │   ├── file2.txt
    └── Lease/
        ├── file1.txt
        ├── ...
```

---

## 🚀 Run the Web App

```bash
python app.py
```

Then open in your browser:  
👉 http://localhost:5000

---

## 📤 Upload a PDF

1. Select a PDF from the form.
2. Click **Upload**.
3. View:
   - Predicted document type
   - Match percentage
   - Top keywords
   - AI-generated summary

---

## 🛠️ API Endpoints

### `/upload` [POST]
- Uploads a PDF and returns classification + summary.

### `/train` [POST]
- Triggers model training using the `data/CONTRACT_TYPES` folder.

---

## 🧠 Technologies Used

- **Flask** – Backend API
- **Transformers (T5)** – Text summarization
- **Scikit-learn** – Text classification
- **pdf2image + pytesseract** – OCR
- **TF-IDF Vectorizer** – Feature extraction

---

## 🧾 Example Output

```json
{
  "document_type": "Employment",
  "match_percentage": 92.15,
  "keywords": ["employee", "agreement", "salary", ...],
  "summary": "This agreement outlines the conditions of employment between..."
}
```

---

## 📌 To-Do / Improvements

- [ ] Frontend enhancements
- [ ] Docker support
- [ ] Deployment on Render/Heroku
- [ ] Add history tracking for uploaded documents

---

## 👨‍💻 Author

**Rutesh Pratap Ghorpade**  
📫 [LinkedIn](https://www.linkedin.com/in/ruteshghorpade)  
🔗 GitHub: [@RuteshGhorpade](https://github.com/RuteshGhorpade)

---

## 📜 License

This project is licensed under the MIT License.


