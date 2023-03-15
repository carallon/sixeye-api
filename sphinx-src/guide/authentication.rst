Authentication
##############

In order to make any requests to the SixEye API, you need to authenticate to the service. Authentication is performed using a bearer token, with the API Key generated as described in the introduction, used as the token.

Token Authentication
====================

Token authentication is typically used by HTTP APIs in cases where a web browser is not the client.

To use the token in a request, set the ``Authorization`` header value to ``Bearer {your token}``, where ``{your token}`` should be replaced with the value of the API Key.
