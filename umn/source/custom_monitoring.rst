:original_name: en-us_topic_0094279601.html

.. _en-us_topic_0094279601:

Custom Monitoring
=================

The **Custom Monitoring** page displays all custom metrics reported by users. You can use simple API requests to report collected monitoring data of those metrics to Cloud Eye for processing and display.

Viewing Custom Monitoring
-------------------------

#. Log in to the management console.

#. Click **Service List** in the upper left corner, and select **Cloud Eye**.

#. In the navigation pane on the left, choose **Custom Monitoring**.

#. On the **Custom Monitoring** page, view the data reported by yourself through API requests, including custom services and metrics.

   .. note::

      -  Only after you add monitoring data through APIs, will those data be displayed on the Cloud Eye console.
      -  For details about how to add monitoring data, see section "Adding Monitoring Data" in the *Cloud Eye API Reference*.

#. Locate the row that contains the cloud service resource to be viewed, and click **View Metric**.

   On the page displayed, you can view graphs based on raw data collected in **1h**, **3h**, **12h**, **1d**, and **7d**. In the upper right corner of each graph, the maximum and minimum values of the metric in the corresponding time periods are dynamically displayed.

Creating an Alarm Rule
----------------------

#. Log in to the management console.
#. Click **Service List** in the upper left corner, and select **Cloud Eye**.
#. In the navigation pane on the left, choose **Custom Monitoring**.
#. On the **Custom Monitoring** page, locate the target resource and click **Create Alarm Rule** in the **Operation** column.
#. In the **Create Alarm Rule** dialog box, follow the prompts to configure the parameters. For details, see :ref:`Table 2 <ces_01_0074__table4534051437>`.
#. Click **Create**.
