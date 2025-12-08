:original_name: ces_faq_0128.html

.. _ces_faq_0128:

How Do I Change the Process Collection Frequency by Modifying the Configuration File?
=====================================================================================

The following describes how to modify the configuration file to change the process collection frequency.

.. note::

   This operation applies only to Agent 2.7.2 or later.

Linux
-----

#. Log in to a server as user **root**.

#. Modify the configuration file.

   .. code-block::

      cd /usr/local/uniagent/extension/install/telescope/conf && vi custom_conf.json

   Enter the following configuration content in {} to change the number of processes updated per minute. The calculation method is as follows: (*${telescope.metric.proc.flush_metric_batch_size}* x *${telescope.metric.proc.flush_metric_period}*)/60

   .. code-block::

      "telescope.metric.proc.flush_metric_batch_size":"num1",
      "telescope.metric.proc.flush_metric_period":"num2"

   Configurations for updating 50 processes per minute

   |image1|

#. Restart the Agent.

   .. code-block::

      service ces-uniagent stop
      service ces-uniagent start
      /usr/local/uniagent/extension/install/telescope/telescoped restart

Windows
-------

#. Log in to a server.

#. Modify the **custom_conf.json** configuration file in **C:\\Program Files\\uniagent\\extension\\install\\telescope\\conf** to change the number of processes updated per minute. The calculation method is as follows: (*${telescope.metric.proc.flush_metric_batch_size}* x *${telescope.metric.proc.flush_metric_period}*)/60

   Example: If you want to update 50 processes every minute, enter the following content in {}:

   .. code-block::

      "telescope.metric.proc.flush_metric_batch_size":"50",
      "telescope.metric.proc.flush_metric_period":"60"

#. In the **C:\\Program Files\\uniagent\\extension\\install\\telescope** directory, restart the Agent.

   a. Double-click **shutdown.bat** to stop the Agent process.
   b. Double-click **start.bat** to start the Agent process.

.. |image1| image:: /_static/images/en-us_image_0000002461366529.png
