![alt text](https://raw.githubusercontent.com/Nekmo/cookiecutter-django-backend/master/images/logo.png)
This Project is a Django + Nginx + WSGI + Mysql + PMA Containers :bowtie:



#Start Djnago Project
    ```docker-compose run python django-admin.py startproject app```


#Connection to MySQL
"""
Django settings for app project.
Generated by 'django-admin startproject' using Django 2.0.4.
For more information on this file, see
https://docs.djangoproject.com/en/2.0/topics/settings/
For the full list of settings and their values, see
https://docs.djangoproject.com/en/2.0/ref/settings/
"""
```
import os
import pymysql
```

# connect mysql
```
pymysql.install_as_MySQLdb()

DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.mysql',
        'NAME': 'todoList',
        'USER': 'user',
        'PASSWORD': 'password',
        'HOST': 'db',
        'PORT': '3306',
    }
}
```

"""

Run the migrate and make superuser.
    ```
    docker-compose run python ./manage.py migrate
    docker-compose run python ./manage.py createsuperuser
    docker-compose manage.py collectstatic```


add below sentences at settings.py
    ```
    STATIC_URL = '/static/'
    STATICFILES_DIRS = [
    os.path.join(BASE_DIR, 'web/static'),
    ]
    STATIC_ROOT =  os.path.join(BASE_DIR, 'static')
    MEDIA_URL = '/media/'
    MEDIA_ROOT = os.path.join(BASE_DIR, 'media')
    ```

Run Command
    ```docker-compose run python ./manage.py collectstatic```

Up Containers
    ```docker-compose up -d```
