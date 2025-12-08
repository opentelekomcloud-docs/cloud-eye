:original_name: ces_faq_0126.html

.. _ces_faq_0126:

How Do I Enable or Disable Metric Collection by Modifying the Configuration File?
=================================================================================

This following describes how to enable or disable metric collection by modifying the configuration file.

.. note::

   This operation applies only to Agent 2.7.2 or later.

Modifying the Configuration File to Enable Metric Collection
------------------------------------------------------------

#. Log in to a server as the root user (Linux) or as an administrator (Windows).
#. Modify the **custom_conf.json** file.

   a. Go to the configuration file directory.

      Windows:

      .. code-block::

         cd C:\Program Files\uniagent\extension\install\telescope\conf

      Linux:

      .. code-block::

         cd /usr/local/uniagent/extension/install/telescope/conf

   b. Open the **custom_conf.json** file.

      .. code-block::

         vi custom_conf.json

   c. Enter the following configuration content in {}. Replace **metric_name1** and **metric_name2** with the metric values in :ref:`What Metrics Are Supported by the Agent <ces_faq_2513>`.

      .. code-block::

         "telescope.metric.metric_name1.enable": "true",
         "telescope.metric.metric_name2.enable": "true"

      Example: :ref:`Figure 1 <ces_faq_0126__en-us_topic_0000002239812385_fig17191645155716>` shows the configuration content for enabling metric collection for cpu_usage and cpu_usage_idle.

      .. _ces_faq_0126__en-us_topic_0000002239812385_fig17191645155716:

      .. figure:: /_static/images/en-us_image_0000002461365577.png
         :alt: **Figure 1** Enabling metric collection for cpu_usage and cpu_usage_idle

         **Figure 1** Enabling metric collection for cpu_usage and cpu_usage_idle

#. Restart the Agent.

   -  Windows:

      a. In the **C:\\Program Files\\uniagent\\extension\\install\\telescope** directory, double-click **shutdown.bat** to stop the Agent, and then run **start.bat** to start the Agent.
      b. In the **C:\\Program Files\\uniagent\\script** directory, double-click **shutdown.bat** to stop the Agent, and then run **start.bat** to start the Agent.

   -  Linux:

      .. code-block::

         service ces-uniagent stop
         service ces-uniagent start
         /usr/local/uniagent/extension/install/telescope/telescoped restart

Modifying the Configuration File to Disable Metric Collection
-------------------------------------------------------------

#. Log in to the server as the root user (Linux) or as an administrator (Windows).
#. Modify the **custom_conf.json** file.

   a. Go to the configuration file directory.

      Windows:

      .. code-block::

         cd C:\Program Files\uniagent\extension\install\telescope\conf

      Linux:

      .. code-block::

         cd /usr/local/uniagent/extension/install/telescope/conf

   b. Open the **custom_conf.json** file.

      .. code-block::

         vi custom_conf.json

   c. Enter the following configuration content in {}. Replace **metric_name1** and **metric_name2** with the metric values in :ref:`What Metrics Are Supported by the Agent <ces_faq_2513>`.

      .. code-block::

         "telescope.metric.metric_name1.enable": "false",
         "telescope.metric.metric_name2.enable": "false"

      Example: :ref:`Figure 2 <ces_faq_0126__en-us_topic_0000002239812385_fig17531214152718>` shows the configuration content for disabling metric collection for cpu_usage and cpu_usage_idle.

      .. _ces_faq_0126__en-us_topic_0000002239812385_fig17531214152718:

      .. figure:: /_static/images/en-us_image_0000002462468769.png
         :alt: **Figure 2** Disabling metric collection for cpu_usage and cpu_usage_idle

         **Figure 2** Disabling metric collection for cpu_usage and cpu_usage_idle

#. Restart the Agent.

   -  Windows:

      a. In the **C:\\Program Files\\uniagent\\extension\\install\\telescope** directory, double-click **shutdown.bat** to stop the Agent, and then run **start.bat** to start the Agent.
      b. In the **C:\\Program Files\\uniagent\\script** directory, double-click **shutdown.bat** to stop the Agent, and then run **start.bat** to start the Agent.

   -  Linux:

      .. code-block::

         service ces-uniagent stop
         service ces-uniagent start
         /usr/local/uniagent/extension/install/telescope/telescoped restart
