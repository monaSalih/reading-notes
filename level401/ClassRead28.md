# Django CRUD and Forms

>  Django is based on MVT (Model View Template) architecture and revolves around CRUD (Create, Retrieve, Update, Delete) operations. 

>CRUD can be best explained as an approach to building a Django web application.
![](https://media.geeksforgeeks.org/wp-content/uploads/20200114185631/Untitled-Diagram-316-1024x630.jpg)

Create – create or add new entries in a table in the database. 

Retrieve – read, retrieve, search, or view existing entries as a list or retrieve a particular entry in detail.

Update – update or edit existing entries in a table in the database 

Delete – delete, deactivate, or remove existing entries in a table in the database

### step:
* as usual start with creat Django project
* create view ,Create View refers to a view (logic) to create an instance of a table in the database.
```
from django.shortcuts import render
 
# relative import of forms
from .models import GeeksModel
from .forms import GeeksForm
 
 
def create_view(request):
    # dictionary for initial data with
    # field names as keys
    context ={}
 
    # add the dictionary during initialization
    form = GeeksForm(request.POST or None)
    if form.is_valid():
        form.save()
         
    context['form']= form
    return render(request, "create_view.html", context)
```
* Retrieve View ,retrieve view is basically divided into two types of views Detail View and List View. 
```
from django.shortcuts import render
 
# relative import of forms
from .models import GeeksModel
 
 
def list_view(request):
    # dictionary for initial data with
    # field names as keys
    context ={}
 
    # add the dictionary during initialization
    context["dataset"] = GeeksModel.objects.all()
         
    return render(request, "list_view.html", context)
```

* Update View,update View refers to a view (logic) to update a particular instance of a table from the database with some extra details. 
```
from django.shortcuts import (get_object_or_404,
                              render,
                              HttpResponseRedirect)
 
# relative import of forms
from .models import GeeksModel
from .forms import GeeksForm
 
# after updating it will redirect to detail_View
def detail_view(request, id):
    # dictionary for initial data with
    # field names as keys
    context ={}
  
    # add the dictionary during initialization
    context["data"] = GeeksModel.objects.get(id = id)
          
    return render(request, "detail_view.html", context)
 
# update view for details
def update_view(request, id):
    # dictionary for initial data with
    # field names as keys
    context ={}
 
    # fetch the object related to passed id
    obj = get_object_or_404(GeeksModel, id = id)
 
    # pass the object as instance in form
    form = GeeksForm(request.POST or None, instance = obj)
 
    # save the data from the form and
    # redirect to detail_view
    if form.is_valid():
        form.save()
        return HttpResponseRedirect("/"+id)
 
    # add form dictionary to context
    context["form"] = form
 
    return render(request, "update_view.html", context)
```

* Delete View,delete View refers to a view (logic) to delete a particular instance of a table from the database. 
```
from django.shortcuts import (get_object_or_404,
                              render,
                              HttpResponseRedirect)
 
from .models import GeeksModel
 
 
# delete view for details
def delete_view(request, id):
    # dictionary for initial data with
    # field names as keys
    context ={}
 
    # fetch the object related to passed id
    obj = get_object_or_404(GeeksModel, id = id)
 
 
    if request.method =="POST":
        # delete object
        obj.delete()
        # after deleting redirect to
        # home page
        return HttpResponseRedirect("/")
 
    return render(request, "delete_view.html", context)
```