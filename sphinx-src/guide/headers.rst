Recommended Headers
###################

When sending an HTTP request to the API, we recommend the following headers are included with the request:

.. list-table::
   :widths: 3 3 10
   :header-rows: 1

   * - Header
     - Notes
     - Example Value
   * - ``Origin``
     - The base URL of the application being accessed
     - ``Origin: https://cloud.pharoscontrols.com``
   * - ``Authorization``
     - The authentication token as described in :doc:`authentication`
     - ``Authorization: "Bearer {{token}}"``
   * - ``Accept``
     - When getting data, we recommend Accept be set to ``application/vnd.api+json``
     - ``Accept: application/vnd.api+json``
   * - ``Content-Type``
     - When sending a request with a JSON body, we recommend setting the content type as ``application/vnd.api+json``
     - ``Content-Type: application/vnd.api+json``

