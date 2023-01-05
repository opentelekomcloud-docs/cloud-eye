:original_name: ces_01_0019.html

.. _ces_01_0019:

Resource Group List
===================

The resource group list displays all resource groups you have on Cloud Eye, the resources they contain, and the health status of each resource group.

Procedure
---------

#. Log in to the management console.

#. In the upper left corner, select a region and project.

#. Click **Service List** in the upper left corner, and select **Cloud Eye**.

#. In the navigation pane on the left, choose **Resource Groups**.

   On the **Resource Groups** page, you can view all the resource groups that have been created.

   .. table:: **Table 1** Parameters of the resource group list

      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                                                                                                                               |
      +===================================+===========================================================================================================================================================================================================================+
      | Name/ID                           | Specifies the resource group name and ID.                                                                                                                                                                                 |
      |                                   |                                                                                                                                                                                                                           |
      |                                   | .. note::                                                                                                                                                                                                                 |
      |                                   |                                                                                                                                                                                                                           |
      |                                   |    The group name can contain a maximum of 128 characters. Only letters, digits, hyphens (-), and underscores (_) are allowed.                                                                                            |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Health Status                     | -  **Healthy**: No alarms have been generated for the group.                                                                                                                                                              |
      |                                   | -  **Unhealthy**: An alarm or alarms have been generated for a resource or resources in the group.                                                                                                                        |
      |                                   | -  **No alarm rule**: No alarm rules have been set for the group.                                                                                                                                                         |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Unhealthy Resources               | Specifies the number of resources in a group whose alarms have been triggered. For example, if there are two ECSs and one EVS disk that are in the **Alarm** state in a resource group, **Unhealthy Resources** is **3**. |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Total Resources                   | Specifies the number of resources in a group. For example, if there are four resources, namely, two ECSs, one EVS disk, and one elastic IP address in a resource group, **Total Resources** is **4**.                     |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Resource Types                    | Specifies the number of different resource types in a group. For example, if there are two ECSs and one EVS disk in a resource group, then there are two types of resources and **Resource Types** is **2**.              |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Created                           | Specifies the time when the resource group was created.                                                                                                                                                                   |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Operation                         | Specifies the operations that can be performed on a resource group. You can only modify or delete a resource group.                                                                                                       |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
