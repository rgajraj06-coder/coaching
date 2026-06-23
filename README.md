# Udaan Master Admin - Coaching Management System

A comprehensive administration panel for managing a coaching institute, featuring student registries, mock test results, faculty management, and a dashboard with real-time statistics simulated through `localStorage`.

## 🚀 Features

- **Master Dashboard**: Overview of total registrations, tests taken, and simulated revenue.
- **Student Registry**: Manage student enrollment, track trial periods (3-day default), and mark fee payments.
- **Mock Test Results**: Review and approve student test submissions.
- **Faculty Management**: Overview of faculty members, their subjects, and assigned batches.
- **Course Catalog**: Visual representation of active courses like IIT-JEE, NEET, and Foundation.
- **Fee Management**: Sandbox for tracking student payments and overdue receipts.
- **Authentication Guard**: Simulated admin session check to prevent unauthorized access.

## 🗄️ Database Schema (localStorage)

The project uses `localStorage` to persist data in the browser. Below are the primary keys and their structures:

### 1. `udaan-users-db` (Array of Objects)
Stores all registered users (Students and Faculty).
- `id`: Unique identifier.
- `name`: Full name.
- `role`: 'student' or 'faculty'.
- `mobile`/`email`: Contact information.
- `course`/`batch`: Academic details.
- `paid`: Boolean (for students).
- `feeStatus`: 'paid' or 'pending'.
- `joinedAt`: Timestamp (used for trial calculation).
- `paymentHistory`: Array of simulated transactions.

### 2. `udaan-results` (Array of Objects)
Stores mock test submissions.
- `id`: Unique submission ID (e.g., `SUB-12345`).
- `student`: Name of the student.
- `studentId`: Reference to user ID.
- `course`: Course name.
- `score`: Achieved marks.
- `total`: Maximum marks.
- `date`: Submission date.
- `approved`: Boolean (released to student).

### 3. `udaan-user-session` (Object)
Stores the currently logged-in user's data.
- `role`: Must be 'admin' to access `admin-panel.html`.

## 🛠️ Getting Started

1. **Accessing the Panel**: Open `admin-panel.html` in any modern web browser.
2. **Authentication**: The panel requires a valid session in `localStorage`.
   - If not logged in as an admin, it redirects to `login.html` (which should populate the `udaan-user-session`).
3. **Data Population**: The system dynamically populates tables from `udaan-users-db` and `udaan-results`.

## 💻 Tech Stack

- **Frontend**: HTML5, CSS3 (Custom Variables, Flexbox, Grid).
- **Styling**: Google Fonts (Outfit, Inter).
- **Logic**: Vanilla JavaScript.
- **Storage**: Browser `localStorage` API.

## 📄 License
This project is for demo purposes as part of the Udaan Coaching Website.
