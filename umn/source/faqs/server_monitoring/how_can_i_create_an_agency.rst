:original_name: ces_faq_0028.html

.. _ces_faq_0028:

How Can I Create an Agency?
===========================

Scenarios
---------

Create an agency so that the Agent can automatically obtain the AK and SK. This frees you from exposing the AK or SK in the configuration file.

Procedure
---------

#. Log in to the management console.

#. Click |image1| in the upper left to select a region and project.

#. Click **Service List** in the upper left corner and select **Identity and Access Management**.

#. In the navigation pane on the left, choose **Agencies**. In the upper right corner, click **Create Agency**.

#. .. _ces_faq_0028__en-us_topic_0105568468_en-us_topic_0067564154_li34323751141623:

   Configure the parameters by referring to :ref:`Table 1 <ces_faq_0028__en-us_topic_0105568468_en-us_topic_0067564154_table38871321141759>`, and click **Next**.

   .. _ces_faq_0028__en-us_topic_0105568468_en-us_topic_0067564154_table38871321141759:

   .. table:: **Table 1** Creating an agency

      +-----------------------------------+-----------------------------------------------------------------+
      | Parameter                         | Description                                                     |
      +===================================+=================================================================+
      | Agency Name                       | Specifies the name of the agency.                               |
      |                                   |                                                                 |
      |                                   | Example: **CESAgentAutoConfigAgency**                           |
      +-----------------------------------+-----------------------------------------------------------------+
      | Agency Type                       | Select **Cloud service**.                                       |
      +-----------------------------------+-----------------------------------------------------------------+
      | Cloud Service                     | Select **ECS/BMS** from the drop-down list.                     |
      +-----------------------------------+-----------------------------------------------------------------+
      | Validity Period                   | Select **Unlimited**.                                           |
      +-----------------------------------+-----------------------------------------------------------------+
      | Description                       | (Optional) Provides supplementary information about the agency. |
      +-----------------------------------+-----------------------------------------------------------------+

#. On the **Select Policy/Role** page, search for **CES Administrator**, select **CES Administrator** from the search results, and click **Next**.

#. On the **Select Scope** page, select the authorized scope.

#. Click **OK**.

Agency Configuration
--------------------

If no agency is configured for a server, perform the following operations to configure an agency:

#. Log in to the management console.
#. Choose **Service List** > **Computing** > **Elastic Cloud Server**.

   .. note::

      If you purchase a BMS, choose **Computing** > **Bare Metal Server**.

#. Click the name of the ECS or BMS where the Agent is located. The parameter configuration page is displayed.
#. In the **Management Information** area, select the agency created in :ref:`5 <ces_faq_0028__en-us_topic_0105568468_en-us_topic_0067564154_li34323751141623>` for **Agency** and click the green tick to make the agency take effect.

.. |image1| image:: /_static/images/en-us_image_0110267213.png
