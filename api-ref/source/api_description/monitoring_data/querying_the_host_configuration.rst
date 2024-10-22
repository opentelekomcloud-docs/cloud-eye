:original_name: ces_03_0035.html

.. _ces_03_0035:

Querying the Host Configuration
===============================

Function
--------

This API is used to query the host configuration for a specified event type in a specified time range. You can specify the dimension of data to be queried.

.. important::

   This API is provided for SAP Monitor in the HANA scenario to query the host configuration. In other scenarios, the host configuration cannot be queried with this API.

URI
---

GET /V1.0/{project_id}/event-data

-  Parameter description

   .. table:: **Table 1** Parameter description

      +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------+
      | Parameter             | Mandatory             | Description                                                                                      |
      +=======================+=======================+==================================================================================================+
      | project_id            | Yes                   | Specifies the project ID.                                                                        |
      |                       |                       |                                                                                                  |
      |                       |                       | For details about how to obtain the project ID, see :ref:`Obtaining a Project ID <ces_03_0057>`. |
      +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------+

-  Parameters that are used to query the host configuration

   +-----------------+-----------------+-----------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                                                                                                                                                                                                                                                                                               |
   +=================+=================+=================+===========================================================================================================================================================================================================================================================================================================+
   | namespace       | Yes             | String          | Specifies the namespace of a service. For details, see :ref:`Services Interconnected with Cloud Eye <ces_03_0059>`.                                                                                                                                                                                       |
   |                 |                 |                 |                                                                                                                                                                                                                                                                                                           |
   |                 |                 |                 | The namespace must be in the **service.item** format and contain 3 to 32 characters. **service** and **item** each must start with a letter and contain only letters, digits, and underscores (_).                                                                                                        |
   +-----------------+-----------------+-----------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | type            | Yes             | String          | Specifies the event type.                                                                                                                                                                                                                                                                                 |
   |                 |                 |                 |                                                                                                                                                                                                                                                                                                           |
   |                 |                 |                 | It can contain only letters, underscores (_), and hyphens (-). It must start with a letter and cannot exceed 64 characters, for example, **instance_host_info**.                                                                                                                                          |
   +-----------------+-----------------+-----------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | from            | Yes             | String          | Specifies the start time of the query.                                                                                                                                                                                                                                                                    |
   |                 |                 |                 |                                                                                                                                                                                                                                                                                                           |
   |                 |                 |                 | The time is a UNIX timestamp and the unit is ms.                                                                                                                                                                                                                                                          |
   +-----------------+-----------------+-----------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | to              | Yes             | String          | Specifies the end time of the query.                                                                                                                                                                                                                                                                      |
   |                 |                 |                 |                                                                                                                                                                                                                                                                                                           |
   |                 |                 |                 | The time is a UNIX timestamp and the unit is ms.                                                                                                                                                                                                                                                          |
   |                 |                 |                 |                                                                                                                                                                                                                                                                                                           |
   |                 |                 |                 | **from** must be earlier than **to**.                                                                                                                                                                                                                                                                     |
   +-----------------+-----------------+-----------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | dim             | Yes             | String          | Specifies the dimension. For example, the ECS dimension is **instance_id**. For details about the dimensions corresponding to the monitoring metrics of each service, see the monitoring metrics description of the corresponding service in :ref:`Services Interconnected with Cloud Eye <ces_03_0059>`. |
   |                 |                 |                 |                                                                                                                                                                                                                                                                                                           |
   |                 |                 |                 | Specifies the dimension. A maximum of three dimensions are supported, and the dimensions are numbered from 0 in **dim.{i}=key,value** format. **key** cannot exceed 32 characters and **value** cannot exceed 256 characters.                                                                             |
   |                 |                 |                 |                                                                                                                                                                                                                                                                                                           |
   |                 |                 |                 | Example: **dim.0=instance_id,i-12345**                                                                                                                                                                                                                                                                    |
   +-----------------+-----------------+-----------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

-  Example: Query the configuration information about the ECS whose **ID** is **33328f02-3814-422e-b688-bfdba93d4051** and **type** is **instance_host_info**.

   .. code-block:: text

      GET https://{Cloud Eye endpoint}/V1.0/{project_id}/event-data?namespace=SYS.ECS&dim.0=instance_id,33328f02-3814-422e-b688-bfdba93d4051&type=instance_host_info&from=1450234543422&to=1450320943422

Request
-------

None

Response
--------

-  Response parameters

   .. table:: **Table 2** Parameter description

      +-----------------------+-----------------------+----------------------------------------------------------------------------------------------------------------+
      | Parameter             | Type                  | Description                                                                                                    |
      +=======================+=======================+================================================================================================================+
      | datapoints            | Array of objects      | Specifies the configuration list.                                                                              |
      |                       |                       |                                                                                                                |
      |                       |                       | If the corresponding configuration information does not exist, **datapoints** is an empty array and is **[]**. |
      |                       |                       |                                                                                                                |
      |                       |                       | For details, see :ref:`Table 3 <ces_03_0035__table19905142618343>`.                                            |
      +-----------------------+-----------------------+----------------------------------------------------------------------------------------------------------------+

   .. _ces_03_0035__table19905142618343:

   .. table:: **Table 3** **datapoints** data structure description

      +-----------+--------+----------------------------------------------------------------------------------+
      | Parameter | Type   | Description                                                                      |
      +===========+========+==================================================================================+
      | type      | String | Specifies the event type, for example, **instance_host_info**.                   |
      +-----------+--------+----------------------------------------------------------------------------------+
      | timestamp | Long   | Specifies when the event is reported. It is a UNIX timestamp and the unit is ms. |
      +-----------+--------+----------------------------------------------------------------------------------+
      | value     | String | Specifies the host configuration information.                                    |
      +-----------+--------+----------------------------------------------------------------------------------+

-  Example response

   .. code-block::

      {
          "datapoints": [
              {
                  "type": "instance_host_info",
                  "timestamp": 1450231200000,
                  "value": "xxx"
              },
              {
                  "type": "instance_host_info",
                  "timestamp": 1450231800000,
                  "value": "xxx"
              }
          ]
      }

Returned Values
---------------

-  Normal

   200

-  Abnormal

   +---------------------------+----------------------------------------------------------------------+
   | Returned Value            | Description                                                          |
   +===========================+======================================================================+
   | 400 Bad Request           | Request error.                                                       |
   +---------------------------+----------------------------------------------------------------------+
   | 401 Unauthorized          | The authentication information is not provided or is incorrect.      |
   +---------------------------+----------------------------------------------------------------------+
   | 403 Forbidden             | Access to the requested page is forbidden.                           |
   +---------------------------+----------------------------------------------------------------------+
   | 408 Request Timeout       | The request timed out.                                               |
   +---------------------------+----------------------------------------------------------------------+
   | 429 Too Many Requests     | Concurrent requests are excessive.                                   |
   +---------------------------+----------------------------------------------------------------------+
   | 500 Internal Server Error | Failed to complete the request because of an internal service error. |
   +---------------------------+----------------------------------------------------------------------+
   | 503 Service Unavailable   | The service is currently unavailable.                                |
   +---------------------------+----------------------------------------------------------------------+

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
