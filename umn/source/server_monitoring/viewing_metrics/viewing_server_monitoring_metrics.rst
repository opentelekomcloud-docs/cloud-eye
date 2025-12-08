:original_name: en-us_topic_0079332017.html

.. _en-us_topic_0079332017:

Viewing Server Monitoring Metrics
=================================

Scenarios
---------

This topic describes how to view server monitoring metrics, including fine-grained OS metrics collected by the Agent and basic ECS metrics.

For details, see :ref:`Services Interconnected with Cloud Eye <en-us_topic_0202622212>`.

Prerequisites
-------------

You have installed the Agent. For details, see :ref:`Installing and Configuring the Agent on a Linux ECS or BMS <ces_01_0004>` and :ref:`Installing the Agent on a Windows server <en-us_topic_0110258146>`.

Procedure
---------

#. Log in to the management console.

#. Choose **Service List** > **Cloud Eye**.

#. View ECS or BMS metrics.

   -  To view OS monitoring metrics of an ECS, in the left navigation pane, choose **Server Monitoring** > **Elastic Cloud Server**, locate the ECS, and click **View Metric** in the **Operation** column.
   -  To view basic monitoring metrics of an ECS, in the left navigation pane, choose **Server Monitoring** > **Elastic Cloud Server**, locate the ECS, and click **View Metric** in the **Operation** column. Click the **Basic Monitoring** tab.
   -  To view OS monitoring metrics of a BMS, in the left navigation pane, choose **Server Monitoring** > **Bare Metal Server**, locate the BMS, and click **View Metric** in the **Operation** column.
   -  To view processing monitoring metrics, in the left navigation pane, choose **Server Monitoring** > **Elastic Cloud Server**, locate the ECS, and click **View Metric** in the **Operation** column, and then click the **Process Monitoring** tab.

#. View metrics.

   -  In the upper part of the **OS Monitoring** page, different metric types, such as CPU, memory, and disk metrics are displayed.

      You can view the monitoring data curves of different metrics. By default, raw metric data is displayed if you select **1h**, **3h**, **12h**, or **1d**. For **Last 7d** and longer time ranges, aggregated data is displayed.

   -  Cloud Eye provides the **Auto Refresh** function at 30-second intervals.

   -  Select the **Select Date for Comparison** check box and select a date to compare the monitoring data of the current date with that of the specified date on a graph.

#. Hover your mouse over a graph. In the upper right corner, click |image1| to enlarge the graph for viewing detailed data.

   In the upper right corner, you can see the following default monitoring periods: **1h**, **3h**, **12h**, **1d**, **7d**, and **30d**. You can also customize a time range (up to six months).

#. In the upper left corner of the graph, locate **Period** and configure the rollup method.

   -  If you select **1h**, **3h**, **12h**, or **1d**, raw data is displayed by default.
   -  If you select **7d** or **30d**, aggregated data is displayed by default.

   -  After clicking the zoom in icon in the upper right of an enlarged graph, you can drag the mouse to customize a time range.

.. |image1| image:: /_static/images/en-us_image_0000002236842869.png
