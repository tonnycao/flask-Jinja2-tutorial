# Python/Flask Jinja2 Tutorial

* This sample contains the completed program from the tutorial.

* It also contains the *Dockerfile* and *uwsgi.ini* files necessary to build a container with a production server.

* To run the app locally:
  1. Run the command `cd hello_app`, to change into the folder that contains the Flask app.
  1. Run the command `set FLASK_APP=webapp` (Windows cmd) or `FLASK_APP=webapp` (macOS/Linux) to point to the app module.
  1. Start the Flask server with `flask run`.

## The startup.py file

In the root folder, the `startup.py` file is specifically for deploying to Azure App Service on Linux without using a containerized version of the app (that is, deploying the code directly, not as a container).

Because the app code is in its own *module* in the `hello_app` folder (which has an `__init__.py`), trying to start the Gunicorn server within App Service on Linux produces an "Attempted relative import in non-package" error.

The `startup.py` file, therefore, is a shim to import the app object from the `hello_app` module, which then allows you to use startup:app in the Gunicorn command line (see `startup.txt`).

## comments pages and mange comments in dashboard

1. comment form: email, title, content.
2. comments dashboard: pagination, edit, delete.