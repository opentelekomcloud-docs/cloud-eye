:original_name: ces_01_0033.html

.. _ces_01_0033:

Installing the Agents in Batches on Linux ECSs
==============================================

Scenarios
---------

This topic describes how to batch install the Agents on Linux ECSs.

Operation
---------

After binding an elastic IP address to an ECS, install and configure the Agent by following instructions in :ref:`Installing and Configuring the Agent on a Linux ECS or BMS <ces_01_0004>` to ensure that data collection is normal. Use the ECS as a jump server and run scripts in batches to copy, decompress, and install the Agent package and configuration file to other ECSs.

.. important::

   -  The ECSs where the Agent is to be installed in batches must belong to the same VPC.

   -  Agents cannot be installed on Windows servers in batches.

Constraints
-----------

Some OSs are not supported. For details about which Linux OSs are supported, see :ref:`What OSs Does the Agent Support? <ces_faq_0024>`

Prerequisites
-------------

-  You have configured an agency by referring to :ref:`Configuring an Agency by One Click <en-us_topic_0000002452369417>`.
-  The IP addresses and password of user **root** of all ECSs for which the Agent is to be installed have been collected, sorted in the iplist.txt format, and uploaded to the **/usr/local** directory on the first ECS.

   .. note::

      In the **iplist.txt** file, each line contains only one IP address in the "IP address,Password of user **root**" format.

      In the following example, **abcd** is the password.

      .. code-block::

         192.168.1.1,abcd
         192.168.1.2,abcd

Procedure
---------

#. Log in to the ECS on which the Agent has been installed as user **root**.

#. Run the following command to download and run the batch installation script:

   EU DE:

   .. code-block::

      cd /usr/local && curl -k -O https://uniagent-eu-de.obs.eu-de.otc.t-systems.com/package/batch_agent_install.sh && bash batch_agent_install.sh -r eu-de -u 0.1.9 -t 2.7.2 -d agent.ces.otc.t-systems.com -o otc.t-systems.com

   EU NL:

   .. code-block::

      cd /usr/local && curl -k -O https://uniagent-eu-nl.obs.eu-nl.otc.t-systems.com/package/batch_agent_install.sh && bash batch_agent_install.sh -r eu-nl -u 0.1.9 -t 2.7.2 -d agent.ces.otc.t-systems.com -o otc.t-systems.com

#. Check whether **Telescope process starts successfully.** is displayed. If so, the installation is successful. Wait for 3 to 5 minutes until the Agent starts collecting monitoring data.

   .. note::

      -  After you configure the Agent, its status is still displayed as **Not installed** on the **Server Monitoring** page because no monitoring data is reported yet. Wait 3 to 5 minutes and refresh the page.
      -  If the Agent status is **Running** and monitoring is enabled, the Agent has been recognized by Cloud Eye and has started to report fine-grained metric data.


   .. figure:: /_static/images/en-us_image_0000001567952750.png
      :alt: **Figure 1** Successful installation

      **Figure 1** Successful installation

Helpful Links
-------------

If the error message "SSH dial error" is displayed during batch installation, rectify the fault by referring to :ref:`How Can I Fix the "SSH dial error" During Batch Agent Installation? <ces_faq_2514>`.
