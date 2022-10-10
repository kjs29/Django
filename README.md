# This repository is for creating a website.

# Django

What is a Django?

Django is a python web based framework.

# Things I learned.

## - Every time I make an app, I need to go to settings.py, I need to register an app in the `INSTALLED_APPS`
## - `views.py` in the app folder handles REQUESTS. Request -> Response
```
# What views.py can do
# Pull data from database
# Transform data
# Send email
```
## - How to add a new url 

Let's say I want to add a new url address to my website called `lawyer.com` like `lawyer.come/profile`

First I need to create an app called `profile_main`
```
django-admin startapp profile
```
1. Create a `urls.py` in the app folder called `profile_main`

<em>profile(app folder)/urls.py</em>
```py
from django.urls import path

# from the current directory import views.py
from . import views

urlpatterns = [
    # always put / at the end of route
    
    # new URL(lawyer.com/profile) is added
    path("",views.index),
    
    # new URL(lawyer.com/profile/jin) is added
    path("jin/", views.say_hello)
]
```
2. Go to <em>urls.py</em> in the project folder (NOT an app folder), and add path to <em>urls.py</em> in `profile`(app folder)
```py
from django.contrib import admin

# include include after path
from django.urls import path, include

urlpatterns = [
    path("admin/", admin.site.urls),
    
    # playground means that people now can type homepageaddress/playground/ to go to the page and view it
    path("profile/", include("profile_main.urls"))
]
```
