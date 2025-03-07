:original_name: ces_01_0088.html

.. _ces_01_0088:

Viewing Cloud Eye Logs
======================

Scenarios
---------

After CTS is enabled, CTS starts recording operations on cloud resources. The CTS management console stores the operation records of the last 7 days.

This section describes how to query or export the last seven days of operation records on the management console.

Procedure
---------

#. Log in to the management console.

#. In the upper left corner, select a region and project.

#. Click |image1| in the upper left corner and choose **Management & Deployment** > **Cloud Trace Service**. The CTS console is displayed.

#. Choose **Trace List** in the navigation pane on the left.

#. Set filters to search for your desired traces, as shown in :ref:`Figure 1 <ces_01_0088__en-us_topic_0179639644_fig139361441134311>`. The following filters are available.

   .. _ces_01_0088__en-us_topic_0179639644_fig139361441134311:

   .. figure:: /_static/images/en-us_image_0000001744598325.png
      :alt: **Figure 1** Filters

      **Figure 1** Filters

   -  **Trace Type**, **Trace Source**, **Resource Type**, and **Search By**: Select a filter from the drop-down list.

      -  If you select **Resource ID** for **Search By**, specify a resource ID.
      -  If you select **Trace name** for **Search By**, specify a trace name.
      -  If you select **Resource name** for **Search By**, specify a resource name.

   -  **Operator**: Select a user.
   -  **Trace Status**: Select **All trace statuses**, **Normal**, **Warning**, or **Incident**.
   -  Time range: Select **Last 1 hour**, **Last 1 day**, or **Last 1 week**, or specify a custom time range within the last seven days.

#. Click **Query**.

#. On the **Trace List** page, you can also export and refresh the trace list.

   -  Click **Export** to export all traces in the query result as a CSV file. The file can contain up to 5,000 records.
   -  Click |image2| to view the latest information about traces.

#. Click |image3| on the left of a trace to expand its details.


   .. figure:: /_static/images/en-us_image_0111203217.jpg
      :alt: **Figure 2** Expanding trace details

      **Figure 2** Expanding trace details

#. Click **View Trace** in the **Operation** column. On the displayed **View Trace** dialog box, view details of the trace.


   .. figure:: /_static/images/en-us_image_0111203223.png
      :alt: **Figure 3** View Trace

      **Figure 3** View Trace

.. |image1| image:: /_static/images/en-us_image_0000001696838310.png
.. |image2| image:: /_static/images/en-us_image_0000001696678850.png
.. |image3| image:: /_static/images/en-us_image_0110317533.jpg
