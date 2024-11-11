:original_name: ces_01_0030.html

.. _ces_01_0030:

Restoring the Agent Configurations on a Linux Server
====================================================

Scenarios
---------

This topic describes how to restore the Agent configurations on the Cloud Eye console (recommended).

.. note::

   -  The **Restore Agent Configurations** option is unavailable for BMSs. For details, see :ref:`(Optional) Manually Configuring the Agent (Linux) <ces_01_0031>`.
   -  After you configure the Agent, its status is still displayed as **Not installed** because no monitoring data is reported yet. Wait 3 to 5 minutes and refresh the page.
   -  If the Agent is in the **Running** state, the Agent has been installed and has started to collect fine-grained metric data.

Restoring the Agent Configurations
----------------------------------

#. Log in to the management console.

#. Click **Service List** in the upper left corner and select **Cloud Eye**. In the navigation pane on the left, choose **Server Monitoring**.

#. On the **Server Monitoring** page, select a server that has the Agent installed.

#. Click **Restore Agent Configurations**.

#. In the displayed **Restore Agent Configurations** dialog box, click **One-Click Restore**.

   If the Agent status changes to **Running**, the Agent has been installed and has started to collect fine-grained metric data.
