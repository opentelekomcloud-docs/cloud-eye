:original_name: ces_03_0048.html

.. _ces_03_0048:

Supported Actions of the Metric Management API
==============================================

+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+--------------------------------+------------------+-------------+--------------------+
| Permission                                                                                                                                                                          | API                            | Action           | IAM Project | Enterprise Project |
+=====================================================================================================================================================================================+================================+==================+=============+====================+
| Query the metric list. You can specify the namespace, metric name, dimension, sorting order, start records, and the maximum number of records when using this API to query metrics. | GET /V1.0/{project_id}/metrics | ces:metrics:list | Y           | x                  |
+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+--------------------------------+------------------+-------------+--------------------+
