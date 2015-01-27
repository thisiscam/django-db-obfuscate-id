django-db_obfuscate-id
============

A reusable Django app that psuedo encrypts your id from a database level.

Installation
------------

To get the latest stable release from PyPi

.. code-block:: bash

    pip install db-obcuscate-id

To get the latest commit from GitHub

.. code-block:: bash

    pip install -e git+git://github.com/thisiscam/django-db_obfuscate-id.git#egg=db_obfuscate

TODO: Describe further installation steps (edit / remove the examples below):

Add ``db_obfuscate`` to your ``INSTALLED_APPS``

.. code-block:: python

    INSTALLED_APPS = (
        ...,
        'db_obfuscate',
    )

Add full paths to your models to your ``settings.py``

.. code-block:: python

    ENCRYPT_ID_FOR_MODELS = patterns('',
        'django.contrib.auth.models.User',
        ...
    )

Alternatively, you can set a class attribute flag as follow:
.. code-block:: python

    class MyEncrypedIdModel(models.Model):
        pseudo_encrypt_id = True

Usage
-----

After setting up, you can conveniently call the management command

.. code-block:: bash
    python manage.py db --encrypt-all #this will encrypt all your models specified in settings.py and flagged true for pseudo_encrypt_id

    python manage.py db --encrypt-model myapp.models.SomeModelA myapp.models.SomeModelB #this will encrypt all the models specified in this command, use this if you want a one time setting


Contribute
----------

If you want to contribute to this project, please perform the following steps

.. code-block:: bash

    # Fork this repository
    # Clone your fork
    mkvirtualenv -p python2.7 db-obcuscate-id
    make develop

    git co -b feature_branch master
    # Implement your feature and tests
    git add . && git commit
    git push -u origin feature_branch
    # Send us a pull request for your feature branch

In order to run the tests, simply execute ``tox``. This will install two new
environments (for Django 1.6 and Django 1.7) and run the tests against both
environments.
