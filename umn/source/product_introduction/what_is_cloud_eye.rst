:original_name: en-us_topic_0015479882.html

.. _en-us_topic_0015479882:

What Is Cloud Eye?
==================

Cloud Eye is a multi-dimensional resource monitoring service. You can use Cloud Eye to monitor resources, configure alarm rules, identify resource exceptions, and quickly respond to resource changes. :ref:`Figure 1 <en-us_topic_0015479882__fig1135112504519>` shows the Cloud Eye architecture.

.. _en-us_topic_0015479882__fig1135112504519:

.. figure:: /_static/images/en-us_image_0000001089625394.png
   :alt: **Figure 1** Cloud Eye architecture

   **Figure 1** Cloud Eye architecture

Cloud Eye provides the following functions:

-  Automatic monitoring

   Monitoring starts automatically after you create resources such as Elastic Cloud Servers (ECSs). On the Cloud Eye console, you can view statuses of the resources and configure alarm rules for them as needed.

-  Server monitoring

   After you install the Agent (Telescope) on an ECS or a Bare Metal Server (BMS), you can collect ECS or BMS monitoring data at a real-time granularity of 60 seconds. Cloud Eye tracks 40 different metrics, such as CPU, memory, and disk usage, for resources. For details, see :ref:`Introduction to Server Monitoring <en-us_topic_0078721772>`.

-  Flexible alarm rule configurations

   You can create alarm rules for multiple resources at the same time. After you create an alarm rule, you can modify, enable, disable, or delete it at any time. For more information, see :ref:`Alarm Rule Management <ces_01_0077>`.

-  Real-time notifications

   You can enable **Alarm Notification** when creating alarm rules. When the cloud service status changes and metrics reach the thresholds specified in alarm rules, Cloud Eye notifies you by SMS, email, or by sending messages to server addresses, allowing you to monitor your cloud resource statuses and changes in real time.

-  Dashboard

   Various dashboards enable you to view cross-service and cross-dimension monitoring data. They display key metrics and provide an overview of the service status and monitoring details that you can use for troubleshooting. For more information, see :ref:`Introduction to Dashboards <en-us_topic_0015479901>`.

-  Resource group

   A resource group allows you to add and monitor correlated resources and provides a collective health status for all resources that it contains.

-  Event monitoring

   You can query system events that are automatically reported to Cloud Eye and custom events reported to Cloud Eye through the API. You can create alarm rules for both system events and custom events. When specific events occur, Cloud Eye generates alarms for you.

-  Data dump

   You can use the data dump function to query metrics on the DMS for Kafka console or on an open-source Kafka client. It helps you dump cloud service monitoring data to Kafka in real time.
