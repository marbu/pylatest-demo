Test Bar Insane Mode
********************

:author: nobody@example.com
:date: 2018-06-10
:priority: medium

Description
===========

Make sure *insane mode* can be enabled in Bar.

Setup
=====

#. Make sure you have bar installed

#. Enable *insane mode* in ``bar.conf``

#. Disable *attack flag* in ``bear.conf``

#. Reload bar daemon

Test Steps
==========

.. test_action::
   :step: List files in the volume: ``ls -a /mnt/helloworld``
   :result: There are no files, output should be empty.

.. test_action::
   :step:
       Run the following commands::

           $ bar --extra sth
           $ bar -vvv

       And wait at least 10 seconds.

   :result:
       Maecenas congue ligula ac quam viverra nec
       consectetur ante hendrerit.

.. test_action::
   :step:
       Run the following commands::

           $ bar --extra sth
           $ bar -vvv

       And wait at least 10 seconds.

   :result:
       Maecenas congue ligula ac quam viverra nec
       consectetur ante hendrerit.

.. test_action::
   :step:
       Run the following commands::

           $ bar --extra sth
           $ bar -vvv

       And wait at least 10 seconds.

   :result:
       Maecenas congue ligula ac quam viverra nec
       consectetur ante hendrerit.

Teardown
========

#. Disable *insane mode* in ``bar.conf``

#. Delete ``bear.conf``

#. Reload bar daemon
