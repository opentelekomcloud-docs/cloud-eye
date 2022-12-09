:original_name: ces_01_0083.html

.. _ces_01_0083:

Creating a Custom Template
==========================

#. On the **Alarm Templates** page, click **Create Custom Template**.

#. In the **Configure Template** step, specify the parameters listed in :ref:`Table 1 <ces_01_0083__table1956141511220>`.

   .. _ces_01_0083__table1956141511220:

   .. table:: **Table 1** Parameters

      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                              |
      +===================================+==========================================================================================================================+
      | Resource Type                     | Specifies the type of the resource the alarm rule is created for.                                                        |
      |                                   |                                                                                                                          |
      |                                   | Example value: **Elastic Cloud Server**                                                                                  |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------+
      | Dimension                         | Specifies the metric dimension of the selected resource type.                                                            |
      |                                   |                                                                                                                          |
      |                                   | Example value: **ECSs**                                                                                                  |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------+
      | Import Template                   | -  Enable                                                                                                                |
      |                                   |                                                                                                                          |
      |                                   |    Select an existing template, then you can use or modify default alarm rules contained in the selected alarm template. |
      |                                   |                                                                                                                          |
      |                                   | -  Disable                                                                                                               |
      |                                   |                                                                                                                          |
      |                                   |    Manually add one or more alarm rules.                                                                                 |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------+

#. Click **Next** to go to the **Add Alarm Rule** step. Specify parameters listed in :ref:`Table 2 <ces_01_0083__table691022118227>`. You can add one or more rules to the alarm template.

   .. _ces_01_0083__table691022118227:

   .. table:: **Table 2** Parameters

      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                                            |
      +===================================+========================================================================================================================================+
      | Metric                            | For example:                                                                                                                           |
      |                                   |                                                                                                                                        |
      |                                   | -  CPU Usage                                                                                                                           |
      |                                   |                                                                                                                                        |
      |                                   |    Indicates the CPU usage of the monitored object in percent.                                                                         |
      |                                   |                                                                                                                                        |
      |                                   | -  Memory Usage                                                                                                                        |
      |                                   |                                                                                                                                        |
      |                                   |    Indicates the memory usage of the monitored object in percent.                                                                      |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------+
      | Alarm Policy                      | Specifies the policy for triggering an alarm.                                                                                          |
      |                                   |                                                                                                                                        |
      |                                   | For example, an alarm is triggered if the average value of the monitored metric is 80% or more for three consecutive 5-minute periods. |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------+
      | Alarm Severity                    | Specifies the alarm severity, which can be **Critical**, **Major**, **Minor**, or **Informational**.                                   |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------+
      | Operation                         | When the number of the alarm policies is two or more, you can delete alarm policies.                                                   |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------+

#. Click **Next** to go to the **Specify Template Details** step. Specify parameters listed in :ref:`Table 3 <ces_01_0083__table722215293225>`.

   .. _ces_01_0083__table722215293225:

   .. table:: **Table 3** Parameters

      +-----------------------------------+-----------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                   |
      +===================================+===============================================================================================+
      | Name                              | Specifies the custom template name. The system generates a random name, which you can modify. |
      |                                   |                                                                                               |
      |                                   | Example value: **alarmTemplate-ku0x**                                                         |
      +-----------------------------------+-----------------------------------------------------------------------------------------------+
      | Description                       | (Optional) Provides supplementary information about the alarm template.                       |
      +-----------------------------------+-----------------------------------------------------------------------------------------------+

#. Click **Finish**.
