# ⚡ DJANGO COMPLETE MASTER GUIDE  
## 🚀 Python Backend Framework (Beginner → Advanced → Pro)

---

# 📖 What is Django?

### English
Django is a high-level Python web framework that allows fast development of secure and scalable web applications.

### বাংলা
Django হলো Python-এর একটি powerful backend framework যা দিয়ে দ্রুত, secure এবং scalable web application বানানো যায়।

---

# 🌟 Why Django?

- ⚡ Fast Development
- 🔐 Built-in Security
- 🧠 Powerful ORM
- 🚀 Admin Panel Ready
- 🌐 REST API Support
- 📦 Scalable Architecture

---

# 🛠️ INSTALLATION

## Install Django

```bash
pip install django
```

---

## Check Version

```bash
django-admin --version
```

---

## Create Project

```bash
django-admin startproject myproject
```

---

## Run Server

```bash
cd myproject
python manage.py runserver
```

👉 Open:
```
http://127.0.0.1:8000/
```

---

# 📁 PROJECT STRUCTURE

```
myproject/
 ├── manage.py
 ├── myproject/
 │     ├── settings.py
 │     ├── urls.py
 │     ├── wsgi.py
 ├── app/
```

---

# 🧱 CREATE APP

```bash
python manage.py startapp core
```

---

# ⚙️ BASIC COMMANDS

## Migrations

```bash
python manage.py makemigrations
python manage.py migrate
```

---

## Create Superuser

```bash
python manage.py createsuperuser
```

---

## Start App Server

```bash
python manage.py runserver
```

---

# 👋 BASIC VIEW

## views.py

```python
from django.http import HttpResponse

def home(request):
    return HttpResponse("Hello Django")
```

---

## urls.py

```python
from django.urls import path
from . import views

urlpatterns = [
    path('', views.home),
]
```

---

# 🌐 DJANGO MTV ARCHITECTURE

```
Model → Template → View
```

---

# 🗄️ DATABASE (ORM)

## Model Example

```python
from django.db import models

class User(models.Model):
    name = models.CharField(max_length=100)
    age = models.IntegerField()
```

---

## Apply Model

```bash
python manage.py makemigrations
python manage.py migrate
```

---

## Query Data

```python
User.objects.all()
User.objects.create(name="Rahat", age=25)
```

---

# 🔐 DJANGO ADMIN PANEL

## Enable Admin

```bash
python manage.py createsuperuser
```

---

## Register Model

```python
from django.contrib import admin
from .models import User

admin.site.register(User)
```

---

👉 Admin URL:
```
http://127.0.0.1:8000/admin
```

---

# 🌐 DJANGO REST API

## Install DRF

```bash
pip install djangorestframework
```

---

## Add in settings.py

```python
INSTALLED_APPS = [
    'rest_framework',
]
```

---

## Simple API View

```python
from rest_framework.response import Response
from rest_framework.decorators import api_view

@api_view(['GET'])
def api_home(request):
    return Response({"message": "Hello API"})
```

---

# 🔁 CRUD API

## CREATE

```python
User.objects.create(name="Rahat")
```

## READ

```python
User.objects.all()
```

## UPDATE

```python
user = User.objects.get(id=1)
user.name = "New"
user.save()
```

## DELETE

```python
User.objects.get(id=1).delete()
```

---

# 🗄️ DATABASE CONFIG

## SQLite (Default)

```python
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.sqlite3',
        'NAME': BASE_DIR / "db.sqlite3",
    }
}
```

---

## MySQL Setup

```bash
pip install mysqlclient
```

```python
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.mysql',
        'NAME': 'test',
        'USER': 'root',
        'PASSWORD': '',
        'HOST': 'localhost',
    }
}
```

---

# 🔐 AUTH SYSTEM

## Login Check

```python
from django.contrib.auth import authenticate

user = authenticate(username="admin", password="123")
```

---

## Login Required

```python
from django.contrib.auth.decorators import login_required

@login_required
def dashboard(request):
    return HttpResponse("Dashboard")
```

---

# 📦 TEMPLATES (HTML)

```python
return render(request, "index.html")
```

---

# 🌐 STATIC FILES

```python
STATIC_URL = '/static/'
```

---

# ⚡ DJANGO COMMANDS

```bash
django-admin startproject project
python manage.py startapp app
python manage.py runserver
python manage.py makemigrations
python manage.py migrate
python manage.py createsuperuser
```

---

# 🧰 BEST TOOLS

## 💻 IDE
- VS Code (Best)
- PyCharm
- Sublime Text

---

## 🔌 EXTENSIONS
- Python Extension
- Django Snippets
- Pylance
- Prettier

---

## 🌐 TOOLS
- Postman (API testing)
- DB Browser for SQLite
- MySQL Workbench
- Git & GitHub

---

# 🏗️ PROJECT IDEAS

- Blog System
- E-commerce Backend
- Admin Dashboard
- Inventory System
- ERP System
- API Backend SaaS
- Social Media App

---

# 🏆 LEARNING ROADMAP

## 🟢 Beginner
- Python basics
- Django setup
- Views & URLs

## 🟡 Intermediate
- Models
- ORM
- Templates

## 🟠 Advanced
- REST API
- Authentication
- Database design

## 🔴 Expert
- Microservices
- Celery (background tasks)
- Docker deployment
- Production server (Nginx + Gunicorn)

---

# 💡 PRO TIPS

- Always use virtual environment
- Follow MVC pattern
- Use Django REST Framework for APIs
- Keep settings secure
- Separate apps for modules

---

# 👨‍💻 DEVELOPER

**Md. Moklasur Rahman Rahat**

🚀 Full Stack Developer  
⚡ Django & Python Backend Specialist  
💻 API & SaaS Builder  

GitHub: codexvisual

---

⭐ If you like this Django guide, give it a star on GitHub
