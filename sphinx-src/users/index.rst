Users
#####

The Users API provides methods to list users, invite a user to join a site, or delete users.

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
   * - ``superadmin``
     - boolean
     - Whether or not this user is a superadmin
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
   * - ``tenantAdmin``
     - boolean
     - TODO
   * - ``superAdmin``
     - boolean
     - Whether this user is a superadmin for the site


Methods
*******

GET
===

Gets information about all users (if not parameters are provided), or a single user if that users UUID is included in the URL.

``GET /users`` or ``GET /users/{{user_uuid}}``

Returns a JSON object with an array of users

.. collapse:: Example response

    .. code-block:: json

        {
            "data": [
                {
                    "id": "465acd55-6e48-4297-839f-bc0f7d70020b",
                    "type": "users",
                    "links": {
                        "self": "https://primary-release.republic-api.com/users/465acd55-6e48-4297-839f-bc0f7d70020b"
                    },
                    "attributes": {
                        "firstName": "Joe",
                        "lastName": "Manager",
                        "email": "joe.manager@example.com",
                        "phoneNumber": "123456789",
                        "superadmin": true,
                        "suspended": false,
                        "lastLoginTime": "2023-03-08T10:18:38.501+00:00",
                        "lastActionTime": "2023-03-16T13:32:26.056+00:00",
                        "twoFactorEnabled": true,
                        "tenantAdmin": false,
                        "superAdmin": true
                    },
                    "relationships": {
                        "projects": {
                            "links": {
                                "self": "https://primary-release.republic-api.com/users/465acd55-6e48-4297-839f-bc0f7d70020b/relationships/projects",
                                "related": "https://primary-release.republic-api.com/users/465acd55-6e48-4297-839f-bc0f7d70020b/projects"
                            }
                        },
                        "projectSuites": {
                            "links": {
                                "self": "https://primary-release.republic-api.com/users/465acd55-6e48-4297-839f-bc0f7d70020b/relationships/project_suites",
                                "related": "https://primary-release.republic-api.com/users/465acd55-6e48-4297-839f-bc0f7d70020b/project_suites"
                            }
                        },
                        "receivedInvitations": {
                            "links": {
                                "self": "https://primary-release.republic-api.com/users/465acd55-6e48-4297-839f-bc0f7d70020b/relationships/received_invitations",
                                "related": "https://primary-release.republic-api.com/users/465acd55-6e48-4297-839f-bc0f7d70020b/received_invitations"
                            }
                        },
                        "sentInvitations": {
                            "links": {
                                "self": "https://primary-release.republic-api.com/users/465acd55-6e48-4297-839f-bc0f7d70020b/relationships/sent_invitations",
                                "related": "https://primary-release.republic-api.com/users/465acd55-6e48-4297-839f-bc0f7d70020b/sent_invitations"
                            }
                        }
                    }
                },
                {
                    "id": "dfd54e1f-3bce-4322-a935-f98ba97a9201",
                    "type": "users",
                    "links": {
                        "self": "https://primary-release.republic-api.com/users/dfd54e1f-3bce-4322-a935-f98ba97a9201"
                    },
                    "attributes": {
                        "firstName": "Bob",
                        "lastName": "User",
                        "email": "bob.user@example.com",
                        "phoneNumber": "+1 234 567 890",
                        "superadmin": false,
                        "suspended": false,
                        "lastLoginTime": "2023-03-13T10:37:02.176+00:00",
                        "lastActionTime": "2023-03-14T16:12:51.626+00:00",
                        "twoFactorEnabled": false,
                        "tenantAdmin": false,
                        "superAdmin": false
                    },
                    "relationships": {
                        "projects": {
                            "links": {
                                "self": "https://primary-release.republic-api.com/users/dfd54e1f-3bce-4322-a935-f98ba97a9201/relationships/projects",
                                "related": "https://primary-release.republic-api.com/users/dfd54e1f-3bce-4322-a935-f98ba97a9201/projects"
                            }
                        },
                        "projectSuites": {
                            "links": {
                                "self": "https://primary-release.republic-api.com/users/dfd54e1f-3bce-4322-a935-f98ba97a9201/relationships/project_suites",
                                "related": "https://primary-release.republic-api.com/users/dfd54e1f-3bce-4322-a935-f98ba97a9201/project_suites"
                            }
                        },
                        "receivedInvitations": {
                            "links": {
                                "self": "https://primary-release.republic-api.com/users/dfd54e1f-3bce-4322-a935-f98ba97a9201/relationships/received_invitations",
                                "related": "https://primary-release.republic-api.com/users/dfd54e1f-3bce-4322-a935-f98ba97a9201/received_invitations"
                            }
                        },
                        "sentInvitations": {
                            "links": {
                                "self": "https://primary-release.republic-api.com/users/dfd54e1f-3bce-4322-a935-f98ba97a9201/relationships/sent_invitations",
                                "related": "https://primary-release.republic-api.com/users/dfd54e1f-3bce-4322-a935-f98ba97a9201/sent_invitations"
                            }
                        }
                    }
                }
            ]
        }


``GET /users/{user_uuid}``

Returns a JSON object with a singular data item for the user, or a 404 error if the user UUID is not recognized.

.. collapse:: Example response

    .. code-block:: json

        {
            "data": {
                "id": "dfd54e1f-3bce-4322-a935-f98ba97a9201",
                "type": "users",
                "links": {
                    "self": "https://primary-release.republic-api.com/users/dfd54e1f-3bce-4322-a935-f98ba97a9201"
                },
                "attributes": {
                    "firstName": "Bob",
                    "lastName": "User",
                    "email": "bob.user@example.com",
                    "phoneNumber": "+1 234 567 890",
                    "superadmin": false,
                    "suspended": false,
                    "lastLoginTime": "2023-03-13T10:37:02.176+00:00",
                    "lastActionTime": "2023-03-14T16:12:51.626+00:00",
                    "twoFactorEnabled": false,
                    "tenantAdmin": false,
                    "superAdmin": false
                },
                "relationships": {
                    "projects": {
                        "links": {
                            "self": "https://primary-release.republic-api.com/users/dfd54e1f-3bce-4322-a935-f98ba97a9201/relationships/projects",
                            "related": "https://primary-release.republic-api.com/users/dfd54e1f-3bce-4322-a935-f98ba97a9201/projects"
                        }
                    },
                    "projectSuites": {
                        "links": {
                            "self": "https://primary-release.republic-api.com/users/dfd54e1f-3bce-4322-a935-f98ba97a9201/relationships/project_suites",
                            "related": "https://primary-release.republic-api.com/users/dfd54e1f-3bce-4322-a935-f98ba97a9201/project_suites"
                        }
                    },
                    "receivedInvitations": {
                        "links": {
                            "self": "https://primary-release.republic-api.com/users/dfd54e1f-3bce-4322-a935-f98ba97a9201/relationships/received_invitations",
                            "related": "https://primary-release.republic-api.com/users/dfd54e1f-3bce-4322-a935-f98ba97a9201/received_invitations"
                        }
                    },
                    "sentInvitations": {
                        "links": {
                            "self": "https://primary-release.republic-api.com/users/dfd54e1f-3bce-4322-a935-f98ba97a9201/relationships/sent_invitations",
                            "related": "https://primary-release.republic-api.com/users/dfd54e1f-3bce-4322-a935-f98ba97a9201/sent_invitations"
                        }
                    }
                }
            }
        }


POST
====

Allows invitation of a new user to the site. This call will send an invitation email to a new user.

``POST /users``

The body of the request must be a JSON object with type of inviteUser, and including:

* ``id`` - a newly generated UUID for the new user
* ``email`` - the email to which the invitation will be sent
* ``projectId`` - the project (site) to which the user will be invited

For example:

.. code-block:: json

    {
        "data": {
            "type": "inviteUser",
            "id": "{{$randomUUID}}",
            "attributes": {
                "email": "new.user@example.com",
                "projectId": "{{project_id}}"
            }
        }
    }
