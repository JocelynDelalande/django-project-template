Django project template
=======================

Boilerplate template to start a Django project, replacing the default one
(which is IMHO confusing).

It's using the template feature of
[the startproject command](https://docs.djangoproject.com/en/1.9/ref/django-admin/#startproject).

Getting started
---------------

1. Create the project named as you like :

        django-admin startproject <project_name>\
          --template=https://github.com/JocelynDelalande/django-project-template/archive/master.zip\
          --extension=py,md,.gitignore

2. Trash or edit this README.md if you want :)

Highlights
----------


- minimalist, just a file layout
- Django applicationrs are in a clean *apps/*
- prod/dev settings, and local overriding feature (creating a *settings/local.py*)
- clear separation of runtime media files in var/
- put all cross-app resources in core/ (site-wide templates, assets, shared code...)
- separated dev/prod requirements
- sensible *.gitignore*

Layout
------

        project_name/
        ├── .gitignore
        ├── manage.py
        ├── project_name
        │   ├── apps
        │   │   └── __init__.py
        │   ├── core
        │   │   ├── __init__.py
        │   │   ├── templates
        │   │   └── urls.py
        │   ├── __init__.py
        │   ├── settings
        │   │   ├── base.py
        │   │   ├── dev.py
        │   │   ├── __init__.py
        │   │   └── prod.py
        │   ├── wsgi.py
        ├── README.md
        ├── requirements
        │   ├── base.txt
        │   └── dev.txt
        └── var
            ├── media
            └── static


Creating a new app
------------------

Sadly, a bit more complicated than with vanilla template :

    mkdir {{ project_name }}/apps/<app_name>
    ./manage.py startapp app_name> {{ project_name }}/apps/<app_name>

And add `{{ project_name }}.apps.<app_name>` to your `INSTALLED_APPS`.

Credit
------

That's personal taste template, inspired by
[django-project-skeleton](https://github.com/Mischback/django-project-skeleton)
and [ychab](https://github.com/ychab) practices.
