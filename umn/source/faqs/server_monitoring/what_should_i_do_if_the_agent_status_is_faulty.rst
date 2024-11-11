:original_name: ces_faq_0025.html

.. _ces_faq_0025:

What Should I Do If the Agent Status Is Faulty?
===============================================

The OS monitoring Agent sends a heartbeat message to Cloud Eye every minute. If Cloud Eye does not receive any heartbeat messages for three consecutive minutes, **Agent Status** is displayed as **Faulty**.

It may because:

-  Your account is in arrears.
-  If the Agent process is faulty, restart it by following the instructions provided in :ref:`Managing the Agent <ces_01_0035>`. If the restart fails, related files have been deleted accidentally. In this case, reinstall the Agent.
-  The server time is inconsistent with the local standard time.
-  The Agent plug-in logs are stored in the following directories:

   -  Linux: **/usr/local/telescope/log/ces.log**
   -  Windows: **C:\\Program Files\\telescope\\log\\ces.log**

It may be that the Agent is incorrectly configured. Check whether the DNS server address is correct. If it is, check the Agent configurations by referring to :ref:`Modifying the DNS Server Address and Adding Security Group Rules (Linux) <en-us_topic_0150354069>` and :ref:`(Optional) Manually Configuring the Agent (Linux) <ces_01_0031>`.

Locate the cause in log **/usr/local/telescope/log/common.log**.
