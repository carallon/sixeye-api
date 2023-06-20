Sites
#####

The Sites API provides methods to list sites within a portal.

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
     - The Timezone of the site, in `tz database <https://en.wikipedia.org/wiki/List_of_tz_database_time_zones>`_ format
   * - ``offset``
     - floating point
     - The time offset from UTC for the site
   * - ``geoAddress``
     - string
     - The physical, geographical address of the site
   * - ``notes``
     - string
     - A field for arbitrary notes about this site
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
   * - ``onlineDevices``
     - integer
     - The number of devices reporting as online
   * - ``offlineDevices``
     - integer
     - The number of devices reporting as offline
   * - ``unassociatedDevices``
     - integer
     - The number of logical devices, where the real devices were removed from the SixEye system or moved to another logical device
   * - ``devicesForUpgrade``
     - integer
     - The number of devices that have firmware upgrades available


Methods
*******

Get a List of Sites
===================

This call retrieves an array of information about all sites.

``GET /projects``

Returns a JSON object with an array of sites

.. collapse:: Example response

    .. code-block:: json

        {
            "data": [
                {
                    "id": "0da10710-4240-4f5c-81a7-cb8bca666d3b",
                    "type": "projects",
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
                    }
                }
            ]
        }


Get a Single Site
=================

``GET /projects/{{project_uuid}}``

Returns a JSON object with a singular data item for the site, or a 404 error if the project (site) UUID is not recognized.

.. collapse:: Example response

    .. code-block:: json

        {
            "data": {
                "id": "0da10710-4240-4f5c-81a7-cb8bca666d3b",
                "type": "projects",
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
                }
            }
        }
