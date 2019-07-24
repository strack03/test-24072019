Hello World for Flask with heroku
======================

In this tutorial, we'll create a web app and deploy it to Heroku, using
`Flask <https://pypi.org/project/Flask/>`_.



Dependencies: 
-------------

1. Flask supports Python-2.7 and 2.7.16 is the latest version. Create runtime.txt::

    python-2.7.16

2. Declare the requirements of your app in requirements.txt::

    Flask==0.9
    Jinja2==2.6
    Werkzeug==0.8.3
    gunicorn==0.17.2

3. Create your python app ``hello.py``::

    from flask import Flask

    app = Flask(__name__)

    @app.route('/')
    def hello():
       return 'Hello World!'

4. Procfile::
    web: gunicorn hello:app

Deploy:
------------

Navigate to your project folder. Add your files to git:: 
    $ git init
    $ git add .
    $ git commit -m "Deploying app."

Push the app to remote ::

    $ heroku git:remote -a <your heroku app>
    $ git push heroku master
