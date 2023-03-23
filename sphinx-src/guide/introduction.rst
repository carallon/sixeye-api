Introduction
############

This API provides facilities for interaction with the SixEye system.

Working with the API
********************

In order to work with the API you need the following:

* API URL

  * This is the URL of the installation you are working with
  * TODO: in a real system how does a user get this? Is it always republic-api.com?

* Shareable API Key Token

  * This is the token that grants access to use the API.

See the :doc:`authentication` section for details on how to obtain and use API keys.

API Features
************

The following is a brief overview of facilities available using the API:

Portals
=======

You can retrieve information about the :doc:`../portals/index` you are working with. Portals are the gateway into the SixEye system, and usually contain one or more :doc:`../sites/index`.

Sites
=====

:doc:`../sites/index` typically represent a single, physical installation of products incorporating the SixEye system. A site has associated data such as personnel contact details, location, and subscription state.

The API also allows you to modify some of these details for a site.

Users
=====

:doc:`../users/index` are the users who have access and are able to log in to the SixEye web portal. Using this API you can manage the users for a site, including getting information about existing users and inviting new users.

Permissions
===========

:doc:`../permissions/index` control what users can do, both site-wide and on a per-device basis. You can use the Permissions API to get the permissions for a user, and grant or revoke user permissions.

Devices
=======

:doc:`../logical_devices/index`, or logical devices, are the representation within the SixEye system of real devices which are communicating with the system.
Devices can be edited, added or removed via the API, and they can be triggered to perform Actions (such as setting a colour override), data (such as status or logs) can be retrieved, and files (such as project files) can be uploaded or downloaded from them.

Tasks
=====

:doc:`../tasks/index` are a collection of operations performed on one or more devices. Tasks can be initiated, edited and deleted using the API.

Scheduling
==========

:doc:`../scheduling/index` allows you to configure Tasks to occur at specific dates or times. You can configure schedules which recur, or just run once. The API allows you to create, modify or delete schedules.
