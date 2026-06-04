# 🎯 Django Projects

Collection of Django web applications demonstrating enterprise-grade backend development with best practices.

## 📋 Overview

This repository contains multiple Django projects showcasing:
- MVT (Model-View-Template) architecture
- Django ORM and database design
- RESTful API development
- User authentication and authorization
- Middleware and decorators
- Django admin customization
- Testing and documentation
- Production deployment strategies

## 🛠️ Technologies Used

- **Framework**: Django 3.2+, Django REST Framework
- **Language**: Python 3.8+
- **Database**: PostgreSQL, SQLite
- **API**: Django REST Framework
- **Task Queue**: Celery (optional)
- **Testing**: pytest, Django TestCase
- **Frontend**: HTML5, CSS3, JavaScript

## 📁 Project Structure

```
project/
├── manage.py
├── requirements.txt
├── .env.example
├── config/
│   ├── settings.py
│   ├── urls.py
│   ├── asgi.py
│   └── wsgi.py
├── apps/
│   ├── users/
│   │   ├── models.py
│   │   ├── views.py
│   │   ├── urls.py
│   │   └── serializers.py
│   ├── products/
│   ├── orders/
│   └── core/
├── templates/
├── static/
├── media/
└── tests/
```

## ✨ Key Features

- ✅ Database modeling with relationships
- ✅ Custom user models and authentication
- ✅ Permission-based access control
- ✅ Signal handlers for automation
- ✅ Query optimization (select_related, prefetch_related)
- ✅ API versioning
- ✅ API documentation with Swagger
- ✅ Comprehensive testing
- ✅ Environment-based configuration
- ✅ Security best practices

## 🚀 Getting Started

### Prerequisites
- Python 3.8+
- pip
- PostgreSQL (optional)

### Installation

```bash
# Clone repository
git clone https://github.com/codexvisual/Django.git
cd Django

# Create virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Setup environment variables
cp .env.example .env

# Run migrations
python manage.py migrate

# Create superuser
python manage.py createsuperuser

# Run development server
python manage.py runserver
```

### Access
- Application: http://localhost:8000
- Admin Panel: http://localhost:8000/admin

## 📚 Django Concepts

### Models

```python
from django.db import models

class User(models.Model):
    name = models.CharField(max_length=100)
    email = models.EmailField(unique=True)
    created_at = models.DateTimeField(auto_now_add=True)
    
    def __str__(self):
        return self.name
```

### Views

```python
from django.shortcuts import render
from rest_framework.decorators import api_view
from rest_framework.response import Response

@api_view(['GET', 'POST'])
def user_list(request):
    if request.method == 'POST':
        # Handle POST
        pass
    return Response({'users': []})
```

### URLs

```python
from django.urls import path
from . import views

urlpatterns = [
    path('users/', views.user_list, name='user-list'),
    path('users/<int:pk>/', views.user_detail, name='user-detail'),
]
```

### Serializers

```python
from rest_framework import serializers
from .models import User

class UserSerializer(serializers.ModelSerializer):
    class Meta:
        model = User
        fields = ['id', 'name', 'email', 'created_at']
```

## 🧪 Testing

```bash
# Run all tests
python manage.py test

# Run specific app tests
python manage.py test apps.users

# With pytest
pytest
pytest --cov=apps
```

### Test Example

```python
from django.test import TestCase
from .models import User

class UserTestCase(TestCase):
    def setUp(self):
        User.objects.create(name="Test", email="test@example.com")
    
    def test_user_created(self):
        user = User.objects.get(name="Test")
        self.assertEqual(user.email, "test@example.com")
```

## 🔒 Security Features

- CSRF protection
- XSS prevention
- SQL injection protection
- Password hashing with bcrypt
- Secure session management
- CORS configuration
- Rate limiting
- Input validation

## 📊 API Documentation

Access Swagger docs at: `/api/schema/swagger/`

## 🌐 Database Migrations

```bash
# Create migrations
python manage.py makemigrations

# Apply migrations
python manage.py migrate

# View migration status
python manage.py showmigrations

# Revert migration
python manage.py migrate app_name 0001
```

## 🚀 Deployment

### Using Gunicorn

```bash
pip install gunicorn
gunicorn config.wsgi:application
```

### Using Docker

```bash
docker build -t django-app .
docker run -p 8000:8000 django-app
```

## 📦 Requirements

```
Django==4.2.0
DjangoRestFramework==3.14.0
Postgres==15.0
celery==5.2.0
redis==4.5.0
pytest==7.0.0
pytest-django==4.5.0
```

## 💡 Best Practices

- Use virtual environments
- Keep settings in environment variables
- Use class-based views
- Implement proper error handling
- Write comprehensive tests
- Use Django signals judiciously
- Optimize database queries
- Implement caching
- Use transactions for critical operations

## 🔗 Useful Resources

- [Django Documentation](https://docs.djangoproject.com/)
- [Django REST Framework](https://www.django-rest-framework.org/)
- [PostgreSQL Documentation](https://www.postgresql.org/docs/)
- [Celery Documentation](https://docs.celeryproject.io/)

## 🤝 Contributing

Contributions are welcome! Please:
1. Fork the repository
2. Create a feature branch
3. Make your improvements
4. Submit a pull request

## 📧 Support

For issues and questions, please open an issue on GitHub.

---

Made with 🔥 for Django developers