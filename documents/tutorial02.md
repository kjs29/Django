```py
import datetime
from django.utils import timezone
from django.db import models

class Question(models.Model):
    # ...
    pub_date = models.DateTimeField('date publisehd', timezone.now()) # 1
    
    def was_published_recently(self):
        return self.pub_date >= timezone.now() - datetime.timedelta(days=1) # 2
```

1.

```py
pub_date = models.DateTimeField('date publisehd')
```

`date published` is a human-readable name. 

The human-readable name is used in the following places:

- In the admin interface, the human-readable name is used as the label for the field in the form.

- When you use the field in a form, it will be used as the label for the form field

- When you use the field in a model form, it will be used as the label for the form field

- When you use the field in the serializer, it will be used as the label for the serialized field

If you don't specify a human-readable name, Django will use the name of the field as the label.

It's worth noting that you can also use the verbose_name attribute of a field to set the human-readable name, but this is less common and the first positional argument is more readable and common.

2.

```py
tomorrow = datetime.now() + datetime.timedelta(days=1)
```

So if it hasn't been a day or less since its published date, it will return True otherwise False.

---


