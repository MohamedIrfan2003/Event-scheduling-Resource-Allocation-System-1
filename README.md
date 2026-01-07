# Event Scheduling & Resource Allocation System

## 📌 Project Description

This is a **Flask-based web application** that allows organizations to:

* Create and manage events (workshops, seminars, classes)
* Manage shared resources (rooms, instructors, equipment)
* Allocate resources to events
* Automatically **prevent scheduling conflicts** for the same resource
* Generate **resource utilization reports** within a selected date range

The system is built using **Flask**, **SQLAlchemy ORM**, and **SQLite**, following clean relational database design principles.

---

## ⚙️ Technologies Used

* Python 3.x
* Flask
* Flask-SQLAlchemy
* SQLite
* HTML (Jinja2 Templates)

---

## 🚀 Installation Instructions

### 1️⃣ Clone the Repository

```bash
git clone <your-repository-url>
cd event-scheduling-system
```

### 2️⃣ Create & Activate Virtual Environment

**Windows**

```bash
python -m venv venv
venv\Scripts\activate
```

**Linux / macOS**

```bash
python3 -m venv venv
source venv/bin/activate
```

### 3️⃣ Install Dependencies

```bash
pip install flask flask-sqlalchemy
```

---

## 🗄️ Database Setup

The application uses **SQLite** as the database.

* Database file: `events.db`
* Tables are **automatically created** when the app runs for the first time.

No manual SQL execution is required.

---

## ▶️ How to Run the Application

```bash
python app.py
```

* The application will start in **debug mode**
* Open your browser and go to:

```
http://127.0.0.1:5000/
```

---

## ✨ Features Implemented

### ✅ Event Management

* Add events with:

  * Title
  * Start time
  * End time
  * Description
* View all events

### ✅ Resource Management

* Add shared resources
* Categorize resources by type
* View all available resources

### ✅ Resource Allocation

* Allocate resources to events
* **Automatic conflict detection**
* Prevents double-booking of the same resource for overlapping time slots

### ✅ Conflict Validation Logic

* A resource cannot be allocated if:

  * Another event already uses it
  * Event times overlap

### ✅ Utilization Report

* Select date range
* View per-resource:

  * Total usage hours
  * Number of bookings
  * Upcoming future events

---

## 🗂️ Database Schema Diagram

```
+------------------+        +------------------------------+        +------------------+
|      Events      |        | EventResourceAllocations     |        |    Resources     |
+------------------+        +------------------------------+        +------------------+
| event_id (PK)    |◄───────| allocation_id (PK)           |───────►| resource_id (PK) |
| title            |        | event_id (FK)                |        | resource_name    |
| start_time       |        | resource_id (FK)             |        | resource_type    |
| end_time         |        +------------------------------+        +------------------+
| description      |
+------------------+
```

**Relationships:**

* One Event → Many Resource Allocations
* One Resource → Many Event Allocations
* Unique constraint on `(event_id, resource_id)`

---


## 📌 Future Enhancements (Optional)

* User authentication & roles
* Calendar-based event view
* Resource availability timeline
* Export reports (PDF / Excel)

---

## 👨‍💻 Author

Developed as part of an **Event Scheduling & Resource Allocation System project** using Flask & SQLAlchemy.

---

