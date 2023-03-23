Available Actions
#################

The following lists the currently available actions with the device types they apply to:

simple_triggers_cond
====================

.. note:: Applies to Pharos and Mosaic products.

TODO: Fires a trigger with conditions


start_timelines
===============

.. note:: Applies to Pharos and Mosaic products.

start_scenes
============

.. note:: Applies to Pharos and Mosaic products.

release_all
===========

.. note:: Applies to Pharos and Mosaic products.

release_timelines
=================

.. note:: Applies to Pharos and Mosaic products.

release_scenes
==============

.. note:: Applies to Pharos and Mosaic products.

set_groups_intensity
====================

.. note:: Applies to Pharos and Mosaic products.

set_rgb_override
================

.. note:: Applies to Pharos and Mosaic products.

clear_rgb_override
==================

.. note:: Applies to Pharos and Mosaic products.

pause_timelines
===============

.. note:: Applies to Pharos and Mosaic products.

pause_all_timelines
===================

.. note:: Applies to Pharos and Mosaic products.

resume_timelines
================

.. note:: Applies to Pharos and Mosaic products.

resume_all_timelines
====================

.. note:: Applies to Pharos and Mosaic products.

set_timelines_rate
==================

.. note:: Applies to Pharos and Mosaic products.

set_timelines_position
======================

.. note:: Applies to Pharos and Mosaic products.

toggle_timelines
================

.. note:: Applies to Pharos and Mosaic products.

toggle_scenes
=============

.. note:: Applies to Pharos and Mosaic products.

triggers_cond
=============

.. note:: Applies to Pharos and Mosaic products.

Fires a trigger either with or without checking conditions


.. list-table::
   :widths: 3 3 10
   :header-rows: 1

   * - Attribute
     - Value Type
     - Description
   * - triggerIds
     - Array of integers
     - The trigger(s) to fire
   * - testConditions
     - Boolean
     - Whether or not to test conditions of the triggers

.. code-block:: json

    {
    "data": {
        "type": "performAction",
        "id": "e841a004-4443-4171-b762-1ab60401e63a",
        "attributes": {
            "action": "triggers_cond",
            "meta": {
                "triggerIds": [
                20
                ],
                "testConditions": false
            }
        }
    }
    }

beacon
======

reset
=====
