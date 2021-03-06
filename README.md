# Codedadies_list

## Flow of project :
1. First create a venv by ,
   ```
   python -m venv <name_of_folder>
   ```  
   and activate by ,
   ``` 
   .\<name_of_folder>\Scripts\activate
   ```
   
2. Install django , create project and also create app by following commands
   ```
   py -m pip install Django
   ``` 
   ```
   django-admin startproject codedadies_list
   ```
   ```
   django-admin startapp myapp
   ```
3. Check django interpreter detect your virtual venv 

4. Create folder templates and also create base.html file in 
    ```
   codedadies_list
       |__ myapp   
       |__ temlates
          |__ base.html   
   ```   
5. Add 'myapp' in installed_apps array
6. Add this line after BASE_DIR line because you want your django to know , where your templates are stored
   ```
   TEMPLATE_DIR = os.path.join(BASE_DIR, 'templates')
   ```
   
7. Add this line after STATIC_URLS line 
   ```
   STATICFILES_DIRS = (os.path.join(BASE_DIR, 'static'),)
   ```
9. you should also add TEMPLATE_DIR in TEMPLATES array in settings.py otherwise it will not able to detect your file in templates
    ```
    'DIRS': [TEMPLATE_DIR,],
    ```
8. Create a home function in Views.py in myapp

9. Create urls.py file to show the pages and use to navigate and add urlpatterns of views.home 
10. now migrate to make changes in database 
     ```
    py manage.py makemigrations
    py manage.py migrate
     ```
11. Now its time for you to create a superuser 
    ```
    py manage.py createsuperuser
    ```
12. use this in admin.py 
     ```
    admin.site.register(Search)
    ```
11. It`s time to build a model of Search function and also make sure to migrate after every change in models 
12. adding search functionality with the help of beautiful soup    
13. install heroku-cli from it`s web
    ```
    https://devcenter.heroku.com/articles/heroku-cli#download-and-install
    ``` 
15. remember to add this in your **Procfile**
    ```
    web: gunicorn <your-project-name>.wsgi:application --log-file - --log-level debug
    python manage.py collectstatic --noinput
    manage.py migrate
    ```

14. now follow these steps to deploy to heroku 
    ```
    https://medium.com/@dev117uday/deploying-django-app-on-heroku-in-few-minutes-e977bf7bf187
    ```
 