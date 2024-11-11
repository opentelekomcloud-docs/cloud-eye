:original_name: ces_faq_0004.html

.. _ces_faq_0004:

What Alarm Status Does Cloud Eye Support?
=========================================

**Alarm**, **Resolved**, **Insufficient data**, **Triggered**, and **Expired** are supported.

-  Alarm: The metric value reached the alarm threshold, and an alarm has been triggered but not cleared for the resource.
-  Resolved: The metric value went back to the normal range, and the resource alarm was cleared.
-  Insufficient data: No monitoring data has been reported for three consecutive hours, and this is generally because the instance has been deleted or is abnormal.
-  Triggered: An event configured in the alarm policy triggered an alarm.
-  Expired: The monitored resources or alarm policies in the alarm rule were adjusted, so the original alarm record status expired.
