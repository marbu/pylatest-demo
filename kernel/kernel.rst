Kernel regression
*****************

:source: `QA:Testcase kernel regression <https://fedoraproject.org/wiki/QA:Testcase_kernel_regression>`_
:requirement: Basic Release Criteria

Description
===========

This test case tests ``kernel`` using the kernel regression test suite. For
details about the test suite, see
https://fedoraproject.org/wiki/KernelTestingInitiative.

Setup
=====

#. Ensure the ``gcc``, ``git`` and ``python-fedora`` packages are installed

#. Clone the kernel-tests repository::

     $ git clone https://pagure.io/kernel-tests.git

#. For submission of test results make sure you have the package
   ``python-fedora`` installed (``python3-fedora`` on Fedora 29/Rawhide)::

     $ sudo dnf install python-fedora

#. You need ``gcc``, ``make``, ``libtirpc`` and ``libtirpc-devel`` in order to
   run the tests, if it is not already installed::

     $ sudo dnf install gcc make libtirpc libtirpc-devel

#. cd into the kernel-tests directory::

     $ cd kernel-tests

#. Configure automatic submission of the test results and your FAS username::

     $ cp config.example .config
     $ vim .config

   Look for lines with ``submit=`` and ``username=`` and set these settings to
   ``submit=authenticated`` and ``username=<your FAS login without quotes>``.

Test Steps
==========

.. test_action::
   :step:
       Run the default test suite::

           $ sudo ./runtests.sh
   :result:
       Run of the test suite should result in PASS.

.. test_action::
   :step:
       Run the performance test suite::

           $ sudo ./runtests.sh -t performance
   :result:
       Run of the test suite should result in PASS.
