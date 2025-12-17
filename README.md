# ELEVATE LABS – Cybersecurity Internship  
## Project: Password Strength Analyzer Using Entropy & Dictionary Checks  
## Objective: Analyze password strength in real-time using entropy calculation, character diversity, and common password detection.

## **Name:** Kothamasu Sai Prasad  

This task demonstrates how I designed and implemented a **Password Strength Analyzer Web Application** that evaluates password security in **real time**.  
The goal was to calculate password entropy, detect common passwords using a dictionary list, assign a strength score, and provide actionable security suggestions to users.

This project demonstrates how I designed and implemented a Password Strength Analyzer Web Application that evaluates password security in real time. The goal was to calculate password entropy, detect common passwords using a dictionary list, assign a strength score, and provide actionable security suggestions to users in order to improve password hygiene and prevent common attacks.

---

## Live Project Link
Website URL: https://password-strength-analyzer-1jix.onrender.com

The application is hosted online and can be accessed publicly. Users can test password strength instantly without installing any software. No passwords are stored or logged, ensuring privacy and security.

---

## Tools Used
Python (Flask Framework) – Backend logic and API  
HTML5 – Page structure  
CSS3 – Styling and responsive UI  
JavaScript – Real-time password analysis  
Gunicorn – Production WSGI server  
Dictionary-based password list  
Windows 10/11  

---

## Project Structure
```plaintext
password-strength-analyzer/
├── app.py
├── dictionary.txt
├── requirements.txt
├── Procfile
├── templates/
│ └── index.html
├── static/
│ ├── style.css
│ └── script.js
└── README.md
```
---

## 🟦 Step-by-Step Process

### **1. Project Setup**
- Created a Flask application (`app.py`) to handle backend logic.
- Organized frontend files using `templates` and `static` folders.
- Installed required dependencies using `requirements.txt`.

---

### **2. Backend Implementation (Flask)**
The backend performs:
- Password entropy calculation
- Strength scoring
- Dictionary-based common password detection
- Suggestion generation

Key components:
- `calculate_entropy()` – Calculates entropy using character set size
- `entropy_to_score()` – Converts entropy to a 0–100 strength score
- `/api/check` – API endpoint for password analysis

---

### **3. Dictionary Attack Detection**
- Loaded a large list of commonly used passwords from `dictionary.txt`.
- Compared user input against the list (case-insensitive).
- If matched, the password is marked as **Very Weak**, regardless of entropy.

This simulates **dictionary attack prevention**.

---

### **4. Frontend Real-Time Analysis**
To provide instant feedback:
- JavaScript calculates entropy locally while typing.
- Displays:
  - Strength meter (circular progress)
  - Entropy value (in bits)
  - Password length
  - Strength rating (Very Weak → Very Strong)

This avoids unnecessary server calls during typing.

---

### **5. Full Server-Side Validation**
- On clicking **“Run full check”**, the password is sent to Flask backend.
- Backend performs:
  - Dictionary verification
  - Final score calculation
  - Suggestion generation
- Results are returned as JSON and displayed to the user.

---

## 📊 Strength Metrics Used

### **1. Entropy Calculation**
**Purpose:** Measure randomness and unpredictability.  

Formula used:
Entropy = Password Length × log₂(Character Set Size)

Character sets include:
- Lowercase letters (a–z)
- Uppercase letters (A–Z)
- Numbers (0–9)
- Special characters

---

### **2. Strength Rating Scale**
| Score Range | Rating |
|------------|--------|
| 0 – 24 | Very Weak |
| 25 – 44 | Weak |
| 45 – 64 | Fair |
| 65 – 84 | Strong |
| 85 – 100 | Very Strong |

Passwords found in the dictionary are automatically rated **Very Weak**.

---

## 🛑 Security Analysis Summary

### **1. Weak Password Detection**
**Observation:**
- Short passwords or dictionary words scored very low.
- Example: `password123`, `hello`, `123456`

**Risk Identified:**
- Vulnerable to brute-force and dictionary attacks.

---

### **2. Strong Password Characteristics**
**Observation:**
- Longer passwords with mixed characters scored higher.
- Passphrases (20+ characters) showed very high entropy.

**Security Benefit:**
- Resistant to brute-force and guessing attacks.

---

## 💡 Suggestions Generated
The system provides real-time improvement tips such as:
- Increase password length to at least 12 characters
- Add uppercase and lowercase letters
- Include numbers and special symbols
- Avoid commonly used passwords
- Use passphrases for better memorability and security

---

## 🌐 Deployment Configuration
- Used **Gunicorn** for production deployment.
- Created `Procfile`:
web: gunicorn app:app
- Application is ready for hosting on platforms like Heroku or Render.

---

## 📝 Summary of Findings
During this task, I successfully implemented a password analysis system that:

| Feature | Description |
|-------|------------|
| **Entropy Analysis** | Measures randomness of passwords |
| **Dictionary Check** | Detects commonly used passwords |
| **Real-Time Feedback** | Instant UI updates while typing |
| **Suggestions Engine** | Improves password hygiene |

This helped me understand **how weak passwords are identified and strengthened** in real-world security systems.

---

## 🎉 Conclusion
This task enhanced my practical understanding of:
- Password security fundamentals
- Entropy-based strength evaluation
- Dictionary attack prevention
- Secure web application design using Flask

The Password Strength Analyzer demonstrates how cybersecurity principles can be applied to build **user-friendly and security-focused applications**.

---
