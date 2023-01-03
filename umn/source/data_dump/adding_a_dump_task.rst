:original_name: ces_01_0056.html

.. _ces_01_0056:

Adding a Dump Task
==================

Scenarios
---------

It helps you dump cloud service monitoring data to DMS for Kafka in real time. You can use the data dump function to query metrics on the DMS for Kafka console or on an open-source Kafka client.

.. note::

   An account can create a maximum of 20 data dump tasks.

Procedure
---------

#. Log in to the management console.
#. Click **Service List** in the upper left corner, and select **Cloud Eye**.
#. In the navigation pane, choose **Data Dump**.
#. Click **Add Dump Task**.
#. In the **Add Dump Task** dialog box, configure parameters as prompted.

   .. table:: **Table 1** Dump task parameters

      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                                                                                                                                                                                            |
      +===================================+========================================================================================================================================================================================================================================================================================+
      | Name                              | Specifies the dump task name.                                                                                                                                                                                                                                                          |
      |                                   |                                                                                                                                                                                                                                                                                        |
      |                                   | The name can contain 1 to 64 characters and consist of only letters, digits, underscores (_), and hyphens (-).                                                                                                                                                                         |
      |                                   |                                                                                                                                                                                                                                                                                        |
      |                                   | Example value: **dataShareJob-ECSMetric**                                                                                                                                                                                                                                              |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Resource Type                     | Specifies the type of resources monitored by Cloud Eye.                                                                                                                                                                                                                                |
      |                                   |                                                                                                                                                                                                                                                                                        |
      |                                   | Example value: **Elastic Cloud Server**                                                                                                                                                                                                                                                |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Dimension                         | Specifies the dimension of the monitored object.                                                                                                                                                                                                                                       |
      |                                   |                                                                                                                                                                                                                                                                                        |
      |                                   | For details, see **Metrics** and **Dimension** on the monitoring metric description page.                                                                                                                                                                                              |
      |                                   |                                                                                                                                                                                                                                                                                        |
      |                                   | If **All** is selected, all monitored objects of the selected service will be dumped to Kafka.                                                                                                                                                                                         |
      |                                   |                                                                                                                                                                                                                                                                                        |
      |                                   | If another dimension is selected, monitored objects of this dimension will be dumped.                                                                                                                                                                                                  |
      |                                   |                                                                                                                                                                                                                                                                                        |
      |                                   | Example value: **All**                                                                                                                                                                                                                                                                 |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Monitoring Scope                  | The scope can only be **All resources**, indicating that all metrics of the specified monitored object will be dumped to DMS for Kafka.                                                                                                                                                |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Resource Type                     | The type can only be **Distributed Message Service for Kafka**.                                                                                                                                                                                                                        |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Destination                       | Specifies the Kafka instance name and topic name the data is to be dumped to.                                                                                                                                                                                                          |
      |                                   |                                                                                                                                                                                                                                                                                        |
      |                                   | If no Kafka instance or topic is available, see `Creating an Instance <https://docs.otc.t-systems.com/en-us/usermanual/dms/dms-ug-180604013.html>`__ and `Creating a Topic in a Kafka Premium Instance <https://docs.otc.t-systems.com/en-us/usermanual/dms/dms-ug-180604018.html>`__. |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

#. Click **Add**.

   .. note::

      You can query the dumped data in Kafka.
