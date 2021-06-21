========
gleandoc
========


.. image:: https://img.shields.io/pypi/v/gleandoc.svg
        :target: https://pypi.python.org/pypi/gleandoc

.. image:: https://img.shields.io/travis/datagazing/gleandoc.svg
        :target: https://travis-ci.com/datagazing/gleandoc

.. image:: https://readthedocs.org/projects/gleandoc/badge/?version=latest
        :target: https://gleandoc.readthedocs.io/en/latest/?version=latest
        :alt: Documentation Status



Simple convenience functions to extract docstring and write README

* Intent: store one copy of top-level docstring in <package>/__init__.py
* Allows generation of top level gitub README based on the package docstring

Examples
--------

Print the first line of a docstring:

.. code-block:: python

  >>> import gleandoc
  >>> docstring = gleandoc.docstring('re')
  >>> docstring.splitlines()[0]
  'Support for regular expressions (RE).'
  >>>

Do the same thing from the command line:

.. code-block:: console

  $ gleandoc re | head -1
  Support for regular expressions (RE).
  $

Interpolate template README.rst.fstr and write results to README.rst,
replacing {__doc__} with extracted docstring based on the name of the
current directory:

.. code-block:: console

  $ gleandoc README.rst.fstr README.rst
  gleandoc: WARNING: replacing README.rst
  gleandoc: INFO: wrote README.rst
  $

Features
--------

* Determine package name from current directory
* Extract docstring using Python semantics and standards
* No dependencies

Limitations
-----------

* Embedded backslash-n newlines are treated as actual newlines
* Relies on various pseudo-internals: locals(), exec()



Credits
-------

This package was created with Cookiecutter_ and the `audreyr/cookiecutter-pypackage`_ project template.

.. _Cookiecutter: https://github.com/audreyr/cookiecutter
.. _`audreyr/cookiecutter-pypackage`: https://github.com/audreyr/cookiecutter-pypackage
