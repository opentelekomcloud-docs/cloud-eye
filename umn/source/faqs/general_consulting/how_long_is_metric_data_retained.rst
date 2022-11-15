:original_name: ces_faq_0010.html

.. _ces_faq_0010:

How Long Is Metric Data Retained?
=================================

Metric data includes raw data and rolled-up data.

-  Raw data is retained for two days.
-  Rolled-up data is data aggregated based on raw data. The retention period for rolled-up data depends on the rollup period.

   .. table:: **Table 1** Retention periods for rolled-up data

      ============= ================
      Rollup Period Retention Period
      ============= ================
      5 minutes     10 days
      20 minutes    20 days
      1 hour        155 days
      4 hours       300 days
      1 day         5 years
      ============= ================

If an instance is disabled, stopped, or deleted, its metrics will be deleted one hour after the raw data reporting of those metrics stops. When the instance is enabled or restarted, raw data reporting of its metrics will resume. If the instance has been disabled or stopped for less than two days or for less time than the previous rolled-up data retention period, you can view the historical data of its metrics generated before these metrics were deleted.
