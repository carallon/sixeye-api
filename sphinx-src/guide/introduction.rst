Introduction
############

This API provides facilities for interaction with the SixEye system.

Working with the API
********************

In order to work with the API you need the following:

* API URL

  * The URL of the system. At the moment this will always be https://primary.sixeye-api.com
  * All API calls described in these documents are relative to that URL - for example ``/version`` would mean a full URL of https://primary.sixeye-api.com/version

* Shareable API Key Token

  * This is the token that grants access to use the API
  * See the :doc:`authentication` section for details on how to obtain and use API keys.

API Features
************

The following is a brief overview of facilities available using the API:

Sites
=====

:doc:`../sites/index` typically represent a single, physical installation of products incorporating the SixEye system. A site has associated data such as personnel contact details, location, and subscription state.

The API allows you to retrieve a list of sites, and details for a site.

Users
=====

:doc:`../users/index` are the users who have access and are able to log in to the SixEye web portal. Using this API you can retrieve information about existing users.

Devices
=======

:doc:`../logical_devices/index`, or logical devices, are the representation within the SixEye system of real devices which are communicating with the system.
Devices can be listed via the API, and data about them (such as status or logs) can be retrieved.

Actions
=======

:doc:`../actions/index` can be applied to devices to make them perform actions such as starting a timeline or setting a colour override. This documentation includes a list of available action types, and how to apply them to devices.

Tasks
=====

:doc:`../tasks/index` are a collection of operations performed on one or more devices. Tasks can be initiated using the API.
