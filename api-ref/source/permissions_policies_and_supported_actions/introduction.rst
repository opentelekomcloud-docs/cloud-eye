:original_name: ces_03_0046.html

.. _ces_03_0046:

Introduction
============

This chapter describes fine-grained permissions management for your Cloud Eye. If your account does not need individual IAM users, then you may skip over this chapter.

Policies: A type of fine-grained authorization mechanism that defines permissions required to perform operations on specific cloud resources under certain conditions. This mechanism allows for more flexible policy-based authorization, meeting requirements for secure access control. By default, new IAM users do not have any permissions assigned. You need to add a user to one or more groups, and assign permissions policies to these groups. The user then inherits permissions from the groups it is a member of. This process is called authorization. After authorization, the user can perform specified operations on Cloud Eye based on the permissions.

You can grant users permissions by using roles and policies. A policy consists of permissions for an entire service. Users with such a policy assigned are granted all of the permissions required for that service. Policies define API-based permissions for operations on specific resources, allowing for more fine-grained, secure access control of cloud resources.

.. note::

   If you want to allow or deny the access to an API, use policies for authorization.

An account has all the permissions required to call all APIs, but IAM users must be assigned the required permissions. The permissions required for calling an API are determined by the actions supported by the API. Only users who have been granted permissions allowing the actions can call the API successfully. For example, if an IAM user queries the alarm rule list using an API, the user must have been granted permissions that allow the **ces:alarms:list** action.

Supported Actions
-----------------

Cloud Eye provides system-defined policies that can be directly used in IAM. You can also create custom policies and use them to supplement system-defined policies, implementing more refined access control. Operations supported by policies are specific to APIs. The following are common concepts related to policies:

-  Permissions: Defined by actions in a custom policy.
-  Actions: Added to a custom policy to control permissions for specific operations.
-  Related actions: Actions on which a specific action depends to take effect. When assigning permissions for the action to a user, you also need to assign permissions for the dependent actions.
-  Authorization Scope: A custom policy can be applied to IAM projects or enterprise projects or both. Policies that contain actions supporting both IAM and enterprise projects can be assigned to user groups and take effect in both IAM and Enterprise Management. Policies that only contain actions supporting IAM projects can be assigned to user groups and only take effect for IAM. Such policies will not take effect if they are assigned to user groups in Enterprise Management.
-  APIs: REST APIs that can be called in a custom policy

Cloud Eye supports the following actions that can be defined in custom policies:

.. note::

   Y indicates that the item is supported, and x indicates that the item is not supported.

:ref:`Supported Actions of the API Version Management APIs <ces_03_0047>`

:ref:`Supported Actions of the Metric Management API <ces_03_0048>`

:ref:`Supported Actions of the Alarm Rule Management APIs <ces_03_0049>`

:ref:`Supported Actions of the Monitoring Data Management APIs <ces_03_0050>`

:ref:`Supported Actions of the Quota Management API <ces_03_0051>`

:ref:`Supported Actions of the Event Monitoring API <ces_03_0052>`
