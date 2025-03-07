:original_name: en-us_topic_0150366044.html

.. _en-us_topic_0150366044:

Modifying the DNS Server Address and Adding Security Group Rules (Windows)
==========================================================================

Scenarios
---------

This topic describes how to add the DNS server address and security group rules to a Windows ECS to ensure successful downloading of the Agent installation package and successful monitoring data collection.

The DNS server address of an ECS can be modified in either of the following ways: Windows GUI or management console. Choose a method based on your habits.

.. note::

   DNS and security group configuration are intended for the primary NIC.

Modifying the DNS Server Address (Windows GUI)
----------------------------------------------

The following describes how to use the Windows GUI to add the DNS server address.

#. Click **Service List** in the upper left corner. Under **Compute**, select **Elastic Cloud Server**. Use VNC to log in to the Windows ECS.
#. Choose **Control Panel** > **Network and Sharing Center**, and click **Change adapter settings**.
#. Right-click the used network, choose **Settings** from the shortcut menu, and configure the DNS.

Modifying the DNS Server Address (Management Console)
-----------------------------------------------------

The following describes how to modify the DNS server address of an ECS on the management console. This section takes an ECS as an example. The operations for BMSs are similar.

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

      The new DNS server address is applied after the ECS or BMS is restarted.

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

#. Add rules based on :ref:`Table 1 <en-us_topic_0150366044__en-us_topic_0150354069_table168311845185818>`.

   .. _en-us_topic_0150366044__en-us_topic_0150354069_table168311845185818:

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
