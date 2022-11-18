I have `models.py`, `home.html` that look like these,

<em>models.py</em>
```py
from django.db import models
from django.contrib.auth.models import User


# Create your models here.
class Topic(models.Model):
    
    name = models.CharField(max_length=200)
    
    def __str__(self):
        return self.name

class Room(models.Model):
    host = models.ForeignKey(User, on_delete=models.SET_NULL, null=True)
    topic = models.ForeignKey(Topic, on_delete=models.SET_NULL, null=True)
    name = models.CharField(max_length=200)
    description = models.TextField(null=True,blank=True)
    # participants = 
    
    # takes a snapshot of everytime
    updated=models.DateTimeField(auto_now=True)
    
    # takes a timestamp of only  when it was created
    created=models.DateTimeField(auto_now_add=True)

    def __str__(self):
        return self.name

class Message(models.Model):
    user = models.ForeignKey(User, on_delete=models.CASCADE)
    room = models.ForeignKey(Room, on_delete=models.CASCADE)
    body = models.TextField()

    # takes a snapshot of everytime
    updated=models.DateTimeField(auto_now=True)
    
    # takes a timestamp of only  when it was created
    created=models.DateTimeField(auto_now_add=True)


    def __str__(self):
        return self.body[:50]
```
<em>home.html</em>
```html
{% extends "main.html" %}


{% block content %}
<h1>home template</h1>

<div>
    <div>
        {% for room in rooms %}
            <div>
                <h5>hosted by {{room.host}}</h5>
                <h3>{{room.id}} -- <a href="{% url 'room' room.id %}">{{room.name}}</a> (updated: {{room.updated}})</h3>
                <h5>Created : {{room.created}}</h5>
            </div>
            
            <div>
                {% for each in messages %}
                    {% if each.room == room %}    
                        <h5>message : {{each.body}}</h5>
                    {% endif %}
                {% endfor %}
            </div>
        <hr>
        {% endfor %}
    </div>
</div>
{% endblock %}
```
And I would like to show the total number of messages in each room instead of showing `{{each.body}}`.

