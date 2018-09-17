Pylatest Demo Project
=====================

This is an example of Sphinx_/Pylatest_ project.

The html builds are available at https://marbu.gitlab.io/pylatest-demo

About Pylatest
--------------

Pylatest is of set of Docutils_/Sphinx_ extensions which allows you to:

* Write a description of a test case using `reStructuredText syntax`_.
* Maintain test case descriptions as Sphinx_ project.

See `Pylatest`_ documentation for details.

About Test Cases
----------------

This demo project uses real `Fedora Test Cases`_ to better demonstrate how
Pylatest_ works.

The test cases are not reused exactly as created by `Fedora Quality
Assurance`_ community, but few necessary changes were made, including
changes of markup (transformation into `reStructuredText syntax`_) and tweaking
of test case structure and metadata (eg. referenced requirements).

How to build html
-----------------

First of all, `make sure you have pylatest installed`_.

Then, in the root directory of this repository, just run::

    $ make html

License
-------

Pylatest Demo Project is distributed under a `Creative Commons
Attribution-ShareAlike 3.0 Unported License`_ (CC BY-SA 3.0).


.. _Docutils: http://docutils.sourceforge.net/
.. _Sphinx: http://www.sphinx-doc.org/en/stable/index.html
.. _Pylatest: https://pylatest.readthedocs.io/en/stable/
.. _`reStructuredText syntax`: http://www.sphinx-doc.org/en/stable/usage/restructuredtext/basics.html
.. _`Creative Commons Attribution-ShareAlike 3.0 Unported License`: https://creativecommons.org/licenses/by-sa/3.0/
.. _`Fedora Test Cases`: https://fedoraproject.org/wiki/Category:Test_Cases
.. _`Fedora Quality Assurance`: https://fedoraproject.org/wiki/QA
.. _`make sure you have pylatest installed`: https://pylatest.readthedocs.io/en/stable/quickstart.html#installation
