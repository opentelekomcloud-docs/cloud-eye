:original_name: ces_01_0017.html

.. _ces_01_0017:

Creating a Resource Group
=========================

Scenarios
---------

If you use multiple cloud services, you can add all related resources, such as ECSs, BMSs, EVS disks, elastic IP addresses, bandwidths, and databases to the same resource group for easier management and O&M.

Restrictions
------------

-  Each user can create up to 10 resource groups.
-  A resource group must contain 1 to 200 cloud service resources.
-  There are restrictions on the number of resources of different types that can be added to a resource group. For details, see the tips on the Cloud Eye console.

Procedure
---------

#. Log in to the management console.

#. In the upper left corner, select a region and project.

#. Click **Service List** in the upper left corner, and select **Cloud Eye**.

#. In the navigation pane on the left, choose **Resource Groups**.

#. In the upper right corner, click **Create Resource Group**.

#. Enter the group name.

#. Select the target cloud service resources.

   .. note::

      You can search for ECSs and BMSs by name, ID, and private IP address. For other cloud services, you can search only by name and ID.

#. Click **Create**.
