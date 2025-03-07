:original_name: ces_01_0042.html

.. _ces_01_0042:

Creating an Alarm Rule to Monitor a Server
==========================================

Scenarios
---------

This topic describes how to create an alarm rule for an ECS or BMS.

Procedure
---------

#. Log in to the management console.

#. In the upper left corner, select a region and project.

#. Click **Service List** in the upper left corner and select **Cloud Eye**.

#. In the navigation pane on the left, choose **Server Monitoring**.

#. Locate the target ECS or BMS, and click **Create Alarm Rule** in the **Operation** column. When you create an alarm rule, related metric parameters will be preset.

#. On the **Create Alarm Rule** page, configure the parameters.

   For details about the parameters, see :ref:`Table 1 <en-us_topic_0084572213__table17694105411317>` to :ref:`Table 4 <en-us_topic_0084572213__table54161352427>`.

   Some parameters have been preset. For details, see :ref:`Table 1 <ces_01_0042__ces_01_0042-a_table1838512257346>`.

   .. _ces_01_0042__ces_01_0042-a_table1838512257346:

   .. table:: **Table 1** Preset parameters for server monitoring alarms

      +------------------+-----------------------------------------------------------------------------+
      | Parameter        | Description                                                                 |
      +==================+=============================================================================+
      | Alarm Type       | Alarm type that the alarm rule applies to. The default value is **Metric**. |
      +------------------+-----------------------------------------------------------------------------+
      | Resource Type    | Specifies the name of the monitored service.                                |
      +------------------+-----------------------------------------------------------------------------+
      | Dimension        | Specifies the metric dimension.                                             |
      +------------------+-----------------------------------------------------------------------------+
      | Monitoring Scope | Specifies the monitoring scope the alarm rule applies to.                   |
      +------------------+-----------------------------------------------------------------------------+
      | Monitored Object | Specifies the monitored object, that is, the name of the selected resource. |
      +------------------+-----------------------------------------------------------------------------+

After the alarm rule is created, if the metric data reaches the specified threshold, Cloud Eye immediately informs you that an exception has occurred.
