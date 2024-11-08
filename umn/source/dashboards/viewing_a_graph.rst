:original_name: ces_01_0013.html

.. _ces_01_0013:

Viewing a Graph
===============

After you add a graph, you can view the metric trends on the **Dashboards** page. The system provides you both default and customizable time ranges to view trends from last month. This topic describes how to view trends for a longer time range.

Procedure
---------

#. Log in to the management console.

#. In the upper left corner, select a region and project.

#. Click **Service List** in the upper left corner and select **Cloud Eye**.

#. In the navigation pane on the left, choose **Dashboard**.

   You can view all graphs on the current dashboard.

   .. note::

      -  You can sort graphs by dragging them.
      -  You can click **1h**, **3h**, **12h**, **1d**, or **7d** in the upper part of the graphs to change the monitoring period of all graphs on the dashboard. By default, raw metric data is displayed for **1h** and **3h**, and the aggregated metric data is displayed for other periods. You can also customize a time range for all graphs.
      -  You can also go to the full screen to view the graphs. For details, see :ref:`Using the Full Screen <ces_01_0013__section4272101412197>`.

#. Hover your mouse over a graph. In the upper right corner, click |image1| to view monitoring details on an enlarged graph. Select a time period or customize a time range to view the metric in a specific monitoring interval.

   Raw metric data is displayed for **1h**, **3h**, **12h**, and **1d** by default. For **7d** and **30d**, rolled-up data is displayed by default.

   On the enlarged graph, you can :ref:`Customizing a Period to View the Graph <ces_01_0013__section116610490136>` or :ref:`Selecting Monitored Objects and Viewing Metrics <ces_01_0013__section737194710148>`.


   .. figure:: /_static/images/en-us_image_0000001644915302.png
      :alt: **Figure 1** Viewing graphs

      **Figure 1** Viewing graphs

.. _ces_01_0013__section4272101412197:

Using the Full Screen
---------------------

The full screen displays metric data more clearly.

-  To enter the full screen, click **Full Screen** in the upper right corner of the **Dashboard** page.
-  To exit the full screen, click **Exit Full Screen** in the upper left corner of the page.

.. _ces_01_0013__section116610490136:

Customizing a Period to View the Graph
--------------------------------------

By default, metrics in the last 1 hour, last 3 hours, last 12 hours, last 24 hours, and last 7 days are displayed. If you want to view metrics in the last 2 hours or a customized time period, you can drag the mouse to select the time range you want to view on the X axis.

-  To view metric details in a customized time period, click the first icon on the right. Drag the mouse to select a customized time range. The system automatically displays the monitoring data in the selected time range.


   .. figure:: /_static/images/en-us_image_0000001692960961.png
      :alt: **Figure 2** Customizing a period

      **Figure 2** Customizing a period

-  To go back to the default graph, click the third icon on the right.

.. _ces_01_0013__section737194710148:

Selecting Monitored Objects and Viewing Metrics
-----------------------------------------------

To compare the same metric of multiple resources, you can combine the metrics of the resources into a graph. When there are a large number of resources, you can drag to select monitored objects if you want to compare the metric data of only some of the resources.

-  To select a monitored object, click the second icon on the right. Drag the mouse on part of the curve of the monitored objects. Then, the system automatically displays the data of the selected monitored objects and hides the monitoring data of other monitored objects.


   .. figure:: /_static/images/en-us_image_0000001644929274.png
      :alt: **Figure 3** Selecting the object to be monitored

      **Figure 3** Selecting the object to be monitored

-  To go back to the default graph, click the third icon on the right.

   .. note::

      In the lower part of an enlarged graph, you can select a monitored object as follows: Click a resource object to hide its trend chart, and click the monitored object again to display its trend chart.

.. |image1| image:: /_static/images/en-us_image_0239514842.png
