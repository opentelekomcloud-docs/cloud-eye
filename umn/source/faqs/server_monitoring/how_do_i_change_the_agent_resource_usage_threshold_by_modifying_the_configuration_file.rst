:original_name: ces_faq_0127.html

.. _ces_faq_0127:

How Do I Change the Agent Resource Usage Threshold by Modifying the Configuration File?
=======================================================================================

This section describes how to modify the configuration file to change the Agent resource usage threshold.

.. note::

   This operation applies only to Agent 2.7.2 or later.

Procedure

#. Use the **root** account to log in to the ECS or BMS for which the Agent does not report data.
#. Modify the **conf.json** configuration file.

   a. Go to the Agent installation path **bin** by running the following command:

      Windows:

      .. code-block::

         cd C:\Program Files\uniagent\extension\install\telescope\bin

      Linux:

      .. code-block::

         cd /usr/local/uniagent/extension/install/telescope/bin

   b. Open **conf.json**.

      .. code-block::

         vi conf.json

   c. Add the following parameters to the **conf.json** file.

      .. code-block::

         {
             "cpu_first_pct_threshold": xx,
             "memory_first_threshold": xxx,
             "cpu_second_pct_threshold": xx,
             "memory_second_threshold": xxx
         }

      .. table:: **Table 1** Parameters in the **conf.json** file

         +--------------------------+----------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------+
         | Parameter                | Description                                                                                  | How to Query Parameter Values                                                                      |
         +==========================+==============================================================================================+====================================================================================================+
         | cpu_first_pct_threshold  | Tier-1 threshold of CPU usage. The default value is 10 (%).                                  | To query the CPU usage and memory usage of the Agent process, use either of the following methods: |
         |                          |                                                                                              |                                                                                                    |
         |                          |                                                                                              | -  Linux:                                                                                          |
         |                          |                                                                                              |                                                                                                    |
         |                          |                                                                                              |    **top -p** *telescope PID*                                                                      |
         |                          |                                                                                              |                                                                                                    |
         |                          |                                                                                              | -  Windows:                                                                                        |
         |                          |                                                                                              |                                                                                                    |
         |                          |                                                                                              |    View the details of the Agent process in **Task Manager**.                                      |
         +--------------------------+----------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------+
         | memory_first_threshold   | Tier-1 threshold of memory usage. The default value is 209715200 (200 MB). The unit is byte. |                                                                                                    |
         +--------------------------+----------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------+
         | cpu_second_pct_threshold | Tier-2 threshold of CPU usage. The default value is 30 (%).                                  |                                                                                                    |
         +--------------------------+----------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------+
         | memory_second_threshold  | Tier-2 threshold of memory usage. The default value is 734003200 (700 MB). The unit is byte. |                                                                                                    |
         +--------------------------+----------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------+

   d. Save the **conf.json** file and exit.

      .. code-block::

         :wq

#. Modify the **manifest.json** configuration file.

   a. Switch to the **manifest.json** file directory.

      Windows:

      .. code-block::

         cd C:\Program Files\uniagent\extension\holder\telescope

      Linux:

      .. code-block::

         cd /usr/local/uniagent/extension/holder/telescope

   b. Open **manifest.json**.

      .. code-block::

         vi manifest.json

   c. Modify the parameters **mem** and **cpuUsage** in **resourceLimit**, three parameter sets in total. Retain the default values of other parameters.

      .. code-block::

         [
             {
                 "arch": "amd64",
                 ...
                 "resourceLimit": {
                     "mem": 200,
                     "cpuUsage": 10
                 }
             },
             {
                 "arch": "arm64",
                 ...
                 "resourceLimit": {
                     "mem": 200,
                     "cpuUsage": 10
                 }
             },
             {
                 "arch": "amd64",
                 "os": "linux",
                 ...
                 "resourceLimit": {
                     "mem": 200,
                     "cpuUsage": 10
                 }
             }
         ]

      .. table:: **Table 2** Parameters in the **manifest.json** file

         +-----------------------------------+---------------------------------------------------------------------+
         | Parameter                         | Description                                                         |
         +===================================+=====================================================================+
         | "resourceLimit": {                | **mem**: memory threshold. The default value is **200**, in MB.     |
         |                                   |                                                                     |
         | "mem": 200,                       | **cpuUsage**: CPU usage threshold (%). The default value is **10**. |
         |                                   |                                                                     |
         | "cpuUsage": 10                    |                                                                     |
         |                                   |                                                                     |
         | }                                 |                                                                     |
         +-----------------------------------+---------------------------------------------------------------------+

   d. Save the **manifest.json** file and exit.

      .. code-block::

         :wq

#. Restart the Agent.

   -  Windows:

      a. In the **C:\\Program Files\\uniagent\\extension\\install\\telescope** directory, double-click **shutdown.bat** to stop the Agent, and then run **start.bat** to start the Agent.
      b. In the **C:\\Program Files\\uniagent\\script** directory, double-click **shutdown.bat** to stop the Agent, and then run **start.bat** to start the Agent.

   -  Linux:

      .. code-block::

         service ces-uniagent stop
         service ces-uniagent start
         /usr/local/uniagent/extension/install/telescope/telescoped restart
