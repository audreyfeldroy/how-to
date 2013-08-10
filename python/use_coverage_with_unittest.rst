====================================
How To Use Coverage.py With Unittest
====================================

This is adapted from:
* http://nedbatchelder.com/code/coverage/

Install It
----------

First, install Coverage.py:

.. code-block:: bash

    pip install coverage

Gather Data
-----------

Run your test suite, but replace `python blah blah` with `coverage blah blah`
and specify a source directory.

For example:

.. code-block:: bash

    coverage run --source cookiecutter setup.py test

Ideally your tests should be outside of your source directory, so that you
don't have to configure excludes or package them. It's much neater that way.

Print Coverage Reports
----------------------

Command-Line Report
~~~~~~~~~~~~~~~~~~~

To print a quick command line report, maximize your command prompt and type:

.. code-block:: bash

    coverage report -m

HTML Report
~~~~~~~~~~~

To print a fancier HTML report:

.. code-block:: bash

    coverage html
    open html_cov/index.html

Set Up Coveralls
----------------

Sign up for Coveralls.io with your GitHub account. Click [Add Repo] and add
the repo for which you want a badge.

Here you'll use `coveralls-python`_.

Add this to `.travis.yml` in the corresponding spots:

.. code-block:: yaml

    install:
     - pip install coveralls

    # change from 'script: python setup.py test' to this
    script: coverage run --source cookiecutter setup.py test

    after_success:
        coveralls

Then when you push, after Travis finishes building, check your Coveralls
account for the results.

.. _`coveralls-python`: https://github.com/coagulant/coveralls-python
