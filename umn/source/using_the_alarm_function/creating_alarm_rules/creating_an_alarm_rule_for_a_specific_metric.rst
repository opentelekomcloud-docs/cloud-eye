:original_name: ces_01_0074.html

.. _ces_01_0074:

Creating an Alarm Rule for a Specific Metric
============================================

Cloud Eye enables you to create alarm rules for a metric of one or multiple cloud services, making it convenient for you to monitor the metric of your resources.

Adding a Custom Alarm Rule
--------------------------

#. Log in to the management console.
#. In the upper left corner, select a region and project.
#. Click **Service List** in the upper left corner, and select **Cloud Eye**.
#. In the navigation pane on the left, choose **Alarm Management** > **Alarm Rules**, and click **Create Alarm Rule** in the upper right corner.
#. In the **Create Alarm Rule** dialog box, configure the parameters.

   a. Select an object and configure other parameters listed in :ref:`Table 1 <ces_01_0074__table35986202162751>`.

      .. _ces_01_0074__table35986202162751:

      .. table:: **Table 1** Parameters

         +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------+
         | Parameter                         | Description                                                                                                             |
         +===================================+=========================================================================================================================+
         | Name                              | Specifies the alarm rule name. The system generates a random name, which you can modify.                                |
         |                                   |                                                                                                                         |
         |                                   | Example value: **alarm-b6al**                                                                                           |
         +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------+
         | Description                       | (Optional) Provides supplementary information about the alarm rule.                                                     |
         +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------+
         | Resource Type                     | Specifies the type of the resource the alarm rule is created for.                                                       |
         |                                   |                                                                                                                         |
         |                                   | Example value: **Elastic Cloud Server**                                                                                 |
         +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------+
         | Dimension                         | Specifies the metric dimension of the selected resource type.                                                           |
         |                                   |                                                                                                                         |
         |                                   | Example value: **ECSs**                                                                                                 |
         +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------+
         | Monitoring Scope                  | Specifies the monitoring scope the alarm rule applies to. You can select **Resource groups** or **Specific resources**. |
         |                                   |                                                                                                                         |
         |                                   | .. note::                                                                                                               |
         |                                   |                                                                                                                         |
         |                                   |    -  If **Resource groups** is selected and any resource in the group meets the alarm policy, an alarm is triggered.   |
         |                                   |    -  If **Resource groups** is selected, alarm rules cannot be created using templates.                                |
         +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------+
         | Monitored Object                  | Specifies the resource the alarm rule is created for. You can specify one or more resources.                            |
         +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------+

   b. In the **Select Metric** step, select **Create manually** and configure parameters based on :ref:`Table 2 <ces_01_0074__table4534051437>`.

      .. _ces_01_0074__table4534051437:

      .. table:: **Table 2** Parameters

         +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
         | Parameter             | Description                                                                                                                                                                                                                                                                                       | Example Value         |
         +=======================+===================================================================================================================================================================================================================================================================================================+=======================+
         | Method                | Specifies the means you use to create the alarm rule.                                                                                                                                                                                                                                             | Configure manually    |
         +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
         | Metric                | For example:                                                                                                                                                                                                                                                                                      | CPU Usage             |
         |                       |                                                                                                                                                                                                                                                                                                   |                       |
         |                       | -  CPU Usage                                                                                                                                                                                                                                                                                      |                       |
         |                       |                                                                                                                                                                                                                                                                                                   |                       |
         |                       |    Indicates the CPU usage of the monitored object. The unit is percent.                                                                                                                                                                                                                          |                       |
         |                       |                                                                                                                                                                                                                                                                                                   |                       |
         |                       | -  Memory Usage                                                                                                                                                                                                                                                                                   |                       |
         |                       |                                                                                                                                                                                                                                                                                                   |                       |
         |                       |    Indicates the memory usage of the monitored object. The unit is percent.                                                                                                                                                                                                                       |                       |
         +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
         | Alarm Policy          | Specifies the policy for triggering an alarm.                                                                                                                                                                                                                                                     | N/A                   |
         |                       |                                                                                                                                                                                                                                                                                                   |                       |
         |                       | For example, an alarm is triggered if the average value of the monitored metric is 80% or more for three consecutive 5-minute periods.                                                                                                                                                            |                       |
         +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
         | Alarm Severity        | Specifies the alarm severity, which can be **Critical**, **Major**, **Minor**, or **Informational**.                                                                                                                                                                                              | Major                 |
         +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
         | Alarm Notification    | Specifies whether to notify users when alarms are triggered. Notifications can be sent by email, text message, or HTTP/HTTPS message.                                                                                                                                                             | Enable                |
         +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
         | Notification Object   | Specifies the object that receives alarm notifications. You can select the account contact or a topic.                                                                                                                                                                                            | N/A                   |
         |                       |                                                                                                                                                                                                                                                                                                   |                       |
         |                       | -  **Account contact** is the mobile phone number and email address of the registered account.                                                                                                                                                                                                    |                       |
         |                       |                                                                                                                                                                                                                                                                                                   |                       |
         |                       | -  **Topic**: A topic is used to publish messages and subscribe to notifications. If the required topic is unavailable, create one first and add subscriptions to it. For details, see :ref:`Creating a Topic <en-us_topic_0085216039>` and :ref:`Adding Subscriptions <en-us_topic_0084572343>`. |                       |
         +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
         | Validity Period       | Cloud Eye sends notifications only within the validity period specified in the alarm rule.                                                                                                                                                                                                        | N/A                   |
         |                       |                                                                                                                                                                                                                                                                                                   |                       |
         |                       | If **Validity Period** is set to **08:00-20:00**, Cloud Eye sends notifications only within 08:00-20:00.                                                                                                                                                                                          |                       |
         +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
         | Trigger Condition     | Specifies the condition for triggering the alarm notification. You can select **Generated alarm** (when an alarm is generated), **Cleared alarm** (when an alarm is cleared), or both.                                                                                                            | N/A                   |
         +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
