Response Format
###############

While working with this API, you will see that most responses are provided in a common format. We use the `JSON API <https://jsonapi.org/>`_ format for our responses.

Here is an example of a response (in this case from the ``GET /projects/{{project_id}}/logical_devices`` endpoint):

.. code-block:: json

    {
        "data": [
            {
                "id": "00ec20e6-e8e4-4ed9-a640-5615e1a409b0",
                "type": "logicalDevices",
                "links": {
                    "self": "https://primary.sixeye-api.com/logical_devices/00ec20e6-e8e4-4ed9-a640-5615e1a409b0"
                },
                "attributes": {
                    "name": "Fake LPC",
                    "model": "LPC",
                    "serialNumber": "FAKELPC",
                    "manufacturerName": "Pharos Controls",
                    "deviceAssigned": "5580aa7d-e647-4f13-a180-114655910846",
                    "online": true,
                    "beacon": false,
                    "viewSelector": {
                        "manufacturerSDK": "pharos",
                        "sixeyeFirmwareVersion": "2.8",
                        "model": "LPC"
                    },
                    "updated": [],
                    "attachedAt": "2023-03-13T10:33:09.977+00:00",
                    "detachedAt": null,
                    "label": "LPC"
                },
                "relationships": {
                    "notifications": {
                        "links": {
                            "self": "https://primary.sixeye-api.com/logical_devices/00ec20e6-e8e4-4ed9-a640-5615e1a409b0/relationships/notifications",
                            "related": "https://primary.sixeye-api.com/logical_devices/00ec20e6-e8e4-4ed9-a640-5615e1a409b0/notifications"
                        }
                    },
                    "deviceActionTypesList": {
                        "links": {
                            "self": "https://primary.sixeye-api.com/logical_devices/00ec20e6-e8e4-4ed9-a640-5615e1a409b0/relationships/device_action_types_list",
                            "related": "https://primary.sixeye-api.com/logical_devices/00ec20e6-e8e4-4ed9-a640-5615e1a409b0/device_action_types_list"
                        }
                    }
                }
            },
            {
                "id": "086e0ea4-908d-4147-a1e0-3946e1de3b00",
                "type": "logicalDevices",
                "links": {
                    "self": "https://primary.sixeye-api.com/logical_devices/086e0ea4-908d-4147-a1e0-3946e1de3b00"
                },
                "attributes": {
                    "name": "Fake M-TS 5",
                    "model": "M-TS 5",
                    "serialNumber": "FAKEMTS5",
                    "manufacturerName": "ETC",
                    "deviceAssigned": "80638a1e-5bce-4b3f-b17e-6c804afcb95e",
                    "online": true,
                    "beacon": false,
                    "viewSelector": {
                        "manufacturerSDK": "etc",
                        "sixeyeFirmwareVersion": "2.8",
                        "model": "M-TS 5"
                    },
                    "updated": [],
                    "attachedAt": "2023-03-13T10:33:23.487+00:00",
                    "detachedAt": null,
                    "label": "M-TS 5"
                },
                "relationships": {
                    "notifications": {
                        "links": {
                            "self": "https://primary.sixeye-api.com/logical_devices/086e0ea4-908d-4147-a1e0-3946e1de3b00/relationships/notifications",
                            "related": "https://primary.sixeye-api.com/logical_devices/086e0ea4-908d-4147-a1e0-3946e1de3b00/notifications"
                        }
                    },
                    "deviceActionTypesList": {
                        "links": {
                            "self": "https://primary.sixeye-api.com/logical_devices/086e0ea4-908d-4147-a1e0-3946e1de3b00/relationships/device_action_types_list",
                            "related": "https://primary.sixeye-api.com/logical_devices/086e0ea4-908d-4147-a1e0-3946e1de3b00/device_action_types_list"
                        }
                    }
                }
            }
        ]
    }

To break down the structure of this JSON reply:

* The JSON reply always contains an object with a single property, ``data``.
* ``data`` is always either an array of objects or a single object
* Within the ``data`` object(s), there are :

  * An ``id`` - a UUID (universally unique identifier), which identifies this object - in the example above, these are unique IDs for the devices
  * A ``type`` - the type of the object as a string
  * ``attributes`` - the property data of the object
  * ``links`` and ``relationships`` - URLs of resources associated with this particular class of objects


.. NOTE::
  Note that this documentation may not cover all attributes returned by a particular call - any undocumented attributes can be safely ignored.
