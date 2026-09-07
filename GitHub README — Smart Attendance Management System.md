# 🎓 TCET Smart Attendance Management System

## 📌 Project Overview

The **TCET Smart Attendance Management System** is a web-based attendance management application developed using **Python and Django**.

The system helps faculty manage student records, subjects, daily attendance, attendance history, performance analytics, reports, and attendance requirements through a centralized web application.

The main goal of the project is to replace manual attendance management with a simple digital system that makes attendance tracking faster, organized, and easier to analyze.

---

## 🎯 Objectives

- Digitize the student attendance process
- Maintain student and subject records
- Allow faculty to mark daily attendance
- Prevent duplicate attendance records
- Calculate attendance percentages automatically
- Identify students below the 75% attendance requirement
- Provide visual attendance analytics
- Generate attendance reports
- Export attendance data as CSV
- Provide a simple and user-friendly dashboard

---

## ✨ Features

### 🔐 Faculty Authentication

- Faculty login and logout
- User registration
- Django authentication system
- Protected dashboard and management pages

### 👨‍🎓 Student Management

- Add students
- View student records
- Search students
- Edit student information
- Delete student records
- View individual student attendance details

### 📚 Subject Management

- Add subjects
- Store subject code and subject name
- Store faculty name
- Store semester information
- Store total lectures
- Edit and delete subjects

### 📝 Attendance Management

- Mark daily attendance
- Select subject and date
- Mark students as Present or Absent
- Update existing attendance records
- Prevent duplicate attendance for the same student, subject, and date

### 📊 Dashboard & Analytics

The dashboard provides information such as:

- Total students
- Total subjects
- Average attendance
- Present and absent counts
- Students below 75%
- Subject-wise attendance
- Monthly attendance trends
- Attendance performance categories

### 📈 Attendance Performance

Students are categorized based on attendance percentage:

| Attendance | Status |
|---|---|
| 90% or above | Excellent |
| 75% – 89% | Good |
| 65% – 74% | Warning |
| Below 65% | Critical |

### ⚠️ 75% Attendance Support

The system can calculate how many additional lectures a student needs to attend to reach the target attendance percentage.

The default target is **75%**.

### 📑 Reports

- Attendance reports
- Attendance history
- Filtering options
- CSV export

### 📤 CSV Export

Attendance information can be exported into CSV format for further analysis and record keeping.

---

## 🛠️ Technologies Used

### Backend

- Python
- Django
- Django ORM

### Frontend

- HTML
- CSS
- JavaScript
- Chart.js

### Database

- SQLite

### Data Processing

- Pandas
- NumPy
- OpenPyXL

---

## 🏗️ System Architecture

```text
                 ┌─────────────────────┐
                 │       Faculty       │
                 └──────────┬──────────┘
                            │
                            ▼
                 ┌─────────────────────┐
                 │    Django Web App   │
                 └──────────┬──────────┘
                            │
             ┌──────────────┼──────────────┐
             ▼              ▼              ▼
       Student Module  Subject Module  Attendance Module
             │              │              │
             └──────────────┼──────────────┘
                            ▼
                   ┌────────────────┐
                   │  Django ORM    │
                   └───────┬────────┘
                           ▼
                   ┌────────────────┐
                   │ SQLite Database │
                   └───────┬────────┘
                           ▼
                  ┌──────────────────┐
                  │ Analytics/Report │
                  └──────────────────┘
```

---

## 🔄 Project Workflow

```text
Faculty Login
     ↓
Dashboard
     ↓
Add Students
     ↓
Add Subjects
     ↓
Select Subject & Date
     ↓
Mark Attendance
     ↓
Save Attendance
     ↓
Calculate Attendance Percentage
     ↓
Generate Analytics
     ↓
Identify Students Below 75%
     ↓
Generate Reports
     ↓
Export CSV
```

---

## 🗄️ Database Design

The application primarily works with three important models:

### Student

Stores student information such as:

- Student ID
- Name
- Roll Number
- Academic year
- Creation date

### Subject

Stores:

- Subject code
- Subject name
- Faculty name
- Semester
- Total lectures

### Attendance

Stores:

- Student
- Subject
- Date
- Attendance status
- Creation date

The system uses relationships between students, subjects, and attendance records.

---

## 🔒 Duplicate Attendance Protection

The application prevents multiple attendance records for the same:

```text
Student + Subject + Date
```

This ensures that a student cannot accidentally receive multiple attendance entries for the same subject on the same day.

---

## 📊 Analytics

The system dynamically calculates attendance statistics and displays them through dashboard visualizations.

Analytics include:

- Subject-wise attendance
- Monthly attendance
- Present vs absent statistics
- Student performance categories
- Students requiring attention

---

## 📁 Project Structure

```text
TCET-Smart-Attendance-Management-System/
│
├── attendance/
│   ├── migrations/
│   ├── management/
│   │   └── commands/
│   ├── admin.py
│   ├── apps.py
│   ├── forms.py
│   ├── models.py
│   ├── urls.py
│   ├── utils.py
│   └── views.py
│
├── attendance_project/
│   ├── settings.py
│   ├── urls.py
│   ├── asgi.py
│   └── wsgi.py
│
├── templates/
│   └── attendance/
│
├── static/
│   └── attendance/
│
├── manage.py
├── requirements.txt
├── README.md
└── .gitignore
```

---

## ⚙️ Installation

### 1. Clone the repository

```bash
git clone https://github.com/YOUR-USERNAME/TCET-Smart-Attendance-Management-System.git
```

### 2. Open the project

```bash
cd TCET-Smart-Attendance-Management-System
```

### 3. Create a virtual environment

```bash
python -m venv venv
```

### 4. Activate the virtual environment

#### Windows

```bash
venv\Scripts\activate
```

#### macOS/Linux

```bash
source venv/bin/activate
```

### 5. Install dependencies

```bash
pip install -r requirements.txt
```

### 6. Apply database migrations

```bash
python manage.py migrate
```

### 7. Create an admin/superuser

```bash
python manage.py createsuperuser
```

Follow the instructions shown in the terminal.

### 8. Start the development server

```bash
python manage.py runserver
```

Open:

```text
http://127.0.0.1:8000/
```

---

## 🧪 Sample Data

The project contains a Django management command for creating sample data.

Run:

```bash
python manage.py create_sample_data
```

This can be used to populate the application with sample students, subjects, and attendance records for testing.

---

## 📈 Attendance Calculation

Attendance percentage is calculated using:

```text
Attendance Percentage =
(Present Lectures / Total Lectures) × 100
```

Example:

```text
Present = 30
Total = 40

Attendance =
(30 / 40) × 100

= 75%
```

---

## 💡 Key Learning Outcomes

This project helped me understand:

- Django project structure
- Django models
- Django views
- Django forms
- Django templates
- Django ORM
- CRUD operations
- User authentication
- Relational database design
- Data filtering
- Attendance calculations
- Data visualization
- CSV report generation
- Backend and frontend integration

---

## 🚀 Future Improvements

The project can be extended with:

- 🤖 Machine-learning-based attendance risk prediction
- 📸 Face recognition attendance
- 📱 QR-code attendance
- 📧 Email notifications
- 📱 Student mobile application
- 👨‍🏫 Faculty-specific permissions
- ☁️ Cloud database
- 📊 Power BI integration
- 🔔 Low-attendance alerts
- Student login and personalized dashboard

---

## 🎓 Academic Use

This project can be used as an academic project to demonstrate practical knowledge of:

**Python + Django + Database + Web Development + Data Analytics**

---

## 👨‍💻 Author

**Omkar**

B.Voc Artificial Intelligence & Data Science Student

---

## ⭐ Support

If you found this project useful, consider giving the repository a ⭐ on GitHub.