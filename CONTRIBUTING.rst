Contributing to django-taggit
=============================

.. image:: https://jazzband.co/static/img/jazzband.svg
   :target: https://jazzband.co/
   :alt: Jazzband

This is a `Jazzband <https://jazzband.co>`_ project. By contributing you agree
to abide by the `Contributor Code of Conduct
<https://jazzband.co/about/conduct>`_ and follow the `guidelines
<https://jazzband.co/about/guidelines>`_.

Thank you for taking the time to contribute to django-taggit.

Follow these guidelines to speed up the process.

Reach out before you start
--------------------------

Before opening a new issue, look if somebody else has already started working
on the same issue in the `GitHub issues
<https://github.com/jazzband/django-taggit/issues>`_ and `pull requests
<https://github.com/jazzband/django-taggit/pulls>`_.

Fork the repository
-------------------

Once you have forked this repository to your own GitHub account, install your
own fork in your development environment:

.. code-block:: console

    git clone git@github.com:<your_fork>/django-taggit.git
    cd django-taggit
    python setup.py develop

Running tests
-------------

django-taggit uses `tox <https://tox.readthedocs.io/>`_ to run tests:

.. code-block:: console

    tox

Running the sample application
------------------------------

There is a sample application in ``sample_taggit``. You can run it by doing the following:


**Prepare the Database**
~~~~~~~~~~~~~~~~~~~~~~~~

Use the `reset-db` command to prepare your database. This will remove any existing data, run migrations, and load fixtures, including creating a default admin user.

**On Windows:**

.. code-block:: console

     cd sample_taggit
     call make.bat reset-db

**On Mac/Linux:**

.. code-block:: console

     cd sample_taggit
     make reset-db

**Launch the Sample Project**
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Launch the sample project itself with:

.. code-block:: console

     sample_taggit/manage.py runserver

**Default Admin User Login:**

Username: taggit

Password: admin

Follow style conventions (black, flake8, isort)
-----------------------------------------------

Check that your changes are not breaking the style conventions with:

.. code-block:: console

    tox -e black,flake8,isort

Update the documentation
------------------------

If you introduce new features or change existing documented behavior, please
remember to update the documentation.

The documentation is located in the ``docs`` directory of the repository.

To do work on the docs, proceed with the following steps:

.. code-block:: console

    pip install sphinx
    sphinx-build -n -W docs docs/_build

Add a changelog line
--------------------

Even when the change is minor, a changelog line is helpful to both describe
the intent of the change, and to give a heads up to people upgrading. You can
add a line in the ``(Unreleased)`` section of ``CHANGELOG.rst``, along with
any more detailed explanations for more complicated changes.

Send pull request
-----------------

It is now time to push your changes to GitHub and open a `pull request
<https://github.com/jazzband/django-taggit/pulls>`_!


Release Checklist
-----------------

These steps need to happen by a release maintainer.

To make a release, the following needs to happen:

- Make sure that ``setup.cfg`` is set up properly w/r/t Python and Django requirements
- Make sure the documentation (``docs/index.rst``) also describes the right Python/Django versions
- Bump the version number in ``taggit/__init__.py``
- Update the changelog (making sure to add the (Unreleased) section to the top)
- Get those changes onto the ``master`` branch
- Tag the commit with the version number
- CI should then upload a release to be verified through Jazzband
