### Creating a project
From the command line, `cd` into a directory where you’d like to store your code, then run the following command:
```
django-admin startproject
```
This will create a `mysite` directory in your current directory.
### Creating the Polls app
To create your app, make sure you’re in the same directory as `manage.py` and type this command:
```
python manage.py startapp polls
```
### Write your first view
Open the file `polls/views.py` and put the following Python code in it:
```
[...]
from django.http import HttpResponse


def index(request):
    return HttpResponse("Hello, world. You're at the polls index.")
```
Create a URLconf in the polls directory, create a file called `urls.py`
In the `polls/urls.py` file include the following code:
```
from django.contrib import admin
from django.urls import include, path

urlpatterns = [
    path('polls/', include('polls.urls')),
    path('admin/', admin.site.urls),
]
```
**Verify it’s working with the following command:**
```
python manage.py runserver
```
Go to `http://localhost:8000/polls/` in your browser, and you should see the text:
> “Hello, world. You’re at the polls index.”
