:original_name: en-us_topic_0078721772.html

.. _en-us_topic_0078721772:

Introduction to Server Monitoring
=================================

Server monitoring includes basic monitoring, process monitoring, and OS monitoring for servers.

-  Basic monitoring covers metrics automatically reported by ECSs. The data is collected every 5 minutes. For details, see :ref:`Services Interconnected with Cloud Eye <en-us_topic_0202622212>`.
-  OS monitoring provides proactive and fine-grained OS monitoring for ECSs or BMSs, and it requires the Agent to be installed on all servers that will be monitored. The data is collected every minute. OS monitoring supports metrics such as CPU usage and memory usage (Linux). For details, see :ref:`Services Interconnected with Cloud Eye <en-us_topic_0202622212>`.
-  Process monitoring provides monitoring of active processes on hosts. By default, Cloud Eye collects CPU usage, memory usage, and number of opened files of active processes.

.. note::

   -  For the ECS specifications, use 2 vCPUs and 4 GB memory for a Linux ECS and 4 vCPUs and 8 GB memory or higher specifications for a Windows ECS.
   -  The Agent will use the system ports. For details, see descriptions of **ClientPort** and **PortNum** in :ref:`(Optional) Manually Configuring the Agent (Linux) <ces_01_0031>`. If the Agent port conflicts with a service port, see :ref:`What Should I Do If the Service Port Is Used by the Agent? <ces_faq_0037>`
   -  To install the Agent in a Linux server, you must have the root permissions. For a Windows server, you must have the administrator permissions.

Scenarios
---------

Whether you are using ECSs or BMSs, you can use server monitoring to track various OS metrics, monitor server resource usage, and query monitoring data when faults occur.

Monitoring Capabilities
-----------------------

Server monitoring provides multiple metrics, such as metrics for CPU, memory, disk, and network usage, meeting the basic monitoring and O&M requirements for servers.

Resource Usage
--------------

The Agent uses considerably less resources. When the Agent is installed on a server, it uses less than 5% of the CPU and less than 100 MB of memory.
