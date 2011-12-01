---
layout: main
title: MOTECH - Mobile Technology for Community Health
---

{% include releases/dr1/OutboxHeader.incl %}

## Consumed events:

***

OutboxExecutionHandler handles and consumes the following keyed events:

EventKeys.EXECUTE_OUTBOX_SUBJECT (execute method)  
Parameters/Payload:  
EventKeys.PARTY_ID_KEY (PartyID) - String  
EventKeys.PHONE_NUMBER_KEY (PhoneNumber) - String  
EventKeys.LANGUAGE_KEY (Language) - String  
And the parameters inherited from the SCHEDULE_EXECUTION_SUBJECT  

EventKeys.SCHEDULE_EXECUTION_SUBJECT (schedule method)  
Parameters/Payload:  
EventKeys.CALL_HOUR_KEY (CallHour) - Integer  
EventKeys.CALL_MINUTE_KEY (CallMinute) - Integer  
EventKeys.PARTY_ID_KEY (PartyID) - String  
EventKeys.PHONE_NUMBER_KEY (PhoneNumber) - String  
EventKeys.LANGUAGE_KEY (Language) - String  
And any other parameters inherited from the emitted schedule event.  

EventKeys.UNSCHEDULE_EXECUTION_SUBJECT (unschedule method)  
Parameters/Payload:  
EventKeys.SCHEDULE_JOB_ID_KEY (JobID) - String  



**Emitted events:**

***

OutboxExecutionHandler emits the following keyed events:  

EventKeys.EXECUTE_OUTBOX_SUBJECT (schedule method)  
This event is emitted by the scheduler. It originates from the schedule method found in the   OutboxExecutionHandler.  
Parameters/Payload:  
EventKeys.PARTY_ID_KEY (PartyID) - String  
EventKeys.PHONE_NUMBER_KEY (PhoneNumber) - String  
EventKeys.LANGUAGE_KEY (Language) - String  
And the parameters inherited from the SCHEDULE_EXECUTION_SUBJECT  

EventKeys.INCOMPLETE_OUTBOX_CALL_SUBJECT (execute method) 
This event is emitted if the execution of a call fails  
Parameters/Payload: 
EventKeys.PARTY_ID_KEY (PartyID) - String  

EventKeys.COMPLETED_OUTBOX_CALL_SUBJECT (execute method)  
This event is emitted if the execution of a call is successful  
Parameters/Payload:  
EventKeys.PARTY_ID_KEY(PartyID) - String  


VoiceOutBoxServiceImpl emits the following keyed event(s):  

EventKeys.OUTBOX_MAX_PENDING_MESSAGES_EVENT_SUBJECT  
This event is emitted if the maximum number of messages in a party's outbox has been reached  
Parameters/Payload:  
EventKeys.PARTY_ID_KEY(PartyID) - String