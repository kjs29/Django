# This repository is for creating a website using Django

# What is Django?

Django is free and open source web application framework, written in Python.

Frameworks exist to save you from having to reinvent the wheel.

Source 

- [DjangoGirls Tutorials](https://tutorial.djangogirls.org/en/django/)

- [Django official document](https://docs.djangoproject.com/en/4.1/)

# Django follows this MVT(MODEL VIEW TEMPLATE) structure.

![basic-django](https://user-images.githubusercontent.com/96529477/214358944-bfc56162-8513-4173-acba-e8326cc81945.png)

[Source : Mozilla website](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Django/Introduction)


# Things I learned.
.

.

.

## - Learn from [Official Django Documentation](https://docs.djangoproject.com/en/4.1/) and [Django Core Contributors](https://github.com/django/django/graphs/contributors) 

## - DRY is important but understanding core concepts of Django such as MVT architecture (I like to call it MVT since View is in the middle), URL routing, basic database management, should come first for beginners like me.

## - Learning Class based views without understanding how Django works is like building a castle on sand. Not a good solid way to start. I am a beginner. 

## - `views.py`handles HTTP REQUESTS. Request -> Response
```
# What views.py can do
# Pull data from database
# Transform data
# Send email
# Anything that is possible...
```

## - `views.py` is the core engine of Django. It is literally like a function. It takes input and returns an output. Practice function based view first to understand how view works.

## - Django Template Language is important but it is intended to avoid advanced logic. Even Django Document mentions that it shouldn't be assumed as Python knowledge (https://docs.djangoproject.com/en/4.1/misc/design-philosophies/#don-t-invent-a-programming-language)

## - How to add a new url 

<details>
  <summary>Click to expand</summary>
  
  
  Let's say I want to add a new url address(`/profile`) to my website called `lawyer.com` like `lawyer.com/profile`

  Assuming that we have created a project already, 

  On a project root directory, first I need to create an app called `profile_main`

  ```
  django-admin startapp profile_main
  ```

  1. Go to `urls.py` in the project folder (NOT an app folder), import `include` function and add path to <em>urls.py</em> in `profile_main`(app folder)

  ```py
  from django.contrib import admin

  # include include after path
  from django.urls import path, include

  urlpatterns = [
      path("admin/", admin.site.urls),

      # now a new URL 'lawyer.com/profile' is added,
      # it will search related sub URLS in the file profile_main/urls.py
      # this does NOT mean 'lawyer.com/' will work.
      path("profile/", include("profile_main.urls"))
  ]
  ```


  2. Create a `urls.py` in the app folder called `profile_main`

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

  3. Go to <em>views.py</em> in the `profile_main` folder, and decides what to show

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
  
</details>
