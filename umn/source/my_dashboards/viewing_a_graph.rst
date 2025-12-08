:original_name: ces_01_0230.html

.. _ces_01_0230:

Viewing a Graph
===============

After adding a graph, you can view monitoring data in a default or custom time range.

Procedure
---------

#. Log in to the management console.
#. In the upper left corner, select a region and project.
#. Choose **Service List** > **Cloud Eye**.

4. In the navigation pane, choose **My Dashboards**.

5. Click the name of the dashboard you created and view all graphs on it.

   .. note::

      -  You can drag a graph to adjust its display sequence or modify how many graphs appear per row as needed.
      -  You can also click **Full Screen** to view the graphs in full-screen mode. For details, see :ref:`Using the Full Screen <ces_01_0230__en-us_topic_0000001735744197_en-us_topic_0000001688462813_en-us_topic_0000001525332094_en-us_topic_0084572324_section4272101412197>`.
      -  You can configure the refresh interval for graphs on the dashboard. The default option is **Never refresh**.
      -  You can click the unit above the Y-axis on the graph to switch the metric unit if supported.

6. On the monitoring graph page, click |image1| or select an auto refresh interval to refresh the graph.


   .. figure:: /_static/images/en-us_image_0000002418960597.png
      :alt: **Figure 1** Refreshing a graph

      **Figure 1** Refreshing a graph

7. Hover your mouse over a graph. In the upper right corner, click |image2| to view monitoring details. You can select a default or custom time range for viewing metrics of a cloud service. In the search box, select filters and then the monitored objects to be displayed. Select the refresh interval and aggregation method to display metrics.


   .. figure:: /_static/images/en-us_image_0000002418825513.png
      :alt: **Figure 2** Viewing monitoring details in a line chart

      **Figure 2** Viewing monitoring details in a line chart

   By default, raw metric data is displayed if **Last 1h**, **Last 3h**, or **Last 12h** is selected. For **Last 1d**, **Last 7d**, and longer time ranges, aggregated data is displayed by default.

   On the monitoring details page of the line chart, you can perform the operations described in :ref:`Customizing a Period to View Metrics <ces_01_0230__en-us_topic_0000001735744197_en-us_topic_0000001688462813_en-us_topic_0000001525332094_en-us_topic_0084572324_section116610490136>` or :ref:`Selecting Monitored Objects and Viewing Metrics <ces_01_0230__en-us_topic_0000001735744197_en-us_topic_0000001688462813_en-us_topic_0000001525332094_en-us_topic_0084572324_section737194710148>`.


   .. figure:: /_static/images/en-us_image_0000002318778793.png
      :alt: **Figure 3** Viewing graphs

      **Figure 3** Viewing graphs

.. _ces_01_0230__en-us_topic_0000001735744197_en-us_topic_0000001688462813_en-us_topic_0000001525332094_en-us_topic_0084572324_section4272101412197:

Using the Full Screen
---------------------

The full screen displays metric data more clearly.

-  To enter the full screen, select a dashboard, click its name, and click **Full Screen** in the upper left corner.

-  To exit the full screen, press **Esc**.


   .. figure:: /_static/images/en-us_image_0000001882024953.png
      :alt: **Figure 4** Full screen

      **Figure 4** Full screen

.. _ces_01_0230__en-us_topic_0000001735744197_en-us_topic_0000001688462813_en-us_topic_0000001525332094_en-us_topic_0084572324_section116610490136:

Customizing a Period to View Metrics
------------------------------------

By default, you can select **Last 1h**, **Last 3h**, **Last 12h**, **Last 1d**, or **Last 7d**. In a line chart, if you want to view metrics in the last two hours or a custom period, you can drag the mouse to select the time range you want to view on the X-axis.

-  To view metric details in a custom time range, click the second icon on the right, as shown in :ref:`Figure 5 <ces_01_0230__en-us_topic_0000001735744197_fig62017141117>`. Drag the mouse to select a customized time range. The system displays the monitoring data in the selected time range.

   .. _ces_01_0230__en-us_topic_0000001735744197_fig62017141117:

   .. figure:: /_static/images/en-us_image_0000001882025765.png
      :alt: **Figure 5** Customizing a time range

      **Figure 5** Customizing a time range

-  To stop viewing the metric details within a custom time range, click the third icon on the right, as shown in :ref:`Figure 6 <ces_01_0230__en-us_topic_0000001735744197_fig375064810112>`. The system will reset the time range.

   .. _ces_01_0230__en-us_topic_0000001735744197_fig375064810112:

   .. figure:: /_static/images/en-us_image_0000001835186776.png
      :alt: **Figure 6** Going back to the default time range

      **Figure 6** Going back to the default time range

.. _ces_01_0230__en-us_topic_0000001735744197_en-us_topic_0000001688462813_en-us_topic_0000001525332094_en-us_topic_0084572324_section737194710148:

Selecting Monitored Objects and Viewing Metrics
-----------------------------------------------

In a line chart, you can compare the same metric of multiple resources on one graph. When there are a large number of resources, you can select only some resources and compare their metrics.

-  Select monitored objects. By default, resources are sorted by **Name**, as shown in :ref:`Figure 7 <ces_01_0230__en-us_topic_0000001735744197_fig08964201964>`. You can also select resources by **ID**, **Metric Name**, or **Resource Type**. The system displays the data of selected resources and hides that of other resources.

   .. _ces_01_0230__en-us_topic_0000001735744197_fig08964201964:

   .. figure:: /_static/images/en-us_image_0000001881907489.png
      :alt: **Figure 7** Selecting monitored objects

      **Figure 7** Selecting monitored objects

-  To clear the monitored resources you have selected, click |image3|.


   .. figure:: /_static/images/en-us_image_0000001881907649.png
      :alt: **Figure 8** Clearing monitored objects

      **Figure 8** Clearing monitored objects

-  Click |image4| to display the monitored objects. Click |image5| to customize columns to be displayed in the list below the graph.


   .. figure:: /_static/images/en-us_image_0000002418840789.png
      :alt: **Figure 9** Viewing monitoring items

      **Figure 9** Viewing monitoring items

-  Alternatively, click the fourth icon |image6| on the right of the graph and select the instance range to be viewed. Then, the system automatically displays the data of the selected monitored objects and hides the monitoring data of other monitored objects.


   .. figure:: /_static/images/en-us_image_0000002448236893.png
      :alt: **Figure 10** Select Metrics

      **Figure 10** Select Metrics

-  Click the fifth icon |image7| on the right of the graph to reset the selected instance range. The system will display data of all monitored objects.


   .. figure:: /_static/images/en-us_image_0000002414598814.png
      :alt: **Figure 11** Reset Metrics

      **Figure 11** Reset Metrics

-  Click the sixth icon |image8| on the right of the graph to reset the selected custom time range and instance range.


   .. figure:: /_static/images/en-us_image_0000002414759378.png
      :alt: **Figure 12** Reset

      **Figure 12** Reset

.. |image1| image:: /_static/images/en-us_image_0000002418840729.png
.. |image2| image:: /_static/images/en-us_image_0000002178756434.png
.. |image3| image:: /_static/images/en-us_image_0000001696202802.png
.. |image4| image:: /_static/images/en-us_image_0000002385201528.png
.. |image5| image:: /_static/images/en-us_image_0000002418960629.png
.. |image6| image:: /_static/images/en-us_image_0000002448236001.png
.. |image7| image:: /_static/images/en-us_image_0000002448237989.png
.. |image8| image:: /_static/images/en-us_image_0000002414599170.png
