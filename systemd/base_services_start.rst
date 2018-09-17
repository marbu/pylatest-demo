Base services start
*******************

:source: `QA:Testcase base services start <https://fedoraproject.org/wiki/QA:Testcase_base_services_start>`_
:requirement: Basic Release Criteria

Description
===========

This test case tests whether all services start properly in a default install.

Setup
=====

#. Perform an installation of the Fedora release, you wish to test, following
   all defaults.

Test Steps
==========

.. test_action::
   :step: Log in to the installed system.

.. test_action::
   :step:
       In a console, run the command ``systemctl --all --failed``
   :result:
       All services should start properly and systemctl should report no
       failed service.

.. test_action::
   :step:
       In a console, run the command ``journalctl -b``
   :result:
       There should be **NO** messages of the type ``Job foo.service/start
       deleted to break ordering cycle`` shown by the second command; these
       indicate that a service was entirely thrown out from the boot process
       due to a dependency loop (e.g. A.service is After B.service is After
       C.service is After A.service; when systemd encounters such a situation
       it arbitrarily discards one of the services to resolve the problem). If
       you see such a message, check the journal manually for more detail on
       the loop
