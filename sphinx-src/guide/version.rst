Version
#######

The API is versioned; you can retrieve the current version of the API using a GET to the /version endpoint.

``GET /version``

.. code-block:: json

    {
        "backendVersion": "23.21.0",
        "API": {
            "defaultVersion": "v1",
            "supportedVersions": [
                {
                    "version": "v1",
                    "versionNumber": "1.128.0"
                }
            ]
        }
    }
