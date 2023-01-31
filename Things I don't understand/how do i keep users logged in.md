# How do I keep users logged in?

<em>models.py</em>

So I created a page when people can log in and out.

But there is more than just one page in the whole website.

So when I create the page 2 like this

```html
<a href="{% url 'page1' %}">click here</a>
```

The logged in user can't be logged in anymore. How can I solve this?

Right now all I know is that Middleware has to do with it.

