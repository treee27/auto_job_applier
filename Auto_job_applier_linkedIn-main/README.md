# Job Applications Tracker API

A Flask-based backend application for tracking and managing applied job applications using CSV files.  
This project provides REST APIs to fetch applied jobs and update application dates, along with a simple frontend UI using HTML templates.

---

# Features

- View all applied job applications
- Update application applied date
- CSV-based lightweight storage
- REST API support
- Flask backend
- Flask-CORS enabled
- Simple frontend support using Jinja templates

---

# Tech Stack

- Python
- Flask
- Flask-CORS
- CSV File Handling
- HTML Templates

---

# Project Structure

```bash
project/
│
├── app.py
├── templates/
│   └── index.html
│
├── all excels/
│   └── all_applied_applications_history.csv
│
└── README.md
```

---

# CSV File Format

The application expects a CSV file named:

```bash
all_applied_applications_history.csv
```

inside the folder:

```bash
all excels/
```

## Required CSV Columns

```csv
Job ID,Title,Company,HR Name,HR Link,Job Link,External Job link,Date Applied
```

---

# Installation

## 1. Clone Repository

```bash
git clone <your-repository-url>
cd <project-folder>
```

---

## 2. Create Virtual Environment

### Windows

```bash
python -m venv venv
venv\Scripts\activate
```

### Linux / Mac

```bash
python3 -m venv venv
source venv/bin/activate
```

---

## 3. Install Dependencies

```bash
pip install flask flask-cors
```

---

# Running the Application

```bash
python app.py
```

The Flask server will start at:

```bash
http://127.0.0.1:5000/
```

---

# API Endpoints

---

# 1. Home Route

## Endpoint

```http
GET /
```

## Description

Renders the frontend homepage using:

```bash
templates/index.html
```

---

# 2. Get Applied Jobs

## Endpoint

```http
GET /applied-jobs
```

## Description

Returns all applied job applications from the CSV file.

---

## Sample Response

```json
[
  {
    "Job_ID": "101",
    "Title": "Backend Developer",
    "Company": "Google",
    "HR_Name": "John Doe",
    "HR_Link": "https://linkedin.com/in/johndoe",
    "Job_Link": "https://company.com/job/101",
    "External_Job_link": "https://linkedin.com/jobs/view/101",
    "Date_Applied": "2026-05-27 10:30:00"
  }
]
```

---

## Error Response

### File Not Found

```json
{
  "error": "No applications history found"
}
```

---

# 3. Update Applied Date

## Endpoint

```http
PUT /applied-jobs/<job_id>
```

## Description

Updates the `Date Applied` field of the specified job with the current timestamp.

---

## Example Request

```http
PUT /applied-jobs/101
```

---

## Success Response

```json
{
  "message": "Date Applied updated successfully"
}
```

---

## Error Responses

### Job ID Not Found

```json
{
  "error": "Job ID 101 not found"
}
```

### CSV File Missing

```json
{
  "error": "CSV file not found"
}
```

---

# Example cURL Requests

## Get All Jobs

```bash
curl http://127.0.0.1:5000/applied-jobs
```

---

## Update Applied Date

```bash
curl -X PUT http://127.0.0.1:5000/applied-jobs/101
```

---

# Future Improvements

- Add database support (SQLite/MySQL/PostgreSQL)
- Authentication system
- Search and filtering
- Pagination
- Export to Excel
- Add job status tracking
- Docker support
- Deploy on Render/Heroku/AWS

---

# Author

## Darshan Salunke

Backend Developer | Python Developer

---

# License

This project is licensed under the MIT License.

```text
MIT License © 2026
```