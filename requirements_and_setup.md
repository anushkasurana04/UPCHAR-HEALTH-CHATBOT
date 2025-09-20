# Health Chatbot - Setup Instructions

## 📋 Requirements (requirements.txt)

```txt
Flask==2.3.3
googletrans==4.0.0rc1
sqlite3
```

## 🚀 Installation & Setup

### 1. Create Project Structure
```bash
mkdir health-chatbot
cd health-chatbot
mkdir templates static
```

### 2. Create Files
Create the following files in your project directory:

- `app.py` - Main Flask application (from first artifact)
- `requirements.txt` - Dependencies list
- `templates/base.html` - Base template
- `templates/login.html` - Login page
- `templates/signup.html` - Signup page  
- `templates/chat.html` - Main chat interface

### 3. Install Dependencies
```bash
# Create virtual environment (recommended)
python -m venv venv

# Activate virtual environment
# On Windows:
venv\Scripts\activate
# On Mac/Linux:
source venv/bin/activate

# Install dependencies
pip install -r requirements.txt
```

### 4. Run the Application
```bash
# Set environment variables (optional)
export FLASK_ENV=development
export FLASK_DEBUG=True

# Run the application
python app.py
```

The application will start on `http://localhost:5000`

## 🌟 Features

### 🔐 Authentication System
- User registration with username, email, password
- Secure login with password hashing
- Session management
- SQLite database for user storage

### 💬 ChatGPT-Style Interface
- Clean, responsive design
- Real-time chat bubbles (user = blue, bot = grey/green)
- Typing indicators
- Quick action buttons
- Mobile-friendly responsive layout

### 🩺 Symptom Checker
- JSON-based symptom-disease mapping
- Keyword matching algorithm
- Emergency condition detection
- Multilingual support (English/Hindi)
- Medical disclaimers

### 🌐 Multilingual Support
- Auto-detects Hindi/English text
- Google Translate integration
- Bidirectional translation for queries and responses

### 🔔 Health Reminders
- Vaccination reminders
- Custom health reminders
- Flexible scheduling (1 day to 1 year)
- Database storage for reminders

## 🏥 Symptom Database

The system includes knowledge base for common conditions:
- Flu/viral infections
- Dengue fever
- Tuberculosis
- Malaria
- Heart conditions
- Respiratory issues
- Emergency conditions (stroke, heart attack)

## 🎨 UI Features

### Design Elements:
- Gradient backgrounds
- Card-based layouts
- Font Awesome icons
- Bootstrap 5 styling
- Smooth animations and transitions

### Chat Interface:
- User messages: Blue bubbles (right-aligned)
- Bot messages: Grey bubbles (left-aligned)
- Avatar icons for users and bot
- Scrollable chat history
- Quick action buttons for common queries

## 🔧 API Endpoints

- `POST /signup` - User registration
- `POST /login` - User authentication
- `GET /logout` - User logout
- `GET /chat` - Chat interface (protected)
- `POST /api/chat` - General health Q&A
- `POST /api/symptom-check` - Symptom analysis
- `POST /api/reminder` - Set health reminders

## ⚠️ Important Notes

### Medical Disclaimer
Every response includes: "This is only awareness information. Please consult a doctor for medical advice."

### Emergency Detection
System detects emergency symptoms and urges immediate medical attention.

### Security Features
- Password hashing with SHA-256
- Session-based authentication
- SQL injection prevention
- Input validation

### Language Support
- Automatic language detection
- Google Translate API integration
- Supports English and Hindi
- Expandable to other languages

## 🎯 Usage Examples

### Symptom Checking:
- User: "I have fever and cough"
- Bot: "Based on your symptoms, you may have Flu or common viral infection. This is only for awareness purposes..."

### General Health:
- User: "Tell me about vaccines"
- Bot: "Vaccines are crucial for preventing diseases. Common vaccines include..."

### Emergency Detection:
- User: "Severe chest pain and sweating"
- Bot: "⚠️ URGENT: This could be a heart attack. Please seek immediate medical attention!"

### Reminders:
- User: Clicks "Set Reminder" → Sets vaccination reminder
- Bot: "Reminder set successfully! I'll remind you about 'Flu vaccine' on 2024-10-18."

## 🔄 Future Enhancements

1. **Advanced NLP**: Integrate with more sophisticated language models
2. **Medical API**: Connect with medical databases for more accurate information
3. **User History**: Track user health patterns and provide personalized advice
4. **Push Notifications**: Actual reminder notifications via email/SMS
5. **Telemedicine**: Integration with healthcare provider booking systems
6. **Voice Support**: Speech-to-text and text-to-speech capabilities
7. **Health Tracking**: BMI calculator, medication tracking, appointment scheduling

## 📱 Mobile Responsiveness

The application is fully responsive and works on:
- Desktop computers
- Tablets
- Mobile phones
- Different screen orientations

## 🔒 Security Considerations

For production deployment:
1. Change the Flask secret key
2. Use environment variables for sensitive data
3. Implement rate limiting
4. Add HTTPS/SSL certificates
5. Use production-grade database (PostgreSQL/MySQL)
6. Implement proper logging and monitoring
7. Add input sanitization and validation

## 🏥 Legal Compliance

Remember to:
- Include proper medical disclaimers
- Comply with local healthcare regulations
- Implement data privacy measures (GDPR, HIPAA if applicable)
- Regular content updates based on medical guidelines
- Professional medical review of content