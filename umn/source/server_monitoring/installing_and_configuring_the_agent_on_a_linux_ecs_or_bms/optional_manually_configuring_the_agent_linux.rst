:original_name: ces_01_0031.html

.. _ces_01_0031:

(Optional) Manually Configuring the Agent (Linux)
=================================================

Scenarios
---------

After you install the Agent, configure it by clicking **Restore Agent Configurations** on the Cloud Eye console. If the Agent fails to be configured by clicking **Restore Agent Configurations** or due to other reasons, manually configure it by following the instructions provided in this topic.

This topic takes an ECS as an example. The operations for BMSs are similar.

Prerequisites
-------------

The Agent has been installed.

Procedure
---------

#. Log in to an ECS as user **root**.

#. Run the following command to go to the Agent installation path **bin**:

   **cd** **/usr/local/telescope/bin**

#. Modify configuration file **conf.json**.

   a. Run the following command to open **conf.json**:

      **vi** **conf.json**

   b. Modify the parameters in the file. For details, see :ref:`Table 1 <ces_01_0031__table18647151253120>`.

      ECS parameters

      .. important::

         Storing plaintext AKs and SKs poses great security risks. You are advised to delegate all ECS or BMS Agents in the region. For details, see :ref:`How Can I Create an Agency? <ces_faq_0028>`

      .. code-block::

         {
             "InstanceId":"XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX",
             "ProjectId": "XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX",
             "AccessKey": "XXXXXXXXXXXXXXXXXXXX",
             "SecretKey": "XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX",
             "RegionId": "eu-de",
             "ClientPort": 0,
             "PortNum": 200
         }

      BMS parameters

      .. code-block::

         {
             "InstanceId":"XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX",
             "ProjectId": "XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX",
             "AccessKey": "XXXXXXXXXXXXXXXXXXXX",
             "SecretKey": "XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX",
             "RegionId": "eu-de",
             "ClientPort": 0,
             "PortNum": 200,
             "BmsFlag": true
         }

      .. _ces_01_0031__table18647151253120:

      .. table:: **Table 1** Public parameters

         +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         | Parameter                         | Description                                                                                                                                                                            |
         +===================================+========================================================================================================================================================================================+
         | InstanceId                        | (Optional) Specifies the ECS ID. You can log in to the management console and view the ECS ID in the ECS list.                                                                         |
         |                                   |                                                                                                                                                                                        |
         |                                   | .. note::                                                                                                                                                                              |
         |                                   |                                                                                                                                                                                        |
         |                                   |    If you do not configure **InstanceId**, retain **"InstanceId":""**.                                                                                                                 |
         |                                   |                                                                                                                                                                                        |
         |                                   |    If you configure it, ensure that the following two requirements are met:                                                                                                            |
         |                                   |                                                                                                                                                                                        |
         |                                   |    -  The ECS ID must be unique at all sites, that is, in the same region, **InstanceId** used by the Agent cannot be the same. Otherwise, errors may occur.                           |
         |                                   |    -  The **InstanceId** value must be consistent with the actual ECS or BMS ID. Otherwise, you cannot see the OS monitoring data on Cloud Eye.                                        |
         +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         | ProjectId                         | (Optional) Specifies the project ID.                                                                                                                                                   |
         |                                   |                                                                                                                                                                                        |
         |                                   | If you do not configure **ProjectId**, retain **"ProjectId": ""**.                                                                                                                     |
         |                                   |                                                                                                                                                                                        |
         |                                   | If you configure it, perform the following operations:                                                                                                                                 |
         |                                   |                                                                                                                                                                                        |
         |                                   | #. Log in to the Cloud Eye console, click the username in the upper right corner, and choose **My Credentials**.                                                                       |
         |                                   | #. Under **Projects**, obtain the project ID for the region where the ECS or BMS is located.                                                                                           |
         +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         | AccessKey/SecretKey               | To obtain the AK and SK, perform the following operations:                                                                                                                             |
         |                                   |                                                                                                                                                                                        |
         |                                   | Log in to the Cloud Eye console, click the username in the upper right corner, and choose **My Credentials**, and choose **Access Keys**.                                              |
         |                                   |                                                                                                                                                                                        |
         |                                   | -  If you have obtained the access key, obtain the **AccessKey** value and the **SecretKey** value in the **credentials.csv** file saved when you create **Access Keys**.              |
         |                                   | -  If no access keys are available, click **Create Access Key** to create one. Save the **credentials.csv** file and obtain the **AccessKey** value and the **SecretKey** value in it. |
         |                                   |                                                                                                                                                                                        |
         |                                   |    .. important::                                                                                                                                                                      |
         |                                   |                                                                                                                                                                                        |
         |                                   |       NOTICE:                                                                                                                                                                          |
         |                                   |                                                                                                                                                                                        |
         |                                   |       -  For security purposes, it is recommended that the user be an IAM user with the **CES Administrator** permissions only.                                                        |
         +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         | RegionId                          | Specifies the region ID. For example, if the ECS is located in region **EU DE**, **RegionId** is **eu-de**.                                                                            |
         +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         | ClientPort                        | Specifies the start port number used by the Agent.                                                                                                                                     |
         |                                   |                                                                                                                                                                                        |
         |                                   | .. note::                                                                                                                                                                              |
         |                                   |                                                                                                                                                                                        |
         |                                   |    The default value is **0,** indicating that the Agent will randomly use any port. Ports 1 to 1023 are reserved. You are advised not to specify a port in this range for the Agent.  |
         +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         | PortNum                           | Specifies the number of ports configured for the Agent.                                                                                                                                |
         |                                   |                                                                                                                                                                                        |
         |                                   | .. note::                                                                                                                                                                              |
         |                                   |                                                                                                                                                                                        |
         |                                   |    The default value is **200**. If **ClientPort** is **5000**, the port range will be 5000 to 5199.                                                                                   |
         +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         | BmsFlag                           | Set this parameter to **true** for a BMS. This parameter is not required by an ECS.                                                                                                    |
         |                                   |                                                                                                                                                                                        |
         |                                   | You do not need to set this parameter for the Windows OS.                                                                                                                              |
         +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

#. Modify configuration file **conf_ces.json** for the Cloud Eye metric collection module.

   a. Run the following command to open public configuration file **conf_ces.json**:

      **vi** **conf_ces.json**

   b. Modify the endpoint in **conf_ces.json**, and save the **conf_ces.json** file. For details, see :ref:`Table 2 <ces_01_0031__table176514120315>`.

      .. code-block::

         {
           "Endpoint": "https://ces.eu-de.otc.t-systems.com"
         }

      .. _ces_01_0031__table176514120315:

      .. table:: **Table 2** Parameter setting of the metric collection module

         +-----------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         | Parameter | Description                                                                                                                                                                           |
         +===========+=======================================================================================================================================================================================+
         | Endpoint  | Specifies the Cloud Eye endpoint URL in the region of the ECS or BMS. For example, if the ECS or BMS is located in region **EU-DE**, **Endpoint** is **ces.eu-de.otc.t-systems.com**. |
         +-----------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

      .. note::

         -  After you configure the Agent, its status is still displayed as **Uninstalled** because no monitoring data is reported yet. Wait 3 to 5 minutes and refresh the page.
         -  If the Agent is in the **Running** state, the Agent has been installed and has started to collect fine-grained metric data.
