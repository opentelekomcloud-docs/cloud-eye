:original_name: ces_01_0036.html

.. _ces_01_0036:

Managing the Agent (Linux)
==========================

This section describes how to view, start, stop, restart, uninstall, or upgrade the Agent on the Linux platform.

.. note::

   To view, start, stop, restart, or uninstall the Agent, you need to log in to the server as user **root**.

.. _ces_01_0036__section73001644182214:

Viewing the Agent Version
-------------------------

#. Log in to an ECS as user **root**.

#. Run the following command to check the Agent version:

   **if [[ -f /usr/local/uniagent/extension/install/telescope/bin/telescope ]]; then /usr/local/uniagent/extension/install/telescope/bin/telescope -v; elif [[ -f /usr/local/telescope/bin/telescope ]]; then echo "old agent"; else echo 0; fi**

   -  If **old agent** is returned, the earlier version of the Agent is used. Manage the Agent based on its version.
   -  If a version is returned, the new version of the Agent is used. Manage the Agent based on its version.
   -  If **0** is returned, the Agent is not installed.

      .. note::

         The new version of the Agent consists of two processes: Telescope and UniAgent. The Telescope process is used to collect and report metrics, and the UniAgent process is used to manage the Telescope lifecycle.

Checking the Agent Status (New Version)
---------------------------------------

Log in to an ECS or BMS as user **root** and check the Agent status.

**service ces-uniagent status**

.. note::

   -  If the command output contains **active (running)**, the UniAgent is running properly and can manage the Telescope lifecycle.
   -  If the command output contains **inactive (dead)**, the UniAgent is not running and cannot manage the Telescope lifecycle.

**/usr/local/uniagent/extension/install/telescope/telescoped status**

.. note::

   -  If the following information is displayed, the Telescope is running properly and can collect and report metrics.

      .. code-block::

         Telescope process is running well.

   -  If the following information is displayed, the Telescope stops working and cannot collect or report metrics.

      .. code-block::

         Telescope process is not running.

Starting the Agent (New Version)
--------------------------------

Start the Agent.

**service ces-uniagent start**

**/usr/local/uniagent/extension/install/telescope/telescoped start**

Restarting the Agent (New Version)
----------------------------------

Restart the Agent.

**service ces-uniagent stop**

**service ces-uniagent start**

**/usr/local/uniagent/extension/install/telescope/telescoped restart**

Stopping the Agent (New Version)
--------------------------------

Log in to an ECS or BMS and stop the Agent.

**service ces-uniagent stop**

**/usr/local/uniagent/extension/install/telescope/telescoped stop**

.. _ces_01_0036__en-us_topic_0078544026_section15609921194423:

Uninstalling the Agent (New Version)
------------------------------------

You can manually uninstall the Agent. After the uninstallation, Cloud Eye does not support monitoring by seconds for ECSs or BMSs. To use the Agent again, reinstall it by referring to :ref:`Installing and Configuring the Agent on a Linux ECS or BMS <ces_01_0004>`.

Uninstall the Agent.

**cd /usr/local/uniagent/script/**

**./uninstall.sh**

.. important::

   Before reinstalling the Agent, run the following command to manually remove the original Agent installation package:

   .. code-block::

      rm /usr/local/uniagent_install_amd64.sh

Checking the Agent Status (Earlier Version)
-------------------------------------------

Log in to an ECS or BMS as user **root** and check the Agent status.

**service telescoped status**

The following message indicates that the Agent is running properly:

.. code-block::

   "Active (running) or "Telescope process is running well."

Starting the Agent (Earlier Version)
------------------------------------

Start the Agent.

**/usr/local/telescope/telescoped start**

Restarting the Agent (Earlier Version)
--------------------------------------

Restart the Agent.

**/usr/local/telescope/telescoped restart**

Stopping the Agent (Earlier Version)
------------------------------------

Log in to an ECS or BMS and run the following command to stop the Agent:

**service telescoped stop**

.. note::

   If the Agent installation fails, it may be impossible to stop the Agent. In this case, run the following command to stop the Agent:

   **/usr/local/telescope/telescoped stop**

.. _ces_01_0036__section828002816109:

Uninstalling the Agent (Earlier Version)
----------------------------------------

Uninstall the Agent.

**/usr/local/telescope/uninstall.sh**

.. important::

   You can manually uninstall the Agent. After the uninstallation, Cloud Eye does not support monitoring by seconds (60s by default) for ECSs or BMSs. To use the Agent again, reinstall it by referring to :ref:`Installing and Configuring the Agent on a Linux ECS or BMS <ces_01_0004>`. Before reinstalling the Agent, manually delete the previous Agent installation package.

Upgrading the Agent
-------------------

If the current Agent version is not the desired one, you can upgrade the Agent. The Cloud Eye Agent will be continuously upgraded to provide you with a better monitoring experience.

#. Uninstall the Agent of the current version.

   -  If **old agent** is returned in :ref:`Viewing the Agent Version <ces_01_0036__section73001644182214>`, the current Agent is using an earlier version. In this case, run the command in :ref:`Uninstalling the Agent (Earlier Version) <ces_01_0036__section828002816109>`.
   -  If a version number is returned in :ref:`Viewing the Agent Version <ces_01_0036__section73001644182214>`, the current Agent is using the new version. In this case, run the command in :ref:`Uninstalling the Agent (New Version) <ces_01_0036__en-us_topic_0078544026_section15609921194423>`.

#. Install the Agent of the latest version by running the command in :ref:`Installing the Agent on a Linux Server <ces_01_0029>`.
