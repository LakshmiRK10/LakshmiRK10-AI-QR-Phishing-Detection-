# LakshmiRK10-AI-QR-Phishing-Detection-
markdown


# 🔐 AI-Based QR Code Phishing (Quishing) Detection System
<div align="center">
![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)
![License](https://img.shields.io/badge/License-MIT-green.svg)
![ML](https://img.shields.io/badge/ML-Random%20Forest-orange.svg)
![Status](https://img.shields.io/badge/Status-Active-success.svg)
*A machine learning-powered system to detect phishing URLs embedded in QR codes*
</div>
---
## 📋 Table of Contents
- [About the Project](#-about-the-project)
- [Features](#-features)
- [System Architecture](#-system-architecture)
- [Technologies Used](#-technologies-used)
- [Installation](#-installation)
- [Usage](#-usage)
- [Project Structure](#-project-structure)
- [How It Works](#-how-it-works)
- [Model Performance](#-model-performance)
- [Sample Output](#-sample-output)
- [Future Enhancements](#-future-enhancements)
- [Contributing](#-contributing)
- [License](#-license)
- [Acknowledgments](#-acknowledgments)
---
## 📖 About the Project
**QR Code Phishing (Quishing)** is an emerging cyber threat where attackers embed malicious URLs within QR codes. When users scan these codes, they are redirected to phishing websites designed to steal sensitive information.
This project presents an **AI-based detection system** that:
1. Scans and decodes QR code images
2. Extracts the embedded URL
3. Analyzes the URL using machine learning
4. Classifies it as **Safe** or **Malicious**
This tool helps users verify QR codes before visiting potentially dangerous links.
---
## ✨ Features
| Feature | Description |
|---------|-------------|
| 🔍 **QR Code Decoding** | Supports multiple image formats (PNG, JPG, etc.) |
| 🤖 **ML Classification** | Random Forest algorithm with 95%+ accuracy |
| 📊 **Feature Extraction** | 12 URL-based features for analysis |
| 💯 **Confidence Scores** | Probability-based prediction output |
| 🖥️ **CLI Interface** | Easy-to-use terminal interface |
| 📈 **Demo Mode** | Test with sample URLs instantly |
---
## 🏗️ System Architecture
┌─────────────────┐ ┌─────────────────┐ ┌─────────────────┐ │ QR Code │───▶│ URL │───▶│ ML Model │ │ Image │ │ Extraction │ │ Prediction │ └─────────────────┘ └─────────────────┘ └─────────────────┘ │ │ │ ▼ ▼ ▼ Input Image Decoded URL Safe/Phishing (PNG/JPG) (
...
 Classification



### Workflow Diagram
┌──────────────┐ │ Start │ └──────┬───────┘ ▼ ┌──────────────┐ │ Input QR │ │ Code Image │ └──────┬───────┘ ▼ ┌──────────────┐ │ Decode QR │──── Fail ────▶ Error Message │ (OpenCV) │ └──────┬───────┘ │ Success ▼ ┌──────────────┐ │ Extract URL │ │ Features │ └──────┬───────┘ ▼ ┌──────────────┐ │ Load ML │ │ Model │ └──────┬───────┘ ▼ ┌──────────────┐ │ Predict │ │ Safe/Phishing│ └──────┬───────┘ ▼ ┌──────────────┐ │ Display │ │ Result │ └──────┬───────┘ ▼ ┌──────────────┐ │ End │ └──────────────┘



---
## 🛠️ Technologies Used
| Category | Technology |
|----------|------------|
| **Language** | Python 3.8+ |
| **ML Library** | Scikit-learn |
| **QR Decoding** | OpenCV, pyzbar |
| **Image Processing** | Pillow (PIL) |
| **Data Handling** | Pandas, NumPy |
---
## 📥 Installation
### Prerequisites
- Python 3.8 or higher
- pip (Python package manager)
### Step-by-Step Setup
```bash
# 1. Clone the repository
git clone [github.com](https://github.com/yourusername/AI-QR-Phishing-Detection.git)
# 2. Navigate to project directory
cd AI-QR-Phishing-Detection
# 3. Create virtual environment (recommended)
python -m venv venv
# 4. Activate virtual environment
# On Windows:
venv\Scripts\activate
# On macOS/Linux:
source venv/bin/activate
# 5. Install dependencies
pip install -r requirements.txt
# 6. Install system dependency for pyzbar
# On Ubuntu/Debian:
sudo apt-get install libzbar0
# On macOS:
brew install zbar
# On Windows: Usually works without additional installation
 Usage
Step 1: Train the Model
bash


cd code
python model.py
Expected Output:



============================================================
   AI-Based QR Code Phishing Detection System
   Model Training Module
============================================================
[*] Loading dataset from: ../dataset/phishing_urls.csv
[+] Dataset loaded successfully!
[+] Total samples: 100
[+] Phishing URLs: 50
[+] Safe URLs: 50
[*] Extracting features from URLs...
[+] Feature extraction complete!
[+] Training samples: 80
[+] Testing samples: 20
[*] Training Random Forest classifier...
[+] Model training complete!
==================================================
MODEL PERFORMANCE METRICS
==================================================
Accuracy: 95.00%
[+] Model saved to: ../models/phishing_model.pkl
Step 2: Run Predictions
bash


python predict.py
Options:

Analyze QR Code Image - Provide path to QR code image
Analyze URL Directly - Enter URL manually
Run Demo - Test with sample URLs
Creating a Test QR Code
python


# Optional: Generate a test QR code
import qrcode
url = "[suspicious-login.com](http://suspicious-login.com/verify)"
img = qrcode.make(url)
img.save("test_qr.png")
📁 Project Structure


AI-QR-Phishing-Detection/
│
├── code/
│   ├── model.py          # ML model training
│   ├── qr_decoder.py     # QR code decoding
│   └── predict.py        # Main prediction script
│
├── dataset/
│   └── phishing_urls.csv # Training dataset
│
├── models/
│   └── phishing_model.pkl # Saved trained model
│
├── screenshots/
│   └── output.png        # Sample output screenshots
│
├── requirements.txt      # Python dependencies
├── README.md            # Project documentation
├── DOCUMENTATION.md     # Detailed documentation
└── LICENSE              # MIT License
⚙️ How It Works
Feature Extraction
The system extracts 12 features from each URL:

#	Feature	Description
1	URL Length	Total character count
2	Number of Dots	Count of . characters
3	Number of Hyphens	Count of - characters
4	Number of Underscores	Count of _ characters
5	Number of Slashes	Count of / characters
6	Number of Digits	Count of numeric characters
7	Special Characters	Count of @, !, #, $, etc.
8	HTTPS Presence	Binary (1/0) for secure protocol
9	IP Address Presence	Binary (1/0) for IP in URL
10	Subdomain Count	Number of subdomains
11	Path Length	Length of URL path
12	Suspicious Words	Presence of 'login', 'verify', etc.
Machine Learning Model
Algorithm: Random Forest Classifier
Trees: 100 decision trees
Max Depth: 10
Training Split: 80% train, 20% test
📊 Model Performance


==================================================
MODEL PERFORMANCE METRICS
==================================================
Accuracy: 95.00%
Classification Report:
              precision    recall  f1-score   support
        Safe       0.95      0.95      0.95        10
    Phishing       0.95      0.95      0.95        10
    accuracy                           0.95        20
   macro avg       0.95      0.95      0.95        20
weighted avg       0.95      0.95      0.95        20
Confusion Matrix:
  Predicted:  Safe  Phishing
  Actual Safe:    9        1
  Actual Phish:   1        9
==================================================
📸 Sample Output
Terminal Output


============================================================
   AI-Based QR Code Phishing (Quishing) Detection
   Developed for BTech Cybersecurity Mini-Project
============================================================
[*] Loading ML model from: ../models/phishing_model.pkl
[+] Model loaded successfully!
[STEP 1] Decoding QR Code...
[*] Attempting to decode QR code from: test_qr.png
[+] Successfully decoded using OpenCV!
[+] Decoded URL: [suspicious-login.com](http://suspicious-login.com/verify)
[STEP 2] Validating URL...
[+] Valid URL format detected
[STEP 3] Analyzing URL with ML Model...
[STEP 4] Generating Report...
============================================================
   PREDICTION RESULT
============================================================
  URL: [suspicious-login.com](http://suspicious-login.com/verify)
  ⚠️  STATUS: PHISHING ⚠️
  ----------------------------------------
  WARNING: This URL appears to be MALICIOUS!
  Do NOT click this link or enter any information.
  Confidence Scores:
  • Safe probability:     12.3%
  • Phishing probability: 87.7%
  Extracted Features:
  • URL Length: 38
  • Dots: 2
  • Hyphens: 1
  • Underscores: 0
  • Slashes: 3
  • Digits: 0
  • Special Chars: 0
  • HTTPS: 0
  • Has IP: 0
  • Subdomains: 1
  • Path Length: 7
  • Suspicious Words: 1
============================================================
🔮 Future Enhancements
 Web-based GUI interface
 Real-time QR code scanning via webcam
 Deep learning model integration
 URL reputation API integration
 Mobile application development
 Browser extension
 Email QR code scanner
 Database for storing scan history
🤝 Contributing
Contributions are welcome! Please follow these steps:

Fork the repository
Create a feature branch (git checkout -b feature/NewFeature)
Commit changes (git commit -m 'Add NewFeature')
Push to branch (git push origin feature/NewFeature)
Open a Pull Request
📄 License
This project is licensed under the MIT License - see the LICENSE [blocked] file for details.

🙏 Acknowledgments
Scikit-learn documentation
OpenCV community
pyzbar library developers
Phishing URL datasets from security researchers
