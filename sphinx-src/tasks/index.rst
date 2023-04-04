Tasks
#####

Tasks are a collection of operations performed on one or more devices.

Tasks are created and configured using the SixEye web interface.

Tasks can be initiated manually via the Web UI (or via this API), or they can be scheduled to occur using the scheduling system.

Task Attributes
===============

.. list-table::
   :widths: 3 3 10
   :header-rows: 1

   * - Attribute
     - Value Type
     - Description
   * - ``name``
     - string
     - The identifying name of this task
   * - ``description``
     - string
     - A user facing description of this task
   * - ``actions``
     - array
     - An array of actions that this task performs - see below for more information
   * - ``projectId``
     - UUID
     - The UUID of the project (site) that this task belongs to


Retrieve List of Tasks
======================

``GET /projects/{{project_id}}/tasks``

Retrieves a list of tasks for the given ``project_id``.


.. collapse:: Example response

    .. code-block:: json

        {
            "data": [
                {
                    "id": "65b4aa94-07af-4624-a588-57580af0c148",
                    "type": "tasks",
                    "links": {
                        "self": "https://primary.sixeye-api.com/tasks/65b4aa94-07af-4624-a588-57580af0c148"
                    },
                    "attributes": {
                        "name": "Toggle Beacon device Fake LPC",
                        "description": "Toggle Beacon device Fake LPC",
                        "actions": [
                            {
                                "id": "6505f7a4-6dc9-4576-a9cc-eed752da51b3",
                                "name": "Beacon - Fake LPC",
                                "index": 0,
                                "typeId": "beacon_v1",
                                "logicalDeviceId": "00ec20e6-e8e4-4ed9-a640-5615e1a409b0",
                                "params": [
                                    {
                                        "key": "enabled",
                                        "value": true
                                    }
                                ]
                            },
                            {
                                "id": "ba4a97bc-f6af-49d5-b490-c42aa65bc32d",
                                "name": "Beacon - Fake LPC",
                                "index": 1,
                                "typeId": "beacon_v1",
                                "logicalDeviceId": "00ec20e6-e8e4-4ed9-a640-5615e1a409b0",
                                "params": [
                                    {
                                        "key": "enabled",
                                        "value": false
                                    }
                                ]
                            }
                        ],
                        "projectId": "0da10710-4240-4f5c-81a7-cb8bca666d3b",
                        "lockVersion": "1",
                        "projectSuiteId": null
                    },
                    "relationships": {
                        "project": {
                            "links": {
                                "self": "https://primary.sixeye-api.com/tasks/65b4aa94-07af-4624-a588-57580af0c148/relationships/project",
                                "related": "https://primary.sixeye-api.com/tasks/65b4aa94-07af-4624-a588-57580af0c148/project"
                            }
                        },
                        "projectSuite": {
                            "links": {
                                "self": "https://primary.sixeye-api.com/tasks/65b4aa94-07af-4624-a588-57580af0c148/relationships/project_suite",
                                "related": "https://primary.sixeye-api.com/tasks/65b4aa94-07af-4624-a588-57580af0c148/project_suite"
                            }
                        }
                    }
                },
                {
                    "id": "8b62d558-80d2-4411-add8-8a4bf4d4d686",
                    "type": "tasks",
                    "links": {
                        "self": "https://primary.sixeye-api.com/tasks/8b62d558-80d2-4411-add8-8a4bf4d4d686"
                    },
                    "attributes": {
                        "name": "Tom Test Task",
                        "description": "Toms Test",
                        "actions": null,
                        "projectId": "0da10710-4240-4f5c-81a7-cb8bca666d3b",
                        "lockVersion": "0",
                        "projectSuiteId": null
                    },
                    "relationships": {
                        "project": {
                            "links": {
                                "self": "https://primary.sixeye-api.com/tasks/8b62d558-80d2-4411-add8-8a4bf4d4d686/relationships/project",
                                "related": "https://primary.sixeye-api.com/tasks/8b62d558-80d2-4411-add8-8a4bf4d4d686/project"
                            }
                        },
                        "projectSuite": {
                            "links": {
                                "self": "https://primary.sixeye-api.com/tasks/8b62d558-80d2-4411-add8-8a4bf4d4d686/relationships/project_suite",
                                "related": "https://primary.sixeye-api.com/tasks/8b62d558-80d2-4411-add8-8a4bf4d4d686/project_suite"
                            }
                        }
                    }
                }
            ]
        }

Execute a Task
==============

A specific Task may be executed immediately by making a POST call:

``POST /tasks/{{task_id}}/execute``

No body is required to the POST.
