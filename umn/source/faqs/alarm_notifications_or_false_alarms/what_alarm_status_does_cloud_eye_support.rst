:original_name: ces_faq_0004.html

.. _ces_faq_0004:

What Alarm Status Does Cloud Eye Support?
=========================================

There are three Cloud Eye alarm statuses: **Alarm**, **OK**, and **Insufficient data**. If an alarm rule is disabled, its status is considered as invalid, and **Disabled** is displayed.

-  **Alarm**: The monitoring data meets the preset alarm policy.
-  **OK**: The monitoring data is reported but does not meet the preset alarm policy.
-  **Insufficient data**: No monitoring data has been reported for three consecutive hours, and this is generally because the instance has been deleted or is abnormal.
