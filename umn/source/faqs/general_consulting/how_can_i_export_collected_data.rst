:original_name: ces_faq_0012.html

.. _ces_faq_0012:

How Can I Export Collected Data?
================================

#. On the Cloud Eye console, choose **Cloud Service Monitoring** or **Server Monitoring**.
#. Click **Export Data**.
#. Configure the time range, resource type, dimension, monitored object, and metric.
#. Click **Export**.

.. note::

   You can export data for multiple metrics at a time to a CSV file.

-  The first row in the exported monitoring report displays the username, region, service, instance name, instance ID, metric name, metric data, time, and timestamp. You can view historical monitoring data.
-  To convert the time using a Unix timestamp to the time of the target time zone, perform the following steps:

   #. Use Excel to open a .csv file.

   #. Use the following formula to convert the time:

      Target time = [Unix timestamp/1000 + (Target time zone) x 3600]/86400 + 70 x 365 + 19

   #. Set cell format to **Date**.
