post_list.html
```py
{% extends 'templates/af/base.html' %}
{% block content %}
    {% for post in posts %}
        <h1><a href="{% url 'post_detail' slug=post.slug %}">{{ post.title }}</a></h1><br>
        {{ post.text }}<br>
        username : {{ post.author.username }}<br>
        {{ post.created_date }}<br>
    {% endfor %}
{% endblock %}
```
