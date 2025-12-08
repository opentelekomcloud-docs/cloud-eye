:original_name: ces_faq_2502.html

.. _ces_faq_2502:

How Do I Configure an Agency?
=============================

To enable you to monitor servers more securely and efficiently, Cloud Eye provides the latest Agent permission-granting method. That is, before installing Agents, you only need to click **Configure** on the **Server Monitoring** page of the Cloud Eye console, the system will perform temporary AK/SK authorization for the Agents installed on all ECSs or BMSs in the region. And in the future, newly created ECSs or BMSs in this region will automatically get this authorization. This section describes the authorization as follows:

-  Authorization object

   On the Cloud Eye console, if you choose **Server Monitoring** > **Elastic Cloud Server** (or **Bare Metal Server**), select a server, and click **Configure**, the system will create an agency named **cesagency** on IAM. The agency permissions are automatically granted to Cloud Eye internal account **op_svc_ces**.

   .. note::

      If the system displays a message indicating that the tenant does not have insufficient permissions, see :ref:`What Can I Do If the System Displays a Message Indicating Insufficient Permissions When I Click Configure on the Server Monitoring Page? <ces_faq_0072>`

-  Authorization scope

   Add the **CES AgentAccess** permissions to internal account **op_svc_ces** in the region.

-  Authorization reason

   The Cloud Eye Agent runs on ECSs or BMSs and reports the collected monitoring data to Cloud Eye. After being authorized, the Agent automatically obtains a temporary AK/SK. This way, you can query the ECS or BMS monitoring data on the Cloud Eye console or by calling the Cloud Eye APIs.

   #. Security: The AK/SK used by the Agent is only the temporary AK/SK that has the **CES AgentAccess** permissions. That is, the temporary AK/SK can only be used to operate Cloud Eye resources.
   #. Convenient: You only need to configure the Cloud Eye Agent once in each region instead of manually configuring each Agent.
