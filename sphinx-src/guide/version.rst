Version
#######

The API is versioned; you can retrieve the current version of the API using a GET to the /version endpoint.

``GET /version``

At the moment the API version is v1. If we add more versions in future, they will be identifiable using this API call.

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
