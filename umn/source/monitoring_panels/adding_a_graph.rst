:original_name: ces_01_0012.html

.. _ces_01_0012:

Adding a Graph
==============

After you create a panel, you can add graphs to the panel to monitor cloud services. Each panel supports up to 24 graphs.

You can add up to 20 metrics to one graph. Monitoring comparison between different services, dimensions, and metrics is supported.

Procedure
---------

#. Log in to the management console.
#. In the upper left corner, select a region and project.
#. Click **Service List** in the upper left corner, and select **Cloud Eye**.

4. Choose **Dashboard** > **Monitoring Panels**, switch to the desired panel, and click **Add Graph**.

   The **Add Graph** dialog box is displayed.

5. Set parameters based on :ref:`Table 1 <ces_01_0012__table49303610201913>`.

   .. _ces_01_0012__table49303610201913:

   .. table:: **Table 1** Parameters

      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                                                          |
      +===================================+======================================================================================================================================================+
      | Title                             | Specifies the title of the graph to be added. Only letters, digits, underscores (_), and hyphens (-) are allowed. Enter a maximum of 128 characters. |
      |                                   |                                                                                                                                                      |
      |                                   | Example value: **widget-axaj**                                                                                                                       |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Resource Type                     | Specifies the type of the resource to be monitored.                                                                                                  |
      |                                   |                                                                                                                                                      |
      |                                   | Example value: **Elastic Cloud Server**                                                                                                              |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Dimension                         | Specifies the metric dimension.                                                                                                                      |
      |                                   |                                                                                                                                                      |
      |                                   | Example value: **ECSs**                                                                                                                              |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Monitored Object                  | Specifies the monitored objects of the metric.                                                                                                       |
      |                                   |                                                                                                                                                      |
      |                                   | You can select a maximum of 20 monitored objects at a time.                                                                                          |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Metric                            | Specifies the metric name.                                                                                                                           |
      |                                   |                                                                                                                                                      |
      |                                   | Example value: **CPU Usage**                                                                                                                         |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------+

6. Click **OK**.

   On the selected panel, you can view the trends of the new graph. If you hover your mouse on the graph and click |image1|, you can view detailed metric data comparison.

.. |image1| image:: /_static/images/en-us_image_0239514208.png
