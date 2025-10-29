# 🌍 ALX Travel App

The **ALX Travel App** is a real-world Django application that lays the foundation for a travel listing platform.
This milestone focuses on setting up a scalable backend, integrating MySQL for database management, and using Swagger for automated API documentation.

---

## 🚀 Project Overview

This project sets up the initial structure of a Django RESTful API with a focus on:

* Modular and scalable configuration
* Secure environment variable management
* MySQL database integration
* CORS and Swagger setup for modern API development

The **`listings`** app powers the core functionalities of the travel platform, such as managing destinations, packages, and listings.

---

## ⚙️ Setup Instructions

### 1️⃣ Create and Activate a Virtual Environment

```bash
python -m venv venv
source venv/bin/activate  # On Windows use: venv\Scripts\activate
```

### 2️⃣ Install Required Packages

```bash
pip install django djangorestframework django-cors-headers drf-yasg celery
```

🐇 **RabbitMQ** is not installed via pip — it’s a message broker service.
You can install it on your system or use Docker:

```bash
# Run RabbitMQ with Docker
docker run -d --hostname my-rabbit --name rabbitmq \
  -p 5672:5672 -p 15672:15672 rabbitmq:3-management
```

### 3️⃣ Create the Django Project and App

```bash
django-admin startproject alx_travel_app
cd alx_travel_app
python manage.py startapp listings
```

### 4️⃣ Add Required Apps in `alx_travel_app/settings.py`

```python
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'rest_framework',
    'corsheaders',
    'drf_yasg',
    'listings',
]
```

### 5️⃣ Configure Middleware for CORS

```python
MIDDLEWARE = [
    'corsheaders.middleware.CorsMiddleware',
    'django.middleware.common.CommonMiddleware',
    'django.middleware.security.SecurityMiddleware',
    'django.contrib.sessions.middleware.SessionMiddleware',
    'django.middleware.csrf.CsrfViewMiddleware',
    'django.contrib.auth.middleware.AuthenticationMiddleware',
    'django.contrib.messages.middleware.MessageMiddleware',
    'django.middleware.clickjacking.XFrameOptionsMiddleware',
]

CORS_ALLOW_ALL_ORIGINS = True
```

### 6️⃣ Verify Installation

```bash
python manage.py runserver
```

Output:

```
Django version X.X.X, using settings 'alx_travel_app.settings'
Starting development server at http://127.0.0.1:8000/
```

---

## 🧱 Project Structure

```
alx_travel_app/
│
├── alx_travel_app/
│   ├── __init__.py
│   ├── asgi.py
│   ├── settings.py
│   ├── urls.py
│   ├── wsgi.py
│
├── listings/
│   ├── __init__.py
│   ├── admin.py
│   ├── apps.py
│   ├── models.py
│   ├── serializers.py
│   ├── urls.py
│   ├── views.py
│
├── manage.py
├── requirements.txt
└── README.md
```

---

## 🧠 Tools and Technologies

* **Django** — Web framework
* **Django REST Framework (DRF)** — RESTful APIs
* **drf-yasg** — Swagger documentation
* **django-cors-headers** — Cross-Origin Resource Sharing
* **Celery + RabbitMQ** — Background task management (future)

---

## 📘 API Documentation (Swagger)

Once configured, visit:
👉 [http://127.0.0.1:8000/swagger/](http://127.0.0.1:8000/swagger/)

---

## 👥 Contributors

**Maintainer:** Ondah James
**Program:** ALX Software Engineering / Backend Development

---

## 🏁 License

This project is part of the **ALX Program** and follows educational use guidelines.
You may modify or extend it for personal learning or portfolio purposes.
