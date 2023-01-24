# This repository is for creating a website using Django

# What is a Django?

Django is free and open source web application framework, written in Python.

Frameworks exist to save you from having to reinvent the wheel.

Source 

- [DjangoGirls Tutorials](https://tutorial.djangogirls.org/en/django/)

- [Django official document](https://docs.djangoproject.com/en/4.1/)

# Django follows this MVT(MODEL VIEW TEMPLATE) structure.

![basic-django](https://user-images.githubusercontent.com/96529477/214358944-bfc56162-8513-4173-acba-e8326cc81945.png)

[Source : https://developer.mozilla.org/en-US/docs/Learn/Server-side/Django/Introduction](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Django/Introduction)


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

Let's say I want to add a new url address to my website called `lawyer.com` like `lawyer.com/profile`

First I need to create an app called `profile_main`

```
django-admin startapp profile_main
```

1. Create a `urls.py` in the app folder called `profile_main`

<em>profile_main (app folder)/urls.py</em>
```py
from django.urls import path

# from the current directory import views.py
from . import views

urlpatterns = [
    # always put / at the end of route
    
    # new URL(lawyer.com/profile) is added
    path("",views.profile_main),
    
    # new URL(lawyer.com/profile/jin) is added
    path("jin/", views.jin)
]
```
2. Go to <em>views.py</em> in the `profile_main` folder, and decides what to show
<em>profile_main / views.py</em>
```py
from django.shortcuts import render
from django.http import HttpResponse

# Create your views here
def profile_main(request):
    return HttpResponse("lawyer.com/profile")
def jin(request):
    return HttpResponse("lawyer.com/profile/jin")
```
3. Go to <em>urls.py</em> in the project folder (NOT an app folder), and add path to <em>urls.py</em> in `profile`(app folder)
```py
from django.contrib import admin

# include include after path
from django.urls import path, include

urlpatterns = [
    path("admin/", admin.site.urls),
    
    # now a new URL lawyer.com/profile is added, and it will search related sub URLS in the file profile_main/urls.py
    path("profile/", include("profile_main.urls"))
]
```
