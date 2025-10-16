# 📝 Full-Featured Django Blog Application

## 📘 Project Overview
This project is a **complete, full-stack Blog Application** built using the **Django web framework**.  
It demonstrates a robust, scalable web solution for content management and user interaction, featuring secure authentication, CRUD functionality, and a fully custom front-end design without CSS frameworks.

Users can register, log in, manage their profiles (including profile pictures), and perform full CRUD (Create, Read, Update, Delete) operations on blog posts.  
The app adheres strictly to Django’s **Model-Template-View (MTV)** architecture.

---

## ⚙️ Tech Stack

| Component | Technology | Purpose |
|------------|-------------|----------|
| **Backend Framework** | Django | Handles routing, models, and application logic |
| **Programming Language** | Python | Core backend development |
| **Database** | PostgreSQL | Persistent data storage (Users, Profiles, Posts) |
| **Frontend** | HTML5 | Provides semantic page structure |
| **Styling** | Custom CSS | Defines responsive layout and aesthetics |
| **Image Handling** | Pillow | Manages profile image uploads |
| **Database Adapter** | psycopg2-binary | Enables Django-PostgreSQL communication |

> ⚠️ *Note:* This project **does not use Bootstrap or any CSS frameworks** — all styling is written from scratch in pure CSS.

---

## 🧩 Application Structure

The project is divided into two main Django apps:
1. **Blog App** – manages post creation, viewing, editing, and deletion.
2. **Users App** – handles authentication, registration, and profile management.

### 🧱 Data Model Overview

| Model | Purpose | Key Fields | Relationships |
|--------|----------|-------------|----------------|
| **User** *(Django built-in)* | Authentication | `username`, `email`, `password` | One-to-One with Profile; One-to-Many with Post |
| **Profile** | Extends user with custom data | `image` (profile picture) | One-to-One with User |
| **Post** | Core blog content | `title`, `content`, `date_posted`, `author` | Many Posts per User |

**Relationships:**
- 1️⃣ One User → Many Posts  
- 1️⃣ One User → One Profile

---

## ✨ Core Features

### 🗒️ Blog Content Management (CRUD)
- **Create:** Authenticated users can write and publish posts.
- **Read:**  
  - Homepage shows paginated post list.  
  - Individual post detail views.  
  - User-specific post lists.
- **Update:** Authors can edit their own posts.
- **Delete:** Authors can delete their own posts permanently.

### User Stories
The application provides the following core functional features:
- As a user, I can register a new account.
- As a user, I can log in and log out of the application.
- As a user, I can update my account details (username, email).
- As a user, I can upload and update a custom profile picture.
- As a user, I can securely reset my password via an email link.
- As a user, I can view all posts written by a specific user on a dedicated page.


### 👤 User Authentication & Profiles
- Register new accounts.
- Log in and log out securely.
- Update username, email, and profile picture.
- Reset password securely via email.
- View posts by specific users.

### 🎨 Frontend & Usability
- Fully responsive custom layout using CSS Grid and Flexbox.
- Consistent design across all pages.
- Intuitive navigation for easy content management.

---

## 🛠️ Installation Guide

### 1️⃣ Prerequisites
Ensure you have:
- **Python 3.x**
- **PostgreSQL** (installed and running)
- **Git** (for cloning the repository)

### 2️⃣ Clone the Repository
```bash
git clone [YOUR_REPOSITORY_URL]
cd [PROJECT_FOLDER_NAME]
```
### 3️⃣ Create and Activate a Virtual Environment
```bash
python3 -m venv venv
source venv/bin/activate      # macOS/Linux
.\venv\Scripts\activate       # Windows
```
### 4️⃣ Install Dependencies
```bash
pip install -r requirements.txt
```
### 5️⃣ Configure PostgreSQL Database
Create a new PostgreSQL database:
```sql
CREATE DATABASE capstone_blog_db;
```
Update your settings.py file:

```python
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': 'capstone_blog_db',
        'USER': '[YOUR_POSTGRES_USER]',
        'PASSWORD': '[YOUR_POSTGRES_PASS]',
        'HOST': 'localhost',
        'PORT': '5432',
    }
}
```
### 6️⃣ Apply Migrations
```bash
python manage.py makemigrations
python manage.py migrate
```

### 7️⃣ Create a Superuser
```bash
python manage.py createsuperuser
```

### 8️⃣ Run the Development Server
```bash
python manage.py runserver
```
Visit the app at 👉 http://127.0.0.1:8000/
