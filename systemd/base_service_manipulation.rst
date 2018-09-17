Base service manipulation
*************************

:source: `QA:Testcase base service manipulation <https://fedoraproject.org/wiki/QA:Testcase_base_service_manipulation>`_
:requirements:
  * Basic Release Criteria
  * system-service-manipulation

Description
===========

.. note:: **Associated release criterion**

   This test case is associated with the `system-service-manipulation release
   criterion
   <https://fedoraproject.org/wiki/Basic_Release_Criteria#system-service-manipulation>`_
   . If you are doing release validation testing, a failure of this test case
   may be a
   breach of that release criterion. If so, please file a bug and nominate it
   as blocking the appropriate milestone, using the blocker bug nomination
   page.

This test case tests whether starting, stopping, enabling and disabling system
services works as expected. 

Setup
=====

#. Perform an installation of the Fedora release you wish to test, making as
   few choices as possible and making the most obvious and simple choices where
   choice is required 

Test Steps
==========

.. note:: Service used for testing

   You may use another service for testing if necessary (for instance, testing
   Fedora Cloud images remotely, where disabling sshd would prevent you
   accessing the system). Ensure it is a service which works reliably (like
   crond) - this is a test of the service management mechanism, not of the
   particular service.

.. test_action::
   :step:
       Log in to the installed system. In a console, run the following
       commands::

           su -c 'systemctl stop sshd.service' 
           su -c 'systemctl disable sshd.service'

.. test_action::
   :step:
       Now reboot. Log in again, and run the following commands::

           su -c 'systemctl status sshd.service'
           ps aux | grep sshd
   :result:
       Each time they appear, the commands ``su -c 'systemctl status
       sshd.service'`` and ``ps aux | grep sshd`` check whether the service is
       running.

       The expected result: disabled and inactive (not running).

.. test_action::
   :step:
       Run the following commands::

           su -c 'systemctl start sshd.service'
           su -c 'systemctl status sshd.service'
           ps aux | grep sshd
   :result:
       Disabled but active (running).

.. test_action::
   :step:
       Run the following commands::

           su -c 'systemctl stop sshd.service'
           su -c 'systemctl status sshd.service'
           ps aux | grep sshd
   :result:
       Disabled and inactive (not running).

.. test_action::
   :step:
       Run the following commands::

           su -c 'systemctl enable sshd.service'

       Then reboot, log in again and run the following commands::

           su -c 'systemctl status sshd.service'
           ps aux | grep sshd
   :result:
       Enabled and active (running)

.. test_action::
   :step:
       Run the following commands::

           su -c 'systemctl disable sshd.service'

       Then reboot, log in again and run the following commands::

           su -c 'systemctl status sshd.service'
           ps aux | grep sshd
   :result:
       Disabled and inactive (not running)
