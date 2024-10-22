:original_name: ces_03_0001.html

.. _ces_03_0001:

API Usage Guidelines
====================

Public cloud APIs comply with the RESTful API design principles. REST-based Web services are organized into resources. Each resource is identified by one or more Uniform Resource Identifiers (URIs). An application accesses a resource based on the resource's Unified Resource Locator (URL). A URL is usually in the following format: *https://Endpoint/uri*. In the URL, **uri** indicates the resource path, that is, the API access path.

Public cloud APIs use HTTPS as the transmission protocol. Requests/Responses are transmitted by using JSON messages, with media type represented by **Application/json**.

For details about how to use APIs, see `API Usage Guidelines <https://docs.otc.t-systems.com/en-us/api/apiug/apig-en-api-180328001.html?tag=API%20Documents>`__.

An endpoint is the **request address** for calling an API. Endpoints vary depending on services and regions. For example, the endpoint of the eu-de region is **ces.eu-de.otc.t-systems.com**. For the endpoints of all services, see `Regions and Endpoints <https://docs.otc.t-systems.com/en-us/endpoint/index.html>`__.
