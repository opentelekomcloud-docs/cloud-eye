:original_name: ces_07_0003.html

.. _ces_07_0003:

Application Scenarios
=====================

Cloud Service Monitoring
------------------------

After enabling a cloud service supported by Cloud Eye, you can view the cloud service status and metric data, and create alarm rules for metrics on the Cloud Eye console.

Server Monitoring
-----------------

By monitoring the ECS or BMS metrics, such as CPU usage, memory usage, and disk usage, you can ensure that the ECS or BMS run normally and prevent service interruptions caused by overuse of resources.

Performance Issues
------------------

When an alarm rule's conditions are met, Cloud Eye generates an alarm and invokes the SMN API to send notifications, allowing you to identify root causes of performance issues.

Capacity Expansion
------------------

After you create alarm rules for metrics such as CPU usage, memory usage, and disk usage, you can track the statuses of cloud services. If the service volume increases, Cloud Eye sends you an alarm notification, enabling you to manually expand the capacity or configure AS policies to automatically increase capacity.

Custom Monitoring
-----------------

Custom monitoring supplements cloud service monitoring. If Cloud Eye does not provide the required metrics, you can use custom monitoring and report the collected monitoring data to Cloud Eye. Cloud Eye helps to display those monitoring data in graphs and allows you to create alarm rules for those custom metrics.

Log Monitoring
--------------

Log monitoring enables you to monitor log content in real time. You can set alarm rules on Cloud Eye to monitor the logs collected by Log Tank Service (LTS), thus to reduce your O&M cost for log monitoring and simplify the log monitoring process.

Event Monitoring
----------------

In event monitoring, you can query system events that are automatically reported to Cloud Eye and custom events reported to Cloud Eye through the API. You can create alarm rules for both system events and custom events. When specific events occur, Cloud Eye generates alarms for you.
