:original_name: ces_01_0078.html

.. _ces_01_0078:

Modifying an Alarm Rule
=======================

Procedure
---------

#. Log in to the management console.
#. In the upper left corner, select a region and project.
#. Click **Service List** in the upper left corner, and select **Cloud Eye**.
#. Choose **Alarm Management** > **Alarm Rules**.
#. On the displayed **Alarm Rules** page, use either of the following two methods to modify an alarm rule:

   -  Locate the row containing the alarm rule you want to modify, click **More** in the **Operation** column, and choose **Modify**.
   -  Click the name of the alarm rule you want to modify. On the page displayed, click **Modify** in the upper right corner.

#. On the **Modify Alarm Rule** page, modify alarm rule parameters as needed.

   .. table:: **Table 1** Parameters

      +-----------------------+----------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Parameter             | Description                                                                                                                            | Example Value         |
      +=======================+========================================================================================================================================+=======================+
      | Name                  | Specifies the alarm rule name. The system generates a random name, which you can modify.                                               | alarm-b6al            |
      +-----------------------+----------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Description           | (Optional) Provides supplementary information about the alarm rule.                                                                    | N/A                   |
      +-----------------------+----------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Monitored Object      | Specifies the resource the alarm rule is created for. You can specify one or more resources.                                           | N/A                   |
      +-----------------------+----------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Metric                | For example:                                                                                                                           | N/A                   |
      |                       |                                                                                                                                        |                       |
      |                       | -  CPU Usage                                                                                                                           |                       |
      |                       |                                                                                                                                        |                       |
      |                       |    Indicates the CPU usage of the monitored object in percent.                                                                         |                       |
      |                       |                                                                                                                                        |                       |
      |                       | -  Memory Usage                                                                                                                        |                       |
      |                       |                                                                                                                                        |                       |
      |                       |    Indicates the memory usage of the monitored object in percent.                                                                      |                       |
      +-----------------------+----------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Alarm Policy          | Specifies the policy for triggering an alarm.                                                                                          | N/A                   |
      |                       |                                                                                                                                        |                       |
      |                       | For example, an alarm is triggered if the average value of the monitored metric is 80% or more for three consecutive 5-minute periods. |                       |
      +-----------------------+----------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Alarm Severity        | Specifies the alarm severity, which can be **Critical**, **Major**, **Minor**, or **Informational**.                                   | Major                 |
      +-----------------------+----------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Alarm Notification    | Specifies whether to notify users when alarms are triggered. Notifications can be sent by email, text message, or HTTP/HTTPS message.  | N/A                   |
      +-----------------------+----------------------------------------------------------------------------------------------------------------------------------------+-----------------------+

7. Click **OK**.
