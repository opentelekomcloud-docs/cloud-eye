:original_name: ces_faq_0013.html

.. _ces_faq_0013:

How Many Rollup Methods Does Cloud Eye Support?
===============================================

Cloud Eye supports the following five rollup methods, among which variance has been disabled and will be removed in later versions:

-  Average

   If **Statistic** is set to **Avg.**, Cloud Eye calculates the average value of metrics collected within a rollup period.

-  Maximum

   If **Statistic** is set to **Max.**, Cloud Eye calculates the maximum value of metrics collected within a rollup period.

-  Minimum

   If **Statistic** is set to **Min.**, Cloud Eye calculates the minimum value of metrics collected within a rollup period.

-  Sum

   If **Statistic** is set to **Sum**, Cloud Eye calculates the sum of metrics collected within a rollup period.

-  Variance

   If **Statistic** is set to **Variance**, Cloud Eye calculates the variance value of metrics collected within a rollup period.

   .. note::

      Take a 5-minute period as an example. If it is 10:35 now and the rollup period starts at 10:30, the raw data generated between 10:30 and 10:35 is rolled up to 10:30.
