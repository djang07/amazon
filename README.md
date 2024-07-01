To create app 
      ->python manage.py startapp appname

config the app in settings.py in installed apps

INSTALLED_APPS = [

    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    
    'home',                  #appname
]

create a view for displaying a msg

syntax->

      def viewname(request):
        print("hello world")
 function or view call is done using rooting name in urls.py        


 from django.contrib import admin
from django.urls import path
from home import views
urlpatterns = [

    path('admin/', admin.site.urls),
    path('home',views.display),  # home :- routingname and views.display :-is the function call 
]

{
In browser
<--
ValueError at /home

The view home.views.hello didn't return an HttpResponse object. It returned None instead.

Request Method: 	GET
Request URL: 	http://127.0.0.1:8000/home
Django Version: 	5.0.6
Exception Type: 	ValueError
Exception Value: 	

The view home.views.hello didn't return an HttpResponse object. It returned None instead.

Exception Location: 	C:\Users\jay\AppData\Local\Programs\Python\Python312\Lib\site-packages\django\core\handlers\base.py, line 332, in check_response
Raised during: 	home.views.hello
Python Executable: 	C:\Users\jay\AppData\Local\Programs\Python\Python312\python.exe
Python Version: 	3.12.4
Python Path: 	

['C:\\Users\\jay\\Desktop\\dj\\amazon',
 'C:\\Users\\jay\\AppData\\Local\\Programs\\Python\\Python312\\python312.zip',
 'C:\\Users\\jay\\AppData\\Local\\Programs\\Python\\Python312\\DLLs',
 'C:\\Users\\jay\\AppData\\Local\\Programs\\Python\\Python312\\Lib',
 'C:\\Users\\jay\\AppData\\Local\\Programs\\Python\\Python312',
 'C:\\Users\\jay\\AppData\\Local\\Programs\\Python\\Python312\\Lib\\site-packages']

Server time: 	Mon, 01 Jul 2024 06:50:29 +0000


}
-->

IN CMD

  **hello world**
  
Internal Server Error: /home

Traceback (most recent call last):

  File "C:\Users\jay\AppData\Local\Programs\Python\Python312\Lib\site-packages\django\core\handlers\exception.py", line 55, in inner
  
    response = get_response(request)
               ^^^^^^^^^^^^^^^^^^^^^
               
  File "C:\Users\jay\AppData\Local\Programs\Python\Python312\Lib\site-packages\django\core\handlers\base.py", line 204, in _get_response
    self.check_response(response, callback)
  File "C:\Users\jay\AppData\Local\Programs\Python\Python312\Lib\site-packages\django\core\handlers\base.py", line 332, in check_response
    raise ValueError(
ValueError: The view home.views.hello didn't return an HttpResponse object. It returned None instead.
[01/Jul/2024 12:20:29] "GET /1 HTTP/1.home" 500 64767
Not Found: /favicon.ico
[01/Jul/2024 12:20:30,109] - Broken pipe from ('127.0.0.1', 52916)

