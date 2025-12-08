:original_name: ces_01_0012-A.html

.. _ces_01_0012-A:

Adding a Graph
==============

If you are using multiple cloud services, you can add their metrics to the same dashboard by creating graphs. This way, you can view global monitoring data of these cloud services.

In the same graph, you can compare data across services, dimensions, and metrics.

Constraints
-----------

-  You can add a maximum of 50 graphs to a dashboard.
-  You can add a maximum of 50 monitoring metrics to a line graph. If 10 monitored objects are selected and 5 metrics are selected, 50 monitoring items will be created.

Prerequisites
-------------

You have created a dashboard by referring to :ref:`Creating a Dashboard <ces_01_0011-a>`.

Procedure
---------

#. Log in to the management console.
#. In the upper left corner, select a region and project.
#. Choose **Service List** > **Cloud Eye**.

4. Choose **My Dashboards** and click the name of the dashboard to which you want to add a graph. On the displayed page, click **Add Graph**. You can select **Line Chart** or **Bar Chart** to display the graph.

   .. note::

      -  Line Chart: The chart visualizes changes and peak values of metrics over time.
      -  Bar Chart: The chart visualizes the metric data of top-ranked resources of the same type.

5. On the **Add Graph** page, set parameters as prompted.

   .. table:: **Table 1** Parameters for adding a graph

      +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                                                                                                                                                                       |
      +===================================+===================================================================================================================================================================================================================================================================+
      | Metric Display                    | -  For a line graph, you can select **One graph for a single metric** or **One graph for multiple metrics**.                                                                                                                                                      |
      |                                   | -  For a bar chart, only **One graph for a single metric** is available.                                                                                                                                                                                          |
      +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Monitoring Scope                  | Select the target resources and metrics. If you selected a bar chart, all resources are selected by default.                                                                                                                                                      |
      |                                   |                                                                                                                                                                                                                                                                   |
      |                                   | .. note::                                                                                                                                                                                                                                                         |
      |                                   |                                                                                                                                                                                                                                                                   |
      |                                   |    If an instance does not report monitoring data for a specified period, the instance will not appear in the resource list. For details about the data retention period, see :ref:`Cloud Services Displayed in the Cloud Service Monitoring List <ces_01_0160>`. |
      +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Quantity                          | When creating a bar chart, you can configure how many resources to show (3 <= *N* <= 10). Metric data of those resources is displayed, in an ascending or descending order.                                                                                       |
      +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Advanced Settings                 | You can configure the name, threshold, and legend name of a graph.                                                                                                                                                                                                |
      +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

6. Click **Save**.
