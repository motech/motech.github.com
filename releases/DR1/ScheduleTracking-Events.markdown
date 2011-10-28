---
layout: main
title: MOTECH - Mobile Technology for Community Health
---

{% include releases/dr1/ScheduleTrackingHeader.incl %}

## Consumed events:

ScheduleTrackingEventService handles and consumes the following keyed event(s):

EventKeys.ENROLLED_ENTITY_REGULAR_ALERT (raiseAlertForEnrolledEntity method)
Parameters/Payload:
SCHEDULE_NAME_KEY (scheduleName) - String
ENROLLMENT_ID (externalId) - String
JOB_ID_KEY (externalId) - String


## Emitted events


ScheduleTrackingEventService emits the following keyed event(s):

EventKeys.ENROLLED_ENTITY_MILESTONE_ALERT
This event is emitted by the tracking event service when an alert needs to be sent out and handled. Checks for alerts are made per user, per schedule on a daily basis.
Parameters/Payload:
WINDOW_NAME (alert.windowName)
MILESTONE_NAME (alert.milestoneName)
Also included are all the data parameters from the alert as specified in the JSON document.


ScheduleTrackingServiceImpl emits the following keyed event(s):

EventKeys.ENROLLED_ENTITY_REGULAR_ALERT 
This event is emitted by the scheduler. It originates from the enroll method in the schedule tracking service implementation.
Parameters/Payload:
SCHEDULE_NAME_KEY (scheduleName) - String
ENROLLMENT_ID (externalId) - String
JOB_ID_KEY (externalId) - String