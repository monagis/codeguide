# Django

## Imports


```python
# future
from __future__ import unicode_literals

# standard library
import json
from itertools import chain

# third-party
import bcrypt

# Django
from django.http import Http404
from django.http.response import (
    Http404, HttpResponse, HttpResponseNotAllowed, StreamingHttpResponse,
    cookie,
)

# local Django
from myapp.models import MyModel
```

## Models

- If a field definition should span more than a single line then each argument should be passed on another line. While this may seem like a waste of space as models grow in size this will keep field definitions readable.

```python
from django.db import models
from geography.models import ZipCode


class Restaurant(models.Model):
    name = models.CharField(max_length=40)
    zip_code = models.ForeignKey(
        ZipCode,
        on_delete=models.SET_NULL,
        blank=True,
        null=True,
    )
```

- The **class `Meta`** should appear after the fields are defined, with a single blank line separating the fields and the class definition.

```python
# Do this:

class Person(models.Model):
    first_name = models.CharField(max_length=20)
    last_name = models.CharField(max_length=40)

    class Meta:
        verbose_name_plural = 'people'
```

- The order of model inner classes and standard methods should be as follows (noting that these are not all required):
	- All database fields
	- Custom manager attributes
	- class Meta
	- def __str__()
	- def save()
	- def get_absolute_url()
	- Any custom methods

- If choices is defined for a given model field, define each choice as a tuple of tuples, with an all-uppercase name as a class attribute on the model. Example:

```python
class MyModel(models.Model):
    DIRECTION_UP = 'U'
    DIRECTION_DOWN = 'D'
    DIRECTION_CHOICES = (
        (DIRECTION_UP, 'Up'),
        (DIRECTION_DOWN, 'Down'),
    )
```


## Views

In Django views, the first parameter in a view function should be called request.

```python
# Do this:

def my_view(request, foo):
    # ...

# Don’t do this:

def my_view(req, foo):
    # ...
```


## Templates

```
{% raw %}
# Do This:

{{ foo }}

# Don’t do this:

{{foo}}
{% endraw %}
```

