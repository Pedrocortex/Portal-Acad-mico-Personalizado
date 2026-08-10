# 🎓 EduTrack AI

A web application for **academic organization and management**, developed with Python and Streamlit and integrated with a REST API hosted on Xano.

EduTrack AI centralizes information about courses, professors, assignments, projects, and exams, while also providing a dashboard for monitoring academic performance.

--- 
🎓 Academic Project

EduTrack AI was developed as a college academic project with the goal of applying software development concepts in a practical environment.

Throughout the project, concepts such as Python programming, web application development, REST APIs, CRUD operations, authentication, data validation, database integration, and data visualization were applied to build a functional academic management system.

The project was designed to simulate a real-world application, combining backend integration, user authentication, data management, and an interactive interface into a single platform.

## 📌 About the Project

**EduTrack AI** was developed to simplify academic organization by providing a single platform for managing academic information.

The application includes user authentication, CRUD operations for academic data, and a dashboard for visualizing grades by course.

The system uses **Streamlit** as the web interface and an external **Xano API** for data persistence and backend management.

---

## 🚀 Features

### 🔐 Authentication

* User registration
* Email and password login
* Email validation
* Password validation
* JWT-based authentication
* Session persistence using cookies
* 24-hour session expiration
* Logout

The application uses a JWT token to authenticate requests sent to the API.

### 👨‍🏫 Professor Management

Users can:

* Register professors
* Add contact emails
* View registered professors
* Edit professor information
* Remove professors

### 📚 Course Management

Users can register and manage:

* Course name
* Professor
* Workload
* Absence limit
* Current absences
* Grade
* Weekday
* Class schedule

### ✅ Task Management

Tasks can include:

* Task name
* Type

  * Academic
  * Personal
* Status

  * Pending
  * In Progress
  * Completed
  * Overdue
* Description
* Assignment date
* Due date
* Link
* Score
* Related course
* Related project

### 📁 Project Management

Projects can be classified as:

* Academic
* Personal

Each project can contain:

* Name
* Description
* Link
* Start date
* End date
* Related course

### 📝 Exam Management

Users can register:

* Exam content
* Date
* Time
* Course
* Grade

### 📊 Dashboard

The main dashboard displays a performance chart showing grades for each course.

The chart is built using **Plotly**, with grades displayed on a 0–10 scale.

### 🌓 Theme Support

The application supports:

* ☀️ Light theme
* 🌙 Dark theme

Users can switch between themes directly from the interface.

---

## 🛠️ Technologies

| Technology          | Purpose                             |
| ------------------- | ----------------------------------- |
| 🐍 Python           | Main programming language           |
| 🎨 Streamlit        | Web interface                       |
| 📊 Pandas           | Data manipulation                   |
| 📈 Plotly           | Data visualization                  |
| 🌐 Requests         | HTTP communication with the API     |
| 🔑 JWT              | Authentication                      |
| ☁️ Xano             | Backend and REST API                |
| HTML/CSS/JavaScript | Interface customization and cookies |

The main application uses `pandas`, `plotly`, `streamlit`, and `requests`.

---

## 🏗️ Project Structure

```text
EduTrack-AI/
│
├── main.py
├── api.py
├── ultilitario.py
└── README.md
```

### `main.py`

The main application file.

Responsible for:

* Streamlit initialization
* Authentication
* Navigation
* User interface
* Professor CRUD
* Course CRUD
* Task CRUD
* Project CRUD
* Exam CRUD
* Dashboard
* Theme management

The main navigation is organized through the application's sidebar.

### `api.py`

Centralizes communication between Streamlit and Xano.

It provides functions for:

```text
GET
POST
PATCH
DELETE
```

The `api_get`, `api_post`, `api_patch`, and `api_delete` functions are used by the application modules to retrieve and modify backend records.

### `ultilitario.py`

Contains utility functions mainly responsible for data validation and text processing.

It includes:

* Text cleaning
* Character counting
* Name validation
* Email validation
* Password validation
* Whitespace removal

For example, passwords must contain at least 8 characters, one uppercase letter, one lowercase letter, one number, and one special character.

---

## ⚙️ Installation

### 1. Clone the repository

```bash
git clone https://github.com/YOUR-USERNAME/EduTrack-AI.git
```

Navigate to the project directory:

```bash
cd EduTrack-AI
```

### 2. Create a virtual environment

```bash
python -m venv venv
```

### 3. Activate the virtual environment

**Windows:**

```bash
venv\Scripts\activate
```

**Linux/macOS:**

```bash
source venv/bin/activate
```

### 4. Install dependencies

```bash
pip install -r requirements.txt
```

### 5. Run the application

```bash
streamlit run main.py
```

The Streamlit server will provide a local URL where the application can be accessed.

---

## 📦 Dependencies

Create a `requirements.txt` file containing:

```txt
pandas
plotly
streamlit
requests
```

---

## 🔄 Architecture

```text
┌─────────────────────────────┐
│            User             │
└──────────────┬──────────────┘
               │
               ▼
┌─────────────────────────────┐
│       Streamlit / UI        │
│          main.py            │
└──────────────┬──────────────┘
               │
               ▼
┌─────────────────────────────┐
│          API Layer          │
│           api.py            │
└──────────────┬──────────────┘
               │
          HTTP + JWT
               │
               ▼
┌─────────────────────────────┐
│            Xano             │
│        Backend / API        │
└─────────────────────────────┘
```

Data validation and utility functions are handled by `ultilitario.py`.

---

## 🔑 Authentication

The application uses **JWT-based authentication**.

After login, the token returned by the API is stored in the Streamlit session and used in subsequent requests through the following header:

```text
Authorization: Bearer <token>
```

This mechanism is implemented in `api.py`.

The application also uses cookies to maintain authentication between requests and includes session expiration control.

---

## 📊 Functional Overview

```text
                    EduTrack AI
                         │
        ┌────────────────┼────────────────┐
        │                │                │
        ▼                ▼                ▼
   Professors         Courses          Projects
        │                │                │
        │                ├───────────────┤
        │                │
        ▼                ▼
      Tasks             Exams
        │                │
        └────────┬───────┘
                 ▼
             Dashboard
                 │
                 ▼
        Academic Performance
```

---

## 🔒 Data Validation

The application validates user input before sending data to the API.

### Password

A password must:

* Contain at least 8 characters
* Contain no more than 255 characters
* Include an uppercase letter
* Include a lowercase letter
* Include a number
* Include a special character

### Name

The system checks:

* Required field
* Maximum length of 255 characters
* Presence of a surname when creating an account
* Maximum number of spaces

### Email

The system checks:

* Required field
* Maximum length
* No spaces
* No commas
* Exactly one `@`
* Basic domain structure

These validation rules are centralized in `ultilitario.py`.

---

## 🎯 Project Goals

This project applies concepts related to:

* Web application development
* Python programming
* Modular programming
* REST APIs
* CRUD operations
* Authentication
* Data manipulation
* Data visualization
* Frontend/backend integration
* Data validation
* State management
* User experience

---

## 🔮 Future Improvements

Possible future improvements include:

* [ ] Academic calendar
* [ ] Task and exam notifications
* [ ] More detailed attendance tracking
* [ ] Academic performance reports
* [ ] Overall grade calculation
* [ ] Dashboard filters
* [ ] Grade progression charts
* [ ] Task priority system
* [ ] External calendar integration
* [ ] Improved responsiveness
* [ ] Environment variables for API configuration
* [ ] Automated tests

---

## 👨‍💻 Academic Project

EduTrack AI was developed as a practical project to apply concepts related to **programming, databases, APIs, web development, and data analysis**.

---

## 📄 License

This project does not currently have a defined license.

If the project is intended to be publicly distributed, modified, or reused, it is recommended to add an appropriate license such as **MIT**, **Apache 2.0**, or **GPL**.

---

## 🤝 Contributing

Contributions are welcome.

To contribute:

```bash
git checkout -b my-feature
```

Make your changes and then:

```bash
git add .
git commit -m "feat: add new feature"
git push origin my-feature
```

Then open a **Pull Request**.

---

## 📬 Contact

Developed by **Cortez**.

If you have suggestions, find a bug, or would like to contribute, open an **Issue** in this repository.
