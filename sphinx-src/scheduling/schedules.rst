Schedules
#########

Schedules are associated with a Task Scheduler. They define when the associated task(s) are run, which can be on a specific date(s), Daily, Monthly or Yearly; and at a single time, a recurring time, an astronomical time (related to sunset or sunrise), or on a time mask.

Attributes
**********

Schedules have the following attributes:

.. list-table::
   :widths: 3 3 10
   :header-rows: 1

   * - Attribute
     - Value Type
     - Description
   * - ``type``
     - string
     - The type of recurrence, can be ``daily``, ``monthly``, ``yearly``
   * - ``automatedOperationId``
     - UUID
     - The UUID of the associated task scheduler
   * - ``name``
     - string
     - The user facing name of the schedule
   * - ``description``
     - string
     - A user facing description of the schedule
   * - ``params``
     - object
     - The recurrence parameters for this schedule. Varies depending on the type - see below for details
   * - ``lockVersion``
     - integer
     - TODO

Params for Monthly Schedules
============================

Monthly schedules have the following parameters:

.. list-table::
   :widths: 3 3 10
   :header-rows: 1

   * - Attribute
     - Value Type
     - Description
   * - ``everyNMonths``
     - integer
     - The number of months between occurrences, e.g. 1 is every month, 2 is every other month
   * - ``startDate``
     - date in yyyy-mm-dd format
     - The date on which recurrences will start
   * - ``startTimes``
     - array
     - An array of time specifications of when the event starts during the day

Params for Daily Schedules
==========================

Daily schedules have the following parameters:

.. list-table::
   :widths: 3 3 10
   :header-rows: 1

   * - Attribute
     - Value Type
     - Description
   * - ``forNTimes``
     - integer
     - The number of times the schedule will occur
   * - ``startTimes``
     - array
     - An array of time specifications of when the event starts during the day
   * - ``everyNDays``
     - integer
     - The number of days on which the schedule will occur
   * - ``startDate``
     - date in yyyy-mm-dd format
     - The date on which recurrences will start

