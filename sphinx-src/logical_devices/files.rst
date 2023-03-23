Device Files
############

TODO - think I need to understand how the flow of files to S3 and back works..

Transfer File
=============

``POST logical_devices/{{device_id}}/file_uploads/transfer``

.. code-block:: json

    {
        "data": [
            {
                "type": "fileUploads",
                "attributes": {
                    "fileName": "example.app",
                    "fileTypeId": "fw"
                }
            }
        ]
    }

File transfer from Device
=========================

``POST /logical_devices/{{device_id}}/file_downloads/transfer``

.. code-block:: json

    {
        "data": [
            {
                "type": "fileDownloads",
                "attributes": {
                    "fileId": "c7542e7a-6eac-4719-8097-91dd91817e0e"
                }
            }
        ]
    }

Download file from S3
=====================

``POST /logical_devices/{{device_id}}/file_uploads/download``

.. code-block:: json

    {
        "data": {
            "fileName": "fixture.pd2",
            "fileTypeId": "proj"
        }
    }

Upload File
===========

``POST /logical_devices/{{device_id}}/file_uploads``

.. code-block:: json

    {
        "data": [{
            "fileName": "fixture.pd2",
            "fileTypeId": "proj",
            "id": "1"
        },{
            "fileName": "fixture2.pd2",
            "fileTypeId": "proj",
            "id": "2"
        }]
    }

Remove File
===========

``DELETE /logical_devices/{{device_id}}/file_uploads/delete``

.. code-block:: json

    {
        "data": [
            {
                "fileName": "example.app",
                "fileTypeId": "fw"
            }
        ]
    }
