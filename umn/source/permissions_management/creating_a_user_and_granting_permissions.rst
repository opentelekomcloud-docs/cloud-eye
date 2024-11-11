:original_name: ces_01_0090.html

.. _ces_01_0090:

Creating a User and Granting Permissions
========================================

You can use `IAM <https://docs.otc.t-systems.com/usermanual/iam/iam_01_0026.html>`__ for fine-grained permissions control for your Cloud Eye resources. With IAM, you can:

-  Create IAM users for employees based on your enterprise's organizational structure. Each IAM user will have their own security credentials for accessing Cloud Eye resources.
-  Grant different permissions to IAM users based on their job responsibilities.
-  Entrust an account or a cloud service to perform efficient O&M on your Cloud Eye resources.

If your account does not require individual IAM users, skip this topic.

This topic describes the procedure for granting permissions (see :ref:`Figure 1 <ces_01_0090__fig129774214310>`).

Prerequisites
-------------

You have learned about the system policies of Cloud Eye before assigning the preset Cloud Eye permissions to user groups (if needed). To grant custom permissions to a user group, ensure that you have :ref:`created a custom Cloud Eye policy <ces_01_0091>`.

For details about the system policies supported by Cloud Eye and the comparison between these policies, see :ref:`Permissions <ces_07_0009>`.

Process Flow
------------

.. _ces_01_0090__fig129774214310:

.. figure:: /_static/images/en-us_image_0000002051460077.png
   :alt: **Figure 1** Process for granting Cloud Eye permissions

   **Figure 1** Process for granting Cloud Eye permissions

#. .. _ces_01_0090__li10269636890:

   `Create a user group and assign permissions <https://docs.otc.t-systems.com/usermanual/iam/iam_01_0030.html>`__.

   Create a user group on the IAM console, and attach the **CES Administrator**, **Tenant Guest**, and **Server Administrator** policies to the group.

   .. note::

      -  Cloud Eye is a region-specific service and must be deployed in specific physical regions. Cloud Eye permissions can be assigned and take effect only in specific regions. If you want a permission to take effect for all regions, assign it in all these regions. The global permission does not take effect.
      -  The preceding permissions are all Cloud Eye permissions. For more refined Cloud Eye permissions, see :ref:`Permissions <ces_07_0009>`.

#. `Create a user and add it to a user group. <https://docs.otc.t-systems.com/usermanual/iam/iam_01_0031.html>`__ Create a user on the IAM console and add the user to the group created in :ref:`1 <ces_01_0090__li10269636890>`.

#. `Log in <https://docs.otc.t-systems.com/usermanual/iam/iam_01_0032.html>`__ and verify permissions.

   Log in to the Cloud Eye console as the created user, and verify that the user only has the **CES Administrator** permissions. After you log in to the Cloud Eye console and use related functions, if no authentication failure message is displayed, the authorization is successful.
