Devices
#######

.. toctree::
   :hidden:

   actions
   data
   files

Devices, or logical devices, represent physical devices in the SixEye system. Devices can perform *actions*, provide *data* and upload and download *files*.

Attributes
**********

A Device has the following attributes:

.. list-table::
   :widths: 3 3 10
   :header-rows: 1

   * - Attribute
     - Value Type
     - Description
   * - ``name``
     - string
     - The identifying name of this device
   * - ``serialNumber``
     - string
     - The serial number of the device
   * - ``manufacturerName``
     - string
     - The manufacturer name of the device
   * - ``deviceAssigned``
     - UUID
     - TODO
   * - ``online``
     - boolean
     - Whether or not the device is online
   * - ``beacon``
     - boolean
     - TODO
   * - ``viewSelector``
     - object
     - TODO
   * - ``updated``
     - array of TODO
     - TODO
   * - ``attachedAt``
     - date-time
     - The time at which the physical device was attached to the system
   * - ``detachedAt``
     - date-time
     - The time at which the physical device was detached from the system
   * - ``label``
     - string
     - TODO - how is this different to name?

Methods
*******

GET
===

``GET /projects/{{project_id}}/logical_devices``

Returns a JSON object with a data member consisting of an array of logicalDevice objects

.. collapse:: Example response

    .. code-block:: json

        {
            "data": [
                {
                    "id": "00ec20e6-e8e4-4ed9-a640-5615e1a409b0",
                    "type": "logicalDevices",
                    "links": {
                        "self": "https://primary-release.republic-api.com/logical_devices/00ec20e6-e8e4-4ed9-a640-5615e1a409b0"
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
                                "self": "https://primary-release.republic-api.com/logical_devices/00ec20e6-e8e4-4ed9-a640-5615e1a409b0/relationships/notifications",
                                "related": "https://primary-release.republic-api.com/logical_devices/00ec20e6-e8e4-4ed9-a640-5615e1a409b0/notifications"
                            }
                        },
                        "deviceActionTypesList": {
                            "links": {
                                "self": "https://primary-release.republic-api.com/logical_devices/00ec20e6-e8e4-4ed9-a640-5615e1a409b0/relationships/device_action_types_list",
                                "related": "https://primary-release.republic-api.com/logical_devices/00ec20e6-e8e4-4ed9-a640-5615e1a409b0/device_action_types_list"
                            }
                        }
                    }
                },
                {
                    "id": "086e0ea4-908d-4147-a1e0-3946e1de3b00",
                    "type": "logicalDevices",
                    "links": {
                        "self": "https://primary-release.republic-api.com/logical_devices/086e0ea4-908d-4147-a1e0-3946e1de3b00"
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
                                "self": "https://primary-release.republic-api.com/logical_devices/086e0ea4-908d-4147-a1e0-3946e1de3b00/relationships/notifications",
                                "related": "https://primary-release.republic-api.com/logical_devices/086e0ea4-908d-4147-a1e0-3946e1de3b00/notifications"
                            }
                        },
                        "deviceActionTypesList": {
                            "links": {
                                "self": "https://primary-release.republic-api.com/logical_devices/086e0ea4-908d-4147-a1e0-3946e1de3b00/relationships/device_action_types_list",
                                "related": "https://primary-release.republic-api.com/logical_devices/086e0ea4-908d-4147-a1e0-3946e1de3b00/device_action_types_list"
                            }
                        }
                    }
                },
                {
                    "id": "489f36a7-11ac-4b84-af63-18f833885d0b",
                    "type": "logicalDevices",
                    "links": {
                        "self": "https://primary-release.republic-api.com/logical_devices/489f36a7-11ac-4b84-af63-18f833885d0b"
                    },
                    "attributes": {
                        "name": "Fake M-TS",
                        "model": "M-TS",
                        "serialNumber": "FAKEMTS",
                        "manufacturerName": "ETC",
                        "deviceAssigned": "45516bfb-d1f6-44c6-bada-7d437060fe9e",
                        "online": true,
                        "beacon": false,
                        "viewSelector": {
                            "manufacturerSDK": "etc",
                            "sixeyeFirmwareVersion": "2.8",
                            "model": "M-TS"
                        },
                        "updated": [],
                        "attachedAt": "2023-03-13T10:33:16.801+00:00",
                        "detachedAt": null,
                        "label": "M-TS"
                    },
                    "relationships": {
                        "notifications": {
                            "links": {
                                "self": "https://primary-release.republic-api.com/logical_devices/489f36a7-11ac-4b84-af63-18f833885d0b/relationships/notifications",
                                "related": "https://primary-release.republic-api.com/logical_devices/489f36a7-11ac-4b84-af63-18f833885d0b/notifications"
                            }
                        },
                        "deviceActionTypesList": {
                            "links": {
                                "self": "https://primary-release.republic-api.com/logical_devices/489f36a7-11ac-4b84-af63-18f833885d0b/relationships/device_action_types_list",
                                "related": "https://primary-release.republic-api.com/logical_devices/489f36a7-11ac-4b84-af63-18f833885d0b/device_action_types_list"
                            }
                        }
                    }
                },
                {
                    "id": "69b9bfd4-372f-4210-9c11-d11324067c04",
                    "type": "logicalDevices",
                    "links": {
                        "self": "https://primary-release.republic-api.com/logical_devices/69b9bfd4-372f-4210-9c11-d11324067c04"
                    },
                    "attributes": {
                        "name": "Fake TPS 5",
                        "model": "TPS 5",
                        "serialNumber": "FAKETPS5",
                        "manufacturerName": "Pharos Controls",
                        "deviceAssigned": "4414e88c-83db-4bd3-9b49-d4ed5daeaac0",
                        "online": true,
                        "beacon": false,
                        "viewSelector": {
                            "manufacturerSDK": "pharos",
                            "sixeyeFirmwareVersion": "2.8",
                            "model": "TPS 5"
                        },
                        "updated": [],
                        "attachedAt": "2023-03-13T10:33:03.095+00:00",
                        "detachedAt": null,
                        "label": "TPS 5"
                    },
                    "relationships": {
                        "notifications": {
                            "links": {
                                "self": "https://primary-release.republic-api.com/logical_devices/69b9bfd4-372f-4210-9c11-d11324067c04/relationships/notifications",
                                "related": "https://primary-release.republic-api.com/logical_devices/69b9bfd4-372f-4210-9c11-d11324067c04/notifications"
                            }
                        },
                        "deviceActionTypesList": {
                            "links": {
                                "self": "https://primary-release.republic-api.com/logical_devices/69b9bfd4-372f-4210-9c11-d11324067c04/relationships/device_action_types_list",
                                "related": "https://primary-release.republic-api.com/logical_devices/69b9bfd4-372f-4210-9c11-d11324067c04/device_action_types_list"
                            }
                        }
                    }
                },
                {
                    "id": "f1dca926-10ac-4bb6-b9d3-47e00d8ed216",
                    "type": "logicalDevices",
                    "links": {
                        "self": "https://primary-release.republic-api.com/logical_devices/f1dca926-10ac-4bb6-b9d3-47e00d8ed216"
                    },
                    "attributes": {
                        "name": "Fake TPS",
                        "model": "TPS",
                        "serialNumber": "FAKETPS",
                        "manufacturerName": "Pharos Controls",
                        "deviceAssigned": "54cf7c3e-8404-406a-b495-fb793d80d9a3",
                        "online": true,
                        "beacon": false,
                        "viewSelector": {
                            "manufacturerSDK": "pharos",
                            "sixeyeFirmwareVersion": "2.8",
                            "model": "TPS"
                        },
                        "updated": [],
                        "attachedAt": "2023-03-13T10:32:55.412+00:00",
                        "detachedAt": null,
                        "label": "TPS"
                    },
                    "relationships": {
                        "notifications": {
                            "links": {
                                "self": "https://primary-release.republic-api.com/logical_devices/f1dca926-10ac-4bb6-b9d3-47e00d8ed216/relationships/notifications",
                                "related": "https://primary-release.republic-api.com/logical_devices/f1dca926-10ac-4bb6-b9d3-47e00d8ed216/notifications"
                            }
                        },
                        "deviceActionTypesList": {
                            "links": {
                                "self": "https://primary-release.republic-api.com/logical_devices/f1dca926-10ac-4bb6-b9d3-47e00d8ed216/relationships/device_action_types_list",
                                "related": "https://primary-release.republic-api.com/logical_devices/f1dca926-10ac-4bb6-b9d3-47e00d8ed216/device_action_types_list"
                            }
                        }
                    }
                }
            ]
        }


``GET  /projects/{{project_id}}/logical_devices/{{device_id}}``

Returns a JSON object with a data member consisting of the logicalDevice object for the specified device_id, or a 404 error if the ID does not exist.

POST
====

A POST action can be used to create a new logical device, or to replace a device with another.

Create Logical Device
---------------------

``POST /logical_devices/connection_data``

Creates a new logical device. The body of the request should be a JSON object including the name for the device and the projectId this device should be associated with.


.. code-block:: json

    {
        "meta": {
            "logicalDeviceName": "New device name",
            "projectId": "{{project_id}}"
        }
    }

Replace Logical Device
----------------------

``POST /logical_devices/connection_data``

Replaces one logical device with another. TODO - explanation

.. code-block:: json

    {
        "meta": {
            "logicalDeviceId": "{{device_id}}",
            "logicalDeviceName": "New device name",
            "projectId": "{{project_id}}",
            "replacement": true
        }
    }

Update Logical Device
---------------------

``POST /logical_devices/{{device_id}}/update_setting``

Updates the information for a logical device. The body of the request should be a JSON object

TODO - don't exactly understand this - is it sending settings change down to the end device?

.. code-block:: json

    {
        "data": {
            "type": "updateSetting",
            "attributes": {
                "setting": "beacon",
                "meta": {
                    "value": true
                }
            }
        }
    }

DELETE
======

The DELETE action can be used to delete a logical device

``DELETE /logical_devices/{{device_id}}``

Deletes the logical device identified by ``device_id``.
