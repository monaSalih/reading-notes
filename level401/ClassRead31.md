# A Beginner's Guide to Docker

- Docker which is a way to isolate and run entire applications.
- doesn’t matter if you are using a Mac, Windows, or Linux computer anymore.
- The entire development environment is isolated: programming language, software packages, databases, and more.
- Docker is a complex beast under the hood. However a little knowledge can take you a long way and that’s the goal of this guide!

## Linux Containers
- Docker is really just Linux containers which are a type of virtualization.
- Virtualization has its roots at the beginning of computer science when large, expensive mainframe computers were the norm
- Linux containers, also known as “containerization,”
- Virtual Machines are like homes: stand-alone buildings with their own infrastructure
- Docker containers are like apartments: they share common infrastructure like plumbing and heating, but come in various sizes that match the exact needs of an owner.

## Containers vs Virtual Environments

* **Virtual Environments**
- used to isolate Python software packages locally.
- can only isolate Python packages.

> we can’t run a production database or other services within virtual environments so compared to Docker containers they are far more limited.

## Install Docker

```
$ docker --version
Docker version 19.03.5, build 633a0ea
```

**Docker Compose**
is an additional tool that is automatically included with Mac and Windows downloads of Docker. 
```
sudo pip install docker-compose
```
## Images and Containers
* A baking analogy we can use here is as follows:

- A Dockerfile is the recipe for a cake
- An image is a snapshot of the recipe at a given time
- A docker-compose.yml says how to make the cake
- And the container is the actual, baked cake

> There are a large number of official images available on Docker Hub 

**Images**
```
$ cd ~/Desktop
$ mkdir code && cd code
$ mkdir python3.7 && cd python3.7
$ touch Dockerfile
```

**Containers**
To demonstrate a real-world image and container example we will now “Dockerize” a basic Django web app. 
```
$ cd ..
$ mkdir djangoapp && cd djangoapp
$ pipenv install django==3.0
$ pipenv shell
(djangoapp) $ django-admin startproject example_project .
(djangoapp) $ python manage.py runserver
```
----
# Library Website and API

Django REST Framework works alongside the Django web framework to create web APIs.
## Traditional Django
First we need a dedicated directory on our computer to store the code. 
```
CREATE DJANGO AS USUALLY AND ADD APP
```
* Django REST Framework

```
(library) $ pipenv install djangorestframework~=3.11.0
```
add to setting for example
```
# config/settings.py
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',

    # 3rd party
    'rest_framework', # new

    # Local
    'books',
]
```
**then create new api**
```
(library) $ python manage.py startapp api
python manage.py migrate
```
**URLs**
include the api app and configure its URL route
```
# config/urls.py
from django.contrib import admin
from django.urls import path, include

urlpatterns = [
    path('admin/', admin.site.urls),
    path('api/', include('api.urls')), # new
    path('', include('books.urls')),
]
```
* create a urls.py file within the api app and update it as follows:
```
(library) $ touch api/urls.py

# api/urls.py
from django.urls import path
from .views import BookAPIView

urlpatterns = [
    path('', BookAPIView.as_view()),
]
```
**Views**

# api/views.py
```
from rest_framework import generics

from books.models import Book
from .serializers import BookSerializer


class BookAPIView(generics.ListAPIView):
    queryset = Book.objects.all()
    serializer_class = BookSerializer
```


**Serializers**
serializers.py file within our api app.

```
(library) $ touch api/serializers.py
Then update it as follows in a text editor.

# api/serializers.py
from rest_framework import serializers

from books.models import Book


class BookSerializer(serializers.ModelSerializer):
    class Meta:
        model = Book
        fields = ('title', 'subtitle', 'author', 'isbn')
```

**cURL**

```
(library) $ python manage.py runserver

$ curl http://127.0.0.1:8000/api/
[  
   {  
      "title":"Django for Beginners",
      "subtitle":"Build websites with Python and Django",
      "author":"William S. Vincent",
      "isbn":"978-198317266"
   }
]
```