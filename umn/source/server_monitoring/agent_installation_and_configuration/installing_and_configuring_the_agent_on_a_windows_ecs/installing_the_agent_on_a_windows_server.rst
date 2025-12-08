:original_name: en-us_topic_0110258146.html

.. _en-us_topic_0110258146:

Installing the Agent on a Windows server
========================================

Scenarios
---------

This topic describes how to install the Agent on a Windows ECS.

Constraints
-----------

-  The Agent cannot be installed on Windows BMSs.
-  Some OSs are not supported. For details about which Windows OSs are supported, see :ref:`What OSs Does the Agent Support? <ces_faq_0024>`

Prerequisites
-------------

-  You have performed operations described in :ref:`Modifying the DNS Server Address and Adding Security Group Rules (Windows) <en-us_topic_0150366044>`.
-  You have configured an agency by referring to :ref:`Configuring an Agency by One Click <en-us_topic_0000002452369417>`.
-  Use an administrator account to install the Agent.
-  Ensure that the Telescope process is not stopped by other processes after the installation.
-  You have obtained the Agent installation package (Windows).

   .. table:: **Table 1** Installation package path

      +-----------------------------------------+-----------------------+---------------------------------------------------------------------------------+
      | Name                                    | Format                | Download Path                                                                   |
      +=========================================+=======================+=================================================================================+
      | Installation package for 64-bit Windows | zip                   | EU DE:                                                                          |
      |                                         |                       |                                                                                 |
      |                                         |                       | .. code-block::                                                                 |
      |                                         |                       |                                                                                 |
      |                                         |                       |    https://uniagent-eu-de.obs.eu-de.otc.t-systems.com/package/install_amd64.exe |
      |                                         |                       |                                                                                 |
      |                                         |                       | EU NL:                                                                          |
      |                                         |                       |                                                                                 |
      |                                         |                       | .. code-block::                                                                 |
      |                                         |                       |                                                                                 |
      |                                         |                       |    https://uniagent-eu-nl.obs.eu-nl.otc.t-systems.com/package/install_amd64.exe |
      +-----------------------------------------+-----------------------+---------------------------------------------------------------------------------+

Procedure
---------

#. Log in to the Windows ECS as an administrator.

#. Open a browser, and enter the address of the Agent installation package in the address box to download and save the installation package.

#. Open Windows PowerShell and go to the directory storing the installation package.

#. Run the following command to install the Agent:

   EU DE:

   .. code-block::

      .\install_amd64.exe -r eu-de -u 0.1.9 -t 2.7.2 -d agent.ces.otc.t-systems.com -o otc.t-systems.com

   EU NL:

   .. code-block::

      .\install_amd64.exe -r eu-nl -u 0.1.9 -t 2.7.2 -d agent.ces.otc.t-systems.com -o otc.t-systems.com

   Wait for 3 to 5 minutes until the Agent starts collecting monitoring data.

   .. note::

      -  After you configure the Agent, its status is still displayed as **Not installed** on the **Server Monitoring** page because no monitoring data is reported yet. Wait 3 to 5 minutes and refresh the page.
      -  If the Agent status is **Running** and monitoring is enabled, the Agent has been recognized by Cloud Eye and has started to report fine-grained metric data.
