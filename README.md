# 📧 Email & Domain Spoofing Detection Web App

A secure Flask web application that detects potential email and domain spoofing by analyzing Gmail messages using SPF, DKIM, and DMARC authentication protocols.

---

## 🚀 Features

* ✅ **Email & Domain Authentication**: Verifies SPF, DKIM, and DMARC records
* ⚠️ **Spoofing Detection**: Flags suspicious messages and spoofed emails/domains
* 📬 **Email Viewer**: Displays full email content and headers
* 🔐 **Secure OAuth Access**: Connects to Gmail API using Google OAuth 2.0
* 💡 **Simple UI**: Clean and user-friendly interface for analysis
* 🔍 **Real-time DNS Checks**: Performs live SPF and DMARC record verification

---

## 🛠️ Getting Started

### Prerequisites

* Python 3.7 or higher
* Gmail account with API access
* Google Cloud Console access

---

### 🔧 Installation

#### 1. Clone the Repository

```bash
git clone https://github.com/your-username/email_spoofing_web.git
cd email_spoofing_web
```

#### 2. Set Up Python Virtual Environment

```bash
python -m venv venv

# Activate the environment
# On macOS/Linux:
source venv/bin/activate

# On Windows:
venv\Scripts\activate

pip install -r requirements.txt
```

---

### 🔐 Google OAuth Setup

1. Go to [Google Cloud Console](https://console.cloud.google.com/)
2. Create a project (or select an existing one)
3. Enable **Gmail API**
4. Configure the **OAuth consent screen**
5. Create **OAuth 2.0 Client ID**
6. Download the credentials file and rename it to `credentials.json`
7. Place `credentials.json` in your project root (next to `app.py`)

---

### ▶️ Run the App

```bash
python app.py
```

Visit: [http://localhost:5000](http://localhost:5000)

---

## 📁 Project Structure

```
Email_Spoofing_Detection/
├── app.py                    # Flask application
├── model.pkl                 # Pre-trained model for analysis
├── vectorizer.pkl            # Text processing component
├── requirements.txt          # Python dependencies
├── credentials.json          # Google OAuth credentials (DO NOT COMMIT)
├── PROJECT_DOCUMENTATION.md  # Technical documentation
├── SYSTEM_FLOW.txt          # System architecture flow
├── setup.bat               # Windows setup script
├── static/
│   └── style.css           # CSS styling
└── templates/
    └── index.html          # HTML frontend
```

---

## 🔧 Dependencies

The application uses the following key libraries:

* **Flask** (3.0.2) - Web framework
* **dnspython** (2.6.1) - DNS queries for SPF/DMARC checks
* **scikit-learn** (1.6.1) - Analysis model
* **google-api-python-client** (2.120.0) - Gmail API integration
* **dkimpy** (1.1.5) - DKIM verification support

---

## 🔒 Security Notes

* ❗ Do not expose `credentials.json` to version control (add it to `.gitignore`)
* Gmail access is **read-only**
* All analysis happens **server-side** to protect user data
* Analysis models are pre-trained and included in the repository

---

## 🛡️ How It Works

### 1. Email Authentication
- **SPF Check**: Verifies if the sending domain has proper SPF records
- **DMARC Check**: Validates domain authentication policies
- **DNS Analysis**: Real-time queries to verify domain authenticity

### 2. Content Analysis
- **Text Processing**: Analyzes email content for suspicious patterns
- **Feature Extraction**: Processes email text for analysis
- **Spoofing Detection**: Combines content analysis with authentication results

### 3. Security Flow
```
User Login → OAuth Consent → Gmail Access → Email Analysis → Results Display
```

---

## 📊 Analysis Results

The system categorizes emails as:

* ✅ **Legitimate**: Proper SPF and DMARC records
* ⚠️ **Spoofed**: Missing or invalid authentication records
* 🚨 **Suspicious**: Failed domain verification

---

## 🤝 Contributing

1. Fork this repository
2. Create a new branch: `git checkout -b feature-name`
3. Commit your changes
4. Push and open a pull request

---

## 📄 License

This project is licensed under the MIT License.
See the [LICENSE](LICENSE) file for full details.

---

## 🙌 Acknowledgements

* [Flask](https://flask.palletsprojects.com/)
* [Google Gmail API](https://developers.google.com/gmail/api)
* [SPF, DKIM, DMARC](https://dmarc.org/)
* [dnspython](https://www.dnspython.org/)
* [scikit-learn](https://scikit-learn.org/)

---

## 📌 GitHub Tips

### `.gitignore`

```
credentials.json
__pycache__/
venv/
*.pyc
token.json
```

### Push to GitHub

```bash
git init
git add .
git commit -m "Initial commit"
git remote add origin https://github.com/your-username/email_spoofing_web.git
git branch -M main
git push -u origin main
```

---

## 🔍 Troubleshooting

### Common Issues

1. **OAuth Token Expired**: Clear session and re-authenticate
2. **DNS Resolution Failures**: Check internet connection
3. **Model Loading Errors**: Ensure `model.pkl` and `vectorizer.pkl` are present

### Quick Setup (Windows)

Run the included setup script:
```bash
setup.bat
```

---

## 📚 Documentation

For detailed technical information, see:
- [PROJECT_DOCUMENTATION.md](PROJECT_DOCUMENTATION.md) - Technical implementation details
- [SYSTEM_FLOW.txt](SYSTEM_FLOW.txt) - System architecture flow diagram
