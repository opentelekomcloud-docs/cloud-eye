:original_name: ces_01_0029.html

.. _ces_01_0029:

Installing the Agent on a Linux Server
======================================

Scenarios
---------

This topic describes how to manually install the Agent on a Linux ECS or BMS.

Constraints
-----------

Some OSs are not supported. For details about which Linux OSs are supported, see :ref:`What OSs Does the Agent Support? <ces_faq_0024>`

Prerequisites
-------------

-  You have the read and write permissions for the installation directories. The Telescope process will not be stopped by other software after the installation.
-  You have performed operations described in :ref:`Modifying the DNS Server Address and Adding Security Group Rules (Linux) <en-us_topic_0150354069>`.
-  You have configured an agency by referring to :ref:`Configuring an Agency by One Click <en-us_topic_0000002452369417>`.

Procedure
---------

#. Log in to the ECS or BMS as user **root**.

#. Install the Agent.

   EU DE:

   .. code-block::

      cd /usr/local && curl -k -O https://uniagent-eu-de.obs.eu-de.otc.t-systems.com/package/agent_install.sh && bash agent_install.sh -r eu-de -u 0.1.9 -t 2.7.2 -o otc.t-systems.com -d agent.ces.otc.t-systems.com

   EU NL:

   .. code-block::

      cd /usr/local && curl -k -O https://uniagent-eu-nl.obs.eu-nl.otc.t-systems.com/package/agent_install.sh && bash agent_install.sh -r eu-nl -u 0.1.9 -t 2.7.2 -o otc.t-systems.com -d agent.ces.otc.t-systems.com

   If the message "Telescope process starts successfully." is displayed, the installation is successful. Wait for 3 to 5 minutes until the Agent starts collecting monitoring data.

   .. note::

      -  After you configure the Agent, its status is still displayed as **Not installed** on the **Server Monitoring** page because no monitoring data is reported yet. Wait 3 to 5 minutes and refresh the page.
      -  If the Agent status is **Running** and monitoring is enabled, the Agent has been recognized by Cloud Eye and has started to report fine-grained metric data.
