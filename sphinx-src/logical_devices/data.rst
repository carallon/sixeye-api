Device Data
###########

The Device Data API allows you to query devices for information about their current status.

Triggers
========

Applies to Pharos Controllers.

``GET logical_devices/{{device_id}}/triggers``

Returns a JSON object including the list of available triggers for this device. The object includes an array of triggers, with attributes for the trigger ID, type, name and description.

.. collapse:: Example response

    .. code-block:: json

        {
            "data": [
                {
                    "id": 1,
                    "type": "triggers",
                    "attributes": {
                        "name": "Normal Startup (Startup)",
                        "description": "At startup: Start Timeline 28 and 1 additional action"
                    }
                },
                {
                    "id": 2,
                    "type": "triggers",
                    "attributes": {
                        "name": "Standard Operation (Real Time)",
                        "description": "(* - * - * - * - * - * - 0): Release all scenes in 2s and 5 additional actions"
                    }
                },
                {
                    "id": 5,
                    "type": "triggers",
                    "attributes": {
                        "name": "Warm Override (Real Time)",
                        "description": "(* - * - * - * - * - * - 30):  and 3 additional actions"
                    }
                },
                {
                    "id": 28,
                    "type": "triggers",
                    "attributes": {
                        "name": "Every mm.x2 second (Real Time)",
                        "description": "(* - * - * - * - * - * - 2,12,22,32,42,52): Execute Random Timeline and 1 additional action"
                    }
                },
                {
                    "id": 20,
                    "type": "triggers",
                    "attributes": {
                        "name": "(Soft)",
                        "description": "When triggered"
                    }
                }
            ],
            "meta": {}
        }

Static Scenes
=============

Applies to Pharos Controllers.

``GET logical_devices/{{device_id}}/static_scenes``

Returns a JSON object including the list of available static scenes for this device. The object includes an array of scenes, with attributes for the scene ID, type, name and status.

.. collapse:: Example response

    .. code-block:: json

        {
            "data": [
                {
                    "id": 1,
                    "type": "staticScenes",
                    "attributes": {
                        "name": "Scene 1",
                        "status": null
                    }
                },
                {
                    "id": 2,
                    "type": "staticScenes",
                    "attributes": {
                        "name": "Scene 2",
                        "status": null
                    }
                },
                {
                    "id": 3,
                    "type": "staticScenes",
                    "attributes": {
                        "name": "Scene 3",
                        "status": null
                    }
                }
            ],
            "meta": {}
        }

Fixture Groups
==============

Applies to Pharos Controllers.

``GET logical_devices/{{device_id}}/fixture_groups``

Returns a JSON object including the list of available fixture groups for this device. The object includes an array of groups, with attributes for the scene ID, type, name and status.

TODO: what is hide_id?


.. collapse:: Example response

    .. code-block:: json

        {
            "data": [
                {
                    "id": 1,
                    "type": "fixtureGroups",
                    "attributes": {
                        "hide_id": false,
                        "name": "Group 1",
                        "status": null,
                        "type": "user"
                    }
                },
                {
                    "id": 2,
                    "type": "fixtureGroups",
                    "attributes": {
                        "hide_id": false,
                        "name": "Group 2",
                        "status": null,
                        "type": "user"
                    }
                },
                {
                    "id": 3,
                    "type": "fixtureGroups",
                    "attributes": {
                        "hide_id": false,
                        "name": "Group 3",
                        "status": null,
                        "type": "user"
                    }
                },
                {
                    "id": 4,
                    "type": "fixtureGroups",
                    "attributes": {
                        "hide_id": false,
                        "name": "Group 4",
                        "status": null,
                        "type": "user"
                    }
                },
                {
                    "id": 5,
                    "type": "fixtureGroups",
                    "attributes": {
                        "hide_id": false,
                        "name": "Group 5",
                        "status": null,
                        "type": "user"
                    }
                },
                {
                    "id": 6,
                    "type": "fixtureGroups",
                    "attributes": {
                        "hide_id": false,
                        "name": "sdfsd",
                        "status": null,
                        "type": "user"
                    }
                },
                {
                    "id": 7,
                    "type": "fixtureGroups",
                    "attributes": {
                        "hide_id": true,
                        "name": "All Fixtures",
                        "status": null,
                        "type": "auto"
                    }
                },
                {
                    "id": 8,
                    "type": "fixtureGroups",
                    "attributes": {
                        "hide_id": true,
                        "name": "All Conventional 8 bit",
                        "status": null,
                        "type": "auto"
                    }
                },
                {
                    "id": 9,
                    "type": "fixtureGroups",
                    "attributes": {
                        "hide_id": true,
                        "name": "All LED - RGB 8 bit",
                        "status": null,
                        "type": "auto"
                    }
                },
                {
                    "id": 10,
                    "type": "fixtureGroups",
                    "attributes": {
                        "hide_id": true,
                        "name": "All LED - WwNwCw 8 bit",
                        "status": null,
                        "type": "auto"
                    }
                }
            ],
            "meta": {}
        }

Timelines
=========

Applies to Pharos Controllers.

``GET logical_devices/{{device_id}}/timelines``

Returns a JSON object including the list of available timelines for this device. The object includes an array of timelines, with attributes for the name, length (in seconds), current time and status.


.. collapse:: Example response

    .. code-block:: json

        {
            "data": [
                {
                    "id": 1,
                    "type": "timelines",
                    "attributes": {
                        "name": "All White",
                        "length": 10,
                        "time": null,
                        "status": null
                    }
                },
                {
                    "id": 2,
                    "type": "timelines",
                    "attributes": {
                        "name": "Standard Operation",
                        "length": 10,
                        "time": null,
                        "status": null
                    }
                },
                {
                    "id": 3,
                    "type": "timelines",
                    "attributes": {
                        "name": "Special Events",
                        "length": 10,
                        "time": null,
                        "status": null
                    }
                },
                {
                    "id": 4,
                    "type": "timelines",
                    "attributes": {
                        "name": "Charity Event",
                        "length": 10,
                        "time": null,
                        "status": null
                    }
                }
            ],
            "meta": {}
        }


File Uploads
============

Applies to Pharos Controllers.

``GET logical_devices/{{device_id}}/file_uploads``

Returns a JSON object including the list of files which have been uploaded for this device. The object includes an array of files, with attributes for:

* File Type
* File Name
* Last modified date (in Unix time format)
* HTTP ETag (a unique identifier for the file)
* File Size (in Bytes)


.. collapse:: Example response

    .. code-block:: json

        {
            "data": [
                {
                    "id": "7a7f5e6e-3354-4a14-afc8-ad56831bc852",
                    "type": "fileUploads",
                    "attributes": {
                        "fileType": "proj",
                        "fileName": "my_project.pd2",
                        "lastModified": 1679405147,
                        "etag": "\"66465aa318494ecb2f667c892749cd28-1\"",
                        "size": 9457
                    }
                }
            ],
            "meta": {}
        }


Patch
=====

Applies to Pharos Controllers.

``GET logical_devices/{{device_id}}/patch``

TODO - I get a 401 unauthorized for this?


Log
===

Applies to Pharos Controllers.

``GET logical_devices/{{device_id}}/log_messages?lines={{lines}}&refreshRate={{refresh_rate}}``

Requests a set of log messages from the controller. This request must be passed query parameters:

* lines - the maximum number of lines to return
* refreshRate - TODO

TODO - I get a 401 unauthorized for this?


Snapshots
=========

Applies to ??? TODO.

``GET logical_devices/{{device_id}}/snapshots``

Zones
=====

Applies to ??? TODO.

``GET logical_devices/{{device_id}}/zones``

IO Modules
==========

Applies to Pharos Controllers.

``GET logical_devices/{{device_id}}/io_modules``

Requests the IO modules that are in use in the currently loaded project.

.. collapse:: Example response

    .. code-block:: json

        {
            "data": [
                {
                    "id": 2,
                    "type": "ioModules",
                    "attributes": {
                        "label": "Single Single Updating"
                    }
                },
                {
                    "id": 4,
                    "type": "ioModules",
                    "attributes": {
                        "label": "Set Status Vars"
                    }
                }
            ],
            "meta": {}
        }

IO Instances
============

Applies to Pharos Controllers.

``GET logical_devices/{{device_id}}/io_instances``

Requests a list of instances of IO modules that are in use in the currently loaded project.

.. collapse:: Example response

    .. code-block:: json

        {
            "data": [
                {
                    "id": 5,
                    "type": "ioInstances",
                    "attributes": {
                        "title": "Single Instance Always Updating",
                        "module_id": 2,
                        "text": {
                            "type": "string",
                            "label": "Text:"
                        }
                    }
                },
                {
                    "id": 43,
                    "type": "ioInstances",
                    "attributes": {
                        "title": "Custom Set 1",
                        "module_id": 4,
                        "var1": {
                            "type": "string",
                            "label": "Var 1"
                        },
                        "var2": {
                            "type": "string",
                            "label": "Var 2"
                        },
                        "var3": {
                            "type": "string",
                            "label": "Var 3"
                        }
                    }
                }
            ],
            "meta": {}
        }

Remote Devices
==============

Applies to Pharos Controllers.

``GET logical_devices/{{device_id}}/remote_devices``

Requests a list of remote devices in the currently loaded project.

.. collapse:: Example response

    .. code-block:: json

        {
            "data": [
                {
                    "id": 0,
                    "type": "remoteDevices",
                    "attributes": {
                        "num": 1,
                        "name": "EDN 20 1",
                        "type": "EDN 20"
                    }
                }
            ],
            "meta": {}
        }


Unjoined Remote Devices
=======================

Applies to Pharos Controllers.

``GET logical_devices/{{device_id}}/unjoined_remote_devices``

Requests a list of remote devices which are detected on the network, but are not in the currently loaded project.

TODO - example

