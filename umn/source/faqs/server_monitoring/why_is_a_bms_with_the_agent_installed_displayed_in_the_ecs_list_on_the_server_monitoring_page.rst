:original_name: ces_faq_0053.html

.. _ces_faq_0053:

Why Is a BMS with the Agent Installed Displayed in the ECS List on the Server Monitoring Page?
==============================================================================================

Symptoms
--------

The Agent was installed on a BMS, but the BMS is listed on the **Server Monitoring** > **Elastic Cloud Server** page on the Cloud Eye console.

Possible Causes
---------------

The Agent determines whether a server is an ECS or BMS based on the services provided by IP address 169.254.169.254. If the route for this address is changed, the Agent will consider the server to be an ECS by default.

Solution
--------

Manually modify the Agent configuration file by adding BMS identifier **BmsFlag** and setting it to **true**.

-  Linux OS: See :ref:`(Optional) Manually Configuring the Agent (Linux) <ces_01_0031>`.
-  Windows OS: See :ref:`(Optional) Manually Configuring the Agent on a Windows Server <ces_01_0032>`.
