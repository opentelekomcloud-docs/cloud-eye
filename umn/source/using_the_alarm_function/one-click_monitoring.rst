:original_name: en-us_topic_0171694487.html

.. _en-us_topic_0171694487:

One-Click Monitoring
====================

Scenarios
---------

One-click monitoring allows you to quickly enable alarm reporting for all resources. This helps you quickly establish a monitoring and alarm system and receive notifications in a timely manner when resources are abnormal. When one-click monitoring is enabled, the alarm rules you selected are added to the alarm rule list. When one-click monitoring is disabled, these alarm rules are deleted from the alarm rule list.

This topic describes how to use one-click monitoring to monitor key metrics or events.

Constraints
-----------

-  Once the alarm threshold is reached, one-click monitoring will trigger alarms immediately.
-  Alarm policies cannot be modified in one-click monitoring.

Enabling One-Click Monitoring
-----------------------------

#. Log in to the management console.

#. Choose **Service List** > **Cloud Eye**.

#. In the navigation pane on the left, choose **Alarm Management** > **One-Click Monitoring**.

#. Locate the cloud service you want to enable one-click monitoring and turn on the toggle in the **One-Click Monitoring** column.


   .. figure:: /_static/images/en-us_image_0000001693305821.png
      :alt: **Figure 1** Enabling one-click monitoring

      **Figure 1** Enabling one-click monitoring

#. On the **Enable Alarm Rule** page, all alarm rules are enabled by default. If you do not want to enable one-click monitoring for certain alarm rules, turn off the toggle in the **One-Click Monitoring** column of those alarm rules.

#. Configure alarm notification parameters as prompted. For details, see :ref:`Table 4 <en-us_topic_0084572213__table54161352427>`.

#. Review and confirm parameter settings. Then, click **OK**.

Enabling or Disabling an Alarm Rule
-----------------------------------

After one-click monitoring is enabled for a cloud service, you can enable or disable the alarm rules of the cloud service.

#. Log in to the management console.

#. Choose **Service List** > **Cloud Eye**.

#. In the navigation pane on the left, choose **Alarm Management** > **One-Click Monitoring**.

#. Click the drop-down button on the left of the cloud service to view the associated alarm rules.

#. Turn on or off the toggle in the **One-Click Monitoring** column of the alarm rule to enable or disable the alarm rule.


   .. figure:: /_static/images/en-us_image_0000002410287150.png
      :alt: **Figure 2** Viewing alarm rules

      **Figure 2** Viewing alarm rules

Enabling or Disabling an Alarm Policy
-------------------------------------

When an alarm rule of one-click monitoring is enabled, all alarm policies under the alarm rule are enabled by default. You can enable or disable them as needed.

#. Log in to the management console.
#. Choose **Service List** > **Cloud Eye**.
#. In the navigation pane on the left, choose **Alarm Management** > **One-Click Monitoring**.
#. Click the drop-down button on the left of the cloud service to view the associated alarm rules.
#. Click the drop-down button on the left of the alarm rule to view the associated alarm policies.
#. Turn on or off the toggle in the **One-Click Monitoring** column of the alarm policy to enable or disable the alarm policy.

Batch Modifying Alarm Notifications
-----------------------------------

When one-click monitoring is enabled for a cloud service, you can modify alarm notifications in batches. Once modified, the new notification settings are applied to all the alarm rules for that cloud service.

#. Log in to the management console.
#. Choose **Service List** > **Cloud Eye**.
#. In the navigation pane on the left, choose **Alarm Management** > **One-Click Monitoring**.
#. Locate the cloud service you want to modify alarm notifications for, and click **Batch Modify Alarm Notifications** in the **Operation** column.
#. In the **Batch Modify Alarm Notifications** dialog box, set alarm notification parameters. For details, see :ref:`Table 4 <en-us_topic_0084572213__table54161352427>`.
#. Click **OK**.

Modifying Alarm Notifications of a Specified Alarm Rule
-------------------------------------------------------

You can also modify alarm notifications of a specified alarm rule for a cloud service.

#. Log in to the management console.
#. Choose **Service List** > **Cloud Eye**.
#. In the navigation pane on the left, choose **Alarm Management** > **One-Click Monitoring**.
#. Click the drop-down button on the left of the cloud service to view the associated alarm rules.
#. Locate the alarm rule and click **Modify Alarm Notifications** in the **Operation** column.
#. In the **Modify Alarm Notifications** dialog box, set alarm notification parameters. For details, see :ref:`Table 4 <en-us_topic_0084572213__table54161352427>`.
