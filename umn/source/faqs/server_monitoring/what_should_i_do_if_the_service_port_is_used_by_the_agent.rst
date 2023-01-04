:original_name: ces_faq_0037.html

.. _ces_faq_0037:

What Should I Do If the Service Port Is Used by the Agent?
==========================================================

Cloud Eye Agent uses HTTP requests to report data. Any port in the range obtained from path **/proc/sys/net/ipv4/ip_local_port_range** may be occupied. If any service port is used by the Agent, you can modify path **/proc/sys/net/ipv4/ip_local_port_range** and restart the Agent to solve the problem.

Procedure
---------

#. Log in an ECS or BMS as user **root**.

#. Open the **sysctl.conf** file:

   **vim /etc/sysctl.conf**

#. (Permanent change) Add new ports to the **sysctl.conf** file:

   **net.ipv4.ip_local_port_range=49152 65536**

#. Make the modification take effect:

   **sysctl -p /etc/sysctl.conf**

   .. note::

      -  The permanent change still takes effect after the ECS or BMS is restarted.
      -  For temporary modification (which expires after the ECS or BMS is restarted), run **# echo 49152 65536 > /proc/sys/net/ipv4/ip_local_port_range**.

#. Run the following command to restart the Agent:

   **/usr/local/telescope/telescoped restart**

   .. note::

      For Windows, in the directory where the Agent installation package is stored, double-click the **shutdown.bat** script to stop the Agent, and execute the **start.bat** script to start the Agent.
