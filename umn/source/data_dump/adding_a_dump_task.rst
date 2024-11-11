:original_name: ces_01_0056.html

.. _ces_01_0056:

Adding a Dump Task
==================

Scenarios
---------

You can dump cloud service monitoring data to DMS for Kafka in real time and query the metrics on the DMS for Kafka console or using an open-source Kafka client.

.. note::

   An account can create a maximum of 20 data dump tasks.

Procedure
---------

#. Log in to the management console.

#. Click **Service List** in the upper left corner and select **Cloud Eye**.

#. In the navigation pane on the left, choose **Data Dump**.

#. Click **Add Dump Task**.

#. In the **Add Dump Task** dialog box, configure parameters.


   .. figure:: /_static/images/en-us_image_0000001693747229.png
      :alt: **Figure 1** Adding a dump task

      **Figure 1** Adding a dump task

   .. table:: **Table 1** Dump task parameters

      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                                                                                                                                                                |
      +===================================+============================================================================================================================================================================================================================================================+
      | Name                              | Specifies the dump task name.                                                                                                                                                                                                                              |
      |                                   |                                                                                                                                                                                                                                                            |
      |                                   | The name can contain 1 to 64 characters and consist of only letters, digits, underscores (_), and hyphens (-).                                                                                                                                             |
      |                                   |                                                                                                                                                                                                                                                            |
      |                                   | Example value: **dataShareJob-ECSMetric**                                                                                                                                                                                                                  |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Resource Type                     | Specifies the type of resources monitored by Cloud Eye.                                                                                                                                                                                                    |
      |                                   |                                                                                                                                                                                                                                                            |
      |                                   | Example value: **Elastic Cloud Server**                                                                                                                                                                                                                    |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Dimension                         | Specifies the dimension of the monitored object.                                                                                                                                                                                                           |
      |                                   |                                                                                                                                                                                                                                                            |
      |                                   | For details about the dimensions of each monitored object, see :ref:`Services Interconnected with Cloud Eye <en-us_topic_0202622212>`.                                                                                                                     |
      |                                   |                                                                                                                                                                                                                                                            |
      |                                   | If you select **All** all monitored objects of the selected resource type will be dumped to Kafka.                                                                                                                                                         |
      |                                   |                                                                                                                                                                                                                                                            |
      |                                   | If you select a specific dimension, only metrics of this dimension will be dumped to Kafka.                                                                                                                                                                |
      |                                   |                                                                                                                                                                                                                                                            |
      |                                   | Example value: **All**                                                                                                                                                                                                                                     |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Monitoring Scope                  | The scope can only be **All resources**, indicating that all metrics of the specified monitored object will be dumped to DMS for Kafka.                                                                                                                    |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Resource Type                     | The type can only be **Distributed Message Service for Kafka**.                                                                                                                                                                                            |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Destination                       | Specifies the Kafka instance and topic where the data is to be dumped.                                                                                                                                                                                     |
      |                                   |                                                                                                                                                                                                                                                            |
      |                                   | If no Kafka instance or topic is available, see `Creating an Instance <https://docs.otc.t-systems.com/en-us/usermanual/dms/dms-ug-180604013.html>`__ and `Creating a Topic <https://docs.otc.t-systems.com/en-us/usermanual/dms/dms-ug-180604018.html>`__. |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

#. Click **Add** after the configuration is complete.

   .. note::

      You can query the dumped data in Kafka. For details, see `Querying Messages <https://docs.otc.t-systems.com/distributed-message-service/umn/managing_messages/viewing_kafka_messages.html>`__.
