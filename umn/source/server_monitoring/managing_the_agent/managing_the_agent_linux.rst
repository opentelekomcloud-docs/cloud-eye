:original_name: ces_01_0036.html

.. _ces_01_0036:

Managing the Agent (Linux)
==========================

.. note::

   To view, start, stop, update, and uninstall the Agent, you must log in as user **root**.

Checking the Agent Status
-------------------------

Log in to an ECS or BMS as user **root** and run the following command to check the Agent status:

**service telescoped status**

The following message indicates that the Agent is running properly:

.. code-block::

   "Active (running) or "Telescope process is running well."

Starting the Agent
------------------

**/usr/local/telescope/telescoped start**

Restarting the Agent
--------------------

**/usr/local/telescope/telescoped restart**

Stopping the Agent
------------------

Log in to an ECS or BMS and run the following command to stop the Agent:

**service telescoped stop**

.. note::

   If the Agent installation fails, it may be impossible to stop the Agent. In this case, run the following command to stop the Agent:

   **/usr/local/telescope/telescoped stop**

Uninstalling the Agent
----------------------

Run the following command to uninstall the Agent:

**/usr/local/telescope/uninstall.sh**

.. important::

   You can manually uninstall the Agent. After the uninstallation, Cloud Eye does not collect the ECS or BMS monitoring data every one minute. To use the Agent again, reinstall it by referring to :ref:`Installing and Configuring the Agent on a Linux ECS or BMS <ces_01_0004>`. Before reinstalling the Agent, manually delete the previous Agent installation package.
