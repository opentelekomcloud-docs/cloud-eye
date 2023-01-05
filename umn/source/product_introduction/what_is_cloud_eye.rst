:original_name: en-us_topic_0015479882.html

.. _en-us_topic_0015479882:

What Is Cloud Eye?
==================

Cloud Eye is a multi-dimensional resource monitoring service. You can use Cloud Eye to monitor resources, set alarm rules, identify resource exceptions, and quickly respond to resource changes. :ref:`Figure 1 <en-us_topic_0015479882__fig1135112504519>` shows the Cloud Eye architecture.

.. _en-us_topic_0015479882__fig1135112504519:

.. figure:: /_static/images/en-us_image_0000001089625394.png
   :alt: **Figure 1** Cloud Eye architecture

   **Figure 1** Cloud Eye architecture

Cloud Eye provides the following functions:

-  Automatic monitoring

   Monitoring starts automatically after you created resources such as Elastic Cloud Servers (ECSs). On the Cloud Eye console, you can view the service status and set alarm rules for these resources.

-  Server monitoring

   After you install the Agent (Telescope) on an ECS and Bare Metal Server (BMS), you can collect 60-second granularity ECS and BMS monitoring data in real-time. Cloud Eye provides 40 metrics, such as CPU, memory, and disk metrics. For details, see :ref:`Introduction to Server Monitoring <en-us_topic_0078721772>`.

-  Flexible alarm rule configuration

   You can create alarm rules for multiple resources at the same time. After you create an alarm rule, you can modify, enable, disable, or delete it at any time. For more information, see :ref:`Alarm Rule Management <ces_01_0077>`.

-  Real-time notification

   You can enable **Alarm Notification** when creating alarm rules. When the cloud service status changes and metrics reach the thresholds specified in alarm rules, Cloud Eye notifies you by text messages, emails, or by sending messages to server addresses, allowing you to monitor the cloud resource status and changes in real time.

-  Monitoring panel

   The panel enables you to view cross-service and cross-dimension monitoring data. It displays key metrics, providing an overview of the service status and monitoring details that you can use for troubleshooting. For more information, see :ref:`Introduction to Monitoring Panels <en-us_topic_0015479901>`.

-  Resource group

   A resource group allows you to add and monitor correlated resources and provides a collective health status for all resources that it contains.

-  Data dump

   You can use the data dump function to query metrics on the DMS for Kafka console or on an open-source Kafka client. It helps you dump cloud service monitoring data to Kafka in real time.
