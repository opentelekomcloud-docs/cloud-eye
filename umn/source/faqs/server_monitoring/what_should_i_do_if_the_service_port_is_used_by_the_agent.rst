:original_name: ces_faq_0037.html

.. _ces_faq_0037:

What Should I Do If the Service Port Is Used by the Agent?
==========================================================

Cloud Eye Agent uses HTTP requests to report data. Any port in the range obtained from path **/proc/sys/net/ipv4/ip_local_port_range** may be occupied. If any service port is used by the Agent, you can modify path **/proc/sys/net/ipv4/ip_local_port_range** and restart the Agent to solve the problem.

Linux
-----

#. Log in an ECS or BMS as user **root**.

#. Open the **sysctl.conf** file.

   .. code-block::

      vim /etc/sysctl.conf

#. (Permanent change) Add new ports to the **sysctl.conf** file.

   .. code-block::

      net.ipv4.ip_local_port_range=49152 65536

#. Apply the changes.

   .. code-block::

      sysctl -p /etc/sysctl.conf

   .. note::

      -  The permanent change still takes effect after the ECS or BMS is restarted.
      -  For temporary changes (which expires after the ECS or BMS is restarted), run the **# echo 49152 65536 > /proc/sys/net/ipv4/ip_local_port_range** command.

#. Restart the Agent.

   Earlier version:

   .. code-block::

      /usr/local/telescope/telescoped restart

   New version:

   .. code-block::

      service ces-uniagent stop
      service ces-uniagent start
      /usr/local/uniagent/extension/install/telescope/telescoped restart

Windows
-------

#. Log in to the ECS as an administrator.

#. Open Windows PowerShell and run the following command to change the number of ports:

   .. code-block::

      netsh int ipv4 set dynamicportrange tcp start=49152 num=16384

#. Go to the Agent installation directory, double-click the **shutdown.bat** script to stop the Agent, and then run the **start.bat** script to start the Agent.

   Earlier version: The Agent is installed in the directory where the Agent installation package is decompressed, for example, if the package is decompressed in **D:\\Agent**, the installation path would be **D:\\Agent\\telescope_windows_amd64**.

   New version: The default Agent installation path is **C:\\Program Files\\uniagent\\extension\\install\\telescope**.
