:original_name: ces_06_0003.html

.. _ces_06_0003:

Using Server Monitoring
=======================

Server monitoring includes basic monitoring, process monitoring, and OS monitoring for servers.

-  Basic monitoring provides Agent-free monitoring for basic ECS or BMS metrics.
-  OS monitoring provides proactive and fine-grained OS monitoring for servers, and it requires the Agent to be installed on all servers that will be monitored.
-  Process monitoring provides monitoring of active processes on hosts.

.. note::

   Agent access statement: After the Agent is installed, it collects and reports server monitoring data to the Cloud Eye service. When you update the Agent software package, Cloud Eye accesses the software package repository address to update the software. In addition to the preceding behaviors, the Agent does not access any other addresses.

Functions
---------

-  Various Metrics

   Server monitoring provides more than 40 metrics, such as metrics for CPU, memory, disk, and network usage, meeting the basic monitoring and O&M requirements for servers.

-  Fine-grained Monitoring

   After the Agent is installed, the metrics collected by the Agent are reported every minute.

-  Process Monitoring

   CPU usage, memory usage, and number of opened files used by active processes are monitored to help you better understand the resource usages on ECSs and BMSs.


Using Server Monitoring
-----------------------

#. Log in to the management console.

#. Click **Service List** in the upper left corner and select **Cloud Eye**.

#. In the navigation pane on the left, choose **Server Monitoring**.

#. Select the ECS or BMS and install the Agent on it.

   a. Change the DNS server address and add security group rules to the ECS or BMS. For details, see :ref:`Modifying the DNS Server Address and Adding Security Group Rules (Linux) <en-us_topic_0150354069>` or :ref:`Modifying the DNS Server Address and Adding Security Group Rules (Windows) <en-us_topic_0150366044>`.
   b. Install the Agent. For details, see :ref:`Installing the Agent on a Linux Server <ces_01_0029>` or :ref:`Installing and Configuring the Agent on a Windows Server <en-us_topic_0110258146>`.

#. After 5 minutes, check whether the Agent status is **Running**.

   If yes, the Agent has been installed successfully.

   On the right of the ECS, click **View Metric** in the **Operation** column to view the monitoring data.
