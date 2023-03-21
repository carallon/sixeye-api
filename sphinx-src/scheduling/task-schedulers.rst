Task Schedulers
###############


Attributes
**********

A Task Scheduler has the following attributes:

.. list-table::
   :widths: 3 3 10
   :header-rows: 1

   * - Attribute
     - Value Type
     - Description
   * - ``name``
     - string
     - The identifying name of this task scheduler
   * - ``projectId``
     - UUID
     - The site that this task scheduler is associated with
   * - ``description``
     - string
     - A text description associated with this task scheduler
   * - ``timeZone``
     - string
     - The timezone in which this scheduler should be calculated, in tz database format
   * - ``location``
     - object
     - An object containing latitude and longitude, used to calculate time for astronomical events
   * - ``taskIds``
     - array of UUID strings
     - The *tasks* which will be initiated when this task scheduler occurs
   * - ``lockVersion``
     - integer
     - TODO
   * - ``enabled``
     - boolean
     - Allows a particular task scheduler to be enabled or disabled
   * - ``occurrenceColour``
     - string, colour in HTML format
     - The colour used to indicate this task scheduler in the application UI
   * - ``deleted``
     - boolean
     - Whether or not this scheduler has been deleted
   * - ``priority``
     - integer
     - TODO
   * - ``priorityType``
     - string
     - TODO
   * - ``mode``
     - string
     - TODO
   * - ``projectSuiteId``
     - TODO
     - TODO
   * - ``hidden``
     - boolean
     - TODO
   * - ``dateBlockingStartTime``
     - TODO
     - TODO
   * - ``calculationState``
     - TODO
     - TODO


Methods
*******

GET
===

``GET projects/{{project_id}}/automated_operations``

Returns a JSON object with a data member consisting of an array of automatedOperations objects


.. collapse:: Example response

    .. code-block:: json

        {
            "data": [
                {
                    "id": "5c875c81-262a-45ef-9b99-fa910b5ef645",
                    "type": "automatedOperations",
                    "links": {
                        "self": "https://primary-release.republic-api.com/automated_operations/5c875c81-262a-45ef-9b99-fa910b5ef645"
                    },
                    "attributes": {
                        "name": "Monthly Astro",
                        "projectId": "0da10710-4240-4f5c-81a7-cb8bca666d3b",
                        "description": null,
                        "timeZone": "Europe/London",
                        "location": {
                            "latitude": "0.51512769e2",
                            "longitude": "-0.311615e0"
                        },
                        "taskIds": [
                            "65b4aa94-07af-4624-a588-57580af0c148"
                        ],
                        "lockVersion": "0",
                        "enabled": true,
                        "occurrenceColour": "#77AA00",
                        "deleted": null,
                        "priority": 2,
                        "priorityType": "times",
                        "mode": "forceExecution",
                        "projectSuiteId": null,
                        "hidden": false,
                        "dateBlockingStartTime": null,
                        "calculationState": "finished"
                    },
                    "relationships": {
                        "project": {
                            "links": {
                                "self": "https://primary-release.republic-api.com/automated_operations/5c875c81-262a-45ef-9b99-fa910b5ef645/relationships/project",
                                "related": "https://primary-release.republic-api.com/automated_operations/5c875c81-262a-45ef-9b99-fa910b5ef645/project"
                            }
                        },
                        "automatedFunction": {
                            "links": {
                                "self": "https://primary-release.republic-api.com/automated_operations/5c875c81-262a-45ef-9b99-fa910b5ef645/relationships/automated_function",
                                "related": "https://primary-release.republic-api.com/automated_operations/5c875c81-262a-45ef-9b99-fa910b5ef645/automated_function"
                            }
                        },
                        "schedules": {
                            "links": {
                                "self": "https://primary-release.republic-api.com/automated_operations/5c875c81-262a-45ef-9b99-fa910b5ef645/relationships/schedules",
                                "related": "https://primary-release.republic-api.com/automated_operations/5c875c81-262a-45ef-9b99-fa910b5ef645/schedules"
                            }
                        },
                        "aoOccurrences": {
                            "links": {
                                "self": "https://primary-release.republic-api.com/automated_operations/5c875c81-262a-45ef-9b99-fa910b5ef645/relationships/ao_occurrences",
                                "related": "https://primary-release.republic-api.com/automated_operations/5c875c81-262a-45ef-9b99-fa910b5ef645/ao_occurrences"
                            }
                        }
                    }
                },
                {
                    "id": "8959d02f-d366-4609-9990-3ab442d2f928",
                    "type": "automatedOperations",
                    "links": {
                        "self": "https://primary-release.republic-api.com/automated_operations/8959d02f-d366-4609-9990-3ab442d2f928"
                    },
                    "attributes": {
                        "name": "Toggle Beacon device Fake LPC",
                        "projectId": "0da10710-4240-4f5c-81a7-cb8bca666d3b",
                        "description": null,
                        "timeZone": "Europe/London",
                        "location": {
                            "latitude": "0.51512769e2",
                            "longitude": "-0.311615e0"
                        },
                        "taskIds": [
                            "65b4aa94-07af-4624-a588-57580af0c148"
                        ],
                        "lockVersion": "0",
                        "enabled": true,
                        "occurrenceColour": "#77AA00",
                        "deleted": null,
                        "priority": 2,
                        "priorityType": "times",
                        "mode": "forceExecution",
                        "projectSuiteId": null,
                        "hidden": false,
                        "dateBlockingStartTime": null,
                        "calculationState": "finished"
                    },
                    "relationships": {
                        "project": {
                            "links": {
                                "self": "https://primary-release.republic-api.com/automated_operations/8959d02f-d366-4609-9990-3ab442d2f928/relationships/project",
                                "related": "https://primary-release.republic-api.com/automated_operations/8959d02f-d366-4609-9990-3ab442d2f928/project"
                            }
                        },
                        "automatedFunction": {
                            "links": {
                                "self": "https://primary-release.republic-api.com/automated_operations/8959d02f-d366-4609-9990-3ab442d2f928/relationships/automated_function",
                                "related": "https://primary-release.republic-api.com/automated_operations/8959d02f-d366-4609-9990-3ab442d2f928/automated_function"
                            }
                        },
                        "schedules": {
                            "links": {
                                "self": "https://primary-release.republic-api.com/automated_operations/8959d02f-d366-4609-9990-3ab442d2f928/relationships/schedules",
                                "related": "https://primary-release.republic-api.com/automated_operations/8959d02f-d366-4609-9990-3ab442d2f928/schedules"
                            }
                        },
                        "aoOccurrences": {
                            "links": {
                                "self": "https://primary-release.republic-api.com/automated_operations/8959d02f-d366-4609-9990-3ab442d2f928/relationships/ao_occurrences",
                                "related": "https://primary-release.republic-api.com/automated_operations/8959d02f-d366-4609-9990-3ab442d2f928/ao_occurrences"
                            }
                        }
                    }
                }
            ]
        }


``GET projects/{{project_id}}/automated_operations/{{automated_operation_id}}``

Returns a JSON object with a data member consisting of the automatedOperations object for the specified automated_operation_id, or a 404 error if the ID does not exist.



POST
====

``POST projects/automated_operations``

Creates a new Task Scheduler. The body must consist of a JSON object with attributes for the name, Project ID and Task IDs to be executed by this scheduler as shown below.


.. code-block:: json

    {
        "data":
        {
            "type": "automated_operations",
            "attributes": {
                "name": "TaskScheduler1",
                "projectId": "{{project_id}}",
                "taskIds": ["{{task_id}}"]
            }
        }
    }

PUT
===

``PUT projects/automated_operations/{{automated_operation_id}}``

Modifies an existing Task Scheduler. The body must consist of a JSON object with attributes for the items to be modified.

.. code-block:: json

    {
        "data": {
            "type": "automatedOperations",
            "id": "{{automated_operation_id}}",
            "attributes": {
                "name": "Beacon device LPC",
                "description": "Some description",
                "taskIds": [
                    "{{task_id}}"
                ],
                "enabled": true,
                "occurrenceColour": "#3FBCF5",
                "priority": 3,
                "priorityType": "dates",
                "mode": "forceExecution",
                "hidden": false,
                "lockVersion": "{{automated_operation_lock_version}}"
            }
        }
    }


DELETE
======

``DELETE projects/automated_operations/{{automated_operation_id}}``

Deletes the Task Scheduler specified by ``automated_operation_id``

TODO: This takes a automated_operation_lock_version??