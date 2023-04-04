List of Available Device Actions
################################

There are different device actions available depending on the device type. This page lists the available actions, and the parameters expected with each one.

simple_triggers_cond_v1
=======================

.. include:: ../snippets/pharos-mosaic.rst

This action fires one or more trigger(s). It requires the following parameters:

.. list-table::
   :widths: 3 3 10
   :header-rows: 1

   * - Parameter
     - Value Type
     - Description
   * - ``triggerIds``
     - Array of integers
     - The list of triggers to fire
   * - ``testConditions``
     - boolean
     - Whether to test the conditions when firing the trigger. Defaults to true if omitted


.. collapse:: simple_triggers_cond_v1 Example

    This example will fire triggers 1 and 2, assessing the conditions for both.

    .. code-block:: json

        {
            "data": {
                "attributes": {
                    "projectId": "{{project_id}}",
                    "actions": [
                        {
                            "typeId": "simple_triggers_cond_v1",
                            "logicalDeviceId": "{{device_id}}",
                            "params": [
                                {
                                    "key": "triggerIds",
                                    "value": [1, 2]
                                },
                                {
                                    "key": "testConditions",
                                    "value": true
                                }
                            ],
                            "index": 1
                        }
                    ]
                }
            }
        }

start_timelines_v1
==================

.. include:: ../snippets/pharos-mosaic.rst

This action starts one or more timelines. It requires the following parameters:

.. list-table::
   :widths: 3 3 10
   :header-rows: 1

   * - Parameter
     - Value Type
     - Description
   * - ``timelineIds``
     - Array of integers
     - The list of timeline numbers to start
   * - ``releaseOthers``
     - boolean
     - Whether to release other timelines or scenes. Defaults to false if omitted
   * - ``filterByType``
     - string
     - If ``releaseOthers`` is true, selects what to release. Should be one of ``all``, ``timelines`` or ``scenes``. If omitted, only other timelines will be released.
   * - ``filterByGroup``
     - string
     - If ``releaseOthers`` is true, allows filtering of what to release. Should be one of ``all``, ``same_group``, ``only_group``, ``except_group``
   * - ``playbackGroup``
     - string
     - If ``filterByGroup`` is ``only_group`` or ``except_group``, specifies the group to filter by. One of ``A``, ``B``, ``C``, ``D``, ``E``, ``F``, ``G``, ``H``
   * - ``releaseMilliSecs``
     - integer
     - If ``releaseOthers`` is true, the time to release the other scenes and/or timelines in milliseconds. Defaults to ``2000`` (i.e. 2 seconds) if omitted

.. collapse:: start_timelines_v1 Example

    This example will start timeline 1, releasing all other timelines in the default time of 2 seconds.

    .. code-block:: json

        {
            "data": {
                "attributes": {
                    "projectId": "{{project_id}}",
                    "actions": [
                        {
                            "typeId": "start_timelines_v1",
                            "logicalDeviceId": "{{device_id}}",
                            "params": [
                                {
                                    "key": "timelineIds",
                                    "value": [1]
                                },
                                {
                                    "key": "releaseOthers",
                                    "value": true
                                }
                            ],
                            "index": 1
                        }
                    ]
                }
            }
        }

start_scenes_v1
===============

.. include:: ../snippets/pharos-mosaic.rst

This action starts one or more scenes. It requires the following parameters:

.. list-table::
   :widths: 3 3 10
   :header-rows: 1

   * - Parameter
     - Value Type
     - Description
   * - ``sceneIds``
     - Array of integers
     - The list of scene numbers to start
   * - ``releaseOthers``
     - boolean
     - Whether to release other timelines or scenes. Defaults to false if omitted
   * - ``filterByType``
     - string
     - If ``releaseOthers`` is true, selects what to release. Should be one of ``all``, ``timelines`` or ``scenes``. If omitted, only other scenes will be released.
   * - ``filterByGroup``
     - string
     - If ``releaseOthers`` is true, allows filtering of what to release. Should be one of ``all``, ``same_group``, ``only_group``, ``except_group``
   * - ``playbackGroup``
     - string
     - If ``filterByGroup`` is ``only_group`` or ``except_group``, specifies the group to filter by. One of ``A``, ``B``, ``C``, ``D``, ``E``, ``F``, ``G``, ``H``
   * - ``releaseMilliSecs``
     - integer
     - If ``releaseOthers`` is true, the time to release the other scenes and/or timelines in milliseconds. Defaults to ``2000`` (i.e. 2 seconds) if omitted

.. collapse:: start_scenes_v1 Example

    This example will start scene 3, leaving any active scenes as still active.

    .. code-block:: json

        {
            "data": {
                "attributes": {
                    "projectId": "{{project_id}}",
                    "actions": [
                        {
                            "typeId": "start_scenes_v1",
                            "logicalDeviceId": "{{device_id}}",
                            "params": [
                                {
                                    "key": "sceneIds",
                                    "value": [3]
                                },
                                {
                                    "key": "releaseOthers",
                                    "value": false
                                }
                            ],
                            "index": 1
                        }
                    ]
                }
            }
        }


release_all_v1
==============

.. include:: ../snippets/pharos-mosaic.rst

This action allows the releasing of timelines, scenes or both. It requires the following parameters:

.. list-table::
   :widths: 3 3 10
   :header-rows: 1

   * - Parameter
     - Value Type
     - Description
   * - ``filterByType``
     - string
     - Selects what to release. Should be one of ``all``, ``timelines`` or ``scenes``. If omitted, ``all``, i.e. both timelines and scenes, will be released.
   * - ``filterByGroup``
     - string
     - Allows filtering of what to release. Should be one of ``off``, ``only_group``, ``except_group``. If omitted or set to ``off``, everything will be released, otherwise filtering will be applied.
   * - ``playbackGroup``
     - string
     - If ``filterByGroup`` is ``only_group`` or ``except_group``, specifies the group to filter by. One of ``A``, ``B``, ``C``, ``D``, ``E``, ``F``, ``G``, ``H``
   * - ``releaseMilliSecs``
     - integer
     - The time to release the other scenes and/or timelines in milliseconds. Defaults to ``2000`` (i.e. 2 seconds) if omitted

.. collapse:: release_all_v1 Example

    This example will release all scenes in group B.

    .. code-block:: json

        {
            "data": {
                "attributes": {
                    "projectId": "{{project_id}}",
                    "actions": [
                        {
                            "typeId": "release_all_v1",
                            "logicalDeviceId": "{{device_id}}",
                            "params": [
                                {
                                    "key": "filterByType",
                                    "value": "scenes"
                                },
                                {
                                    "key": "filterByGroup",
                                    "value": "only_group"
                                },
                                {
                                    "key": "playbackGroup",
                                    "value": "B"
                                }
                            ],
                            "index": 1
                        }
                    ]
                }
            }
        }

release_timelines_v1
====================

.. include:: ../snippets/pharos-mosaic.rst

This action allows the releasing of timelines. It requires the following parameters:

.. list-table::
   :widths: 3 3 10
   :header-rows: 1

   * - Parameter
     - Value Type
     - Description
   * - ``timelineIds``
     - Array of integers
     - The list of timeline numbers to release
   * - ``releaseMilliSecs``
     - integer
     - The time to release the timelines in milliseconds. Defaults to ``2000`` (i.e. 2 seconds) if omitted

.. collapse:: release_timelines_v1 Example

    This example will release timelines 7 and 9 in one second.

    .. code-block:: json

        {
            "data": {
                "attributes": {
                    "projectId": "{{project_id}}",
                    "actions": [
                        {
                            "typeId": "release_timelines_v1",
                            "logicalDeviceId": "{{device_id}}",
                            "params": [
                                {
                                    "key": "timelineIds",
                                    "value": [7, 9]
                                },
                                {
                                    "key": "releaseMilliSecs",
                                    "value": 1000
                                }
                            ],
                            "index": 1
                        }
                    ]
                }
            }
        }


release_scenes_v1
=================

.. include:: ../snippets/pharos-mosaic.rst

This action allows the releasing of scenes. It requires the following parameters:

.. list-table::
   :widths: 3 3 10
   :header-rows: 1

   * - Parameter
     - Value Type
     - Description
   * - ``sceneIds``
     - Array of integers
     - The list of scene numbers to release
   * - ``releaseMilliSecs``
     - integer
     - The time to release the scenes in milliseconds. Defaults to ``2000`` (i.e. 2 seconds) if omitted

.. collapse:: release_scenes_v1 Example

    This example will release scene 8 in ten seconds.

    .. code-block:: json

        {
            "data": {
                "attributes": {
                    "projectId": "{{project_id}}",
                    "actions": [
                        {
                            "typeId": "release_timelines_v1",
                            "logicalDeviceId": "{{device_id}}",
                            "params": [
                                {
                                    "key": "sceneIds",
                                    "value": [8]
                                },
                                {
                                    "key": "releaseMilliSecs",
                                    "value": 10000
                                }
                            ],
                            "index": 1
                        }
                    ]
                }
            }
        }

set_groups_intensity_v1
=======================

.. include:: ../snippets/pharos-mosaic.rst

This action allows setting the intensity master of a group . It requires the following parameters:

.. list-table::
   :widths: 3 3 10
   :header-rows: 1

   * - Parameter
     - Value Type
     - Description
   * - ``filterByGroups``
     - boolean
     - Whether to filter by groups, or apply to all groups. If omitted, will be ``false`` and action will apply to all groups
   * - ``groupIds``
     - array of integers
     - The group IDs to master
   * - ``intensity``
     - floating point, ``0.0`` to ``100.0``
     - The master intensity value, between 1 and 100 percent
   * - ``fadeMilliSecs``
     - integer
     - The fade time to apply the intensity change, in milliseconds
   * - ``delayMilliSecs``
     - integer
     - The time to wait before applying the intensity change, in milliseconds

.. collapse:: set_groups_intensity_v1 Example

    This example will set group 1 to an intensity master level of 50%, with a 5 second fade.

    .. code-block:: json

        {
            "data": {
                "attributes": {
                    "projectId": "{{project_id}}",
                    "actions": [
                        {
                            "typeId": "set_groups_intensity_v1",
                            "logicalDeviceId": "{{device_id}}",
                            "params": [
                                {
                                    "key": "filterByGroups",
                                    "value": true
                                },
                                {
                                    "key": "groupIds",
                                    "value": [1]
                                },
                                {
                                    "key": "intensity",
                                    "value": 50.0
                                },
                                {
                                    "key": "fadeMilliSecs",
                                    "value": 5000
                                }
                            ],
                            "index": 1
                        }
                    ]
                }
            }
        }

set_rgb_override_v1
===================

.. include:: ../snippets/pharos-mosaic.rst

This action allows overriding the RGB colour of a group or fixture. It requires the following parameters:

.. list-table::
   :widths: 3 3 10
   :header-rows: 1

   * - Parameter
     - Value Type
     - Description
   * - ``target``
     - string
     - What to override, either ``fixture`` or ``group``. Defaults to ``group`` if omitted
   * - ``fixtureIds``
     - array of fixture IDs
     - The Fixture IDs to apply the override to. Only applies if the ``target`` is ``fixture``
   * - ``groupIds``
     - array of group IDs
     - The Group IDs to apply the override to. Only applies if the ``target`` is ``group``
   * - ``fadeMilliSecs``
     - integer
     - The fade time to apply the colour change, in milliseconds
   * - ``path``
     - string
     - The crossfade path to use when applying the override. One of ``default``, ``linear``, ``start``, ``end``, ``braked``, ``accelerated``, ``damped``, ``overshoot``, ``col_at_start``, ``col_at_end``, ``int_at_start``, ``int_at_end``, ``colour_first``, ``intensity_first``.
   * - ``intensity``
     - float
     - The intensity to set, in percent from 0.0 to 100.0. Defaults to 100.0 if omitted
   * - ``red``
     - float
     - The red value to set, in percent from 0.0 to 100.0. Defaults to 0.0 if omitted
   * - ``green``
     - float
     - The green value to set, in percent from 0.0 to 100.0. Defaults to 0.0 if omitted
   * - ``blue``
     - float
     - The blue value to set, in percent from 0.0 to 100.0. Defaults to 0.0 if omitted
   * - ``temperature``
     - float
     - The colour temperature value to set, from 0.0 (Cool) to 100.0 (Warm). Defaults to 50.0 if omitted

.. collapse:: set_rgb_override_v1 Example

    This example will set group 1 to an RGB value of (246, 141, 46) in 0-255 notation, with a 5 second fade.

    .. code-block:: json

        {
            "data": {
                "attributes": {
                    "projectId": "{{project_id}}",
                    "actions": [
                        {
                            "typeId": "set_rgb_override_v1",
                            "logicalDeviceId": "{{device_id}}",
                            "params": [
                                {
                                    "key": "target",
                                    "value": "group"
                                },
                                {
                                    "key": "groupIds",
                                    "value": [1]
                                },
                                {
                                    "key": "red",
                                    "value": 96.4
                                },
                                {
                                    "key": "green",
                                    "value": 55.3
                                },
                                {
                                    "key": "blue",
                                    "value": 18.0
                                },
                                {
                                    "key": "fadeMilliSecs",
                                    "value": 5000
                                }
                            ],
                            "index": 1
                        }
                    ]
                }
            }
        }

clear_rgb_override_v1
=====================

.. include:: ../snippets/pharos-mosaic.rst

This action allows clearing an RGB colour of a group or fixture. It requires the following parameters:

.. list-table::
   :widths: 3 3 10
   :header-rows: 1

   * - Parameter
     - Value Type
     - Description
   * - ``target``
     - string
     - What to clear overrides on, either ``fixture`` or ``group``. Defaults to ``group`` if omitted
   * - ``fixtureIds``
     - array of fixture IDs
     - The Fixture IDs to apply the override clear to. Only applies if the ``target`` is ``fixture``
   * - ``groupIds``
     - array of group IDs
     - The Group IDs to apply the override clear to. Only applies if the ``target`` is ``group``
   * - ``fadeMilliSecs``
     - integer
     - The fade time to apply the colour change, in milliseconds

.. collapse:: clear_rgb_override_v1 Example

    This example will clear overrides on group 1 with a 5 second fade.

    .. code-block:: json

        {
            "data": {
                "attributes": {
                    "projectId": "{{project_id}}",
                    "actions": [
                        {
                            "typeId": "clear_rgb_override_v1",
                            "logicalDeviceId": "{{device_id}}",
                            "params": [
                                {
                                    "key": "target",
                                    "value": "group"
                                },
                                {
                                    "key": "groupIds",
                                    "value": [1]
                                },
                                {
                                    "key": "fadeMilliSecs",
                                    "value": 5000
                                }
                            ],
                            "index": 1
                        }
                    ]
                }
            }
        }

pause_timelines_v1
==================

.. include:: ../snippets/pharos-mosaic.rst

This action allows a specific timeline or timeline(s) to be paused. It requires the following parameters:

.. list-table::
   :widths: 3 3 10
   :header-rows: 1

   * - Parameter
     - Value Type
     - Description
   * - ``timelineIds``
     - array of integers
     - The timeline id(s) to pause

.. collapse:: pause_timelines_v1 Example

    This example will pause timelines 2 and 6.

    .. code-block:: json

        {
            "data": {
                "attributes": {
                    "projectId": "{{project_id}}",
                    "actions": [
                        {
                            "typeId": "pause_timelines_v1",
                            "logicalDeviceId": "{{device_id}}",
                            "params": [
                                {
                                    "key": "timelineIds",
                                    "value": [2, 6]
                                }
                            ],
                            "index": 1
                        }
                    ]
                }
            }
        }

pause_all_timelines_v1
======================

.. include:: ../snippets/pharos-mosaic.rst

This action allows all timelines to be paused. It does not require additional parameters.

.. collapse:: pause_all_timelines_v1 Example

    This example will pause all timelines.

    .. code-block:: json

        {
            "data": {
                "attributes": {
                    "projectId": "{{project_id}}",
                    "actions": [
                        {
                            "typeId": "pause_all_timelines_v1",
                            "logicalDeviceId": "{{device_id}}",
                            "params": [
                            ],
                            "index": 1
                        }
                    ]
                }
            }
        }

resume_timelines_v1
===================

.. include:: ../snippets/pharos-mosaic.rst

This action allows a specific timeline or timeline(s) which have been paused to be resumed. It requires the following parameters:

.. list-table::
   :widths: 3 3 10
   :header-rows: 1

   * - Parameter
     - Value Type
     - Description
   * - ``timelineIds``
     - array of integers
     - The timeline id(s) to resume

.. collapse:: resume_timelines_v1 Example

    This example will resume timelines 2 and 6.

    .. code-block:: json

        {
            "data": {
                "attributes": {
                    "projectId": "{{project_id}}",
                    "actions": [
                        {
                            "typeId": "resume_timelines_v1",
                            "logicalDeviceId": "{{device_id}}",
                            "params": [
                                {
                                    "key": "timelineIds",
                                    "value": [2, 6]
                                }
                            ],
                            "index": 1
                        }
                    ]
                }
            }
        }


resume_all_timelines_v1
=======================

.. include:: ../snippets/pharos-mosaic.rst

This action allows any paused timelines to be resumed. It does not require additional parameters.

.. collapse:: resume_all_timelines_v1 Example

    This example will resume all paused timelines.

    .. code-block:: json

        {
            "data": {
                "attributes": {
                    "projectId": "{{project_id}}",
                    "actions": [
                        {
                            "typeId": "resume_all_timelines_v1",
                            "logicalDeviceId": "{{device_id}}",
                            "params": [
                            ],
                            "index": 1
                        }
                    ]
                }
            }
        }

set_timelines_rate_v1
=====================

.. include:: ../snippets/pharos-mosaic.rst

This action sets the rate (i.e. increases or decreases the playback speed) of one or more timelines. It requires the following parameters:

.. list-table::
   :widths: 3 3 10
   :header-rows: 1

   * - Parameter
     - Value Type
     - Description
   * - ``timelineIds``
     - Array of integers
     - The list of timeline numbers to set the rate of
   * - ``rate``
     - float
     - The rate to set the timeline to, in percent. 100.0 represents default playback rate; a value between 0.0 and 100 represents slowing the timeline; a value between 100 and 10000.0 represents speeding up the timeline

.. collapse:: set_timelines_rate_v1 Example

    This example will set timeline 1 to run at five times normal speed.

    .. code-block:: json

        {
            "data": {
                "attributes": {
                    "projectId": "{{project_id}}",
                    "actions": [
                        {
                            "typeId": "set_timelines_rate_v1",
                            "logicalDeviceId": "{{device_id}}",
                            "params": [
                                {
                                    "key": "timelineIds",
                                    "value": [1]
                                },
                                {
                                    "key": "rate",
                                    "value": 500.0
                                }
                            ],
                            "index": 1
                        }
                    ]
                }
            }
        }

set_timelines_position_v1
=========================

.. include:: ../snippets/pharos-mosaic.rst

This action jumps the position of playback of the specified timeline(s). It requires the following parameters:

.. list-table::
   :widths: 3 3 10
   :header-rows: 1

   * - Parameter
     - Value Type
     - Description
   * - ``timelineIds``
     - Array of integers
     - The list of timeline numbers to set the position of
   * - ``position``
     - float
     - The position to jump the timeline to. 0.0 represents the beginning of the timeline; 100.0 represents the end of the timeline

.. collapse:: set_timelines_position_v1 Example

    This example will jump timeline 1 to one third of the way through it's playback.

    .. code-block:: json

        {
            "data": {
                "attributes": {
                    "projectId": "{{project_id}}",
                    "actions": [
                        {
                            "typeId": "set_timelines_position_v1",
                            "logicalDeviceId": "{{device_id}}",
                            "params": [
                                {
                                    "key": "timelineIds",
                                    "value": [1]
                                },
                                {
                                    "key": "position",
                                    "value": 33.3
                                }
                            ],
                            "index": 1
                        }
                    ]
                }
            }
        }

toggle_timelines_v1
===================

.. include:: ../snippets/pharos-mosaic.rst

This action toggles the playback of a timeline or timeline(s) - if it’s running, release it; if it’s not running, start it. Can optionally specify a release fade time in seconds. This action requires the following parameters:

.. list-table::
   :widths: 3 3 10
   :header-rows: 1

   * - Parameter
     - Value Type
     - Description
   * - ``timelineIds``
     - Array of integers
     - The list of timeline numbers to toggle
   * - ``releaseMilliSecs``
     - integer
     - The release fade time in milliseconds. Assumed to be 2000 if omitted

.. collapse:: toggle_timelines_v1 Example

    This example will toggle timeline 1 in 2 seconds.

    .. code-block:: json

        {
            "data": {
                "attributes": {
                    "projectId": "{{project_id}}",
                    "actions": [
                        {
                            "typeId": "toggle_timelines_v1",
                            "logicalDeviceId": "{{device_id}}",
                            "params": [
                                {
                                    "key": "timelineIds",
                                    "value": [1]
                                }
                            ],
                            "index": 1
                        }
                    ]
                }
            }
        }

toggle_scenes_v1
================

.. include:: ../snippets/pharos-mosaic.rst

This action toggles the playback of a scene or scene(s) - if it’s running, release it; if it’s not running, start it. Can optionally specify a release fade time in seconds. This action requires the following parameters:

.. list-table::
   :widths: 3 3 10
   :header-rows: 1

   * - Parameter
     - Value Type
     - Description
   * - ``sceneIds``
     - Array of integers
     - The list of timeline numbers to toggle
   * - ``releaseMilliSecs``
     - integer
     - The release fade time in milliseconds. Assumed to be 2000 if omitted

.. collapse:: toggle_scenes_v1 Example

    This example will toggle scene 1 in 2 seconds.

    .. code-block:: json

        {
            "data": {
                "attributes": {
                    "projectId": "{{project_id}}",
                    "actions": [
                        {
                            "typeId": "toggle_scenes_v1",
                            "logicalDeviceId": "{{device_id}}",
                            "params": [
                                {
                                    "key": "sceneIds",
                                    "value": [1]
                                }
                            ],
                            "index": 1
                        }
                    ]
                }
            }
        }

triggers_cond_v1
================

.. .. include:: ../snippets/pharos-mosaic.rst

This action fires one or more trigger(s), including the option to fire a range of triggers. It requires the following parameters:

.. list-table::
   :widths: 3 3 10
   :header-rows: 1

   * - Parameter
     - Value Type
     - Description
   * - ``triggerIds``
     - string
     - The list of triggers to fire. This is a string format which can include dashes to create ranges, or commas to separate items, for example ``1-5,8,11-12`` would be a valid list of triggers
   * - ``testConditions``
     - boolean
     - Whether to test the conditions when firing the trigger. Defaults to true if omitted


.. collapse:: simple_triggers_cond_v1 Example

    This example will fire triggers 1 thru 5, 8, 11 and 12, assessing the conditions for all of them.

    .. code-block:: json

        {
            "data": {
                "attributes": {
                    "projectId": "{{project_id}}",
                    "actions": [
                        {
                            "typeId": "simple_triggers_cond_v1",
                            "logicalDeviceId": "{{device_id}}",
                            "params": [
                                {
                                    "key": "triggerIds",
                                    "value": "1-5,8,11-12"
                                },
                                {
                                    "key": "testConditions",
                                    "value": true
                                }
                            ],
                            "index": 1
                        }
                    ]
                }
            }
        }


beacon_v1
=========

.. include:: ../snippets/pharos-mosaic.rst

This action sets the controller to perform a physical beacon, typically blinking front panel LEDs or similar:

.. list-table::
   :widths: 3 3 10
   :header-rows: 1

   * - Parameter
     - Value Type
     - Description
   * - ``enabled``
     - boolean
     - Whether to beacon - true for on, false for off

.. collapse:: beacon_v1 Example

    This example will set the controller to beacon.

    .. code-block:: json

        {
            "data": {
                "attributes": {
                    "projectId": "{{project_id}}",
                    "actions": [
                        {
                            "typeId": "toggle_scenes_v1",
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


reset_v1
========

.. include:: ../snippets/pharos-mosaic.rst

This action tells the controller to reset. No parameters are required.

.. WARNING::

    Resetting a controller can lead to loss of control output. Use this command with caution.

.. collapse:: reset_v1 Example

    This example will reset the controller.

    .. code-block:: json

        {
            "data": {
                "attributes": {
                    "projectId": "{{project_id}}",
                    "actions": [
                        {
                            "typeId": "reset_v1",
                            "logicalDeviceId": "{{device_id}}",
                            "params": [
                            ],
                            "index": 1
                        }
                    ]
                }
            }
        }
