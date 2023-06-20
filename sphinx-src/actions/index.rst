Actions
#######

.. toctree::
   :hidden:

   action-list

Actions are a way to initiate an activity on a device immediately.

Different devices are likely to have different actions available, depending on the type of the device.

You can retrieve a list of the available action types for a particular device.


Get Available Action Types
==========================

``GET /logical_devices/{{device_id}}/device_action_types_list``

Returns a list of the actions available for the device specified by ``device_id``.

A reference list of actions is provided at :doc:`action-list`.

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

Trigger an Action
=================

An action can be triggered using a POST call to the API:

POST /actions/execute

The body of the request must include a JSON object which includes:


.. list-table::
   :widths: 3 3 10
   :header-rows: 1

   * - Attribute
     - Value Type
     - Description
   * - ``projectId``
     - UUID
     - The unique identifier of the project to trigger actions in
   * - ``typeId``
     - string
     - The typeId of the action to trigger (from the list of available types, see above)
   * - ``params``
     - array of objects
     - The parameters to pass to the action. See the list of actions for parameters for each action type. Each object should include a ``key`` and a ``value`` attribute
   * - ``index``
     - integer
     - When passing multiple actions in one call, this determines the order in which they will be executed. Should be a sequential number starting at 1; just 1 if only one action is included in the call

Here is an example body one might use to trigger a beacon action.

.. code-block:: json

    {
        "data": {
            "attributes": {
                "projectId": "{{project_id}}",
                "actions": [
                    {
                        "typeId": "beacon_v1",
                        "logicalDeviceId": "{{device_id}}",
                        "params": [
                            {
                                "key": "enabled",
                                "value": true
                            }
                        ],
                        "index": 1
                    }
                ]
            }
        }
    }
