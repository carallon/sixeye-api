Device Data
###########

The Device Data API allows you to query devices for information about their current status.

Each GET returns the last known state and initiates communication with the device to retrieve an update. It is recommended to make two requests to fetch most current status.

Triggers
========

.. include:: ../snippets/data-pharos-mosaic.rst

``GET /logical_devices/{{device_id}}/triggers``

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
            ]
        }

Static Scenes
=============

.. include:: ../snippets/data-pharos-mosaic.rst

``GET /logical_devices/{{device_id}}/static_scenes``

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
            ]
        }

Fixture Groups
==============

.. include:: ../snippets/data-pharos-mosaic.rst

``GET /logical_devices/{{device_id}}/fixture_groups``

Returns a JSON object including the list of available fixture groups for this device. The object includes an array of groups, with attributes for the scene ID, type, name and status.

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
            ]
        }

Timelines
=========

.. include:: ../snippets/data-pharos-mosaic.rst

``GET /logical_devices/{{device_id}}/timelines``

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
            ]
        }

Patch
=====

.. include:: ../snippets/data-pharos-mosaic.rst

``GET /logical_devices/{{device_id}}/patch``

Returns data about the patched universes, local and eDMX, for the device.

.. collapse:: Example response

    .. code-block:: json

        {
            "data": [
                {
                    "id": 0,
                    "type": "patch",
                    "attributes": {
                        "protocol": "DMX",
                        "universes": [
                            {
                                "id": "0",
                                "name": "1"
                            }
                        ]
                    }
                },
                {
                    "id": 1,
                    "type": "patch",
                    "attributes": {
                        "protocol": "EDN SDI",
                        "universes": [
                            {
                                "id": "0",
                                "name": "EDN 20 1 (SDI port 1)"
                            },
                            {
                                "id": "1",
                                "name": "EDN 20 1 (SDI port 2)"
                            },
                            {
                                "id": "2",
                                "name": "EDN 20 1 (SDI port 3)"
                            },
                            {
                                "id": "3",
                                "name": "EDN 20 1 (SDI port 4)"
                            },
                            {
                                "id": "4",
                                "name": "EDN 20 1 (SDI port 5)"
                            },
                            {
                                "id": "5",
                                "name": "EDN 20 1 (SDI port 6)"
                            },
                            {
                                "id": "6",
                                "name": "EDN 20 1 (SDI port 7)"
                            },
                            {
                                "id": "7",
                                "name": "EDN 20 1 (SDI port 8)"
                            },
                            {
                                "id": "8",
                                "name": "EDN 20 1 (SDI port 9)"
                            },
                            {
                                "id": "9",
                                "name": "EDN 20 1 (SDI port 10)"
                            },
                            {
                                "id": "10",
                                "name": "EDN 20 1 (SDI port 11)"
                            },
                            {
                                "id": "11",
                                "name": "EDN 20 1 (SDI port 12)"
                            },
                            {
                                "id": "12",
                                "name": "EDN 20 1 (SDI port 13)"
                            },
                            {
                                "id": "13",
                                "name": "EDN 20 1 (SDI port 14)"
                            },
                            {
                                "id": "14",
                                "name": "EDN 20 1 (SDI port 15)"
                            },
                            {
                                "id": "15",
                                "name": "EDN 20 1 (SDI port 16)"
                            },
                            {
                                "id": "16",
                                "name": "EDN 20 1 (SDI port 17)"
                            },
                            {
                                "id": "17",
                                "name": "EDN 20 1 (SDI port 18)"
                            },
                            {
                                "id": "18",
                                "name": "EDN 20 1 (SDI port 19)"
                            },
                            {
                                "id": "19",
                                "name": "EDN 20 1 (SDI port 20)"
                            }
                        ]
                    }
                }
            ]
        }

Log
===

.. include:: ../snippets/data-pharos-mosaic.rst

``GET /logical_devices/{{device_id}}/log_messages?lines={{lines}}``

Requests a set of log messages from the controller. This request must be passed a query parameter:

* lines - the maximum number of lines to return

.. collapse:: Example response

    .. code-block:: json

        {
            "data": [
                {
                    "id": 0,
                    "type": "logMessages",
                    "attributes": {
                        "message": "ACTION Enqueue Trigger: 20:Trigger 20",
                        "category": "Trigger",
                        "timestamp": 1662457572,
                        "severityLevel": 2
                    }
                },
                {
                    "id": 1,
                    "type": "logMessages",
                    "attributes": {
                        "message": "ACTION Run Script: Random Timeline executed successfully in 560 microseconds (mem in use = 69KB)",
                        "category": "Trigger",
                        "timestamp": 1662457572,
                        "severityLevel": 3
                    }
                },
                {
                    "id": 2,
                    "type": "logMessages",
                    "attributes": {
                        "message": "Script API: Start timeline Charity Event",
                        "category": "Controller API",
                        "timestamp": 1662457572,
                        "severityLevel": 2
                    }
                },
                {
                    "id": 3,
                    "type": "logMessages",
                    "attributes": {
                        "message": "ACTION Run Script: Running script Random Timeline",
                        "category": "Trigger",
                        "timestamp": 1662457572,
                        "severityLevel": 3
                    }
                },
                {
                    "id": 4,
                    "type": "logMessages",
                    "attributes": {
                        "message": "Trigger 28 (Real Time Clock): Matched",
                        "category": "Trigger",
                        "timestamp": 1662457572,
                        "severityLevel": 2
                    }
                },
                {
                    "id": 5,
                    "type": "logMessages",
                    "attributes": {
                        "message": "ACTION Master Intensity of All Conventional 8 bit to 14% (0x23)",
                        "category": "Trigger",
                        "timestamp": 1662457567,
                        "severityLevel": 4
                    }
                }
            ]
        }

IO Modules
==========

.. include:: ../snippets/data-pharos-mosaic.rst

``GET /logical_devices/{{device_id}}/io_modules``

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
            ]
        }

IO Instances
============

.. include:: ../snippets/data-pharos-mosaic.rst

``GET /logical_devices/{{device_id}}/io_instances``

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
            ]
        }

Remote Devices
==============

.. include:: ../snippets/data-pharos-mosaic.rst

``GET /logical_devices/{{device_id}}/remote_devices``

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
            ]
        }

Expert Scenes
=============

.. include:: ../snippets/data-pharos-expert.rst

``GET /logical_devices/{{device_id}}/expert_scenes``

Requests a list of the available scenes for an Expert device.

Each scene is identified by a unique number. Each scene has a ``name``, and a ``parent_space_id`` to identify the space the scene is located in.


.. collapse:: Example response

    .. code-block:: json

        {
            "scenes": {
                "0": {
                    "parent_space_id": 5,
                    "name": "Off"
                },
                "3": {
                    "parent_space_id": 1,
                    "name": "Worklights "
                },
                "2": {
                    "parent_space_id": 1,
                    "name": "Security"
                },
                "4": {
                    "parent_space_id": 2,
                    "name": "Bright entrance"
                },
                "5": {
                    "parent_space_id": 2,
                    "name": "Default"
                },
                "6": {
                    "parent_space_id": 2,
                    "name": "Functional"
                },
                "7": {
                    "parent_space_id": 2,
                    "name": "After hours"
                },
                "8": {
                    "parent_space_id": 4,
                    "name": "Decay"
                }
            }
        }


Expert Spaces
=============

.. include:: ../snippets/data-pharos-expert.rst

``GET /logical_devices/{{device_id}}/expert_spaces``

Requests a list of the available spaces for an Expert device.

Each space is identified by a unique number. Each space has a ``name``, and a ``parent_id`` to identify the parent of the space. If the parent is 0xFFFFFFFF(4294967295), this indicates it is the root space.

For each space the currently active scene and intensity master value is provided. If the active scene is 0, that indicates no active scene / off. If the active scene is 0xFFFFFFFF(4294967295), this indicates that levels are being controlled by a scene in the parent space(s).


.. collapse:: Example response

    .. code-block:: json

        {
            "spaces": {
                "1": {
                    "parent_id": 4294967295,
                    "name": "Project Space",
                    "scene": 2,
                    "int_master": 100
                },
                "2": {
                    "parent_id": 1,
                    "name": "Entrance",
                    "scene": 4294967295,
                    "int_master": 0
                },
                "3": {
                    "parent_id": 1,
                    "name": "Restaurant",
                    "scene": 4294967295,
                    "int_master": 0
                },
                "4": {
                    "parent_id": 3,
                    "name": "Restaurant - Bar",
                    "scene": 0,
                    "int_master": 100
                },
                "6": {
                    "parent_id": 1,
                    "name": "Lounge",
                    "scene": 4294967295,
                    "int_master": 0
                },
                "7": {
                    "parent_id": 1,
                    "name": "Patio",
                    "scene": 4294967295,
                    "int_master": 0
                },
                "8": {
                    "parent_id": 7,
                    "name": "Patio Firepit",
                    "scene": 0,
                    "int_master": 100
                },
                "5": {
                    "parent_id": 3,
                    "name": "Restaurant - Cove",
                    "scene": 0,
                    "int_master": 100
                }
            }
        }

Expert Tag Sets
===============

.. include:: ../snippets/data-pharos-expert.rst

``GET /logical_devices/{{device_id}}/expert_tag_sets``

Requests a list of the available tag sets and tags for an Expert device.

Each tag set contains a set of tags, identified by an ``id`` number and a ``name``.

Each tag set has a currently active tag, indicated by ``value_id``. Each tag set also has a ``name``.


.. collapse:: Example response

    .. code-block:: json

        {
            "tag_sets": {
                "1": {
                    "value_id": 2,
                    "name": "Type of day",
                    "values": [
                        {
                            "name": "Weekend",
                            "id": 1
                        },
                        {
                            "name": "Workdays",
                            "id": 2
                        }
                    ]
                },
                "2": {
                    "value_id": 3,
                    "name": "Mode",
                    "values": [
                        {
                            "name": "Default",
                            "id": 1
                        },
                        {
                            "name": "Cleaning",
                            "id": 2
                        },
                        {
                            "name": "Emergency",
                            "id": 3
                        }
                    ]
                },
                "3": {
                    "value_id": 4,
                    "name": "Usage",
                    "values": [
                        {
                            "name": "Lunch",
                            "id": 1
                        },
                        {
                            "name": "Corporate",
                            "id": 2
                        },
                        {
                            "name": "Dinner",
                            "id": 3
                        },
                        {
                            "name": "Club",
                            "id": 4
                        }
                    ]
                }
            }
        }
