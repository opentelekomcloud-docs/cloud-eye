:original_name: ces_01_0068.html

.. _ces_01_0068:

Introduction to the Alarm Function
==================================

You can set alarm rules for key metrics of cloud services. When the conditions in the alarm rule are met, Cloud Eye sends emails, or SMS messages, or sends HTTP/HTTPS requests, enabling you to quickly respond to resource changes.

Cloud Eye invokes SMN APIs to send notifications. This requires you to create a topic and add subscriptions to this topic on the SMN console. Then, when you create alarm rules on Cloud Eye, you can enable the alarm notification function and select the topic. When alarm rule conditions are met, Cloud Eye sends the alarm information to subscription endpoints in real time.

.. note::

   If no alarm notification topic is created, alarm notifications will be sent to the default email address of the account contact.

The Alarm Rules function supports enterprise projects. If an alarm rule is associated with an enterprise project, only users who have the permission of the enterprise project can view and manage the alarm rule.
