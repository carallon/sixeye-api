Sites
#####

The Sites API provides methods to list sites, get site details, or modify a site within a portal.

Attributes
**********

A site has the following attributes:

.. list-table::
   :widths: 3 3 10
   :header-rows: 1

   * - Attribute
     - Value Type
     - Description
   * - ``name``
     - string
     - The identifying name of this site
   * - ``usersCount``
     - integer
     - The number of users of this site
   * - ``logicalDevicesCount``
     - integer
     - The number of logical devices associated with this site
   * - ``createdAt``
     - date-time
     - The time that this site was created
   * - ``updatedAt``
     - date-time
     - the last time that this site was updated
   * - ``latitude``
     - floating point
     - The latitude of the site, in degrees
   * - ``longitude``
     - floating point
     - The longitude of the site, in degrees
   * - ``timezoneId``
     - string
     - The Timezone of the site, in tz database format
   * - ``offset``
     - floating point
     - TODO
   * - ``geoAddress``
     - string
     - The physical, geographical address of the site
   * - ``address``
     - string
     - TODO
   * - ``notes``
     - string
     - A field for arbitrary notes about this site
   * - ``state``
     - string
     - TODO - what are possible values?
   * - ``points``
     - integer
     - TODO
   * - ``subscriptionPlanCode``
     - string
     - TODO
   * - ``projectedSubscriptionPlanCode``
     - string
     - TODO
   * - ``dateBlockingStartTime``
     - string
     - TODO
   * - ``primaryContactEmail``
     - string
     - The primary email contact for this site
   * - ``primaryContactPerson``
     - string
     - The name of the primary contact for this site
   * - ``primaryContactPhone``
     - string
     - The contact telephone number for the primary contact for this site
   * - ``technicalContactEmail``
     - string
     - The email contact of the technical manager for this site
   * - ``subscriptionContactEmail``
     - string
     - The email contact of the person responsible for dealing with subscriptions for this site
   * - ``commercialContactEmail``
     - string
     - The email contact of the person responsible for dealing with commercial/billing matters for this site
   * - ``projectSuitesCount``
     - integer
     - TODO
   * - ``trialPeriodDays``
     - integer
     - How many days are left in the trial period, or null if this is no longer in a trial period
   * - ``renewalDate``
     - date-time
     - The expiry date of this site's plan
   * - ``projectedRenewalDate``
     - date-time
     - TODO
   * - ``onlineDevices``
     - integer
     - The number of devices reporting as online
   * - ``offlineDevices``
     - integer
     - The number of devices reporting as offline
   * - ``unassociatedDevices``
     - integer
     - The number of devices online but not associated with the SixEye system
   * - ``devicesForUpgrade``
     - integer
     - The number of devices that have firmware upgrades available


Methods
*******

GET
===

Gets information about all sites (if not parameters are provided), or a single site if that site's UUID is included in the URL.

``GET /projects``

Returns a JSON object with an array of sites

.. collapse:: Example response

    .. code-block:: json

        {
            "data": [
                {
                    "id": "0da10710-4240-4f5c-81a7-cb8bca666d3b",
                    "type": "projects",
                    "links": {
                        "self": "https://primary-release.republic-api.com/projects/0da10710-4240-4f5c-81a7-cb8bca666d3b"
                    },
                    "attributes": {
                        "name": "TomSite",
                        "usersCount": 2,
                        "logicalDevicesCount": 5,
                        "createdAt": "2023-03-13T10:30:47.460+00:00",
                        "updatedAt": "2023-03-13T10:33:29.670+00:00",
                        "latitude": "51.512769",
                        "longitude": "-0.311615",
                        "timezoneId": "Europe/London",
                        "offset": 0.0,
                        "geoAddress": "Ibis Styles Hotel, 32-38, Uxbridge Road, London Borough of Ealing, London, Greater London, England, W5 2BS, United Kingdom",
                        "address": null,
                        "notes": null,
                        "state": "active",
                        "points": 12,
                        "subscriptionPlanCode": "A",
                        "projectedSubscriptionPlanCode": "A+",
                        "dateBlockingStartTime": null,
                        "primaryContactEmail": null,
                        "primaryContactPerson": null,
                        "primaryContactPhone": null,
                        "technicalContactEmail": null,
                        "subscriptionContactEmail": null,
                        "commercialContactEmail": null,
                        "projectSuitesCount": 0,
                        "trialPeriodDays": null,
                        "renewalDate": "2025-09-12T23:59:59Z",
                        "projectedRenewalDate": "2024-09-12T23:59:59Z",
                        "onlineDevices": 5,
                        "offlineDevices": 0,
                        "unassociatedDevices": 0,
                        "devicesForUpgrade": 0
                    },
                    "relationships": {
                        "users": {
                            "links": {
                                "self": "https://primary-release.republic-api.com/projects/0da10710-4240-4f5c-81a7-cb8bca666d3b/relationships/users",
                                "related": "https://primary-release.republic-api.com/projects/0da10710-4240-4f5c-81a7-cb8bca666d3b/users"
                            }
                        },
                        "logicalDevices": {
                            "links": {
                                "self": "https://primary-release.republic-api.com/projects/0da10710-4240-4f5c-81a7-cb8bca666d3b/relationships/logical_devices",
                                "related": "https://primary-release.republic-api.com/projects/0da10710-4240-4f5c-81a7-cb8bca666d3b/logical_devices"
                            }
                        },
                        "shareableApiKeys": {
                            "links": {
                                "self": "https://primary-release.republic-api.com/projects/0da10710-4240-4f5c-81a7-cb8bca666d3b/relationships/shareable_api_keys",
                                "related": "https://primary-release.republic-api.com/projects/0da10710-4240-4f5c-81a7-cb8bca666d3b/shareable_api_keys"
                            }
                        },
                        "notifications": {
                            "links": {
                                "self": "https://primary-release.republic-api.com/projects/0da10710-4240-4f5c-81a7-cb8bca666d3b/relationships/notifications",
                                "related": "https://primary-release.republic-api.com/projects/0da10710-4240-4f5c-81a7-cb8bca666d3b/notifications"
                            }
                        },
                        "tasks": {
                            "links": {
                                "self": "https://primary-release.republic-api.com/projects/0da10710-4240-4f5c-81a7-cb8bca666d3b/relationships/tasks",
                                "related": "https://primary-release.republic-api.com/projects/0da10710-4240-4f5c-81a7-cb8bca666d3b/tasks"
                            }
                        },
                        "automatedOperations": {
                            "links": {
                                "self": "https://primary-release.republic-api.com/projects/0da10710-4240-4f5c-81a7-cb8bca666d3b/relationships/automated_operations",
                                "related": "https://primary-release.republic-api.com/projects/0da10710-4240-4f5c-81a7-cb8bca666d3b/automated_operations"
                            }
                        },
                        "aoOccurrences": {
                            "links": {
                                "self": "https://primary-release.republic-api.com/projects/0da10710-4240-4f5c-81a7-cb8bca666d3b/relationships/ao_occurrences",
                                "related": "https://primary-release.republic-api.com/projects/0da10710-4240-4f5c-81a7-cb8bca666d3b/ao_occurrences"
                            }
                        },
                        "controlPanelPage": {
                            "links": {
                                "self": "https://primary-release.republic-api.com/projects/0da10710-4240-4f5c-81a7-cb8bca666d3b/relationships/control_panel_page",
                                "related": "https://primary-release.republic-api.com/projects/0da10710-4240-4f5c-81a7-cb8bca666d3b/control_panel_page"
                            }
                        },
                        "projectSuites": {
                            "links": {
                                "self": "https://primary-release.republic-api.com/projects/0da10710-4240-4f5c-81a7-cb8bca666d3b/relationships/project_suites",
                                "related": "https://primary-release.republic-api.com/projects/0da10710-4240-4f5c-81a7-cb8bca666d3b/project_suites"
                            }
                        },
                        "actionTypesList": {
                            "links": {
                                "self": "https://primary-release.republic-api.com/projects/0da10710-4240-4f5c-81a7-cb8bca666d3b/relationships/action_types_list",
                                "related": "https://primary-release.republic-api.com/projects/0da10710-4240-4f5c-81a7-cb8bca666d3b/action_types_list"
                            }
                        }
                    }
                }
            ]
        }


``GET /projects/{project_uuid}``

Returns a JSON object with a singular data item for the site, or a 404 error if the project UUID is not recognized.

.. collapse:: Example response

    .. code-block:: json

        {
            "data": {
                "id": "0da10710-4240-4f5c-81a7-cb8bca666d3b",
                "type": "projects",
                "links": {
                    "self": "https://primary-release.republic-api.com/projects/0da10710-4240-4f5c-81a7-cb8bca666d3b"
                },
                "attributes": {
                    "name": "TomSite",
                    "usersCount": 2,
                    "logicalDevicesCount": 5,
                    "createdAt": "2023-03-13T10:30:47.460+00:00",
                    "updatedAt": "2023-03-13T10:33:29.670+00:00",
                    "latitude": "51.512769",
                    "longitude": "-0.311615",
                    "timezoneId": "Europe/London",
                    "offset": 0.0,
                    "geoAddress": "Ibis Styles Hotel, 32-38, Uxbridge Road, London Borough of Ealing, London, Greater London, England, W5 2BS, United Kingdom",
                    "address": null,
                    "notes": null,
                    "state": "active",
                    "points": 12,
                    "subscriptionPlanCode": "A",
                    "projectedSubscriptionPlanCode": "A+",
                    "dateBlockingStartTime": null,
                    "primaryContactEmail": null,
                    "primaryContactPerson": null,
                    "primaryContactPhone": null,
                    "technicalContactEmail": null,
                    "subscriptionContactEmail": null,
                    "commercialContactEmail": null,
                    "projectSuitesCount": 0,
                    "trialPeriodDays": null,
                    "renewalDate": "2025-09-12T23:59:59Z",
                    "projectedRenewalDate": "2024-09-12T23:59:59Z",
                    "onlineDevices": 5,
                    "offlineDevices": 0,
                    "unassociatedDevices": 0,
                    "devicesForUpgrade": 0
                },
                "relationships": {
                    "users": {
                        "links": {
                            "self": "https://primary-release.republic-api.com/projects/0da10710-4240-4f5c-81a7-cb8bca666d3b/relationships/users",
                            "related": "https://primary-release.republic-api.com/projects/0da10710-4240-4f5c-81a7-cb8bca666d3b/users"
                        }
                    },
                    "logicalDevices": {
                        "links": {
                            "self": "https://primary-release.republic-api.com/projects/0da10710-4240-4f5c-81a7-cb8bca666d3b/relationships/logical_devices",
                            "related": "https://primary-release.republic-api.com/projects/0da10710-4240-4f5c-81a7-cb8bca666d3b/logical_devices"
                        }
                    },
                    "shareableApiKeys": {
                        "links": {
                            "self": "https://primary-release.republic-api.com/projects/0da10710-4240-4f5c-81a7-cb8bca666d3b/relationships/shareable_api_keys",
                            "related": "https://primary-release.republic-api.com/projects/0da10710-4240-4f5c-81a7-cb8bca666d3b/shareable_api_keys"
                        }
                    },
                    "notifications": {
                        "links": {
                            "self": "https://primary-release.republic-api.com/projects/0da10710-4240-4f5c-81a7-cb8bca666d3b/relationships/notifications",
                            "related": "https://primary-release.republic-api.com/projects/0da10710-4240-4f5c-81a7-cb8bca666d3b/notifications"
                        }
                    },
                    "tasks": {
                        "links": {
                            "self": "https://primary-release.republic-api.com/projects/0da10710-4240-4f5c-81a7-cb8bca666d3b/relationships/tasks",
                            "related": "https://primary-release.republic-api.com/projects/0da10710-4240-4f5c-81a7-cb8bca666d3b/tasks"
                        }
                    },
                    "automatedOperations": {
                        "links": {
                            "self": "https://primary-release.republic-api.com/projects/0da10710-4240-4f5c-81a7-cb8bca666d3b/relationships/automated_operations",
                            "related": "https://primary-release.republic-api.com/projects/0da10710-4240-4f5c-81a7-cb8bca666d3b/automated_operations"
                        }
                    },
                    "aoOccurrences": {
                        "links": {
                            "self": "https://primary-release.republic-api.com/projects/0da10710-4240-4f5c-81a7-cb8bca666d3b/relationships/ao_occurrences",
                            "related": "https://primary-release.republic-api.com/projects/0da10710-4240-4f5c-81a7-cb8bca666d3b/ao_occurrences"
                        }
                    },
                    "controlPanelPage": {
                        "links": {
                            "self": "https://primary-release.republic-api.com/projects/0da10710-4240-4f5c-81a7-cb8bca666d3b/relationships/control_panel_page",
                            "related": "https://primary-release.republic-api.com/projects/0da10710-4240-4f5c-81a7-cb8bca666d3b/control_panel_page"
                        }
                    },
                    "projectSuites": {
                        "links": {
                            "self": "https://primary-release.republic-api.com/projects/0da10710-4240-4f5c-81a7-cb8bca666d3b/relationships/project_suites",
                            "related": "https://primary-release.republic-api.com/projects/0da10710-4240-4f5c-81a7-cb8bca666d3b/project_suites"
                        }
                    },
                    "actionTypesList": {
                        "links": {
                            "self": "https://primary-release.republic-api.com/projects/0da10710-4240-4f5c-81a7-cb8bca666d3b/relationships/action_types_list",
                            "related": "https://primary-release.republic-api.com/projects/0da10710-4240-4f5c-81a7-cb8bca666d3b/action_types_list"
                        }
                    }
                }
            }
        }


PUT
===

Allows modification of the properties of an existing site.

``PUT /projects/{site_uuid}``

The body of the request must be a JSON object including the type ``projects`` field, the UUID for the site, and the list of attributes you wish to update.

For example:


.. code-block:: json

    {
        "data": {
            "type": "projects",
            "id": "0da10710-4240-4f5c-81a7-cb8bca666d3b",
            "attributes": {
                "name": "NewProjectName",
                "latitude": "51.517469",
                "longitude": "-0.319168",
                "address": "New address",
                "notes": "Note value",
                "primaryContactEmail": "primaryEmail@example.com",
                "primaryContactPerson": "John Doe",
                "primaryContactPhone": "123 456 789",
                "technicalContactEmail": "technicalContactEmail@example.com",
                "subscriptionContactEmail": "subscriptionContactEmail@example.com",
                "commercialContactEmail": "commercialContactEmail@example.com"
            }
        }
    }