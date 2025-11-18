:original_name: ces_01_0032.html

.. _ces_01_0032:

(Optional) Manually Configuring the Agent on a Windows Server
=============================================================

Scenarios
---------

The **Configure** feature allows you to configure the AK/SK, region ID, and project ID in one-click mode. If the Agent fails to be configured by clicking **Configure** or due to other reasons, manually configure it by following the instructions provided in this topic.

Constraints
-----------

Some OSs are not supported. For details about which Windows OSs are supported, see :ref:`What OSs Does the Agent Support? <ces_faq_0024>`

Prerequisites
-------------

The Agent has been installed.

Checking the Version of the Agent In Use
----------------------------------------

#. Log in to an ECS as an administrator.
#. Check the installation path and the Agent version.

   -  Earlier version: The Agent is installed in the directory where the Agent installation package is decompressed, for example, if the package is decompressed in **D:\\Agent**, the installation path would be **D:\\Agent\\telescope_windows_amd64**.
   -  New version: **C:\\Program Files\\uniagent\\extension\\install\\telescope**

Procedure
---------

#. Log in to the ECS.

#. Go to the **bin** directory in the Agent installation path.

   Earlier version: The Agent is installed in the directory of the decompressed Agent installation package, for example, if the package is decompressed in **D:\\Agent**, the installation path would be **D:\\Agent\\telescope_windows_amd64**.

   New version: **C:\\Program Files\\uniagent\\extension\\install\\telescope**

#. Modify the **conf.json** file. For details about the parameters, see :ref:`Table 1 <ces_01_0032__table177211067>`.

   .. important::

      To avoid major security risks from storing plaintext AKs and SKs, it is advised to delegate all ECS Agents in the region. For details, see :ref:`How Do I Configure an Agency? <ces_faq_2502>`

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

      +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                                                                                                                                                                                   |
      +===================================+===============================================================================================================================================================================================================================================================================+
      | InstanceId                        | Specifies the instance ID. This parameter is left blank by default, indicating that the instance ID of the current server is specified. Retain the default value. If you need to change the value, log in to the management console and view the instance ID in the ECS list. |
      |                                   |                                                                                                                                                                                                                                                                               |
      |                                   | .. note::                                                                                                                                                                                                                                                                     |
      |                                   |                                                                                                                                                                                                                                                                               |
      |                                   |    When configuring the instance ID, comply with the following rules:                                                                                                                                                                                                         |
      |                                   |                                                                                                                                                                                                                                                                               |
      |                                   |    -  The instance ID must be unique at all sites, that is, in the same region, **InstanceId** used by the Agent cannot be the same, or errors may occur.                                                                                                                     |
      |                                   |    -  The **InstanceId** value must be consistent with the actual ECS ID, or you cannot see the OS monitoring data on Cloud Eye.                                                                                                                                              |
      +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | ProjectId                         | Specifies the project ID. This parameter is left blank by default, indicating that the project ID of the current server is specified. Retain the default value. If you need to configure it, obtain the project ID as follows:                                                |
      |                                   |                                                                                                                                                                                                                                                                               |
      |                                   | a. Log in to the Cloud Eye console, click the username in the upper right corner, and choose **My Credentials**.                                                                                                                                                              |
      |                                   | b. Under **Projects**, obtain the project ID for the region where the ECS is located.                                                                                                                                                                                         |
      +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | AccessKey/SecretKey               | To obtain the AK and SK, perform the following operations:                                                                                                                                                                                                                    |
      |                                   |                                                                                                                                                                                                                                                                               |
      |                                   | Log in to Cloud Eye, click the username in the upper right corner, and choose **My Credentials** > **Access Keys**.                                                                                                                                                           |
      |                                   |                                                                                                                                                                                                                                                                               |
      |                                   | -  If you have obtained the access key, obtain the **AccessKey** value and the **SecretKey** value in the **credentials.csv** file saved when you create **Access Keys**.                                                                                                     |
      |                                   | -  If no access keys are available, click **Create Access Key** to create one. Save the **credentials.csv** file and obtain the **AccessKey** value and the **SecretKey** value in it.                                                                                        |
      |                                   |                                                                                                                                                                                                                                                                               |
      |                                   |    .. important::                                                                                                                                                                                                                                                             |
      |                                   |                                                                                                                                                                                                                                                                               |
      |                                   |       NOTICE:                                                                                                                                                                                                                                                                 |
      |                                   |                                                                                                                                                                                                                                                                               |
      |                                   |       -  For security purposes, it is recommended that the user be an IAM user with the **CES Administrator** permissions only.                                                                                                                                               |
      +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | RegionId                          | Specifies the region ID. For example, if the ECS is located in region **EU DE**, **RegionId** is **eu-de**.                                                                                                                                                                   |
      +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | ClientPort                        | Specifies the start port number used by the Agent.                                                                                                                                                                                                                            |
      |                                   |                                                                                                                                                                                                                                                                               |
      |                                   | .. note::                                                                                                                                                                                                                                                                     |
      |                                   |                                                                                                                                                                                                                                                                               |
      |                                   |    The default value is **0,** indicating that the Agent will randomly use any port. Ports 1 to 1023 are reserved. You are advised not to specify a port in this range for the Agent.                                                                                         |
      +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | PortNum                           | Specifies the number of ports configured for the Agent.                                                                                                                                                                                                                       |
      |                                   |                                                                                                                                                                                                                                                                               |
      |                                   | .. note::                                                                                                                                                                                                                                                                     |
      |                                   |                                                                                                                                                                                                                                                                               |
      |                                   |    The default value is **200**. If **ClientPort** is **5000**, the port range will be 5000 to 5199.                                                                                                                                                                          |
      +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

   .. note::

      -  After you configure the Agent, its status is still displayed as **Not installed** because no monitoring data is reported yet. Wait 3 to 5 minutes and refresh the page.
      -  If the Agent status is **Running** and monitoring is enabled, the Agent has been recognized by Cloud Eye and has started to report fine-grained metric data.
