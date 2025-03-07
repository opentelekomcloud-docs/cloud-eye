:original_name: ces_01_0083.html

.. _ces_01_0083:

Creating a Custom Alarm Template
================================

#. Log in to the management console.

#. In the upper left corner, select a region and project.

#. Click **Service List** in the upper left corner and select **Cloud Eye**.

#. Choose **Alarm Management** > **Alarm Templates**.

#. Click **Create Custom Template**.

#. On the **Create Custom Template** page, configure parameters by referring to :ref:`Table 1 <ces_01_0083__table87269381527>`.


   .. figure:: /_static/images/en-us_image_0000001645251798.png
      :alt: **Figure 1** Create Custom Template

      **Figure 1** Create Custom Template

   .. _ces_01_0083__table87269381527:

   .. table:: **Table 1** Parameters

      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                                            |
      +===================================+========================================================================================================================================+
      | Name                              | Specifies the alarm template name. The system generates a random one, which you can modify.                                            |
      |                                   |                                                                                                                                        |
      |                                   | Example value: **alarmTemplate-c6ft**                                                                                                  |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------+
      | Description                       | (Optional) Provides supplementary information about the custom template.                                                               |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------+
      | Method                            | You can select **Using existing template** or **Configure manually**.                                                                  |
      |                                   |                                                                                                                                        |
      |                                   | -  **Using existing template**: Select an existing template for **Template**. The alarm rules in the template are automatically added. |
      |                                   | -  **Configure manually**: You can customize alarm policies as required.                                                               |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------+
      | Add Resource Type                 | Specifies the type of the resource the alarm rule is created for.                                                                      |
      |                                   |                                                                                                                                        |
      |                                   | Example value: **Elastic Cloud Server**                                                                                                |
      |                                   |                                                                                                                                        |
      |                                   | .. note::                                                                                                                              |
      |                                   |                                                                                                                                        |
      |                                   |    A maximum of 50 resource types can be added for each service.                                                                       |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------+

#. Click **Create**.
