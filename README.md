# [Django Dashboard StarAdmin PRO](https://appseed.us/admin-dashboards/django-dashboard-staradmin-pro)

**Commercial** Admin Dashboard coded in [Django Framework](https://www.djangoproject.com/) on top of **[StarAdmin Dashboard](https://django-dashboard-staradmin-pro.appseed.us/login/)** design (PRO Version) designed by **BootstrapDash** Agency - product generated by AppSeed.

<br />

## Dashboard Features

- UI-Ready app, SQLite Database, Django Native ORM
- Modular design, clean code-base
- Session-Based Authentication, Forms validation
- Deployment scripts: Heroku, Docker, Gunicorn / Nginx
- UI Kit: **StarAdmin Dashboard** (PRO version) provided by **BootstrapDash**
- License: [Commercial](https://github.com/app-generator/django-dashboard-staradmin-pro/blob/master/LICENSE.md)
- LIVE 24/7 Support via [Discord](https://discord.gg/fZC6hup) and email **< support @ appseed.us >**

<br />

## Dashboard Links

- [Django Dashboard StarAdmin PRO](https://appseed.us/admin-dashboards/django-dashboard-staradmin-pro) - Product page
- [Django Dashboard StarAdmin PRO](https://django-dashboard-staradmin-pro.appseed.us/) - LIVE demo

<br />

![Django Dashboard StarAdmin PRO - Admin Panel coded in Django.](https://raw.githubusercontent.com/app-generator/static/master/django-dashboard-staradmin-pro/django-dashboard-staradmin-pro-intro.gif)

<br />

## Get the source code

- Access the [product page](https://appseed.us/admin-dashboards/django-dashboard-staradmin-pro) and purchase a **license**
- Connect with the support team via [Discord](https://discord.gg/fZC6hup) and email **< support @ appseed.us >**
- Accept the invitation to the private repository (sent by the [AppSeed](http://appseed.us/) platform, once the purchase is validated)
- Clone the source code and build the [Django Dashboard StarAdmin PRO](https://appseed.us/admin-dashboards/django-dashboard-staradmin-pro) using the instructions presented in this documentation.

<br />

## Prepare your environment

The product is built on top of [Django](https://www.djangoproject.com/), a popular Python Web Framework. To build the app, Python3 should be installed properly in the workstation. If you are not sure if Python is properly installed, please open a terminal and type `python --version`. The full-list with dependencies and tools required to build the app:

- [Python3](https://www.python.org/) - the programming language used to code the app
- [Git](https://git-scm.com/) - used to clone the source code from the Github repository
- A [Github](https://github.com/) account - the invitation to the source code, will be sent on your account.
- Basic development tools (g++ compiler, python development libraries ..etc) used by Python to compile the app dependencies in your environment.

<br />

> Check Python (using the terminal)

```bash
$ # Check Python version
$ python --version
Python 3.7 # <--- All good
```

<br />

> Check GIT command tool (using the terminal)

```bash
$ # Check git
$ git --version
$ git version 2.10 # <--- All good
```

<br />

For more information on how to set up your environment please access the resources listed below. In case we've missed something, contact us on Discord.

- [How to set up Python](https://docs.appseed.us/how-to/install-python)
- [Setup CentOS for development](https://docs.appseed.us/how-to/setup-centos-for-development/)
- [Setup Ubuntu for development](https://docs.appseed.us/how-to/setup-ubuntu-for-development/)
- [Setup Windows for development](https://docs.appseed.us/how-to/setup-windows-for-development/)

<br />

## Project Structure

The boilerplate code is built with a modular structure that follows the recommended pattern used by many open-source projects. The most important files and  directories are shown below:

<br />

```bash
< PROJECT ROOT >                               # application root folder
    |
    |--- core/__init__.py                      # Handles the core features
    |--- core/                                 # define app settings and serve statis assets and pages
    |      | --- <templates>
    |      |        |---<includes>             # Page chunks, components
    |      |        |---<layouts>              # App Layouts (the master pages)
    |      |        |---<account>              # Auth Pages (login, register)
    |      |        |---<pages>                # App Pages
    |      |
    |      | --- views.py
    |      | --- urls.py
    |      | --- models.py
    |
    |--- app/__init__.py                       # Django app that serve the pages
    |--- app/                                  # for authenticated users
    |      | --- views.py
    |      | --- urls.py
    |      | --- models.py
    |
    |--- authentication/__init__.py            # Django app that serve the pages
    |--- authentication/                       # for authenticated users
    |      | --- forms.py                      # Login, Register forms
    |      | --- views.py
    |      | --- urls.py
    |      | --- models.py
    |
    |--- requirements.txt                      # Requirements - SQLite storage
    |
    |--- manage.py                             # bootstrap the app
    |
    |-----------------------------
```

<br />

## Build from sources

> Note: this is a private repository. To get access, you should buy a license from the [product page](https://appseed.us/admin-dashboards/django-dashboard-staradmin-pro). 

<br />

```bash
$ # Get the code
$ git clone https://github.com/app-generator/priv-django-dashboard-staradmin-pro.git
$ cd priv-django-dashboard-staradmin-pro
$
$ # Virtualenv modules installation (Unix based systems)
$ virtualenv env
$ source env/bin/activate
$
$ # Virtualenv modules installation (Windows based systems)
$ # virtualenv env
$ # .\env\Scripts\activate
$
$ # Install modules - SQLite Database
$ pip3 install -r requirements.txt
$
$ # Create tables
$ python manage.py makemigrations
$ python manage.py migrate
$
$ # Start the application (development mode)
$ python manage.py runserver # default port 8000
$
$ # Start the app - custom port 
$ # python manage.py runserver 0.0.0.0:<your_port>
$
$ # Access the web app in browser: http://127.0.0.1:8000/
```

<br />

## Deployment

The app is provided with a basic configuration to be executed in [Docker](https://www.docker.com/), [Gunicorn](https://gunicorn.org/), and [Waitress](https://docs.pylonsproject.org/projects/waitress/en/stable/).

### [Docker](https://www.docker.com/) execution
---

The application can be easily executed in a docker container. The steps:

> Get the code

```bash
$ git clone https://github.com/app-generator/priv-django-dashboard-staradmin-pro.git
$ cd priv-django-dashboard-staradmin-pro
```

> Start the app in Docker

```bash
$ sudo docker-compose pull && sudo docker-compose build && sudo docker-compose up -d
```

Visit `http://localhost:5005` in your browser. The app should be up & running. 

<br />

### [Gunicorn](https://gunicorn.org/)
---

Gunicorn 'Green Unicorn' is a Python WSGI HTTP Server for UNIX.

> Install using pip

```bash
$ pip install gunicorn
```
> Start the app using gunicorn binary

```bash
$ gunicorn --bind=0.0.0.0:8001 core.wsgi:application
Serving on http://localhost:8001
```

Visit `http://localhost:8001` in your browser. The app should be up & running.


<br />

### [Waitress](https://docs.pylonsproject.org/projects/waitress/en/stable/)
---

Waitress (Gunicorn equivalent for Windows) is meant to be a production-quality pure-Python WSGI server with very acceptable performance. It has no dependencies except ones that live in the Python standard library.

> Install using pip

```bash
$ pip install waitress
```
> Start the app using [waitress-serve](https://docs.pylonsproject.org/projects/waitress/en/stable/runner.html)

```bash
$ waitress-serve --port=8001 core.wsgi:application
Serving on http://localhost:8001
```

Visit `http://localhost:8001` in your browser. The app should be up & running.

<br />

## Django StarAdmin PRO - app screens

<br />

![Django Dashboard StarAdmin PRO - Main Screen.](https://raw.githubusercontent.com/app-generator/static/master/django-dashboard-staradmin-pro/django-dashboard-staradmin-pro-screen-1.png)

<br />

![Django Dashboard StarAdmin PRO - Charts Screen.](https://raw.githubusercontent.com/app-generator/static/master/django-dashboard-staradmin-pro/django-dashboard-staradmin-pro-screen-3.png)

<br />

![Django Dashboard StarAdmin PRO - Widgets Screen.](https://raw.githubusercontent.com/app-generator/static/master/django-dashboard-staradmin-pro/django-dashboard-staradmin-pro-screen-4.png)

<br />

## Credits & Links

<br />

### [Django Admin Dashboards PRO](https://appseed.us/admin-dashboards/django)

Index with **Premium UI-ready admin dashboards** generated by the AppSeed platform in [Django Framework](https://www.djangoproject.com/).
Start fast your next Django project by using functional admin dashboards enhanced with Database, ORM, authentication flow, helpers and deployment scripts.

<br />

### What is [Django](https://www.palletsprojects.com/p/flask/)

[Django](https://www.palletsprojects.com/p/flask/) is a lightweight WSGI web application framework. It is designed to make getting started quick and easy, with the ability to scale up to complex applications. It began as a simple wrapper around Werkzeug and Jinja and has become one of the most popular Python web application frameworks.

<br />

### [What is a dashboard](https://en.wikipedia.org/wiki/Dashboard_(business))

A dashboard is a set of pages that are easy to read and offer information to the user in real-time regarding his business. A dashboard usually consists of graphical representations of the current status and trends within an organization. Having a well-designed dashboard will give you the possibility to act and make informed decisions based on the data that your business provides - *definition provided by [Creative-Tim - Free Dashboard Templates](https://www.creative-tim.com/blog/web-design/free-dashboard-templates/?ref=appseed)*.

<br />

### [StarAdmin Dashboard PRO](https://www.bootstrapdash.com/product/star-admin-pro/)

Designed based on the Bootstrap framework, Star Admin Pro is a powerful, feature-rich, and super flexible admin dashboard template. It serves as the perfect starting point for both simple and complex web development projects. It features a well-designed dashboard with several neatly arranged components and essential elements.

<br />

---
[Django Dashboard StarAdmin PRO](https://appseed.us/admin-dashboards/django-dashboard-staradmin-pro) - Provided by **AppSeed** [Web App Generator](https://appseed.us/app-generator).
