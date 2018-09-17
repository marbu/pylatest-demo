Base shutdown/reboot
********************

:source: `QA:Testcase base shutdown/reboot <https://fedoraproject.org/wiki/QA:Testcase_base_shutdown/reboot>`_
:requirement: Basic Release Criteria

Description
===========

This test case asserts whether the provided console-based mechanisms for
shutdown and reboot operate as intended and without error. While the test
focuses on running commands from a virtual console, this test can be performed
from any terminal application. 

Setup
=====

#. Prepare a system for test. You can use a live image or an already installed
   system.

#. Ensure the package under test is installed on the system. 

Test Steps
==========

.. test_action::
   :step:
       On a running system, change to a virtual console by pressing Ctrl+Alt+F2
   :result:
       A login prompt is offered at the virtual console.

.. test_action::
   :step:
       At the virtual console, login as the ``root`` user.

.. test_action::
   :step:
       Reboot the system by running the command::
      
           reboot
   :result:
       The ``reboot`` is accepted and initiates a system reboot. The system
       reboots with no additional user interaction, without error, and all
       expected disk partitions are cleanly mounted.

.. test_action::
   :step:
       After the system boots, once again change to a virtual console by
       pressing Ctrl+Alt+F2.
      
       Note, manually booting the system may be required if the previous step
       fails.

.. test_action::
   :step:
       At the virtual console, login as a non-root user. If no non-root user
       accounts are available, you can create a new user account using the
       command ``useradd``.

.. test_action::
   :step:
       Power off the system by running the ``shutdown`` command. Consult the
       man page for different acceptable ``[TIME]`` values. For example, to
       power off the system immediately, type the following command::

           shutdown now
   :result:
       The ``shutdown`` is accepted and powers off the system without error.

.. test_action::
   :step:
       Lastly, power on the system.
   :result:
       The system successfully boots without error, and all expected disk
       partitions are cleanly mounted.
