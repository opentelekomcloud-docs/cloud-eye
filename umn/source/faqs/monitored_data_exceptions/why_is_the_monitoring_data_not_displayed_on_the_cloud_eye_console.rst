:original_name: ces_faq_0045.html

.. _ces_faq_0045:

Why Is the Monitoring Data Not Displayed on the Cloud Eye Console?
==================================================================

Possible causes are as follows:

-  The service is not interconnected with Cloud Eye. To check whether a service has been interconnected with Cloud Eye, see :ref:`Services Interconnected with Cloud Eye <en-us_topic_0202622212>`.
-  The service has been interconnected with Cloud Eye. However, the collection and monitoring frequency for each service varies. The data may have just not been collected yet.
-  The ECS has been stopped for more than 1 hour.
-  The EVS disk has not been attached to an ECS.
-  No backend server is bound to the elastic load balancer or all of the backend servers are shut down.
-  It has been less than 10 minutes since the resource was created.
