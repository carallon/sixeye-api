Portals
#######

A portal is an interface into the SixEye system. A Portal can contain multiple sites.

Attributes
**********

Portal(company) objects have the following attributes:

.. list-table::
   :widths: 3 3 10
   :header-rows: 1

   * - Attribute
     - Value Type
     - Description
   * - ``name``
     - string
     - The human-readable name of this portal
   * - ``subdomain``
     - string
     - TODO
   * - ``themeName``
     - string
     - TODO
   * - ``deviceMapping``
     - string
     - TODO
   * - ``manufacturer``
     - string
     - TODO
   * - ``urlOriginId``
     - string
     - TODO
   * - ``mailgunDomain``
     - string
     - TODO
   * - ``tenantService``
     - string
     - TODO
   * - ``registeredName``
     - string
     - TODO
   * - ``email``
     - string
     - TODO
   * - ``twoFactorEnabled``
     - boolean
     - Whether or not two-factor authentication is enabled for this portal
   * - ``trialPeriodDays``
     - string
     - TODO
   * - ``gracePeriodDays``
     - string
     - TODO
   * - ``renewalDate``
     - string
     - TODO
   * - ``renewalReminderDays``
     - string
     - TODO
   * - ``renewalReminderDaysTwo``
     - string
     - TODO
   * - ``vouchersEnabled``
     - string
     - TODO
   * - ``notificationsEnabled``
     - string
     - TODO
   * - ``excludedPlanList``
     - array
     - TODO
   * - ``soldVia``
     - string
     - TODO
   * - ``ssoMicrosoftEnabled``
     - string
     - TODO
   * - ``shareableApiKeysEnabled``
     - string
     - TODO

Methods
*******

GET
===

Gets information about a portal.

``GET /companies``

Returns a JSON object with a single member, ``data``, which is an array of ``company`` objects. Each ``company`` object has attributes listed below:

.. list-table::
   :widths: 3 3 10
   :header-rows: 1

   * - Attribute
     - Value Type
     - Description
   * - ``id``
     - UUID
     - The UUID of this company
   * - ``type``
     - string
     - The object type, in this case ``companies``
   * - ``links``
     - object
     - links about this company
   * - ``attributes``
     - object
     - The attributes of this company - see above
   * - ``relationships``
     - object
     - TODO

.. collapse:: Example response

    .. code-block:: json

      {
          "data": [
              {
                  "id": "36268ad0-e71a-4232-bc7a-1f7512653a0d",
                  "type": "companies",
                  "links": {
                      "self": "https://primary-release.republic-api.com/companies/36268ad0-e71a-4232-bc7a-1f7512653a0d"
                  },
                  "attributes": {
                      "name": "SixEyeRelease",
                      "subdomain": "sixeye",
                      "themeName": "defaultTheme",
                      "deviceMapping": null,
                      "manufacturer": false,
                      "urlOriginId": null,
                      "mailgunDomain": "cloud-demo-mail.pharoscontrols.com",
                      "tenantService": null,
                      "registeredName": "name",
                      "email": "sixeye@sixeye.net",
                      "twoFactorEnabled": false,
                      "trialPeriodDays": 30,
                      "gracePeriodDays": 30,
                      "renewalDate": null,
                      "renewalReminderDays": 30,
                      "renewalReminderDaysTwo": 7,
                      "vouchersEnabled": true,
                      "notificationsEnabled": true,
                      "excludedPlanList": [],
                      "soldVia": "sixeye",
                      "ssoMicrosoftEnabled": false,
                      "shareableApiKeysEnabled": true
                  },
                  "relationships": {
                      "origins": {
                          "links": {
                              "self": "https://primary-release.republic-api.com/companies/36268ad0-e71a-4232-bc7a-1f7512653a0d/relationships/origins",
                              "related": "https://primary-release.republic-api.com/companies/36268ad0-e71a-4232-bc7a-1f7512653a0d/origins"
                          }
                      },
                      "urlOrigin": {
                          "links": {
                              "self": "https://primary-release.republic-api.com/companies/36268ad0-e71a-4232-bc7a-1f7512653a0d/relationships/url_origin",
                              "related": "https://primary-release.republic-api.com/companies/36268ad0-e71a-4232-bc7a-1f7512653a0d/url_origin"
                          }
                      }
                  }
              }
          ]
      }
