# 🔐 SECUREPHISH - Advanced Cybersecurity Training Platform

A comprehensive cybersecurity training platform featuring simulated phishing campaigns, employee risk assessment, and AI-powered interactive training modules.

---

## 🌟 Key Features

### 📧 **Email Notification System**
- **Dynamic Email Sending**: Send emails to any user in the database
- **Automatic Welcome Emails**: Instant welcome emails for new users
- **Flexible SMTP Configuration**: Environment variables for provider setup
- **Custom Phishing Campaigns**: Personalized phishing emails for each employee
- **Individual and Bulk Sending**: Support for individual users and CSV imports

### 👥 **Employee Management**
- Add, edit, and delete employees
- Import employees via CSV files
- Department-based organization
- Risk score tracking and assessment

### 🎯 **Phishing Campaigns**
- Create and manage phishing campaigns
- Multiple template types (bank, cloud, company, reward)
- Real-time campaign analytics
- Individual and bulk email sending

### 📊 **Analytics & Reporting**
- Real-time dashboard with key metrics
- Department risk analysis
- Campaign performance tracking
- Interactive charts and visualizations

### 🏆 **Gamification**
- Training leaderboard
- Progress tracking
- Risk level categorization
- Department competitions

### 🔐 **Security & Compliance**
- ISO 27001 compliance reporting
- Risk assessment engine
- Security awareness tracking
- Audit trails and logging

### 🤖 **AI Features**
- **Campaign Generator**: Create phishing scenarios using Google Gemini
- **Smart Chatbot**: Bilingual support chatbot
- **Link Scanner**: AI-powered suspicious link analysis
- **Content Generation**: Automated training content creation

### 🌍 **Internationalization**
- Dual language support (English/Arabic)
- Responsive user interface
- Customizable translation templates

---

## 🛠️ Technology Stack

### Backend
- **Python Flask** - Main framework
- **SQLAlchemy** - Database ORM
- **Flask-Login** - Session management and authentication
- **Flask-SocketIO** - Real-time communications
- **Flask-Babel** - Internationalization and localization

### Database
- **SQLite** (for development)
- **PostgreSQL** (for production)
- **Supabase** (for cloud hosting)

### Frontend
- **HTML5/CSS3/JavaScript** - Core technologies
- **Bootstrap** - Design framework
- **Chart.js** - Interactive charts
- **Font Awesome** - Icons

### External Services
- **Google Gemini API** - AI features
- **SMTP Providers** - Email sending
- **Twilio** (optional) - SMS messages

---

## 📦 Requirements & Installation

### Prerequisites
- Python 3.8+
- PostgreSQL database (optional for local use)
- Git

### Installation Steps

#### 1. **Clone Repository**
```bash
git clone https://github.com/mshawa77/SECUREPHISH.git
cd SECUREPHISH
```

#### 2. **Create Virtual Environment**
```bash
python -m venv venv
# Windows
venv\Scripts\activate
# Linux/Mac
source venv/bin/activate
```

#### 3. **Install Dependencies**
```bash
pip install -r requirements.txt
```

#### 4. **Set Up Environment Variables**
Create a `.env` file in the root directory:

```env
# Basic App Settings
FLASK_APP=app.py
FLASK_ENV=production
SECRET_KEY=your-secret-key-here

# Database (SQLite default)
DATABASE_URL=sqlite:///securephish.db
# Or PostgreSQL
# DATABASE_URL=postgresql://user:password@localhost/dbname

# SMTP Settings (Gmail example)
SMTP_SERVER=smtp.gmail.com
SMTP_PORT=587
SMTP_USERNAME=your-email@gmail.com
SMTP_PASSWORD=your-app-password
SMTP_USE_TLS=True
SMTP_DEFAULT_SENDER=Your Name <your-email@gmail.com>

# Google Gemini API
GEMINI_API_KEY=your-gemini-api-key
# Or multiple keys for fallback
GEMINI_API_KEY_1=key1
GEMINI_API_KEY_2=key2

# Default Admin Credentials
DEFAULT_ADMIN_EMAIL=admin@yourcompany.com
DEFAULT_ADMIN_PASSWORD=securepassword

# Additional Settings
PHISH_BASE_URL=http://localhost:5000
```

#### 5. **Run Application**
```bash
python app.py
```

#### 6. **Access Platform**
Open browser at `http://localhost:5000`
Login with admin credentials you configured.

---

## 🗂️ Project Structure

```
securproject1-main/
├── 📄 app.py                    # Main Flask application
├── 📄 models.py                 # Database models
├── 📄 config.py                 # App configuration (hidden by .gitignore)
├── 📄 requirements.txt          # Python dependencies
├── 📄 .env                      # Environment variables (hidden)
├── 📄 .gitignore               # Git ignore file
├── 📄 vercel.json              # Vercel deployment settings
│
├── 📁 utils/                   # Utility and helper functions
│   ├── 📄 ai_generator.py      # AI-powered content generator
│   ├── 📄 risk_engine.py       # Risk assessment engine
│   ├── 📄 compliance_engine.py # Compliance engine
│   ├── 📄 email_sender.py      # Email sending functionality
│   ├── 📄 qr_generator.py      # QR code generation
│   ├── 📄 report_generator.py  # Report generation
│   ├── 📄 analytics_engine.py  # Analytics engine
│   ├── 📄 sms_sender.py        # SMS sending
│   ├── 📄 token_utils.py       # Token utilities
│   └── 📄 filters.py           # Custom Jinja2 filters
│
├── 📁 templates/               # HTML templates
│   ├── 📄 base.html           # Base template
│   ├── 📄 dashboard.html      # Dashboard
│   ├── 📄 login.html          # Login page
│   ├── 📄 employees.html      # Employee management
│   ├── 📄 campaigns.html      # Campaign management
│   ├── 📄 reports.html        # Reports and analytics
│   ├── 📄 compliance.html     # Compliance and standards
│   ├── 📄 leaderboard.html    # Leaderboard
│   ├── 📄 link_scanner.html   # Link scanner
│   ├── 📄 campaign_generator.html # Campaign generator
│   └── 📁 phish/              # Phishing page templates
│       ├── 📄 bank.html
│       ├── 📄 cloud.html
│       ├── 📄 company.html
│       └── 📄 reward.html
│
├── 📁 static/                  # Static files
│   ├── 📁 css/                # Stylesheets
│   ├── 📁 js/                 # JavaScript files
│   └── 📁 images/             # Images and icons
│
├── 📁 translations/             # Translation files
│   ├── 📄 en.json             # English
│   └── 📄 ar.json             # Arabic
│
└── 📁 migrations/              # Database migrations
```

---

## 🔧 Configuration & Settings

### SMTP Configuration

The system supports multiple email providers:

#### Gmail
```env
SMTP_SERVER=smtp.gmail.com
SMTP_PORT=587
SMTP_USERNAME=your-email@gmail.com
SMTP_PASSWORD=your-app-password  # App-specific password
```

#### Outlook
```env
SMTP_SERVER=smtp-mail.outlook.com
SMTP_PORT=587
SMTP_USERNAME=your-email@outlook.com
SMTP_PASSWORD=your-password
```

#### SendGrid
```env
SMTP_SERVER=smtp.sendgrid.net
SMTP_PORT=587
SMTP_USERNAME=apikey
SMTP_PASSWORD=your-sendgrid-api-key
```

### Database Configuration

#### SQLite (default for development)
```env
DATABASE_URL=sqlite:///securephish.db
```

#### PostgreSQL (for production)
```env
DATABASE_URL=postgresql://username:password@localhost:5432/dbname
```

#### Supabase
```env
DATABASE_URL=postgresql://postgres:[password]@db.[project-id].supabase.co:5432/postgres
```

---

## 📊 User Interface & Functions

### 🏠 **Main Dashboard**
- Overview of key metrics
- Interactive charts
- Risk tracking by department
- Real-time recent interactions

### 👥 **Employee Management**
- **Add Employee**: Manual entry or CSV import
- **Edit Data**: Update employee information
- **Risk Assessment**: Automatic risk score calculation
- **Interaction Log**: Track all employee interactions

### 🎯 **Campaign Management**
- **Create Campaign**: Define template and audience
- **Customize Content**: Personalized email messages
- **Launch Campaign**: Instant or scheduled sending
- **Monitor Performance**: Real-time result tracking

### 📈 **Reports & Analytics**
- **Campaign Reports**: PDF and Excel exports
- **Employee Analytics**: Individual and group performance
- **Risk Metrics**: Risk distribution across departments
- **Time Trends**: Historical data analysis

### 🔐 **Compliance & Standards**
- **ISO 27001**: International standards compliance assessment
- **Audit Reports**: Detailed audit logs
- **Security KPIs**: Cybersecurity key performance indicators
- **Improvement Recommendations**: Security enhancement suggestions

---

## 🤖 AI Features

### Campaign Generator
- Create realistic phishing scenarios
- Customize by industry and culture
- Multi-language support
- Campaign effectiveness analysis

### Smart Chatbot
- Instant user support
- Frequently asked questions
- Employee training guidance
- Security inquiry analysis

### Link Scanner
- Suspicious link analysis
- Security risk assessment
- Detailed link reports
- Real-time protection

---

## 🔒 Security Features

### Data Protection
- **Password Encryption**: Werkzeug security
- **Session Protection**: Secure cookies and CSRF protection
- **Access Control**: Role-based authentication and authorization
- **Event Logging**: Comprehensive audit trail

### Network Security
- **Rate Limiting**: Prevent automated attacks
- **Input Validation**: Validate all inputs
- **XSS Protection**: Content Security Policy
- **HTTPS Enforcement**: Secure connections

### Data Privacy
- **Data Minimization**: Collect only necessary data
- **PII Protection**: Encrypt personal data
- **Access Control**: Data access control
- **Data Retention**: Data retention policies

---

## 🚀 Deployment & Operations

### Local Deployment
```bash
# Run application
python app.py

# Or using gunicorn for production
gunicorn -w 4 -b 0.0.0.0:5000 app:app
```

### Vercel Deployment
1. Connect repository to Vercel
2. Set environment variables in Vercel dashboard
3. Automatic deployment

### Docker Deployment
```dockerfile
FROM python:3.9-slim
WORKDIR /app
COPY requirements.txt .
RUN pip install -r requirements.txt
COPY . .
EXPOSE 5000
CMD ["python", "app.py"]
```

---

## 📞 Support & Help

### FAQ Section

**Q: How do I add new employees?**
A: You can add employees individually through the interface or import them from a CSV file.

**Q: Does the system support Arabic language?**
A: Yes, the system fully supports both Arabic and English languages.

**Q: How do I configure email settings?**
A: From the settings page, enter your SMTP provider details.

**Q: What are the system requirements?**
A: Python 3.8+ and minimum 1GB disk space.

---

## 📝 License

This project is licensed under the MIT License - see the LICENSE file for details.

---

## 🔄 Updates & Development

### Future Roadmap
- [ ] Add more phishing templates
- [ ] SIEM system integration
- [ ] Advanced AI analytics
- [ ] Mobile app for employees
- [ ] Enterprise SSO integration

### Changelog

#### v2.0.0 (Current)
- Added AI features
- Bilingual support
- Improved user interface
- ISO 27001 reporting

#### v1.0.0
- Initial release with core functionality
- Employee management system
- Phishing campaigns
- Basic reporting

---

## ⚠️ Important Notice

**This platform is designed for cybersecurity training and awareness purposes only. All simulated phishing attacks are for educational purposes only and should not be used for malicious purposes.**

---

## 🤝 Contributing to the Project

We welcome community contributions:

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests for new functionality
5. Submit a Pull Request

---

## 📧 Contact Information

For support and inquiries:
- Email: mohammadshawabkeh693@gamil.com
- Repository: https://github.com/mshawa77/SECUREPHISH
- Additional documentation: docs/ folder

---

**© 2026 SECUREPHISH - All Rights Reserved**
