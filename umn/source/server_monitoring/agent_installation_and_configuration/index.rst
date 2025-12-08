:original_name: ces_01_0027.html

.. _ces_01_0027:

Agent Installation and Configuration
====================================

Based on the OS you are going to use, server quantity, and personal habits, install the Agent by choosing one or more of the following scenarios:

+--------------------------------------------------+-------------------+---------------------------------------------------------------------------------+
| Scenario                                         | Supported Service | Reference                                                                       |
+==================================================+===================+=================================================================================+
| Installing the Agent on a Linux server           | ECS and BMS       | :ref:`Installing and Configuring the Agent on a Linux ECS or BMS <ces_01_0004>` |
+--------------------------------------------------+-------------------+---------------------------------------------------------------------------------+
| Installing the Agent on a Windows server         | ECS               | :ref:`Installing and Configuring the Agent on a Windows ECS <ces_01_0005>`      |
+--------------------------------------------------+-------------------+---------------------------------------------------------------------------------+
| Installing the Agent in batches on Linux servers | ECS               | :ref:`Installing the Agents in Batches on Linux ECSs <ces_01_0033>`             |
+--------------------------------------------------+-------------------+---------------------------------------------------------------------------------+

Agent installation and configuration description:

-  To successfully install the Agent, ensure that both DNS and security group rules are correctly configured.
-  Before installing the Agent, you only need to click **Configure** on the **Server Monitoring** page of the Cloud Eye console, or select **cesgency** for **Agency** in **Advanced Options** when buying an ECS. Cloud Eye automatically performs a temporary AK/SK authorization for the Agent installed on the ECS or BMS in the region. And in the future, the newly created servers in this region will automatically get this authorization. After the configuration is completed, the Agent configurations of all servers in these regions are restored by default.
-  If the Agent fails to be configured by clicking **Configure** or due to other reasons, manually configure it. For details, see :ref:`(Optional) Manually Configuring the Agent on a Linux Server <ces_01_0031>` or :ref:`(Optional) Manually Configuring the Agent on a Windows Server <ces_01_0032>`.
-  Not every Operating System is supported. For details about which Windows and Linux OSs are supported, see :ref:`What OSs Does the Agent Support? <ces_faq_0024>`

-  :ref:`Installing and Configuring the Agent on a Linux ECS or BMS <ces_01_0004>`
-  :ref:`Installing and Configuring the Agent on a Windows ECS <ces_01_0005>`
-  :ref:`Installing the Agents in Batches on Linux ECSs <ces_01_0033>`

.. toctree::
   :maxdepth: 1
   :hidden: 

   installing_and_configuring_the_agent_on_a_linux_ecs_or_bms/index
   installing_and_configuring_the_agent_on_a_windows_ecs/index
   installing_the_agents_in_batches_on_linux_ecss
