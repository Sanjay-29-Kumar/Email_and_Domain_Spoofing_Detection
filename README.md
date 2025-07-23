# Email Spoofing Detection Web Application

This web application analyzes emails for potential spoofing by checking SPF and DMARC records, and other email authentication mechanisms.

## Setup Instructions

1. **Clone the Repository**
   ```bash
   git clone <repository-url>
   cd email_spoofing_web
   ```

2. **Set Up Python Virtual Environment**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   pip install -r requirements.txt
   ```

3. **Google OAuth Setup**
   1. Go to [Google Cloud Console](https://console.cloud.google.com/)
   2. Create a new project or select an existing one
   3. Enable the Gmail API
   4. Configure the OAuth consent screen
   5. Create OAuth client ID credentials
   6. Download the credentials and rename to `credentials.json`
   7. Place `credentials.json` in the project root directory

4. **Run the Application**
   ```bash
   python app.py
   ```
   The application will be available at `http://localhost:5000`

## Features

- Email authentication verification (SPF, DMARC)
- Full email content display
- Security warnings for potential spoofing attempts
- Clean and intuitive user interface

## Project Structure
```
email_spoofing_web/
├── app.py              # Main Flask application
├── requirements.txt    # Python dependencies
├── credentials.json    # Google OAuth credentials (you need to add this)
└── templates/
    └── index.html     # Frontend template
```

## Security Notes

- Keep your `credentials.json` file secure and never commit it to version control
- The application requires access to Gmail API with readonly scope
- All email analysis is done server-side for security

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Submit a pull request

## License

This project is licensed under the MIT License - see the LICENSE file for details. 