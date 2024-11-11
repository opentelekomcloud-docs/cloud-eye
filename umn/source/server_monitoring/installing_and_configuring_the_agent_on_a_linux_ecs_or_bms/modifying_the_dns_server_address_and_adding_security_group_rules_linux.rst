:original_name: en-us_topic_0150354069.html

.. _en-us_topic_0150354069:

Modifying the DNS Server Address and Adding Security Group Rules (Linux)
========================================================================

Scenarios
---------

This topic describes how to add the DNS server address and security group rules to a Linux ECS or BMS to ensure successful downloading of the Agent installation package and successful monitoring data collection. This topic takes an ECS as an example. The operations for BMSs are similar.

You can modify the DNS server address of an ECS via command lines or the management console.

.. note::

   DNS and security group configuration are intended for the primary NIC.

Modifying the DNS Server Address (Command Lines)
------------------------------------------------

The following describes how to add the DNS server address to the **resolv.conf** file using command lines.

To use the management console, see :ref:`Modifying the DNS Server Address (Management Console) <en-us_topic_0150354069__section13121312218>`.

#. Log in to an ECS as user **root**.

#. Run the **vi /etc/resolv.conf** command to open the file.

#. Add the DNS server address, for example, **nameserver 100.125.4.25** to the file. Enter **:wq** and press **Enter** to save the change.


   .. figure:: /_static/images/en-us_image_0183510251.png
      :alt: **Figure 1** Adding the DNS server address (Linux)

      **Figure 1** Adding the DNS server address (Linux)

.. _en-us_topic_0150354069__section13121312218:

Modifying the DNS Server Address (Management Console)
-----------------------------------------------------

The following describes how to modify the DNS server address of an ECS on the management console. This topic takes an ECS as an example. The operations for BMSs are similar.

#. In the upper left corner, select a region and project.

#. Click **Service List** in the upper left corner. Under **Compute**, select **Elastic Cloud Server**.

   On the ECS console, click the name of the ECS to view its details.

#. Click the VPC name on the right of **VPC** to go to the VPC console.

#. Click the name of the VPC.

#. In the **Networking Components** area, click the number following **Subnets**.

   The **Subnets** page is displayed.

#. In the subnet list, click the name of the subnet.

#. In the **Gateway and DNS Information** area, click |image1| following **DNS Server Address**.

#. Change the DNS server address to **100.125.4.25**.

#. Click **OK**.

   .. note::

      The new DNS server address takes effect after the ECS or BMS is restarted.

Modifying the ECS Security Group Rules (Management Console)
-----------------------------------------------------------

The following describes how to modify security group rules for an ECS on the management console. The operations for BMSs are similar.

#. On the ECS details page, click the **Security Groups** tab.

   The security group list is displayed.

#. Click the security group name.

#. Click **Modify Security Group Rule**.

   The security group details page is displayed.

   .. note::

      Procedure for BMS:

      a. Click the security group ID on the upper left.
      b. Click **Manage Rule** in the **Operation** column of the security group.

#. Click the **Outbound Rules** tab, and click **Add Rule**.

#. Add rules based on :ref:`Table 1 <en-us_topic_0150354069__table168311845185818>`.

   .. _en-us_topic_0150354069__table168311845185818:

   .. table:: **Table 1** Security group rules

      +-------------+------+------+----------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Protocol    | Port | Type | Destination    | Description                                                                                                                                                                                                                       |
      +=============+======+======+================+===================================================================================================================================================================================================================================+
      | TCP         | 80   | IPv4 | 100.125.0.0/16 | Used to download the Agent installation package from an OBS bucket to an ECS or BMS and obtain the ECS or BMS metadata and authentication information.                                                                            |
      +-------------+------+------+----------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | TCP and UDP | 53   | IPv4 | 100.125.0.0/16 | Used by DNS to resolve domain names, for example, resolve the OBS domain name when you are downloading the Agent installation package, and resolve the Cloud Eye endpoint when the Agent is sending monitoring data to Cloud Eye. |
      +-------------+------+------+----------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | TCP         | 443  | IPv4 | 100.125.0.0/16 | Used to collect monitoring data and send the data to Cloud Eye.                                                                                                                                                                   |
      +-------------+------+------+----------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. |image1| image:: /_static/images/en-us_image_0000001200355919.png
