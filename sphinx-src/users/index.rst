Users
#####

The Users API provides methods to list users for a site.

Attributes
**********

A user has the following attributes:

.. list-table::
   :widths: 3 3 10
   :header-rows: 1

   * - Attribute
     - Value Type
     - Description
   * - ``firstName``
     - string
     - The first name of the user
   * - ``lastName``
     - string
     - The last name of the user
   * - ``email``
     - string
     - The email address of the user
   * - ``phoneNumber``
     - string
     - The contact phone number of the user
   * - ``suspended``
     - boolean
     - Whether or not this user's account is suspended
   * - ``lastLoginTime``
     - date-time
     - The date and time that this user last logged in
   * - ``lastActionTime``
     - date-time
     - The date and time that this user last triggered an action
   * - ``twoFactorEnabled``
     - boolean
     - Whether two-factor authentication is enabled for this user


Methods
*******

Get List of Users
=================

Gets information about all users (if no parameters are provided), or a single user if that users UUID is included in the URL.

``GET /users``

Returns a JSON object with an array of users

.. collapse:: Example response

    .. code-block:: json

        {
            "data": [
                {
                    "id": "465acd55-6e48-4297-839f-bc0f7d70020b",
                    "type": "users",
                    "attributes": {
                        "firstName": "Joe",
                        "lastName": "Manager",
                        "email": "joe.manager@example.com",
                        "phoneNumber": "123456789",
                        "suspended": false,
                        "lastLoginTime": "2023-03-08T10:18:38.501+00:00",
                        "lastActionTime": "2023-03-16T13:32:26.056+00:00",
                        "twoFactorEnabled": true,
                        "tenantAdmin": false
                    }
                },
                {
                    "id": "dfd54e1f-3bce-4322-a935-f98ba97a9201",
                    "type": "users",
                    "attributes": {
                        "firstName": "Bob",
                        "lastName": "User",
                        "email": "bob.user@example.com",
                        "phoneNumber": "+1 234 567 890",
                        "suspended": false,
                        "lastLoginTime": "2023-03-13T10:37:02.176+00:00",
                        "lastActionTime": "2023-03-14T16:12:51.626+00:00",
                        "twoFactorEnabled": false,
                        "tenantAdmin": false
                    }
                }
            ]
        }


Get Single User
===============

``GET /users/{{user_uuid}}``

Returns a JSON object with a singular data item for the user, or a 404 error if the user UUID is not recognized.

.. collapse:: Example response

    .. code-block:: json

        {
            "data": {
                "id": "dfd54e1f-3bce-4322-a935-f98ba97a9201",
                "type": "users",
                "attributes": {
                    "firstName": "Bob",
                    "lastName": "User",
                    "email": "bob.user@example.com",
                    "phoneNumber": "+1 234 567 890",
                    "suspended": false,
                    "lastLoginTime": "2023-03-13T10:37:02.176+00:00",
                    "lastActionTime": "2023-03-14T16:12:51.626+00:00",
                    "twoFactorEnabled": false,
                    "tenantAdmin": false
                }
            }
        }
