:original_name: ces_01_0019.html

.. _ces_01_0019:

Resource Group List
===================

The resource group list displays all resource groups you have on Cloud Eye, the resources they contain, and the health status of each resource group.

Procedure
---------

#. Log in to the management console.

#. In the upper left corner, select a region and project.

#. Click **Service List** in the upper left corner and select **Cloud Eye**.

#. In the navigation pane on the left, choose **Resource Groups**.

   On the **Resource Groups** page, you can view all the resource groups that have been created.

   .. table:: **Table 1** Parameters of the resource group list

      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                                    |
      +===================================+================================================================================================================================+
      | Name/ID                           | Specifies the resource group name and ID.                                                                                      |
      |                                   |                                                                                                                                |
      |                                   | .. note::                                                                                                                      |
      |                                   |                                                                                                                                |
      |                                   |    The group name can contain a maximum of 128 characters. Only letters, digits, hyphens (-), and underscores (_) are allowed. |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------+
      | Status (Metric Monitoring)        | -  OK: No alarms are generated for resources in the group.                                                                     |
      |                                   | -  In alarm: An alarm is being generated for a resource in the group.                                                          |
      |                                   | -  No alarm rules set: No alarm rules have been created for any resource in the group.                                         |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------+
      | Resources (Alarm/Total)           | Total number of resources that are generating alarms in a group/Total number of resources in the group.                        |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------+
      | (Optional) Enterprise Project     | Specifies the name of the enterprise project that has the resource group permission.                                           |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------+
      | Add Resources                     | Specifies how you add resources to a resource group. The value can be **Manually** or **Automatically**.                       |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------+
      | Created                           | Specifies the time when the resource group was created.                                                                        |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------+
      | Operation                         | You can create alarm rules or delete a resource group.                                                                         |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------+
