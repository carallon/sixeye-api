Authentication
##############

In order to make any requests to the SixEye API, you need to authenticate to the service.

Authentication is performed using a bearer token, with the API Key generated as described in the introduction, used as the token.

Generating an API Key
=====================

API Keys are generated using the *API Keys* section of your site management portal. To generate an API Key Token:

* Go to the *API Keys* section of your site portal
* Click the Add new key button

.. image:: add-key-button.png

* Use the dialog to give the API Key a name, description and expiry time
* Copy the generated key and keep it in a safe place

.. WARNING::
   This is the only time the key value is shown - keep it in a safe location

Using the API Key for Authentication
====================================

The API key is used with HTTP Token Authentication. Token authentication is typically used by HTTP APIs in cases where a web browser is not the client.

To use the token in an HTTP request, set the ``Authorization`` header value to ``Bearer {your token}``, where ``{your token}`` should be replaced with the value of the API Key.
