:original_name: en-us_topic_0092358859.html

.. _en-us_topic_0092358859:

Viewing Process Monitoring
==========================

Process monitoring is used to monitor active processes on a host. By default, the Agent collects CPU usage, memory usage, and the number of opened files of the active processes. If you have customized process monitoring, the number of processes containing keywords is also monitored.

The Agent collects process CPU usages once every minute and displays the top 5 processes, ranked by the CPU usage over the last 24 hours.

.. note::

   To view the process monitoring information, install the Agent.

Querying the System Processes
-----------------------------

After the Agent is installed, you can check system processes on Cloud Eye.

To query the number of processes

#. Log in to the management console.

#. Click **Service List** in the upper left corner and select **Cloud Eye**.

#. Perform the following operations based on the resources to be viewed:

   -  To check the process monitoring of an ECS, choose **Server Monitoring** > **Elastic Cloud Server**.
   -  To check the process monitoring of a BMS, choose **Server Monitoring** > **Bare Metal Server**.

#. On the **Server Monitoring** page, locate the ECS and click **View Metric** to go to the **OS Monitoring** page.

#. Select the **Process Monitoring** tab.

   In the **System Processes** area, the process information is displayed. :ref:`Table 1 <en-us_topic_0092358859__table4129151101318>` describes the metrics of system processes.

   .. _en-us_topic_0092358859__table4129151101318:

   .. table:: **Table 1** System process metrics

      +--------------------+---------------------------------------+-------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------+
      | Metric             | Description                           | Value Range | Collection Mode (Linux)                                                                                                                                                   | Collection Mode (Windows)                                                                             |
      +====================+=======================================+=============+===========================================================================================================================================================================+=======================================================================================================+
      | Running Processes  | Number of processes that are running  | >= 0        | Monitored object: ECS or BMS                                                                                                                                              | Not supported                                                                                         |
      |                    |                                       |             |                                                                                                                                                                           |                                                                                                       |
      |                    |                                       |             | You can obtain the state of each process by checking the **Status** value in the **/proc/pid/status** file, and then collect the total number of processes in each state. |                                                                                                       |
      +--------------------+---------------------------------------+-------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------+
      | Idle Processes     | Number of processes that are idle     | >= 0        | Monitored object: ECS or BMS                                                                                                                                              | Not supported                                                                                         |
      |                    |                                       |             |                                                                                                                                                                           |                                                                                                       |
      |                    |                                       |             | You can obtain the state of each process by checking the **Status** value in the **/proc/pid/status** file, and then collect the total number of processes in each state. |                                                                                                       |
      +--------------------+---------------------------------------+-------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------+
      | Zombie Processes   | Number of zombie processes            | >= 0        | Monitored object: ECS or BMS                                                                                                                                              | Not supported                                                                                         |
      |                    |                                       |             |                                                                                                                                                                           |                                                                                                       |
      |                    |                                       |             | You can obtain the state of each process by checking the **Status** value in the **/proc/pid/status** file, and then collect the total number of processes in each state. |                                                                                                       |
      +--------------------+---------------------------------------+-------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------+
      | Blocked Processes  | Number of processes that are blocked  | >= 0        | Monitored object: ECS or BMS                                                                                                                                              | Not supported                                                                                         |
      |                    |                                       |             |                                                                                                                                                                           |                                                                                                       |
      |                    |                                       |             | You can obtain the state of each process by checking the **Status** value in the **/proc/pid/status** file, and then collect the total number of processes in each state. |                                                                                                       |
      +--------------------+---------------------------------------+-------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------+
      | Sleeping Processes | Number of processes that are sleeping | >= 0        | Monitored object: ECS or BMS                                                                                                                                              | Not supported                                                                                         |
      |                    |                                       |             |                                                                                                                                                                           |                                                                                                       |
      |                    |                                       |             | You can obtain the state of each process by checking the **Status** value in the **/proc/pid/status** file, and then collect the total number of processes in each state. |                                                                                                       |
      +--------------------+---------------------------------------+-------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------+
      | Total Processes    | Total number of processes             | >= 0        | Monitored object: ECS or BMS                                                                                                                                              | Monitored object: ECS or BMS                                                                          |
      |                    |                                       |             |                                                                                                                                                                           |                                                                                                       |
      |                    |                                       |             | You can obtain the state of each process by checking the **Status** value in the **/proc/pid/status** file, and then collect the total number of processes in each state. | Obtain the total number of processes by using the system process status support module **psapi.dll**. |
      +--------------------+---------------------------------------+-------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------+

Viewing the Running Data of Top CPU Processes
---------------------------------------------

-  The Agent collects process CPU usages once every minute and displays the top 5 processes, ranked by the CPU usage over the last 24 hours.
-  Run the **top** command to query the CPU usage and memory usage of a process.
-  Run the **lsof** or **ls /proc/**\ *pid*\ **/fd \|wc -l** command to query the number of files opened by the current process. In the command, replace *pid* with the ID of the process to be queried.

   .. note::

      -  If a process occupies multiple CPUs, the CPU usage may exceed 100% because the collection result is the total usage of multiple CPUs.
      -  The top 5 processes are not fixed. The process list displays the top 5 processes that have entered the statistical period of 1 minute in the last 24 hours.
      -  The CPU usage, memory usage, and number of opened files are collected only for the top 5 processes for which monitoring has been enabled in the last 24 hours. If such a process has been stopped, its data will not be displayed.
      -  The time in the list indicates the time when the process is created.
      -  If the system time on the client browser is different from that on the monitored ECS, the graph may have no metric data. In this case, synchronize the local time with the ECS time.

To query information about top 5 processes with the highest CPU usages

#. Log in to the management console.

#. Click **Service List** in the upper left corner and select **Cloud Eye**.

#. In the navigation pane on the left, choose **Server Monitoring**.

#. On the **Server Monitoring** page, locate the ECS and click **View Metric** to go to the **OS Monitoring** page.

#. Select the **Process Monitoring** tab.

#. In the **Monitored Processes** area, click |image1| in the upper right corner to view **Top 5 Processes with Highest CPU Usage**.

#. In the displayed **TOP 5 Processes with Highest CPU Usage** window, enable process monitoring for the processes, and click **OK**.

   In the **Monitored Processes** area, the system selects processes in the **Running** state by default and displays CPU usage curves of those processes in **1h**. The displayed data is raw data.

   You can also select the process to be displayed and view its CPU usage curve in **1h**.

   You can click **CPU Usage**, **Memory Usage**, or **Open Files** above the graph to view the curves of different metrics of the currently displayed process. :ref:`Table 2 <en-us_topic_0092358859__table15621123928>` lists **Process Monitoring** metrics.

   .. _en-us_topic_0092358859__table15621123928:

   .. table:: **Table 2** **Process Monitoring** metrics

      +--------------+----------------------------------------------------------------------------------------------------------------+-------------+--------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Metric       | Description                                                                                                    | Value Range | Collection Mode (Linux)                                                              | Collection Mode (Windows)                                                                                                                                                                                                  |
      +==============+================================================================================================================+=============+======================================================================================+============================================================================================================================================================================================================================+
      | CPU Usage    | Specifies the usage of CPU consumed by a process.                                                              | 0-100%      | Monitored object: ECS or BMS                                                         | Monitored object: ECS or BMS                                                                                                                                                                                               |
      |              |                                                                                                                |             |                                                                                      |                                                                                                                                                                                                                            |
      |              | **pHashId** (process name and process ID) is the value of **md5**.                                             |             | Check the metric value changes in file **/proc/pid/stat**.                           | Call Windows API GetProcessTimes to obtain the CPU usage of the process.                                                                                                                                                   |
      +--------------+----------------------------------------------------------------------------------------------------------------+-------------+--------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Memory Usage | Specifies the memory consumed by a process. **pHashId** (process name and process ID) is the value of **md5**. | 0-100%      | Monitored object: ECS or BMS                                                         | Monitored object: ECS or BMS                                                                                                                                                                                               |
      |              |                                                                                                                |             |                                                                                      |                                                                                                                                                                                                                            |
      |              |                                                                                                                |             | **Memory Usage** = **RSS**\ \*\ **PAGESIZE**/**MemTotal**                            | Invoke Windows API procGlobalMemoryStatusEx to obtain the total memory size. Invoke GetProcessMemoryInfo to obtain the used memory size. Use the used memory size to divide the total memory size to get the memory usage. |
      |              |                                                                                                                |             |                                                                                      |                                                                                                                                                                                                                            |
      |              |                                                                                                                |             | **RSS**: Obtain its value by checking the second column of file **/proc/pid/statm**. |                                                                                                                                                                                                                            |
      |              |                                                                                                                |             |                                                                                      |                                                                                                                                                                                                                            |
      |              |                                                                                                                |             | **PAGESIZE**: Obtain its value by running the **getconf PAGESIZE** command.          |                                                                                                                                                                                                                            |
      |              |                                                                                                                |             |                                                                                      |                                                                                                                                                                                                                            |
      |              |                                                                                                                |             | **MemTotal**: Obtain its value by checking file **/proc/meminfo**.                   |                                                                                                                                                                                                                            |
      +--------------+----------------------------------------------------------------------------------------------------------------+-------------+--------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Open Files   | Specifies the number of opened files consumed by the process.                                                  | >= 0        | Monitored object: ECS or BMS                                                         | Not supported                                                                                                                                                                                                              |
      |              |                                                                                                                |             |                                                                                      |                                                                                                                                                                                                                            |
      |              | **pHashId** (process name and process ID) is the value of **md5**.                                             |             | You can run the **ls -l /proc/pid/fd** command to view the number.                   |                                                                                                                                                                                                                            |
      +--------------+----------------------------------------------------------------------------------------------------------------+-------------+--------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

#. Hover your mouse over a graph. In the upper right corner, click |image2| to enlarge the graph for viewing detailed data.

   In the upper left corner, you can see six default monitoring periods: **1h**, **3h**, **12h**, **1d**, **7d**, and **30d**. To view historical monitoring data for any period during the last six months, customize the monitoring period by setting **Select Range** in the upper right corner.

   In the upper left corner of the graph, you can click **Settings** to configure the rollup method.

.. |image1| image:: /_static/images/en-us_image_0146378778.png
.. |image2| image:: /_static/images/en-us_image_0239656150.png
