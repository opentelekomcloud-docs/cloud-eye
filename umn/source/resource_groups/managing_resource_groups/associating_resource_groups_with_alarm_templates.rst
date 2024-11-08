:original_name: ces_01_0235.html

.. _ces_01_0235:

Associating Resource Groups with Alarm Templates
================================================

Scenarios
---------

You can create resource groups and associate them with alarm templates to create alarm rules in batches, improving alarm rule configuration efficiency.

Procedure
---------

#. Log in to the management console.

2. In the upper left corner, select a region and project.

3. Click **Service List** in the upper left corner and select **Cloud Eye**.

4. On the **Resource Groups** page, locate the resource group and click **Associate Alarm Template** in the **Operation** column.

5. In the **Associate Alarm Template** dialog box, select an alarm template.


   .. figure:: /_static/images/en-us_image_0000001882550297.png
      :alt: **Figure 1** Associate Alarm Template

      **Figure 1** Associate Alarm Template

6. Configure the alarm notification.


   .. figure:: /_static/images/en-us_image_0000001835592140.png
      :alt: **Figure 2** Alarm Notification

      **Figure 2** Alarm Notification

   .. table:: **Table 1** Alarm Notification

      +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                                                                                                                                                                                         |
      +===================================+=====================================================================================================================================================================================================================================================================================+
      | Alarm Notification                | Specifies whether to notify users when alarms are triggered. Notifications can be sent by email, SMS message, or HTTP/HTTPS message.                                                                                                                                                |
      +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Notification Object               | Specifies the object to which the alarm notification is to be sent. You can select a topic name.                                                                                                                                                                                    |
      |                                   |                                                                                                                                                                                                                                                                                     |
      |                                   | A topic is used to publish messages and subscribe to notifications. If the required topic is unavailable, create one first and add subscriptions to it. For details, see :ref:`Creating a Topic <en-us_topic_0085216039>` and :ref:`Adding Subscriptions <en-us_topic_0084572343>`. |
      +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Validity Period                   | Cloud Eye sends notifications only within the notification window specified in the alarm rule.                                                                                                                                                                                      |
      |                                   |                                                                                                                                                                                                                                                                                     |
      |                                   | If you set **Validity Period** to **08:00-20:00**, Cloud Eye sends notifications only from 08:00 to 20:00.                                                                                                                                                                          |
      +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Trigger Condition                 | Specifies the condition for triggering an alarm notification. You can select **Generated alarm** (when an alarm is generated), **Cleared alarm** (when an alarm is cleared), or both.                                                                                               |
      +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

7. Click **OK**.
