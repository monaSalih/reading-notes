## Django Tutorial : Using models

Django models:
A model is the single, definitive source of information about your data. It contains the essential fields and behaviors of the data you’re storing. Generally, each model maps to a single database table.

the UML association diagram below shows how we can define model 
![](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Django/Models/local_library_model_uml.svg)

Model definition
Models are usually defined in an application's models.py file. They are implemented as subclasses of django.db.models.Model, and can include fields, methods and metadata. The code fragment below shows a "typical" model, named MyModelName:

```
from django.db import models

class MyModelName(models.Model):
    """A typical class defining a model, derived from the Model class."""

    # Fields
    my_field_name = models.CharField(max_length=20, help_text='Enter field documentation')
    ...

    # Metadata
    class Meta:
        ordering = ['-my_field_name']

    # Methods
    def get_absolute_url(self):
        """Returns the url to access a particular instance of MyModelName."""
        return reverse('model-detail-view', args=[str(self.id)])

    def __str__(self):
        """String for representing the MyModelName object (in Admin site etc.)."""
        return self.my_field_name

```

Metadata
You can declare model-level metadata for your Model by declaring class Meta, as shown.
```
class Meta:
    ordering = ['-my_field_name']
```
Methods
A model can also have methods.

Minimally, in every model you should define the standard Python class method __str__() to return a human-readable string for each object.

```
def __str__(self):
    return self.field_name
```
---

Model management
Once you've defined your model classes you can use them to create, update, or delete records, and to run queries to get all records or particular subsets of records.
---

Creating and modifying records
To create a record you can define an instance of the model and then call save().

**Create a new record using the model's constructor.**

record = MyModelName(my_field_name="Instance #1")

**Save the object into the database.**

record.save()

---

Searching for records
You can search for records that match certain criteria using the model's objects attribute (provided by the base class).
```
all_books = Book.objects.all()
```
--- 
Defining the LocalLibrary Models

The boilerplate at the top of the page imports the models module, which contains the model base class models.Model that our models will inherit from.

```
from django.db import models

# Create your models here.

```
---
Genre model
created the Genre as a model rather than as free text or a selection list so that the possible values can be managed through the database rather than being hard coded.

```
class Genre(models.Model):
    """Model representing a book genre."""
    name = models.CharField(max_length=200, help_text='Enter a book genre (e.g. Science Fiction)')

    def __str__(self):
        """String for representing the Model object."""
        return self.name

```

----
## Registering models 

```
from django.contrib import admin

# Register your models here.

```

Creating a superuser
Call the following command, in the same directory as manage.py, to create the superuser. You will be prompted to enter a username, email address, and strong password.
```
python3 manage.py createsuperuser

Now restart the development server so we can test the login:

python3 manage.py runserver
```
---
### Register a ModelAdmin class

```
# admin.site.register(Author)
Now add a new AuthorAdmin and registration as shown below.
# Define the admin class
class AuthorAdmin(admin.ModelAdmin):
    pass

# Register the admin class with the associated model
admin.site.register(Author, AuthorAdmin)
```

Configure list views
Replace your AuthorAdmin class with the code below. The field names to be displayed in the list are declared in a tuple in the required order.
```
class AuthorAdmin(admin.ModelAdmin):
    list_display = ('last_name', 'first_name', 'date_of_birth', 'date_of_death')

```