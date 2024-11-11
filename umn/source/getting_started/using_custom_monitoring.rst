:original_name: ces_06_0005.html

.. _ces_06_0005:

Using Custom Monitoring
=======================

The **Custom Monitoring** page displays all custom metrics reported by users. You can use simple API requests to report collected monitoring data of those metrics to Cloud Eye for processing and display.

For details about how to add monitoring data, see section "Adding Monitoring Data" in the *Cloud Eye API Reference*.

Viewing Custom Monitoring
-------------------------

#. Log in to the management console.

#. Click **Service List** in the upper left corner and select **Cloud Eye**.

#. In the navigation pane on the left, choose **Custom Monitoring**.

#. On the **Custom Monitoring** page, view the data reported by yourself through API requests, including custom services and metrics.

#. Locate the cloud service resource and click **View Metric** in the **Operation** column.

   On the page displayed, you can view graphs based on raw data collected in **1h**, **3h**, and **12h**. In the upper right corner of each graph, the maximum and minimum values of the metric in the corresponding time periods are dynamically displayed.

#. If you want to view metric details, hover your mouse over a graph and click |image1| in the upper right corner.

   In the upper left corner, you can see six default monitoring periods: **1h**, **3h**, **12h**, **1d**, **7d**, and **30d**. To view historical monitoring data for any period during the last six months, customize the monitoring period by setting **Select Range** in the upper right corner.

   In the upper left corner of the graph, click **Settings** to configure the rollup method.

Creating an Alarm Rule
----------------------

#. Log in to the management console.

#. Click **Service List** in the upper left corner and select **Cloud Eye**.

#. In the navigation pane on the left, choose **Custom Monitoring**.

#. Locate the cloud service resource and click **Create Alarm Rule** in the **Operation** column.

#. Configure the alarm rule name, alarm policy, and alarm notification.

   After you create the alarm rule, if the custom metric data reaches the threshold, Cloud Eye immediately notifies you through SMN that an exception has occurred.

.. |image1| image:: /_static/images/en-us_image_0167222995.png
