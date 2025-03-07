:original_name: ces_01_0017.html

.. _ces_01_0017:

Creating a Resource Group
=========================

Scenarios
---------

If you use multiple cloud services, you can add all related resources, such as ECSs, BMSs, EVS disks, elastic IP addresses, bandwidths, and databases to the same resource group for easier management and O&M.

Restrictions
------------

-  Each user can create up to 1,000 resource groups.
-  A resource group can contain 1 to 1,000 cloud service resources.
-  There are restrictions on the number of resources of different types that can be added to a resource group. For details, see the tips on the Cloud Eye console.

Procedure
---------

#. Log in to the management console.

#. In the upper left corner, select a region and project.

#. Click **Service List** in the upper left corner and select **Cloud Eye**.

#. In the navigation pane on the left, choose **Resource Groups**.

#. In the upper right corner, click **Create Resource Group**.


   .. figure:: /_static/images/en-us_image_0000001902856296.png
      :alt: **Figure 1** Creating a resource group

      **Figure 1** Creating a resource group

#. Enter a group name, select the cloud service resources to be added, and optionally set **Enterprise Project**.

   You are advised to associate an enterprise project. After an enterprise project is associated, resources added to or deleted from the enterprise project are automatically added to or deleted from the resource group. If resources are frequently added or deleted, you can improve the efficiency of maintaining resource groups.


   .. figure:: /_static/images/en-us_image_0000001787894604.png
      :alt: **Figure 2** Selecting cloud service resources

      **Figure 2** Selecting cloud service resources

   .. note::

      You can search for ECSs and BMSs by name, ID, and private IP address. For other cloud resources, you can search by name, ID, or tag.

#. Click **Create**.
