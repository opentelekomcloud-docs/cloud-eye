:original_name: ces_01_0031.html

.. _ces_01_0031:

(Optional) Manually Configuring the Agent on a Linux Server
===========================================================

Scenarios
---------

The **Configure** feature allows you to configure the AK/SK, region ID, and project ID If the Agent fails to be configured by clicking **Configure** or due to other reasons, manually configure it by following the instructions provided in this section.

This section takes an ECS as an example. The operations for BMSs are similar.

Constraints
-----------

Not every Operating System is supported. For details about which Linux OSs are supported, see :ref:`What OSs Does the Agent Support? <ces_faq_0024>`

Prerequisites
-------------

The Agent has been installed.

Checking the Version of the Agent In Use
----------------------------------------

#. Log in to an ECS as user **root**.

#. Run the following command to check the Agent version:

   **if [[ -f /usr/local/uniagent/extension/install/telescope/bin/telescope ]]; then /usr/local/uniagent/extension/install/telescope/bin/telescope -v; elif [[ -f /usr/local/telescope/bin/telescope ]]; then echo "old agent"; else echo 0; fi**

   -  If **old agent** is displayed, the earlier version of the Agent is used.
   -  If a version is returned, the new version of the Agent is in use.
   -  If **0** is returned, the Agent is not installed.

Procedure
---------

#. Log in to an ECS as user **root**.

#. Run the following command to go to the Agent installation path **bin**:

   Earlier version:

   .. code-block::

      cd /usr/local/telescope/bin

   New version:

   .. code-block::

      cd /usr/local/uniagent/extension/install/telescope/bin

#. Modify configuration file **conf.json**.

   a. Run the following command to open **conf.json**:

      **vi** **conf.json**

   b. Modify the parameters in the file. For details, see :ref:`Table 1 <ces_01_0031__table18647151253120>`.

      .. important::

         To avoid major security risks from storing plaintext AKs and SKs, it is advised to delegate all ECS or BMS Agents in the region. For details, see :ref:`How Do I Configure an Agency? <ces_faq_2502>`

      ECS parameters

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
         |                                   |    -  The **InstanceId** value must be consistent with the actual ECS or BMS ID. Otherwise, you cannot see the OS monitoring data on Cloud Eye.                                                                                                                               |
         +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         | ProjectId                         | Specifies the project ID. This parameter is left blank by default, indicating that the project ID of the current server is specified. Retain the default value. If you need to configure it, obtain the project ID as follows:                                                |
         |                                   |                                                                                                                                                                                                                                                                               |
         |                                   | #. Log in to the Cloud Eye console, click the username in the upper right corner, and choose **My Credentials**.                                                                                                                                                              |
         |                                   | #. Under **Projects**, obtain the project ID for the region where the ECS or BMS is located.                                                                                                                                                                                  |
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
         | BmsFlag                           | Set this parameter to **true** for a BMS. This parameter is not required by an ECS.                                                                                                                                                                                           |
         |                                   |                                                                                                                                                                                                                                                                               |
         |                                   | You do not need to set this parameter for the Windows OS.                                                                                                                                                                                                                     |
         +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

#. Modify configuration file **conf_ces.json** for the Cloud Eye metric collection module.

   a. Run the following command to open public configuration file **conf_ces.json**:

      **vi** **conf_ces.json**

   b. Modify the endpoint in **conf_ces.json**, and save the **conf_ces.json** file. For details, see :ref:`Table 2 <ces_01_0031__table176514120315>`.

      EU DE:

      .. code-block::

         {
           "Endpoint": "https://ces.eu-de.otc.t-systems.com"
         }

      EU NL:

      .. code-block::

         {
           "Endpoint": "https://ces.eu-nl.otc.t-systems.com"
         }

      .. _ces_01_0031__table176514120315:

      .. table:: **Table 2** Parameter setting of the metric collection module

         +-----------------------------------+-------------------------------------------------------------------------------------------+
         | Parameter                         | Description                                                                               |
         +===================================+===========================================================================================+
         | Endpoint                          | Specifies the Cloud Eye endpoint URL in the region that the ECS or BMS belongs to.        |
         |                                   |                                                                                           |
         |                                   | -  If the ECS or BMS is in the **EU-DE** region, **ces.eu-de.otc.t-systems.com** is used. |
         |                                   | -  If the ECS or BMS is in the **EU-NL** region, **ces.eu-nl.otc.t-systems.com** is used. |
         +-----------------------------------+-------------------------------------------------------------------------------------------+

      .. note::

         -  After you configure the Agent, its status is still displayed as **Not installed** because no monitoring data is reported yet. Wait 3 to 5 minutes and refresh the page.
         -  If the Agent status is **Running**, the Agent has been recognized by Cloud Eye and has started to report fine-grained metric data.
