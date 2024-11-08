:original_name: ces_01_0012.html

.. _ces_01_0012:

Adding a Graph
==============

After you create a dashboard, you can add graphs to the dashboard to monitor cloud services. Each dashboard supports up to 50 graphs.

You can add up to 50 metrics to one graph. Monitoring comparison between different services, dimensions, and metrics is supported.

Procedure
---------

#. Log in to the management console.
#. In the upper left corner, select a region and project.
#. Click **Service List** in the upper left corner and select **Cloud Eye**.

4. In the navigation pane on the left, choose **Dashboard**. Switch to the dashboard to which you want to add a graph, and click **Add Graph**.

   The **Add Graph** dialog box is displayed.

5. Configure parameters based on :ref:`Table 1 <ces_01_0012__table49303610201913>`.

   .. _ces_01_0012__table49303610201913:

   .. table:: **Table 1** Parameters

      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                                                                      |
      +===================================+==================================================================================================================================================================+
      | Title                             | Specifies the title of the graph to be added. Only letters, digits, underscores (_), and hyphens (-) are allowed. Enter a maximum of 128 characters.             |
      |                                   |                                                                                                                                                                  |
      |                                   | Example value: **widget-axaj**                                                                                                                                   |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | (Optional) Enterprise Project     | Specifies the enterprise project associated with the graph. You can view the monitoring data on the graph only when you have the enterprise project permissions. |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Resource Type                     | Specifies the type of the resource to be monitored.                                                                                                              |
      |                                   |                                                                                                                                                                  |
      |                                   | Example value: **Elastic Cloud Server**                                                                                                                          |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Dimension                         | Specifies the metric dimension.                                                                                                                                  |
      |                                   |                                                                                                                                                                  |
      |                                   | Example value: **ECSs**                                                                                                                                          |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Monitored Object                  | Specifies the monitored object. You can add up to 50 monitored objects.                                                                                          |
      |                                   |                                                                                                                                                                  |
      |                                   | You can select multiple monitored objects at a time.                                                                                                             |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Metric                            | Specifies the metric name.                                                                                                                                       |
      |                                   |                                                                                                                                                                  |
      |                                   | Example value: **CPU Usage**                                                                                                                                     |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+

6. Click **OK**.

   On the selected dashboard, you can view the metric trends on the new graph. If you hover your mouse on the graph and click |image1|, you can view detailed metric data comparison in an enlarged graph.

.. |image1| image:: /_static/images/en-us_image_0239514208.png
