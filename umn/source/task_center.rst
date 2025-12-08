:original_name: ces_01_0108.html

.. _ces_01_0108:

Task Center
===========

On the **Task Center** page, you can export data including monitoring data and alarm records. You can go to the **Alarm Records** and **Server Monitoring** (**Elastic Cloud Server**) pages to create an export task. After the export task is submitted, you can view the progress and download the file on the **Task Center** page.

.. important::

   The export tasks on the **Monitoring Data Export Tasks** and **Alarm Record Export Tasks** tabs will be cleared seven days after they are created.

.. _ces_01_0108__section10634348201413:

Exporting Monitoring Data
-------------------------

#. Log in to the management console.

#. Choose **Service List** > **Cloud Eye**.

   -  Export ECS or BMS monitoring data. In the navigation pane, choose **Server Monitoring** > **Elastic Cloud Server**.
   -  Export cloud service monitoring data. In the navigation pane, choose **Cloud Service Monitoring**.

#. Click **Export Data** in the upper right corner.


   .. figure:: /_static/images/en-us_image_0000001693741013.png
      :alt: **Figure 1** Exporting data

      **Figure 1** Exporting data

   .. note::

      The export feature of the new edition only works with certain cloud services, while others still require the older edition. Future updates will extend this compatibility to all cloud services. This enhanced feature allows you to export more monitoring data without restrictions. Once you submit an export task, you can manage it in the task center.

      For services that support the new export feature, the **Export Data** dialog box of the new edition is displayed by default. To return to the earlier version, click **Earlier Edition**. :ref:`Figure 2 <ces_01_0108__fig1388275019294>` shows the earlier edition of the **Export Data** dialog box. In the earlier edition, the data export task is not displayed on the **Task Center** page. Data can be directly downloaded on the current page.

      .. _ces_01_0108__fig1388275019294:

      .. figure:: /_static/images/en-us_image_0000001693820629.png
         :alt: **Figure 2** Exporting data (earlier edition)

         **Figure 2** Exporting data (earlier edition)

#. In the **Export Data** dialog box, set parameters.

   .. table:: **Table 1** Parameters for exporting data (new edition)

      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                                                                                                                               |
      +===================================+===========================================================================================================================================================================================================================+
      | Task Name                         | Name of an export task.                                                                                                                                                                                                   |
      |                                   |                                                                                                                                                                                                                           |
      |                                   | The value allows 1 to 32 characters and can only contain letters, digits, hyphens (-), and underscores (_).                                                                                                               |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Statistic                         | There are two modes: **Aggregated data** and **Raw data**.                                                                                                                                                                |
      |                                   |                                                                                                                                                                                                                           |
      |                                   | -  **Aggregated data**: Data can be exported after being aggregated using the maximum value, minimum value, average value, or sum value.                                                                                  |
      |                                   | -  **Raw data**: The original data is exported.                                                                                                                                                                           |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Time Range                        | Select the time range for the data to be exported.                                                                                                                                                                        |
      |                                   |                                                                                                                                                                                                                           |
      |                                   | -  Data of a maximum of the last 90 days can be exported for an aggregate value.                                                                                                                                          |
      |                                   | -  Raw data from the last 48 hours is available for export.                                                                                                                                                               |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Aggregated By                     | This parameter is mandatory when **Statistic** is set to **Aggregated data**.                                                                                                                                             |
      |                                   |                                                                                                                                                                                                                           |
      |                                   | If you select **Custom range**, data aggregated during your configured time range will be exported. If you select one of the other options, data will be aggregated based on your selected granularity and then exported. |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Monitoring Item                   | -  **Resource Type**: The selected cloud service is used by default. You do not need to set this parameter.                                                                                                               |
      |                                   | -  **Dimension**: Specify the dimension name of the metric to be exported.                                                                                                                                                |
      |                                   | -  **Monitored Object**: You can select **All Resources** or **Specific resources**.                                                                                                                                      |
      |                                   | -  **Metric**: Specify one or more metrics to be exported.                                                                                                                                                                |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

   .. table:: **Table 2** Parameters for exporting data (earlier edition)

      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                                                                                                       |
      +===================================+===================================================================================================================================================================================================+
      | Time Range                        | Select the time range for the data to be exported.                                                                                                                                                |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Period                            | Select how often you want to export the monitoring data.                                                                                                                                          |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Statistic                         | This parameter is required when **Period** is set to 5 minutes, 20 minutes, 1 hour, 4 hours, or 2 hours. You can export the aggregated maximum value, minimum value, average value, or sum value. |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Monitoring Item                   | -  **Resource Type**: The selected cloud service is used by default. You do not need to set this parameter.                                                                                       |
      |                                   | -  **Dimension**: Specify the dimension name of the metric to be exported.                                                                                                                        |
      |                                   | -  **Monitored Object**: You can select **All Resources** or **Specific resources**.                                                                                                              |
      |                                   | -  **Metric**: Specify one or more metrics to be exported.                                                                                                                                        |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

#. After the configuration is complete, click **Export**.

   After the export task is submitted, choose **Task Center**. On the **Monitoring Data Export Tasks** tab, view and download task.

#. In the navigation pane, choose **Task Center**.

#. On the **Monitoring Data Export Task** tab page, view or delete export tasks, and download their export results.

   -  Filtering export tasks: In the search box above the list, filter export tasks by task name, resource type, statistical method, time range, status, or creation time.
   -  Viewing details of multiple export tasks in batches: Select multiple export tasks from the list and click the small arrow in the bottom-right corner to view the monitoring details of multiple events in batches.
   -  Downloading the export results: Locate the target export task and click **Download** in the **Operation** column.
   -  Deleting one or more export tasks:

      -  Locate an export task and click **Delete** in the **Operation** column to delete it.
      -  Select desired export tasks and click **Delete** above the list to delete them in batches.


   .. figure:: /_static/images/en-us_image_0000002473248950.png
      :alt: **Figure 3** Viewing monitoring data export tasks

      **Figure 3** Viewing monitoring data export tasks

Exporting Alarm Records
-----------------------

#. Log in to the management console.

#. Choose **Service List** > **Cloud Eye**.

#. Choose **Alarm Management** > **Alarm Records**.

#. On the **Alarm Records** page, click **Export**.

   .. note::

      You can export all alarm records or alarm records filtered by status, alarm severity, alarm rule name, resource type, resource ID, and alarm rule ID above the alarm record list.

#. In the displayed **Export Alarm Records** dialog box, enter an export task name and click **OK**.

   The name allows 1 to 32 characters and can only contain letters, digits, hyphens (-), and underscores (_).


   .. figure:: /_static/images/en-us_image_0000001645582436.png
      :alt: **Figure 4** Entering an export task name

      **Figure 4** Entering an export task name

   After the export task is submitted, you can view and download the alarm records under the **Alarm Record Export Tasks** tab on the **Task Center** page.

#. In the navigation pane, choose **Task Center**.

#. On the **Alarm Record Export Tasks** tab page, view or delete export tasks, and download their export results.

   -  Filtering export tasks: In the search box above the export list, filter export tasks by task name, time range, filter criteria, status, or creation time.
   -  Downloading the export results: Locate the target export task and click **Download** in the **Operation** column.
   -  Deleting one or more export tasks:

      -  Locate an export task and click **Delete** in the **Operation** column to delete it.
      -  Select desired export tasks and click **Delete** above the list to delete them in batches.


   .. figure:: /_static/images/en-us_image_0000002473248828.png
      :alt: **Figure 5** Viewing alarm record export tasks

      **Figure 5** Viewing alarm record export tasks
