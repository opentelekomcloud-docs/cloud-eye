:original_name: en-us_topic_0110258146.html

.. _en-us_topic_0110258146:

Installing and Configuring the Agent on a Windows Server
========================================================

Scenarios
---------

This topic describes how to install the Agent on a Windows ECS.

Constraints
-----------

The Agent cannot be installed on Windows BMSs.

Prerequisites
-------------

-  You have performed operations described in :ref:`Modifying the DNS Server Address and Adding Security Group Rules (Windows) <en-us_topic_0150366044>`.
-  Use an administrator account to install the Agent.
-  Ensure that the Telescope process is not stopped by other processes after the installation.
-  You have obtained the Agent installation package (Windows).

   .. table:: **Table 1** Installation package path

      +-----------------------------------------+--------+-------------------------------------------------------------------------------------------------+
      | Name                                    | Format | Download Path                                                                                   |
      +=========================================+========+=================================================================================================+
      | Installation package for 64-bit Windows | zip    | EU-DE: http://telescope-eu-de.obs.eu-de.otctest.t-systems.com/agent/telescope_windows_amd64.zip |
      +-----------------------------------------+--------+-------------------------------------------------------------------------------------------------+

Procedure
---------

#. Log in to the Windows ECS as an administrator.

#. Open a browser, and enter the address of the Agent installation package in the address box to download and save the installation package.

#. Create a directory for storing the installation package (for example, **D:\\Agent**) and decompress the package to this directory.

#. Double-click the **install.bat** script to install and start the Agent.

   If **Install service success** is displayed, the Agent is successfully installed and started.

   .. note::

      After you configure the Agent, its status is still displayed as **Uninstalled** because no monitoring data is reported yet. Wait 3 to 5 minutes and refresh the page.

#. On the **Server Monitoring** page, select the target ECS and click **Restore Agent Configurations**.

#. In the displayed **Restore Agent Configurations** dialog box, click **One-Click Restore**.

   The Agent configuration is completed.

   If the Agent is in the **Running** state, the Agent has been installed and has started to collect fine-grained metric data.
