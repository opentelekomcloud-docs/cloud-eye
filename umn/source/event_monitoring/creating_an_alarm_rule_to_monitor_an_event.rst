:original_name: ces_01_0052.html

.. _ces_01_0052:

Creating an Alarm Rule to Monitor an Event
==========================================

Scenarios
---------

This topic describes how to create an alarm rule to monitor an event.

Procedure
---------

#. Log in to the management console.

#. Click **Service List** in the upper left corner, and select **Cloud Eye**.

#. In the navigation pane on the left, choose **Event Monitoring**.

#. Click **Create Alarm Rule**.

#. Specify resource type and event type.


   .. figure:: /_static/images/en-us_image_0000001136164665.png
      :alt: **Figure 1** Creating a alarm rule

      **Figure 1** Creating a alarm rule

   .. table:: **Table 1** Parameter description

      +-----------------------------------+----------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                              |
      +===================================+==========================================================================================================+
      | Name                              | Specifies the alarm rule name. The system generates a random name, which you can modify.                 |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------+
      | Description                       | (Optional) Provides supplementary information about the alarm rule.                                      |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------+
      | Resource Type                     | Specifies the type of the resource the alarm rule is created for.                                        |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------+
      | Dimension                         | Specifies the metric dimension of the selected resource type.                                            |
      |                                   |                                                                                                          |
      |                                   | Example value: **System event**                                                                          |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------+
      | Method                            | It is fixed to **Configure manually**.                                                                   |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------+
      | Event Source                      | Specifies the service the event is generated for.                                                        |
      |                                   |                                                                                                          |
      |                                   | Example value: **Elastic Cloud Server**                                                                  |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------+
      | Event Name                        | Specifies the instantaneous operations users performed on resources, such as login and logout.           |
      |                                   |                                                                                                          |
      |                                   | For events supported by event monitoring, see :ref:`Events Supported by Event Monitoring <ces_01_0054>`. |
      |                                   |                                                                                                          |
      |                                   | Example value: **Delete ECS**                                                                            |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------+
      | Monitoring Scope                  | Specifies the monitoring scope for event monitoring.                                                     |
      |                                   |                                                                                                          |
      |                                   | Example value: **All resources**                                                                         |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------+
      | Trigger Mode                      | You can select immediate trigger or accumulative trigger based on the operation severity.                |
      |                                   |                                                                                                          |
      |                                   | Example value: **Immediate trigger**                                                                     |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------+
      | Alarm Severity                    | Specifies the alarm severity, which can be **Critical**, **Major**, **Minor**, or **Informational**.     |
      |                                   |                                                                                                          |
      |                                   | Example value: **Major**                                                                                 |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------+

#. Enable the alarm notification function and set event alarm parameters.


   .. figure:: /_static/images/en-us_image_0000001081906243.png
      :alt: **Figure 2** Create Alarm Rule

      **Figure 2** Create Alarm Rule

   .. table:: **Table 2** Parameter description

      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                                                                                                                                                                                                       |
      +===================================+===================================================================================================================================================================================================================================================================================================+
      | Alarm Notification                | Specifies whether to notify users when alarms are triggered. Notifications can be sent by email, text message, or HTTP/HTTPS message.                                                                                                                                                             |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Validity Period                   | Cloud Eye sends notifications only within the validity period specified in the alarm rule.                                                                                                                                                                                                        |
      |                                   |                                                                                                                                                                                                                                                                                                   |
      |                                   | If **Validity Period** is set to **08:00-20:00**, Cloud Eye sends notifications only within 08:00-20:00.                                                                                                                                                                                          |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Notification Object               | Specifies the object that receives alarm notifications. You can select the account contact or a topic.                                                                                                                                                                                            |
      |                                   |                                                                                                                                                                                                                                                                                                   |
      |                                   | -  **Account contact** is the mobile phone number and email address of the registered account.                                                                                                                                                                                                    |
      |                                   | -  **Topic**: A topic is used to publish messages and subscribe to notifications. If the required topic is unavailable, create one first and add subscriptions to it. For details, see :ref:`Creating a Topic <en-us_topic_0085216039>` and :ref:`Adding Subscriptions <en-us_topic_0084572343>`. |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Trigger Condition                 | Specifies the trigger of alarm notifications.                                                                                                                                                                                                                                                     |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

#. Click **Create**.

   The alarm rule is created.
