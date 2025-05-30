:original_name: ces_01_0029.html

.. _ces_01_0029:

Installing the Agent on a Linux Server
======================================

Scenarios
---------

This section describes how to manually install the Agent on a Linux ECS or BMS.

Prerequisites
-------------

-  You have the read and write permissions for the installation directories in :ref:`Procedure <ces_01_0029__section494503071814>`. The Telescope process will not be stopped by other software after the installation.
-  You have performed operations described in :ref:`Modifying the DNS Server Address and Adding Security Group Rules (Linux) <en-us_topic_0150354069>`.

.. _ces_01_0029__section494503071814:

Procedure
---------

#. Log in to the ECS or BMS as user **root**.

#. Install the Agent.

   EU DE:

   -  x86_64

      .. code-block::

         cd /usr/local && wget --no-check-certificate https://telescope-eu-de.obs.eu-de.otc.t-systems.com/scripts/agentInstall.sh && chmod 755 agentInstall.sh && ./agentInstall.sh

   -  Arm 64

      .. code-block::

         cd /usr/local && wget --no-check-certificate https://telescope-eu-de.obs.eu-de.otc.t-systems.com/scripts/agentInstallARM.sh && chmod 755 agentInstallARM.sh && ./agentInstallARM.sh

   EU NL:

   -  x86_64

      .. code-block::

         cd /usr/local && wget --no-check-certificate https://telescope-eu-nl.obs.eu-nl.otc.t-systems.com/scripts/agentInstall.sh && chmod 755 agentInstall.sh && ./agentInstall.sh

   -  Arm 64

      .. code-block::

         cd /usr/local && wget --no-check-certificate https://telescope-eu-nl.obs.eu-nl.otc.t-systems.com/scripts/agentInstallARM.sh && chmod 755 agentInstallARM.sh && ./agentInstallARM.sh

   If **Telescope process starts successfully** or **Success to install telescope** is displayed, the Agent is successfully installed.

#. Configure the Agent by referring to :ref:`Restoring the Agent Configurations on a Linux Server <ces_01_0030>` or :ref:`(Optional) Manually Configuring the Agent (Linux) <ces_01_0031>`.

   .. note::

      -  :ref:`Restoring Agent Configurations <ces_01_0030>` allows you to configure **AK/SK**, **RegionID**, and **ProjectId** in just a few clicks. You can also modify related configuration files by referring to :ref:`(Optional) Manually Configuring the Agent (Linux) <ces_01_0031>`.
      -  Agent configuration restoration cannot be performed on BMSs. For details about how to modify the Agent configuration file on a BMS, see :ref:`(Optional) Manually Configuring the Agent (Linux) <ces_01_0031>`.

#. Run the following command to clear the installation script:

   .. code-block::

      if [[ -f /usr/local/uniagent/extension/install/telescope/bin/telescope ]]; then rm /usr/local/agent_install.sh; else rm /usr/local/agentInstall.sh; fi
