:original_name: ces_01_0037.html

.. _ces_01_0037:

Managing the Agent (Windows)
============================

This section describes how to view, start, stop, uninstall, restart, or upgrade the Agent on the Windows platform.

Earlier version: The Agent is installed in the directory where the Agent installation package is decompressed, for example, if the package is decompressed in **D:\\Agent**, the installation path would be **D:\\Agent\\telescope_windows_amd64**.

New version: The default Agent installation path is **C:\\Program Files\\uniagent\\extension\\install\\telescope**.

Checking the Agent Status
-------------------------

In the task manager, check the status of the telescope process.

Starting the Agent
------------------

In the directory where the Agent installation package is stored, double-click the **start.bat** script.

Stopping the Agent
------------------

In the directory where the Agent installation package is stored, double-click the **shutdown.bat** script.

.. _ces_01_0037__en-us_topic_0078544026_section15609921194423:

Uninstalling the Agent
----------------------

In the directory where the Agent installation package is stored, double-click the **uninstall.bat** script.

.. important::

   Before reinstalling the Agent, manually delete the previous Agent installation package.

Restarting the Agent
--------------------

#. In the Agent installation directory, double-click the **shutdown.bat** script to stop the Agent.
#. Double-click the **start.bat** script to start the Agent.

Upgrading the Agent
-------------------

If the current Agent version is not the desired one, you can upgrade the Agent. The Cloud Eye Agent will be continuously upgraded to provide you with a better monitoring experience.

#. Uninstall the Agent of the current version. For details, see :ref:`Uninstalling the Agent <ces_01_0037__en-us_topic_0078544026_section15609921194423>`.
#. Install the Agent of the latest version. For details, see :ref:`Installing the Agent on a Windows server <en-us_topic_0110258146>`.
