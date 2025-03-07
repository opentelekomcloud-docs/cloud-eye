:original_name: en-us_topic_0000001374986910.html

.. _en-us_topic_0000001374986910:

Viewing Details of an Alarm Rule
================================

Procedure
---------

#. Log in to the management console.

#. In the upper left corner, select a region and project.

#. Click **Service List** in the upper left corner and select **Cloud Eye**.

#. Choose **Alarm Management** > **Alarm Rules**.

#. On the displayed page, click the name of the alarm rule to be viewed.


   .. figure:: /_static/images/en-us_image_0000001425588773.png
      :alt: **Figure 1** Alarm rule details

      **Figure 1** Alarm rule details

   .. table:: **Table 1** Basic information about metric alarms

      +-------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                     | Description                                                                                                                                    |
      +===============================+================================================================================================================================================+
      | Name                          | Specifies the alarm rule name.                                                                                                                 |
      +-------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------+
      | Status                        | Specifies whether the alarm rule is enabled or disabled.                                                                                       |
      +-------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------+
      | Alarm Type                    | Specifies the alarm type to which the alarm rule applies.                                                                                      |
      +-------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------+
      | Description                   | (Optional) Provides supplementary information about the alarm rule.                                                                            |
      +-------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------+
      | Resource Type                 | Specifies the type of the resource the alarm rule is created for.                                                                              |
      +-------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------+
      | Dimension                     | Specifies the metric dimension of the selected resource type.                                                                                  |
      +-------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------+
      | (Optional) Enterprise Project | Specifies the enterprise project that the alarm rule belongs to. Only users with the enterprise project permissions can manage the alarm rule. |
      +-------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------+
      | Last Modified                 | Specifies the time when the alarm rule was last modified.                                                                                      |
      +-------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------+

   .. table:: **Table 2** Basic information about event alarms

      +-------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                     | Description                                                                                                                                    |
      +===============================+================================================================================================================================================+
      | Name                          | Specifies the alarm rule name.                                                                                                                 |
      +-------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------+
      | Status                        | Specifies whether the alarm rule is enabled or disabled.                                                                                       |
      +-------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------+
      | Alarm Type                    | Specifies the alarm type that the alarm rule applies to.                                                                                       |
      +-------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------+
      | Description                   | (Optional) Provides supplementary information about the alarm rule.                                                                            |
      +-------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------+
      | Event Type                    | Specifies the event type, which can be **System event** or **Custom event**.                                                                   |
      +-------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------+
      | Event Source                  | Specifies the service the event is generated for.                                                                                              |
      +-------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------+
      | (Optional) Enterprise Project | Specifies the enterprise project that the alarm rule belongs to. Only users with the enterprise project permissions can manage the alarm rule. |
      +-------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------+
      | Last Modified                 | Specifies the time when the alarm rule was last modified.                                                                                      |
      +-------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------+

   .. table:: **Table 3** Monitored Object

      +--------------------+--------------------------------------------------------------------------+
      | Parameter          | Description                                                              |
      +====================+==========================================================================+
      | Resource Name      | Specifies the resource name.                                             |
      +--------------------+--------------------------------------------------------------------------+
      | ID                 | Specifies the resource ID.                                               |
      +--------------------+--------------------------------------------------------------------------+
      | Last Status Update | Specifies the time when the resource alarm is last generated or cleared. |
      +--------------------+--------------------------------------------------------------------------+

   .. note::

      The parameters in the table are displayed only when a specific resource is monitored. If all resources are monitored, the parameters in the table are not displayed.

   .. table:: **Table 4** Alarm Policy

      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                                            |
      +===================================+========================================================================================================================================+
      | Alarm Policy                      | Specifies the policy for triggering an alarm.                                                                                          |
      |                                   |                                                                                                                                        |
      |                                   | For example, an alarm is triggered if the average value of the monitored metric is 80% or more for three consecutive 5-minute periods. |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------+
      | Alarm Severity                    | Specifies the alarm severity, which can be **Critical**, **Major**, **Minor**, or **Informational**.                                   |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------+

   .. table:: **Table 5** Alarm Notifications

      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                                  |
      +===================================+==============================================================================================================================+
      | Notification Group/Topic          | Specifies the name of the topic(s) and/or the Account Contact to which the alarm notification is to be sent.                 |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------+
      | Trigger Condition                 | Specifies the condition for triggering an alarm notification. The options are **Generated alarm** and **Cleared alarm**.     |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------+
      | Notification Window               | Cloud Eye sends notifications only within the notification window specified in the alarm rule.                               |
      |                                   |                                                                                                                              |
      |                                   | For example, if the notification window is set to **00:00-8:00**, Cloud Eye will only send notifications from 00:00 to 8:00. |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------+
