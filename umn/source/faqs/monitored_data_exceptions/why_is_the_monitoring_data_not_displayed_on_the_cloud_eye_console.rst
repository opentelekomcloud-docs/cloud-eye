:original_name: ces_faq_0045.html

.. _ces_faq_0045:

Why Is the Monitoring Data Not Displayed on the Cloud Eye Console?
==================================================================

Possible causes are as follows:

-  The cloud service is not interconnected with Cloud Eye. To check whether a cloud service has been interconnected with Cloud Eye, see :ref:`Services Interconnected with Cloud Eye <en-us_topic_0202622212>`.
-  The collection and monitoring frequency for each service that has been interconnected with Cloud Eye is different. The data may have just not been collected yet.
-  The ECS or BMS has been stopped for more than 1 hour.
-  The EVS disk has not been attached to an ECS or BMS.
-  No backend server is bound to the elastic load balancer or all of the backend servers are stopped.
-  It has been less than 10 minutes since the resource was created.
