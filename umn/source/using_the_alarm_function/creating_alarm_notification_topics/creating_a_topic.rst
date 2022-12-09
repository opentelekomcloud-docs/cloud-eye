:original_name: en-us_topic_0085216039.html

.. _en-us_topic_0085216039:

Creating a Topic
================

Scenarios
---------

A topic serves as a message sending channel, where publishers and subscribers can interact with each other.

You can create your own topic.


Creating a Topic
----------------

#. Log in to the management console.

#. In the upper left corner, select a region and project.

#. In the service list, select **Simple Message Notification**.

   The SMN console is displayed.

#. In the navigation pane on the left, choose **Topics**.

   The **Topics** page is displayed.

#. Click **Create Topic**.

   The **Create Topic** dialog box is displayed.


   .. figure:: /_static/images/en-us_image_0129759242.png
      :alt: **Figure 1** Create Topic

      **Figure 1** Create Topic

#. Enter a topic name and display name (topic description).

   .. table:: **Table 1** Parameters required for creating a topic

      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                                                                                                                                                  |
      +===================================+==============================================================================================================================================================================================================================================+
      | Topic Name                        | Specifies the topic name, which                                                                                                                                                                                                              |
      |                                   |                                                                                                                                                                                                                                              |
      |                                   | -  Contains only letters, digits, hyphens (-), and underscores (_) and must start with a letter or a digit.                                                                                                                                  |
      |                                   | -  Must contain 1 to 255 characters.                                                                                                                                                                                                         |
      |                                   | -  Must be unique and cannot be modified after the topic is created.                                                                                                                                                                         |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Display Name                      | Specifies the message sender name, which must be less than 192 characters.                                                                                                                                                                   |
      |                                   |                                                                                                                                                                                                                                              |
      |                                   | .. note::                                                                                                                                                                                                                                    |
      |                                   |                                                                                                                                                                                                                                              |
      |                                   |    After you specify a display name in *Display name*\ **<username@example.com>** format, the name you specify will be displayed as the email sender. Otherwise, the sender name will be displayed as **username@example.com**.              |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Tag                               | Tags identify cloud resources so that they can be categorized easily and searched quickly.                                                                                                                                                   |
      |                                   |                                                                                                                                                                                                                                              |
      |                                   | -  You can enter a maximum of 36 and 43 characters for **Key** and **Value**, respectively. Both **Key** and **Value** cannot start or end with a space and cannot contain any of the following special characters:=, \*, <, >, \\, ,, \|, / |
      |                                   | -  Each topic supports up to 10 tags.                                                                                                                                                                                                        |
      +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

#. Click **OK.**

   The topic you created is displayed in the topic list.

   After you create a topic, the system generates a uniform resource name (URN) for the topic, which uniquely identifies the topic and cannot be changed.

#. Click a topic name to view the topic details and the total number of topic subscriptions.

Follow-up Operations
--------------------

After you create a topic, :ref:`add subscriptions <en-us_topic_0084572343>`. After the subscriptions have been confirmed, alarm notifications will be sent to the subscription endpoints via SMN.
