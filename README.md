# TCET Smart Attendance Management System

A beginner-friendly Django application for Thakur College of Engineering and Technology faculty to record attendance, understand student performance, and identify learners who need support.

## Features
- Faculty login using Django authentication
- Student and subject management
- Daily attendance marking with duplicate protection
- Attendance history and filters
- Dynamic dashboard with Chart.js
- Student profiles and subject-wise summaries
- 75% attendance support prediction
- Analytics, reports, and CSV export
- SQLite database for simple local development

## Technology
python manage.py create_sample_data
python manage.py runserver
```
Open `http://127.0.0.1:8000/` and sign in with the superuser account.

## How it works
Django models store students, subjects, and one attendance record per student, subject, and date. Views receive a request, use the Django ORM to read or update the database, and send context to templates. Small functions in `attendance/utils.py` calculate totals and percentages dynamically. Chart.js turns those values into interactive charts in the browser.

## Project structure
- `attendance_project/`: Django configuration and root URLs
- `attendance/`: models, forms, views, utilities, admin, and management commands
- `templates/attendance/`: page templates
- `static/attendance/`: CSS and JavaScript

## Interview summary

## MongoDB information
MongoDB is a document database. It stores JSON-like documents instead of rows and tables. It is useful when an application has flexible or changing data, but this attendance system uses related students, subjects, and attendance records, so SQLite with Django ORM is simpler and easier to explain for the current project.

For a future MongoDB version, use MongoDB Atlas for hosting and a Django-compatible connector such as Djongo or MongoEngine. The models and queries would need to be reviewed because Django's standard ORM is designed primarily for relational databases. Do not switch databases just to add MongoDB to a resume; first understand the data model and test migration carefully.
This project demonstrates CRUD operations, authentication, relational data modelling, ORM queries, data cleaning/calculation, visual analytics, and report export. It is intentionally built with simple Django patterns so each part is easy to explain.

## Future improvements
Face recognition, QR attendance, email/SMS alerts, student accounts, faculty-specific permissions, cloud database, mobile app, Power BI integration, and machine-learning risk prediction.
