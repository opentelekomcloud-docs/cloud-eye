:original_name: ces_01_0032.html

.. _ces_01_0032:

(Optional) Manually Configuring the Agent on a Windows Server
=============================================================

Scenarios
---------

After you install the Agent, configure it by clicking **Restore Agent Configurations** on the Cloud Eye console. If the Agent fails to be configured by clicking **Restore Agent Configurations** or due to other reasons, manually configure it by following the instructions provided in this topic.

Constraints
-----------

The Agent cannot be installed on Windows BMSs.

Prerequisites
-------------

The Agent has been installed.

Procedure
---------

#. Log in to the ECS.

#. Open the **conf.json** file in the **telescope_windows_amd64\\bin** directory.

#. Configure the following parameters. For details, see :ref:`Table 1 <ces_01_0032__table177211067>`.

   .. important::

      Storing plaintext AKs and SKs poses great security risks. You are advised to delegate all ECS or BMS Agents in the region. For details, see :ref:`How Can I Create an Agency? <ces_faq_0028>`

   .. code-block::

      {
          "InstanceId":"",
          "ProjectId": "",
          "AccessKey": "",
          "SecretKey": "",
          "RegionId": "eu-de",
          "ClientPort": 0,
          "PortNum": 200
      }

   .. _ces_01_0032__table177211067:

   .. table:: **Table 1** Public parameters

      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                                                                                            |
      +===================================+========================================================================================================================================================================================+
      | InstanceId                        | (Optional) Specifies the ECS ID. You can log in to the management console and view the ECS ID in the ECS list.                                                                         |
      |                                   |                                                                                                                                                                                        |
      |                                   | .. note::                                                                                                                                                                              |
      |                                   |                                                                                                                                                                                        |
      |                                   |    If you do not configure **InstanceId**, retain **"InstanceId":""**. If you configure it, ensure that the following two requirements are met:                                        |
      |                                   |                                                                                                                                                                                        |
      |                                   |    -  The ECS ID must be unique at all sites, that is, in the same region, **InstanceId** used by the Agent cannot be the same. Otherwise, errors may occur.                           |
      |                                   |    -  The **InstanceId** value must be consistent with the actual ECS or BMS ID. Otherwise, you cannot see the OS monitoring data on Cloud Eye.                                        |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | ProjectId                         | Specifies the project ID. You do not need to configure **ProjectId**. Retain **"ProjectId": ""**. If you wish to configure it, perform the following operations:                       |
      |                                   |                                                                                                                                                                                        |
      |                                   | a. Log in to the Cloud Eye console, click the username in the upper right corner, and choose **My Credentials**.                                                                       |
      |                                   | b. Under **Projects**, obtain the project ID for the region where the ECS or BMS is located.                                                                                           |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | AccessKey/SecretKey               | To obtain the AK and SK, perform the following operations:                                                                                                                             |
      |                                   |                                                                                                                                                                                        |
      |                                   | Log in to Cloud Eye, click the username in the upper right corner, and choose **My Credentials** > **Access Keys**.                                                                    |
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

#. Wait for a few minutes. If **Agent Status** is **Running**, the Agent has been installed and starts to collect fine-grained metric data.
