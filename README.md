## first of all i should create venv then activate it -> 
* install django ->
* open vs ->
* make sure that the venv is activate in your vs 
* create a project by django-admin startproject 'the name of mu project'

## create a templates folder and put inside it all your HTML fils (use the enjen )
* about.html : to render about page put whatever you want but dont forget to extend base.html using {% %} && to open and close the block content
* home.html : to render home page 
* base.html : to use the enjen 

## to create an application i should run this code :
* python manage.py startapp 'the name of app' -->

go to views file that inside the app that youe created to do the logic ,
to tell the django if you 'django' if you get req on this rout send a response for the template to allows the client to render it by :

* from django.views.generic import TemplateView

* class HomePageView(TemplateView):
    template_name = 'home.html'

* class AboutPageView(TemplateView):
    template_name = 'about.html'

# then go to the application folder that you created and create a new file name urls.py
inside it :

* from .views import HomePageView,AboutPageView

* *urlpatterns = [
    path('',HomePageView.as_view(),name = 'home'),
    path('about',AboutPageView.as_view(),name = 'about')
]

HomePageView.as_view : its mean if you got a req on this path connect it with this view 

## then go to the globle urls that inside the project 
* from django.urls import path ,include

* path('',include('snacks.urls'))

## then go to the setting 

* inside the TEMPLATES 
'DIRS': [BASE_DIR/ 'templates'],

* inside the INSTALLED_APPS 
put the name of your app