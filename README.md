## Django Filter Search with Source Code

The Django Search Filter is easy for users to manipulate.

First, the user inputs their first name and last name and clicks the submit button.

The data entered is then stored in the table, and the user can filter the data inside the database.

## What is filter () in Django?

You can limit your search fields by using the filter() method to only return the rows that match the search term.

## How do I create a search query in Django?

The operator __search would be employed. 

In the Django Query Set API Reference, it is explained. 

There is also istarts with, which performs a starts-with search that is not case-sensitive.

It should be noted that __search is only supported by MySQL and that adding a full-text index necessitates direct database manipulation.

## Reminders

To perform this python django project make sure that you have knowledge in the following:

* **CSS**
* **HTML**
* **Javascript**
* **Database Management**

## Features of this django search filter

* **Adding Information Data Into Database**
* **Search Filtering The Data In The Database**

## In This Search Filter In Django Consist Of The Following Method:

* **blog** – In this method which is the main feature of this project.
* **server** – In this method which is the main method of this project.

## How to create a django search filter?

Here are the steps on how to create a Search Filter In Django With Source Code.

1. **Open file**.

open “pycharm professional” after that click “file” and click “new project”.

![image](https://github.com/user-attachments/assets/dd014b2f-3334-4c99-8442-594952e698c4)


2. **Choose Django**.
sfter clicking “new project“, choose “Django” and click.

![image](https://github.com/user-attachments/assets/17fa420d-d686-43d1-9d76-3d1b0c426dab)

3. **Select file location**.

Select a file location wherever you want.

4. **Create application name.**

Name your application.

5. **Click create**.

Finish creating project by clicking “create” button.

6. **Start of coding**.

You are free to copy the following codes below in the given modules and method required.

## The List Of Module Given Below Are Under The “Blog” Method

* The Code Given Below Is For The “views.py” Module – you can add the following code below into your “views.py” under the “Blog” method.

```
from django.shortcuts import render, redirect
from .models import Member
from django.db.models import Q

# Create your views here.

def index(request):
    members = Member.objects.all().order_by('lastname')
    return render(request, 'blog/index.html', {'members': members})

def create(request):
    member = Member(firstname=request.POST['firstname'], lastname=request.POST['lastname'])
    member.save()
    return redirect('/')

def search(request):

    members = Member.objects.filter(Q(firstname=request.GET.get('search')) | Q(lastname=request.GET.get('search')))
    return render(request, 'blog/index.html', {'members': members})
```

### In this module which is the index module of the Blog method.

* **The Code Given Below Is For The “urls.py” Module – you can add the following code below into your “urls.py” under the “Blog” method.**

```
from django.conf.urls import url
from . import views

urlpatterns = [
    url(r'^$', views.index, name='index'),
    url(r'^create$', views.create, name='create'),
    url(r'^search$', views.search, name='search'),
]
```

In this module which you can found classes to be call under Blog method.


### In this module which is the URL configuration module under Blog method.

* **The Code Given Below Is For The “models.py” Module – you can add the following code below into your “models.py” under the “Blog” method.**

```
from django.db import models

# Create your models here.
class Member(models.Model):
    firstname = models.CharField(max_length=50)
    lastname = models.CharField(max_length=50)

    def __str__(self):
        return self.firstname + " " + self.lastname
  ```


### 📌Here's the full documentation for the [Filter Search in Django](https://itsourcecode.com/free-projects/python-projects/django-filter-search-with-source-code/)
 

Read or visit the other interesting programming language used in search filter.

**[File Management System In PHP With Source Code](https://itsourcecode.com/free-projects/php-project/file-management-system-in-php-with-source-code/)**
