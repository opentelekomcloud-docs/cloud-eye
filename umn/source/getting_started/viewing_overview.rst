:original_name: en-us_topic_0015479891.html

.. _en-us_topic_0015479891:

Viewing Overview
================

The **Overview** page provides resource overview, alarm statistics, server monitoring, network monitoring, and storage monitoring. You can view **Monitoring Overview** to learn the resource usage and alarms of each cloud service in real time.

The overview page collects statistics on all resources. If you use enterprise project authorization, data not managed by the current enterprise project will also be collected. When you view resources managed in other enterprise projects, the system displays a message about insufficient permissions.

Resource Overview
-----------------

This module displays the total number of monitored cloud service resources and alarms generated for these resources in the current account.

Alarm Statistics
----------------

This module displays the alarm trend for the last seven days and the number of alarms of each severity.

After you click corresponding alarm severity area, the **Alarm Records** page is displayed, showing all alarm records of the severity.

Server Monitoring
-----------------

This module displays the CPU and memory usages of all ECSs, top 5 ECSs (Agent installed) with the highest CPU usage in the last five minutes, memory usages of Windows ECSs, and top 5 ECSs (Agent installed) with the highest memory usage.

Clicking an ECS takes you to the corresponding **Basic Monitoring** page.

Network Monitoring
------------------

This module displays the outbound bandwidth and inbound bandwidth of the current EIP and bandwidth in the last 1 hour.

-  Inbound bandwidth: network rate of inbound traffic.
-  Outbound bandwidth: network rate of outbound traffic.
-  Total outbound bandwidth of all EIPs: total network rate of outbound traffic of all EIPs in the last five minutes.
-  Top 5 EIPs by outbound bandwidth: top 5 EIPs by outbound bandwidth in the last five minutes. You can click the bandwidth name to access the corresponding cloud service monitoring dashboard.

Storage Monitoring
------------------

**Storage Monitoring (EVS)** displays the top 5 EVS disks by read and write bandwidth and the top 5 EVS disks by read and write IOPS in the last five minutes. You can click the EVS disk name to access the corresponding cloud service monitoring dashboard.
