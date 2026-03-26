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
