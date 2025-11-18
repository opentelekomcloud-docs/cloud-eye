:original_name: ces_01_0160.html

.. _ces_01_0160:

Cloud Services Displayed in the Cloud Service Monitoring List
=============================================================

Some connected cloud services may not appear in the monitoring list. If no monitoring data is reported for all instances of a cloud service for a certain period of time, the cloud service will not be displayed in the list.

For cloud services listed in :ref:`Table 1 <ces_01_0160__en-us_topic_0000002098437809_table16148161471314>`, if all instances of a cloud service have not reported any data to Cloud Eye for more than three hours but less than seven days, the cloud service remains on the cloud service monitoring list. However, if no data is sent for more than seven days, the service will be removed from the list.

For other cloud services, if all instances of a cloud service have not reported any data to Cloud Eye for more than three hours, this cloud service will not be displayed in the service list.

.. _ces_01_0160__en-us_topic_0000002098437809_table16148161471314:

.. table:: **Table 1** Cloud services with their monitoring data retained for seven days

   ====================== =========
   Cloud Service          Namespace
   ====================== =========
   API Gateway            SYS.APIC
   Object Storage Service SYS.OBS
   Scalable File Service  SYS.SFS
   ====================== =========
