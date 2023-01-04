:original_name: en-us_topic_0000001374986910.html

.. _en-us_topic_0000001374986910:

Viewing Details of an Alarm Rule
================================

Procedure
---------

#. Log in to the management console.

#. In the upper left corner, select a region and project.

#. Click **Service List** in the upper left corner, and select **Cloud Eye**.

#. Choose **Alarm Management** > **Alarm Rules**.

#. On the displayed page, click the name of the alarm rule to be viewed.


   .. figure:: /_static/images/en-us_image_0000001425588773.png
      :alt: **Figure 1** Alarm rule details

      **Figure 1** Alarm rule details

   .. table:: **Table 1** Basic parameters

      +---------------+------------------------------------------------------------------------------------------+
      | Parameter     | Description                                                                              |
      +===============+==========================================================================================+
      | Name          | Specifies the alarm rule name. The system generates a random name, which you can modify. |
      +---------------+------------------------------------------------------------------------------------------+
      | Status        | Specifies whether the alarm rule is enabled or disabled.                                 |
      +---------------+------------------------------------------------------------------------------------------+
      | Alarm Type    | Specifies the type of the alarm rule.                                                    |
      +---------------+------------------------------------------------------------------------------------------+
      | Description   | (Optional) Provides supplementary information about the alarm rule.                      |
      +---------------+------------------------------------------------------------------------------------------+
      | Resource Type | Specifies the type of the resource the alarm rule is created for.                        |
      +---------------+------------------------------------------------------------------------------------------+
      | Dimension     | Specifies the metric dimension of the selected resource type.                            |
      +---------------+------------------------------------------------------------------------------------------+
      | Last Modified | Specifies the time when the alarm rule was last modified.                                |
      +---------------+------------------------------------------------------------------------------------------+

   .. table:: **Table 2** Monitored objects

      +--------------------+----------------------------------------------------------------------------+
      | Parameter          | Description                                                                |
      +====================+============================================================================+
      | Resource Name      | Specifies the resource name.                                               |
      +--------------------+----------------------------------------------------------------------------+
      | ID                 | Specifies the resource ID.                                                 |
      +--------------------+----------------------------------------------------------------------------+
      | Last Status Update | Specifies the time when the a resource alarm is last generated or cleared. |
      +--------------------+----------------------------------------------------------------------------+

   .. table:: **Table 3** Alarm policies

      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                                            |
      +===================================+========================================================================================================================================+
      | Alarm Policy                      | Specifies the policy for triggering an alarm.                                                                                          |
      |                                   |                                                                                                                                        |
      |                                   | For example, an alarm is triggered if the average value of the monitored metric is 80% or more for three consecutive 5-minute periods. |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------+
      | Alarm Severity                    | Specifies the alarm severity, which can be **Critical**, **Major**, **Minor**, or **Informational**.                                   |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------+
