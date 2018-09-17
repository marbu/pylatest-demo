.. pylatest-demo documentation master file, created by
   sphinx-quickstart on Sun Jun 10 20:39:20 2018.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

Pylatest Demo Project
=====================

This is an example of Sphinx_/Pylatest_ project.


Test Cases
----------

This demo project uses real `Fedora Test Cases`_ to better demonstrate how
Pylatest_ works.

The test cases are not reused exactly as created by `Fedora Quality
Assurance`_ community, but few necessary changes were made, including
changes of markup (transformation into `reStructuredText syntax`_) and tweaking
of test case structure and metadata (eg. referenced requirements).

.. The following directive (test_defaults) makes sure that all test cases have
   "Fedora Quality Assurance" specified as "author", without listing this in
   every test case.

.. test_defaults::
   :author: Fedora Quality Assurance

.. toctree::
   :maxdepth: 2
   :caption: Structure of Test Cases

   systemd/index.rst
   kernel/index.rst

Overview of Requirements
------------------------

This is list of all requirements, with a sublist of test cases covering each
requirement.

.. requirementlist::

License
-------

|Creative Commons License|

This work is licensed under a `Creative Commons Attribution-ShareAlike 3.0
Unported License`_.


.. |Creative Commons License| image:: by-sa-3.0-88x31.png
   :target: https://creativecommons.org/licenses/by-sa/3.0/
   :alt: Creative Commons License

.. _Sphinx: http://www.sphinx-doc.org/en/stable/index.html
.. _`reStructuredText syntax`: http://www.sphinx-doc.org/en/stable/usage/restructuredtext/basics.html
.. _Pylatest: https://pylatest.readthedocs.io/en/stable/
.. _`Creative Commons Attribution-ShareAlike 3.0 Unported License`: https://creativecommons.org/licenses/by-sa/3.0/
.. _`Fedora Test Cases`: https://fedoraproject.org/wiki/Category:Test_Cases
.. _`Fedora Quality Assurance`: https://fedoraproject.org/wiki/QA
