Test Defaults
*************

:author: nobody@example.com
:date: 2018-06-10
:priority: high

Description
===========

Check default functionality.

Setup
=====

#. Make sure you have foo installed

#. Make sure foo daemon is running

Test Steps
==========

.. test_action::
   :step: List files in the volume: ``ls -a /mnt/helloworld``
   :result: There are no files, output should be empty.

.. test_action::
   :step:
       Run the following commands::

           $ foo --extra sth
           $ bar -vvv

       And wait at least 10 seconds.

   :result:
       Maecenas congue ligula ac quam viverra nec
       consectetur ante hendrerit.

.. test_action::
   :step:
       List all the files: ``ls -a /mnt/helloworld/this/is/long/path``
   :result:
       There are no files, output should be empty.

Teardown
========

#. Make sure foo daemon is running
