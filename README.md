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

First we have to start a project

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

