:original_name: ces_01_0034.html

.. _ces_01_0034:

Installing the Agents in Batches on Linux ECSs
==============================================

Scenarios
---------

This topic describes how to batch install the Agents on Linux ECSs.

Operation
---------

After binding an elastic IP address (EIP) to an ECS, use the ECS as the execution node and run scripts in batches to copy, decompress, and install the Agent package and configuration file to other ECSs (target nodes).

.. important::

   -  The target nodes in one batch must be deployed in the same VPC.

   -  For servers running Windows OSs, Agents cannot be installed in batches.

Prerequisites
-------------

-  During the creation, all ECSs use the same PEM file. Upload the PEM file to the **/usr/local** directory of the ECS on which the Agent has been installed, and name the file **user.pem**.
-  The IP addresses of all ECSs (target nodes) have been listed in a **iplist.txt** file and uploaded to the **/usr/local** directory on the execution node.

   .. note::

      In the iplist.txt file, list each IP address on a separate line:

      .. code-block::

         192.168.1.1
         192.168.1.2

Procedure
---------

#. Log in to the execution node as user **root**.

#. Run the following commands to set the permission for **user.pem** to **0600** and download the batch installation script:

   **cd /usr/local && chmod 0600 user.pem && wget http://telescope-eu-de.obs.eu-de.otc.t-systems.com/scripts/batchInstall && chmod +x batchInstall**

#. Run the following command to install the Agent on the execution and target nodes:

   **cd /usr/local && ./batchInstall -pem -c "wget https://telescope-eu-de.obs.eu-de.otc.t-systems.com/scripts/agentInstall.sh && chmod 755 agentInstall.sh && ./agentInstall.sh"**

#. After the installation completes, log in to the Cloud Eye console.

#. In the navigation pane on the left, choose **Server Monitoring**.

   View the list of ECSs on which the Agents have been installed.

   .. note::

      After you configure the Agent, its status is still displayed as **Uninstalled** because the monitoring data is not reported yet. Wait 3 to 5 minutes and refresh the page.

#. On the **Server Monitoring** page, select all ECSs and click **Restore Agent Configurations**.

#. Click **One-Click Restore**.
