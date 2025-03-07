:original_name: ces_01_0091.html

.. _ces_01_0091:

Cloud Eye Custom Policies
=========================

Custom policies can be created to supplement the system-defined policies of Cloud Eye. For the actions that can be added to custom policies, see :ref:`Table 3 <ces_07_0009__table1289923815224>` in .

You can create custom policies in either of the following two ways:

-  Visual editor: Select cloud services, actions, resources, and request conditions. This does not require knowledge of policy syntax.
-  JSON: Edit JSON policies from scratch or based on an existing policy.

For details, see `Creating a Custom Policy <https://docs.otc.t-systems.com/identity-access-management/umn/user_guide/permissions/creating_a_custom_policy.html>`__. This topic contains examples of common Cloud Eye custom policies.

Example Custom Policies
-----------------------

-  Example 1: allowing users to modify alarm rules

   .. code-block::

      {
            "Version": "1.1",
            "Statement": [
                  {
                        "Action": [
                              "ces:alarms:put"
                        ],
                        "Effect": "Allow"
                  }
            ]
      }

-  Example 2: denying alarm rule deletion

   A policy with only "Deny" permissions must be used in conjunction with other policies to take effect. If the permissions assigned to a user contain both "Allow" and "Deny", the "Deny" permissions take precedence over the "Allow" permissions.

   The following method can be used if you need to assign permissions of the **CES FullAccess** policy to a user but you want to prevent the user from deleting alarm rules. Create a custom policy for denying alarm rule deletion, and attach both policies to the group the user belongs. Then the user can perform all operations on alarm rules except deleting alarm rules. The following is an example of a deny policy:

   .. code-block::

      {
            "Version": "1.1",
            "Statement": [
                  {
                        "Action": [
                              "ces:alarms:delete"
                        ],
                        "Effect": "Deny"
                  }
            ]
      }

-  Example 3: allowing users to create, modify, query, and delete alarm rules

   A custom policy can contain the actions of multiple services that are of the global or project-level type. The following is a policy with multiple actions:

   .. code-block::

      {
            "Version": "1.1",
            "Statement": [
                  {
                        "Action": [
                              "ces:alarms:create",
                              "ces:alarms:put",
                              "ces:alarms:list",
                              "ces:alarms:delete"
                        ],
                        "Effect": "Allow"
                  }
            ]
      }
