:original_name: ces_faq_2514.html

.. _ces_faq_2514:

How Can I Fix the "SSH dial error" During Batch Agent Installation?
===================================================================

Symptom
-------

When the Agent installation command provided by the Cloud Eye console is used to batch install the Agent, the error message "SSH dial error" was displayed. As a result, the Agent failed to be installed, as shown in :ref:`Figure 1 <ces_faq_2514__fig10919432155614>`.

.. _ces_faq_2514__fig10919432155614:

.. figure:: /_static/images/en-us_image_0000002451256404.png
   :alt: **Figure 1** Batch Agent installation failed

   **Figure 1** Batch Agent installation failed

Possible Causes
---------------

Login to the target server as user **root** or using a password is not allowed in its **sshd** settings.

Solution
--------

-  Check the **sshd** configuration file.

   #. Log in to the server where Agent installation fails as user **root**.

   #. Check whether both **PermitRootLogin** and **PasswordAuthentication** are set to **yes** in the **sshd** configuration file.

      If they are not, modify their settings by referring to :ref:`Modifying the sshd Configuration File <ces_faq_2514__li108624463315>`.

      .. code-block::

         cat /etc/ssh/sshd_config

-  .. _ces_faq_2514__li108624463315:

   Modify the **sshd** configuration file.

   #. Edit the **sshd_config** file.

      .. code-block::

         vi /etc/ssh/sshd_config

   #. Modify the configuration items.

      .. code-block::

         PermitRootLogin yes
         PasswordAuthentication yes

   #. Restart the sshd process.

      .. code-block::

         systemctl restart sshd
