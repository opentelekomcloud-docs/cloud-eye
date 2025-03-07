:original_name: ces_07_0006.html

.. _ces_07_0006:

Basic Concepts
==============

The following concepts are central to your understanding and use of Cloud Eye:

-  :ref:`Metrics <ces_07_0006__section20446181418613>`
-  :ref:`Aggregation <ces_07_0006__section061013819719>`
-  :ref:`Dashboards <ces_07_0006__section983754719710>`
-  :ref:`Topics <ces_07_0006__section06147561378>`
-  :ref:`Alarm Rules <ces_07_0006__section14279171685>`
-  :ref:`Alarm Templates <ces_07_0006__section7358181816813>`
-  :ref:`User Permission <ces_07_0006__section992611851011>`
-  :ref:`Projects <ces_07_0006__section4484122111318>`

.. _ces_07_0006__section20446181418613:

Metrics
-------

A metric refers to a quantized value of a resource dimension on the cloud platform, such as the ECS CPU usage and memory usage. A metric is a time-dependent variable that generates a certain amount of monitoring data over time. It helps you understand the changes over a specific period.

.. _ces_07_0006__section061013819719:

Aggregation
-----------

Aggregation is the process in which Cloud Eye calculates the average, maximum, minimum, sum, or variance value based on sample raw data reported by each cloud service in specific periods. The calculation period is called aggregation period. Cloud Eye supports the following aggregation periods: 5 minutes, 20 minutes, 1 hour, 4 hours, and 24 hours.

.. _ces_07_0006__section983754719710:

Dashboards
----------

Dashboards allow you to view monitoring data of metrics of different services and dimensions. You can use dashboards to display metrics of key services in a centralized way, get an overview of the service statuses, and use monitoring data for troubleshooting.

.. _ces_07_0006__section06147561378:

Topics
------

A topic is used to publish messages and subscribe to notifications in SMN. Topics provide you with one-to-many publish subscription and message notification functions. You can send messages to different types of endpoints with just one message request. Cloud Eye uses SMN to notify you of cloud service resource changes, enabling you to track the cloud service status in a timely manner.

.. _ces_07_0006__section14279171685:

Alarm Rules
-----------

You can create alarm rules to set thresholds for cloud service metrics. When the status (**Alarm** and **OK**) of the alarm rule changes, Cloud Eye notifies you by sending emails, SMS messages, or HTTP/HTTPS messages.

.. _ces_07_0006__section7358181816813:

Alarm Templates
---------------

Alarm templates contain one or more alarm rules for specific services. The templates help you create alarm rules for multiple cloud services, improving O&M efficiency.

.. _ces_07_0006__section992611851011:

User Permission
---------------

By default, the system provides two types of user permissions by default: user management and resource management. User management permissions can manage users, user groups, and user group permissions. Resource management permissions can control users' operations on cloud service resources.

For details about Cloud Eye user permissions, see `Permissions <https://docs.otc.t-systems.com/en-us/permissions/index.html>`__.

.. _ces_07_0006__section4484122111318:

Projects
--------

A project is used to group and isolate OpenStack resources, such as the compute, storage, and network resources. A project can either be a department or a project team. You can use an account to create multiple projects.
