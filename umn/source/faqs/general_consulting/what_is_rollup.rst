:original_name: ces_faq_0009.html

.. _ces_faq_0009:

What Is Rollup?
===============

Rollup is a process where Cloud Eye calculates the maximum, minimum, average, sum, or variance value of raw data sampled for different periods and repeats the process for each subsequent period. A calculation period is called a rollup period.

During the rollup, data sets are smoothed. A longer rollup period means more smoothing and precise data, enabling you to predict trends more precisely. On the contrary, a shorter rollup period means more accurate alarms.

The rollup period can be 5 minutes, 20 minutes, 1 hour, 4 hours, or 1 day.

During the rollup, Cloud Eye processes data sampled based on the data type.

-  If the data sampled is integers, Cloud Eye rounds off the aggregation results.
-  If the data includes decimal values (floating point number), Cloud Eye truncates the data after the second decimal place.

For example, if the instance quantity in Auto Scaling is an integer value, the rollup period is 5 minutes, and the current time is 10:35, Cloud Eye rolls up the raw data generated between 10:30 and 10:35 to the time point of 10:30. If the sampled metrics are 1 and 4 respectively, after aggregation, the maximum value is 4, the minimum value is 1, and the average value is [(1 + 4)/2] = 2, instead of 2.5.

Choose whichever rollup method best meets your service requirements.
