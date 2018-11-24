# Django Tutorial


A simple blogging website developed by using Django framework

In this project I will tell you how to get started with django from strach.

## Making your machine django ready

For this tutorial I will be using python 3, so if you are on python 2 will suggest you to first upgrade to python 3 form [here](https://www.python.org).

In order to get django in your machine no matter weather you are using windows, Mac OS or any LINUX distrubutions you just have to run only one coomand from your terminal/command prompt which is:

<code>pip install django</code>

and if you already have django installed then upgrade it to latest version:
<code>pip install --upgrade django</code>


## Let's get started with django

### 1. First we have to start a project

<code>django-admin startproject _______</code>

fill in the blanks with the name of your project, in my case its <strong>mysite</strong>.


It will create a container with the name of your project. Inside that there will be a bunch of files and a folder with the same name. The second folder with the same name contains follwing files:
  1. __init__.py (it will tell python to treat it as a pakage.)_mysite
  2. settings.py (it is central setting hub for website in which you install all your apps)
  3. urls.py (it is file which reroutes to your apps and htmls)
  4. wsgi.py (don't play with it)
  

For starting a brand new app :

inside the root directory (the container you have created after you start the project) open terminal/command prompt and then run it

<code>python manage.py startapp ______</code>

similarly fill in the blank with the app name in my case its <strong>Blog and Personal</strong>. 


After creating a project just run the server for ensuring the installation :

    python manage.py runserver

and the output will be like this: 

<img alt="" src="https://tutorial.djangogirls.org/en/django_start_project/images/install_worked.png">

<img alt="" src="https://1.bp.blogspot.com/-U0i4-G4-Ev8/WWeaGxBgvfI/AAAAAAAAFkE/892zkk2-8KM2hpcR2F3EkHPBiNngkPpQwCLcBGAs/s1600/Run-Django-server-for-permanent-on-Centos-and-Ubuntu.png">



### 2. Register your freshly created app 


After the creation your first app you have to register/installed it in the project so that django can recognise it and redirect the user to that app. in other words we have to define our apps.
To register/install an app you have to go to the directory as follows:


<code>Project_name/Project_name/settings.py</code>

in that file you will see a section called <strong>installed_apps</strong> :


  
  
    Application definition


    INSTALLED_APPS = [
    'blog',
    'personal',
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
      ]





### 3. Rerouting 

After defining/installation/registering the app we have to reroute the to the app.
As default if you start your server locally the site will be available on <strong>127.0.0.1:8000</strong>.
So when the user enters 127.0.0.1:8000/blog we have to route the user to the app.
To do that we have to edit the urls.py file in the same directory where we edited settings.py .
urls.py would be like [this](https://github.com/Deep-Mind-Hive/Django_mysite/blob/master/mysite/urls.py)
To reroute the user we have two ways:
  1. by using url module with include function or
  2. by using path module.
  
I have used both of the method for your understanding.
After you user to the app's urls.py you have to reroute user to the appropriate html file.

Main urls.py file:

    from django.contrib import admin
    from django.urls import path
    from django.conf.urls import include, url

    urlpatterns = [
        path('admin/', admin.site.urls),
        url(r'^', include('personal.urls')),
        url(r'^blog/', include('blog.urls')),   
    ]


App's urls.py (Personal App's urls.py)

    from django.conf.urls import url, include
    from . import views


    urlpatterns = [url(r'^$', views.index, name='index'),url(r'^contact/$', views.contact, name='contact')] 


    




### 4. Where to keep HTML, CSS and .js file

To store all the HTML, CSS, JavaScript and Images file have to be stored in two containers(folder):
  
  1. Template
  2. static



For HTML we use template and for Cascade Styling Sheet, JavaScript and Image we use statics container.

Note: Never use same name for any of the html,css or js file even if you have created different folders/containers for each app django stack them up and treat them as one container.
Solution:
  1. Never use same name
  2. use different folder for each app
  
like:

  <code>mysite/mysite/blog/template/blog/home.html</code>


  <code>mysite/mysite/static/blog/css/home.css</code>


  <code>mysite/mysite/static/blog/js/home.js</code>


  <code>mysite/mysite/static/blog/img/logo.jpg</code>
 



