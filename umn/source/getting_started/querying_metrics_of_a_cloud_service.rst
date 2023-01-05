:original_name: en-us_topic_0018121651.html

.. _en-us_topic_0018121651:

Querying Metrics of a Cloud Service
===================================

Cloud Eye provides multiple built-in metrics based on the characteristics of each service. After you enable one cloud service on the cloud platform, Cloud Eye automatically associates its built-in metrics. You can track the cloud service status by monitoring these metrics.

This topic describes how to view monitoring data of a cloud service resource.

Procedure
---------

#. Log in to the management console.

2. In the upper left corner, select a region and project.

3. Click **Service List** in the upper left corner, and select **Cloud Eye**.

4. In the navigation pane on the left, choose **Cloud Service Monitoring**, and select a cloud service.

   The cloud service page is displayed.

5. Locate the row that contains the cloud service resource you want to monitor and click **View Metric** in the **Operation** column.

   The detailed monitoring page is displayed.

   You can view graphs based on raw data collected in the last **1h**, **3h**, **12h**, **1d**, and **7d**. In the upper right corner of the graph, the maximum and minimum values of the metric in the corresponding time periods are dynamically displayed. You can also enable **Auto Refresh** to view the real-time data refreshed every minute.

   .. note::

      -  Metric units can be changed between byte or byte/s and GB or GB/s on graphs. When you are changing the unit, if the maximum value of a metric is smaller than 10^ (-5), both the maximum value and the minimum value of this metric are 0. In addition, all data displayed on the graph is 0.
      -  If **Auto Refresh** is enabled, data is automatically refreshed every minute.
      -  You can search for a specific metric in the search box.
      -  Some cloud services allow you to view resource details. You can click **View Resource Details** in the upper part of the page to view details about monitored resources.

6. Near the top right corner of the page, click **Select Metric**.

   The **Select Metric** dialog box is displayed.

   Select at least one metric. Drag and drop the selected metrics at desired locations to sort them. This helps you customize metrics to be viewed.

7. Hover your mouse over a graph and click |image1| in the upper right corner.

   An enlarged graph of the metric is displayed, on which you can view the metric monitoring details for longer time ranges. In the upper left corner, you can see six default monitoring periods: **1h**, **3h**, **12h**, **1d**, **7d**, and **30d**. You can also view historical monitoring data for any period during the last six months by customizing the monitoring period in the upper right corner of the graph.

   .. note::

      -  If you select **1h**, **3h**, **12h**, or **1d**, raw data is displayed by default. Near the top left corner of the page, you can click **Settings** to change the rollup period of the monitoring data. For details about the rollup period, see :ref:`What Is Rollup? <ces_faq_0009>`.
      -  If you select **7d** or **30d**, aggregated data is displayed by default. Near the top left corner of the page, you can click **Settings** to change the rollup period of the monitoring data.

8. In the upper right corner of the monitoring view, click |image2| to create an alarm rule for a metric. For details about the parameters, see :ref:`Creating an Alarm Rule for a Specific Metric <ces_01_0074>`.

9. To export data, click **Export Data** on the **Cloud Service Monitoring** page, configure parameters as prompted, and click **Export**. For details, see :ref:`How Can I Export Collected Data? <ces_faq_0012>`

.. |image1| image:: /_static/images/en-us_image_0000001089785046.png
.. |image2| image:: /_static/images/en-us_image_0000001220441482.png
