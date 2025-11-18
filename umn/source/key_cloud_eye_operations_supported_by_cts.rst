:original_name: ces_01_0087.html

.. _ces_01_0087:

Key Cloud Eye Operations Supported by CTS
=========================================

With CTS, you can record operations associated with Cloud Eye for future query, audit, and backtracking.

Prerequisites
-------------

CTS has been enabled.

Key Cloud Eye Operations
------------------------

.. table:: **Table 1** Cloud Eye operations that can be recorded by CTS

   +----------------------------------------------------------------------+-----------------+----------------------------------+
   | Operation                                                            | Resource Type   | Event Name                       |
   +======================================================================+=================+==================================+
   | Creating an alarm rule                                               | alarm_rule      | createAlarmRule                  |
   +----------------------------------------------------------------------+-----------------+----------------------------------+
   | Deleting an alarm rule                                               | alarm_rule      | deleteAlarmRule                  |
   +----------------------------------------------------------------------+-----------------+----------------------------------+
   | Disabling an alarm rule                                              | alarm_rule      | disableAlarmRule                 |
   +----------------------------------------------------------------------+-----------------+----------------------------------+
   | Enabling an alarm rule                                               | alarm_rule      | enableAlarmRule                  |
   +----------------------------------------------------------------------+-----------------+----------------------------------+
   | Modifying an alarm rule                                              | alarm_rule      | updateAlarmRule                  |
   +----------------------------------------------------------------------+-----------------+----------------------------------+
   | Creating a custom template                                           | alarm_template  | createAlarmTemplate              |
   +----------------------------------------------------------------------+-----------------+----------------------------------+
   | Deleting a custom template                                           | alarm_template  | deleteAlarmTemplate              |
   +----------------------------------------------------------------------+-----------------+----------------------------------+
   | Modifying a custom template                                          | alarm_template  | updateAlarmTemplate              |
   +----------------------------------------------------------------------+-----------------+----------------------------------+
   | Creating a dashboard                                                 | dashboard       | createDashboard                  |
   +----------------------------------------------------------------------+-----------------+----------------------------------+
   | Deleting a dashboard                                                 | dashboard       | deleteDashboard                  |
   +----------------------------------------------------------------------+-----------------+----------------------------------+
   | Modifying a dashboard                                                | dashboard       | updateDashboard                  |
   +----------------------------------------------------------------------+-----------------+----------------------------------+
   | Enabling or disabling a Kafka data dump task                         | data_share_job  | actionDataShareJob               |
   +----------------------------------------------------------------------+-----------------+----------------------------------+
   | Creating a Kafka data dump task                                      | data_share_job  | createDataShareJob               |
   +----------------------------------------------------------------------+-----------------+----------------------------------+
   | Deleting a Kafka data dump task                                      | data_share_job  | deleteDataShareJob               |
   +----------------------------------------------------------------------+-----------------+----------------------------------+
   | Updating a Kafka data dump task                                      | data_share_job  | updateDataShareJob               |
   +----------------------------------------------------------------------+-----------------+----------------------------------+
   | Sorting metrics                                                      | metric          | createMetricSort                 |
   +----------------------------------------------------------------------+-----------------+----------------------------------+
   | Exporting monitoring data                                            | metrics_job     | createMetricsJobs                |
   +----------------------------------------------------------------------+-----------------+----------------------------------+
   | Batch enabling or disabling alarm policies for one-click monitoring  | one_click_alarm | batchActionOneClickAlarmPolicy   |
   +----------------------------------------------------------------------+-----------------+----------------------------------+
   | Batch disabling one-click monitoring                                 | one_click_alarm | batchDeleteOneClickAlarm         |
   +----------------------------------------------------------------------+-----------------+----------------------------------+
   | Enabling or disabling one-click monitoring                           | one_click_alarm | updateOneClickAlarm              |
   +----------------------------------------------------------------------+-----------------+----------------------------------+
   | Updating alarm notifications for one service in one-click monitoring | one_click_alarm | updateOneClickAlarmNotifications |
   +----------------------------------------------------------------------+-----------------+----------------------------------+
   | Batch deleting data export tasks                                     | report_job      | batchDeleteReportJobs            |
   +----------------------------------------------------------------------+-----------------+----------------------------------+
   | Creating a data export task                                          | report_job      | createReportJobs                 |
   +----------------------------------------------------------------------+-----------------+----------------------------------+
   | Downloading an export report                                         | report_job      | downloadReportJobs               |
   +----------------------------------------------------------------------+-----------------+----------------------------------+
   | Clearing tenant resources                                            | resource_clear  | clearAllResource                 |
   +----------------------------------------------------------------------+-----------------+----------------------------------+
   | Creating a resource group                                            | resource_group  | createResourceGroup              |
   +----------------------------------------------------------------------+-----------------+----------------------------------+
   | Updating a resource group                                            | resource_group  | deleteResourceGroup              |
   +----------------------------------------------------------------------+-----------------+----------------------------------+
   | Deleting a resource group                                            | resource_group  | updateResourceGroup              |
   +----------------------------------------------------------------------+-----------------+----------------------------------+
   | Creating a graph                                                     | widget          | createWidget                     |
   +----------------------------------------------------------------------+-----------------+----------------------------------+
   | Updating a graph                                                     | widget          | deleteWidget                     |
   +----------------------------------------------------------------------+-----------------+----------------------------------+
   | Deleting a graph                                                     | widget          | updateWidget                     |
   +----------------------------------------------------------------------+-----------------+----------------------------------+

Viewing Audit Logs
------------------

For details, see `Querying Real-Time Traces <https://docs.otc.t-systems.com/en-us/usermanual/cts/en-us_topic_0030598499.html>`__.
