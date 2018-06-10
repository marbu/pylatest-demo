Test Foo Insane Mode
********************

:author: nobody@example.com
:date: 2018-06-10
:priority: high

Description
===========

Make sure *insane mode* can be enabled in Foo.

Setup
=====

#. Make sure you have foo installed

#. Enable *insane mode* in foo.conf

#. Reload foo daemon

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

Teardown
========

#. Disable *insane mode* in foo.conf

#. Reload foo daemon
