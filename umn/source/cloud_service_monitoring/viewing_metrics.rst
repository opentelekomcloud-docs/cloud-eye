:original_name: ces_01_0110.html

.. _ces_01_0110:

Viewing Metrics
===============

#. Log in to the management console.

#. In the upper left corner, select a region and project.

#. Click **Service List** in the upper left corner and select **Cloud Eye**.

#. In the navigation pane on the left, choose **Cloud Service Monitoring** and select the cloud service whose resources you want to view.

#. Locate the cloud service resource and click **View Metric** in the **Operation** column.

   .. note::

      -  You can sort graphs by dragging them based on service requirements.
      -  If **Auto Refresh** is enabled, data is automatically refreshed every minute.
      -  Some cloud services allow you to view resource details. You can click **View Resource Details** in the upper part of the page to view details about monitored resources.
      -  You can search for a specific metric in the search box.
      -  For details about how to export monitoring data, see :ref:`How Can I Export Collected Data? <ces_faq_0012>`

#. Near the top right corner of the page, click **Select Metric**.

   The **Select Metric** dialog box is displayed.

   Select at least one metric. Drag and drop the selected metrics at desired locations to sort them. This helps you customize metrics to be viewed.

#. Hover your mouse over a graph. In the upper right corner, click |image1| to view monitoring details on an enlarged graph. Select a time period or customize a time range to view the metric in a specific monitoring interval.

   .. note::

      -  If you select **1h**, **3h**, **12h**, or **1d**, raw data is displayed by default. You can set **Period** and **Statistic** to change the aggregation period of monitoring data. For details about aggregation periods, see :ref:`What Is Aggregation? <ces_faq_0009>`
      -  If you select **7d** or **30d**, aggregated data is displayed by default. You can set **Period** and **Statistic** to change the aggregation period of monitoring data.

#. In the upper right corner of the monitoring graph, click |image2| to create alarm rules for the metric. For details about the parameters, see :ref:`Creating an Alarm Rule <en-us_topic_0084572213>`.

.. |image1| image:: /_static/images/en-us_image_0000001220595446.png
.. |image2| image:: /_static/images/en-us_image_0000001264836141.png
