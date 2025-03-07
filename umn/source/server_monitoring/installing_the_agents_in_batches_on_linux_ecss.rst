:original_name: ces_01_0033.html

.. _ces_01_0033:

Installing the Agents in Batches on Linux ECSs
==============================================

Scenarios
---------

This topic describes how to install Agents in batches on Linux ECSs.

Operation
---------

After binding an elastic IP address to an ECS, install and configure the Agent by following instructions in :ref:`Installing and Configuring the Agent on a Linux ECS or BMS <ces_01_0004>` to ensure that data collection is normal. Use the ECS as a jump server and run scripts in batches to copy, decompress, and install the Agent package and configuration file to other ECSs.

.. important::

   -  The ECSs where the Agent is to be installed in batches must belong to the same VPC.

   -  Agents cannot be installed on Windows servers in batches.

Prerequisites
-------------

-  The IP addresses and password of user **root** of all ECSs for which the Agent is to be installed have been collected, sorted in the iplist.txt format, and uploaded to the **/usr/local** directory on the first ECS.

   .. note::

      In the **iplist.txt** file, each line contains only one IP address in the "IP address,Password of user **root**" format.

      In the following example, **abcd** is the password.

      .. code-block::

         192.168.1.1,abcd
         192.168.1.2,abcd

Procedure
---------

#. Use PuTTY to log in to the ECS on which the Agent has been installed as user **root**.

#. Run the following command to download and run the batch installation script:

   eu-de:

   -  x86_64

      .. code-block::

         cd /usr/local && wget --no-check-certificate https://telescope-eu-de.obs.eu-de.otc.t-systems.com/scripts/agentBatchPackage.sh && chmod 755 agentBatchPackage.sh && ./agentBatchPackage.sh

   -  Arm 64

      .. code-block::

         cd /usr/local && wget --no-check-certificate https://telescope-eu-de.obs.eu-de.otc.t-systems.com/scripts/agentBatchPackageARM.sh && chmod 755 agentBatchPackageARM.sh && ./agentBatchPackageARM.sh

   eu-nl:

   -  x86_64

      .. code-block::

         cd /usr/local && wget --no-check-certificate https://telescope-eu-nl.obs.eu-nl.otc.t-systems.com/scripts/agentBatchPackage.sh && chmod 755 agentBatchPackage.sh && ./agentBatchPackage.sh

   -  Arm 64

      .. code-block::

         cd /usr/local && wget --no-check-certificate https://telescope-eu-nl.obs.eu-nl.otc.t-systems.com/scripts/agentBatchPackageARM.sh && chmod 755 agentBatchPackageARM.sh && ./agentBatchPackageARM.sh

#. Run the following command to run the script and enter the password (the passwords of multiple ECSs are the same):

   **cd /usr/local && ./batchInstall.sh** *$password*

   .. important::

      -  If multiple passwords are involved in the configured **iplist.txt**, enter the preceding commands and passwords for multiple times. If the password of an ECS is incorrect, the Agent installation on the ECS will fail.
      -  If the passwords of multiple ECSs are different, run the **cd /usr/local && ./batchInstall.sh** command.
      -  Ensure that the ECSs are running during script execution.

#. After the installation is complete, log in to the Cloud Eye console and choose **Server Monitoring** in the navigation pane on the left.

   View the list of ECSs on which the Agent has been installed.

   .. note::

      After you configure the Agent, its status is still displayed as **Uninstalled** because no monitoring data is reported yet. Wait 3 to 5 minutes and refresh the page.

#. On the **Server Monitoring** page, select all ECSs and click **Restore Agent Configurations**.

#. On the page that is displayed, click **One-Click Restore**.
