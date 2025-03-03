################
django-starter
################

***********
Description
***********
This repository provides a template designed to serve as a base for new Django projects. It includes:

- Custom Template Components
- Custom Template Tags
- Custom Template Filters
- Pycharm Professional Run Configurations

  - ``runserver`` from ``manage.py``
  - ``runserver_plus`` from `django-extensions`_

.. _django-extensions: https://django-extensions.readthedocs.io/en/latest/


************
Installation
************
With git
========
.. code-block:: bash

  git clone https://github.com/nullandvoid-digital/django-starter.git

With GitHub CLI
===============
.. code-block:: bash

  gh repo clone nullandvoid-digital/django-starter


*****************
Included Packages
*****************

- Base Dependencies

  - Python 3.12
  - Django 5
  - `Whitenoise`_
  - pip

- Dev Dependencies

  - ipython
  - `black`_
  - setuptools
  - `django-extensions`_
  - `django-debug-toolbar`_
  - werkzeug
  - pygraphviz

.. _Whitenoise: https://whitenoise.readthedocs.io/en/latest/
.. _black: https://black.readthedocs.io/en/stable/
.. _django-debug-toolbar: https://django-debug-toolbar.readthedocs.io/en/latest/

*******************
Template Components
*******************
alpine-counter
==============
A button counts clicks and displays the number in itself [#f1]_

Pass keyword arguments ``classes``, ``name``,
and ``id`` to customize the respective attributes

.. code-block:: html+django

  <div>
  {% include "components/alpine-counter.html" with classes="button is-success" name="Correct" id="num-correct" %}
  </div>


.. [#f1] Requires `alpinejs`_ for the counting functionality

.. _alpinejs: https://alpinejs.dev


*************
Template Tags
*************
Operators
=========
Multiply
--------
.. code-block:: html+django

  <p>The number is {{ number }} and double that is {{ number|multiply: 2 }}</p>


Time
====
Seconds => Minutes
------------------
.. code-block:: html+django

  <p>You have {{ quiz.time|minutes }} minutes to complete the quiz</p>

**********
Decorators
**********
htmx_required
=============
Returns HTML Status Code 403 Forbidden if the request does not have htmx. [#f2]_

.. code-block:: python

  @htmx_required
  def view(request):
      return render(request, "template.html")

.. [#f2] Requires `htmx`_ JavaScript package and `django-htmx`_ Python package

.. _htmx: https://htmx.org

.. _django-htmx: https://django-htmx.readthedocs.io/en/latest/