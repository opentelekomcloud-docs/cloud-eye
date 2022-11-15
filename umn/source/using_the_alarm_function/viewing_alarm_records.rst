:original_name: ces_01_0076.html

.. _ces_01_0076:

Viewing Alarm Records
=====================

The alarm records display the status changes of all alarm rules in the last 30 days.

When an alarm is generated, you can view the alarm details about the cloud resource.

Procedure
---------

#. Log in to the management console.

#. In the upper left corner, select a region and project.

#. Click **Service List** in the upper left corner, and select **Cloud Eye**.

#. Choose **Alarm Management** > **Alarm Records**.

   On the **Alarm Records** page, you can view the status changes of all alarm rules from the last 7 days.

   .. note::

      -  You can select a time range to search for the alarm records.
      -  In the upper right corner of the alarm record list, you can filter the alarm records by the alarm rule name, resource ID, and alarm rule ID.

#. Click the target alarm rule to go to the **Alarm Rules** page. In the lower part of the **Alarm Records** area, you can view the history of the selected alarm rule from the last 30 days.

   In the alarm record list, you can check whether resources are abnormal and handle the exceptions, if any.

   .. note::

      -  Typically, alarms are triggered based on calculation. Therefore, the alarm triggering time may be a few seconds later than the time the threshold was reached.
      -  If you have created or modified an alarm rule after obtaining the monitoring data and an alarm is triggered, the alarm triggering time is the time when you created or modified the alarm rule.
