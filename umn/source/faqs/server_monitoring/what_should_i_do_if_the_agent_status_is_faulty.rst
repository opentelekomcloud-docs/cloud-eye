:original_name: ces_faq_0025.html

.. _ces_faq_0025:

What Should I Do If the Agent Status Is Faulty?
===============================================

The OS monitoring Agent sends a heartbeat message to Cloud Eye every minute. If Cloud Eye does not receive any heartbeat messages for three consecutive minutes, **Agent Status** is displayed as **Faulty**.

It may because:

-  The account is in arrears.

-  If the Agent process is faulty, restart it by following the instructions provided in :ref:`Managing the Agent <ces_01_0035>`. If the restart fails, related files have been deleted accidentally. In this case, reinstall the Agent.

-  The server time is inconsistent with the local standard time.

-  The Agent is incorrectly configured. Check whether the DNS server address is correct. If it is, check the Agent configurations by referring to :ref:`Modifying the DNS Server Address and Adding Security Group Rules (Linux) <en-us_topic_0150354069>` and :ref:`(Optional) Manually Configuring the Agent on a Linux Server <ces_01_0031>`.

-  Specific causes are logged. You can check the log file for the cause. The log path varies with the Agent version.

   The log paths are as follows:

   -  Linux:

      New Agent version: **/usr/local/uniagent/extension/install/telescope/log/ces.log**

      Early Agent version: **/usr/local/telescope/log/ces.log**

   -  Windows:

      New version: **C:\\Program Files\\uniagent\\extension\\install\\telescope\\log\\ces.log**

      Earlier version: path where the Agent installation package is decompressed. For example, if the decompression path is **D:\\Agent**, the log path is **D:\\Agent\\telescope_windows_amd64\\log\\ces.log**.
