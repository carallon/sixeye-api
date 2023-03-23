Device Actions
##############

.. toctree::
   :hidden:

   action_list


Actions are things that devices can be requested to do. The available action types will depend on the device type.

GET
===

``GET /logical_devices/{{device_id}}/device_action_types_list``

This will retrieve the list of available actions for this particular device ID. It returns a JSON object, in which the attributes.actions property is an array of the names of available actions.

.. collapse:: Example response

    .. code-block:: json

        {
            "data": {
                "id": "ae846158-9f5a-5d69-968f-cfec1ed0e2de",
                "type": "deviceActionTypesLists",
                "attributes": {
                    "actions": [
                        "simple_triggers_cond_v1",
                        "start_timelines_v1",
                        "start_scenes_v1",
                        "release_all_v1",
                        "release_timelines_v1",
                        "release_scenes_v1",
                        "set_groups_intensity_v1",
                        "set_rgb_override_v1",
                        "clear_rgb_override_v1",
                        "pause_timelines_v1",
                        "pause_all_timelines_v1",
                        "resume_timelines_v1",
                        "resume_all_timelines_v1",
                        "set_timelines_rate_v1",
                        "set_timelines_position_v1",
                        "toggle_timelines_v1",
                        "toggle_scenes_v1",
                        "triggers_cond_v1",
                        "beacon_v1",
                        "reset_v1"
                    ]
                }
            }
        }

POST
====


``POST /logical_devices/{{device_id}}/perform_action``

This call will trigger a device to perform an action. The body of the request should be a JSON object which includes the action to be performed, and within the ``meta`` object, the data associated with the action.

TODO - list of actions and expected meta data?

.. code-block:: json

    {
        "data": {
            "type": "performAction",
            "id": "{{$randomUUID}}",
            "attributes": {
                "action": "triggers",
                "meta": {
                    "trigger_ids": [
                        0
                    ]
                }
            }
        }
    }
