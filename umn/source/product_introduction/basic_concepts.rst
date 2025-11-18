:original_name: ces_07_0006.html

.. _ces_07_0006:

Basic Concepts
==============

The following concepts are central to your understanding and use of Cloud Eye:

Metrics
-------

A metric refers to a quantized value of a resource dimension on the cloud platform, such as the ECS CPU usage and memory usage. A metric is a time-dependent variable that generates a certain amount of monitoring data over time. It helps you understand the changes over a specific period.

Rollup
------

Rollup is the process in which Cloud Eye calculates the average, maximum, minimum, sum, or variance value based on sample raw data reported by each cloud service in specific periods. The calculation period is called a rollup period. Cloud Eye supports the following rollup periods: 5 minutes, 20 minutes, 1 hour, 4 hours, and 24 hours.

Dashboards
----------

Dashboards allow you to view monitoring data of metrics of different services and dimensions. You can use dashboards to display metrics of key services in a centralized way, get an overview of the service statuses, and use monitoring data for troubleshooting.

Topics
------

A topic is used to publish messages and subscribe to notifications in SMN. Topics provide you with one-to-many publish subscription and message notification functions. You can send messages to different types of endpoints with just one message request. Cloud Eye uses SMN to notify you of cloud service resource changes, enabling you to track the cloud service status in a timely manner.

Alarm Rules
-----------

You can create alarm rules to set thresholds for cloud service metrics. When the status (**Alarm** and **OK**) of the alarm rule changes, Cloud Eye notifies you by sending emails, SMS messages, or HTTP/HTTPS messages.

Alarm Templates
---------------

Alarm templates contain one or more alarm rules for specific services. The templates help you create alarm rules for multiple cloud services, improving O&M efficiency.

User Permission
---------------

By default, the system provides two types of user permissions by default: user management and resource management. User management permissions can manage users, user groups, and user group permissions. Resource management permissions can control users' operations on cloud service resources.

For details about Cloud Eye user permissions, see :ref:`Permissions <ces_07_0009>`.

Projects
--------

A project is used to group and isolate OpenStack resources, such as the compute, storage, and network resources. A project can either be a department or a project team. You can use an account to create multiple projects.
