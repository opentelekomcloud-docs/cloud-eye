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
#. Click **Service List** in the upper left corner, and select **Cloud Eye**.
#. In the navigation pane on the left, choose **Server Monitoring**.
#. Locate the target ECS or BMS. In the **Operation** column, click **More**, and select **Create Alarm Rule**.
#. On the **Create Alarm Rule** page, follow the prompts to configure the parameters.

   a. Configure the alarm rule name and description.

      .. table:: **Table 1** Alarm rule **Name** and **Description**

         +-----------------------------------+------------------------------------------------------------------------------------------+
         | Parameter                         | Description                                                                              |
         +===================================+==========================================================================================+
         | Name                              | Specifies the alarm rule name. The system generates a random name, which you can modify. |
         |                                   |                                                                                          |
         |                                   | Example value: **alarm-b6al**                                                            |
         +-----------------------------------+------------------------------------------------------------------------------------------+
         | Description                       | (Optional) Provides supplementary information about the alarm rule.                      |
         +-----------------------------------+------------------------------------------------------------------------------------------+

   b. You do not need to set the monitored object because it is the current ECS.

   c. In the **Select Metric** step, select **Create manually** and configure parameters based on :ref:`Table 2 <ces_01_0042__table4534051437>`.

      .. _ces_01_0042__table4534051437:

      .. table:: **Table 2** Parameters

         +-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
         | Parameter             | Description                                                                                                                                                                                                                                          | Example Value         |
         +=======================+======================================================================================================================================================================================================================================================+=======================+
         | Method                | Specifies the means you use to create the alarm rule.                                                                                                                                                                                                | Create manually       |
         +-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
         | Metric                | For details about basic monitoring metrics, see :ref:`Services Interconnected with Cloud Eye <en-us_topic_0202622212>`.                                                                                                                              | N/A                   |
         +-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
         | Mount Point or Disk   | This parameter is mandatory when the metric is a fine-grained disk metric.                                                                                                                                                                           | /dev                  |
         |                       |                                                                                                                                                                                                                                                      |                       |
         |                       | For the Windows OS, enter a drive letter, such as **C**, **D**, or **E**. For the Linux OS, enter a mount point, such as **/dev** or **/opt**.                                                                                                       |                       |
         +-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
         | Alarm Policy          | Specifies the policy for triggering an alarm.                                                                                                                                                                                                        | N/A                   |
         |                       |                                                                                                                                                                                                                                                      |                       |
         |                       | For example, an alarm is triggered if the average value of the monitored metric is 80% or more for three consecutive 5-minute periods.                                                                                                               |                       |
         +-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
         | Alarm Severity        | Specifies the alarm severity, which can be **Critical**, **Major**, **Minor**, or **Informational**.                                                                                                                                                 | Major                 |
         +-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
         | Alarm Notification    | Specifies whether to notify users when alarms are triggered. Notifications can be sent by email, text message, or HTTP/HTTPS message.                                                                                                                | Enable                |
         |                       |                                                                                                                                                                                                                                                      |                       |
         |                       | You can enable (recommended) or disable this function.                                                                                                                                                                                               |                       |
         +-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
         | Topic                 | Specifies the name of the topic the alarm notification is to be sent to.                                                                                                                                                                             | N/A                   |
         |                       |                                                                                                                                                                                                                                                      |                       |
         |                       | If you have enabled **Alarm Notification**, select a topic. If no desirable topics are available, create one first, whereupon the SMN service is invoked. For details about how to create a topic, see the *Simple Message Notification User Guide*. |                       |
         +-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
         | Validity Period       | Cloud Eye sends notifications only within the validity period specified in the alarm rule.                                                                                                                                                           | N/A                   |
         |                       |                                                                                                                                                                                                                                                      |                       |
         |                       | If **Validity Period** is set to **00:00-8:00**, Cloud Eye sends notifications only within 00:00-8:00.                                                                                                                                               |                       |
         +-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
         | Trigger Condition     | Specifies the condition for triggering the alarm notification. You can select **Generated alarm** (when an alarm is generated), **Cleared alarm** (when an alarm is cleared), or both.                                                               | N/A                   |
         +-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+

   d. Click **Create**.

After the alarm rule is created, if the metric data reaches the specified threshold, Cloud Eye immediately informs you that an exception has occurred.
