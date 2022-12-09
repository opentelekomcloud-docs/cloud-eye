:original_name: en-us_topic_0084572343.html

.. _en-us_topic_0084572343:

Adding Subscriptions
====================

A topic is a channel used by SMN to broadcast messages. Therefore, after you create a topic, add subscriptions. In this way, when the metric triggers an alarm, Cloud Eye sends the alarm information to subscription endpoints of the topic.


Adding Subscriptions
--------------------

#. Log in to the management console.

#. In the upper left corner, select a region and project.

#. Under **Application**, select **Simple Message Notification**.

   The SMN console is displayed.

#. In the navigation pane on the left, choose **Topics**.

   The **Topics** page is displayed.

#. Locate the topic you want to add subscriptions to, click **More** under **Operation**, and select **Add Subscription**.

   The **Add Subscription** dialog box is displayed.


   .. figure:: /_static/images/en-us_image_0129738465.png
      :alt: **Figure 1** Adding Subscriptions

      **Figure 1** Adding Subscriptions

#. Specify the subscription protocol and endpoints.

   If you enter multiple endpoints, enter each endpoint on a separate line.

#. Click **OK**.

   The subscription you added is displayed in the subscription list.

   .. note::

      After the subscription is added, the corresponding subscription endpoint will receive a subscription notification. You need to confirm the subscription so that the endpoint can receive alarm notifications.
