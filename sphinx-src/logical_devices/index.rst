Devices
#######

.. toctree::
   :hidden:

   data

Devices, or logical devices, represent physical devices in the SixEye system. This API allows you to list devices and retrieve data about them.

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
     - The user-assigned name of the device
   * - ``model``
     - string
     - The manufacturer model of the device
   * - ``serialNumber``
     - string
     - The serial number of the device
   * - ``manufacturerName``
     - string
     - The manufacturer of the device
   * - ``online``
     - boolean
     - Whether or not the device is online
   * - ``beacon``
     - boolean
     - Whether or not the device is in a beacon state - typically blinking LEDs or similar to identify a device
   * - ``attachedAt``
     - date-time
     - The time at which the physical device was attached to the system
   * - ``detachedAt``
     - date-time
     - The time at which the physical device was detached from the system

Methods
*******

Get a List of Devices
=====================

``GET /projects/{{project_id}}/logical_devices``

Returns a JSON object with a data member consisting of an array of logicalDevices objects

.. collapse:: Example response

    .. code-block:: json

        {
            "data": [
                {
                    "id": "00ec20e6-e8e4-4ed9-a640-5615e1a409b0",
                    "type": "logicalDevices",
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
                    }
                },
                {
                    "id": "086e0ea4-908d-4147-a1e0-3946e1de3b00",
                    "type": "logicalDevices",
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
                    }
                },
                {
                    "id": "489f36a7-11ac-4b84-af63-18f833885d0b",
                    "type": "logicalDevices",
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
                    }
                },
                {
                    "id": "69b9bfd4-372f-4210-9c11-d11324067c04",
                    "type": "logicalDevices",
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
                    }
                },
                {
                    "id": "f1dca926-10ac-4bb6-b9d3-47e00d8ed216",
                    "type": "logicalDevices",
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
                    }
                }
            ]
        }

Get a Single Device
===================

``GET /logical_devices/{{device_id}}``

Returns a JSON object with a data member consisting of a single logicalDevices object, or a 404 Not Found error if the device with identifier ``device_id`` does not exist.

.. collapse:: Example response

    .. code-block:: json

        {
            "data": {
                "id": "00ec20e6-e8e4-4ed9-a640-5615e1a409b0",
                "type": "logicalDevices",
                "attributes": {
                    "name": "Fake LPC",
                    "model": "LPC",
                    "serialNumber": "FAKELPC",
                    "manufacturerName": "Pharos Controls",
                    "online": true,
                    "beacon": false,
                    "updated": [],
                    "attachedAt": "2023-03-13T10:33:09.977+00:00",
                    "detachedAt": null,
                    "label": "LPC"
                }
            }
        }
