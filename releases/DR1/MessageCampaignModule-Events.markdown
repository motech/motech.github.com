---
layout: main
title: MOTECH - Mobile Technology for Community Health
---


## Consumed events:
CampaignMessageHandler handles and consumes events with the key EventKeys.MESSAGE_CAMPAIGN_SEND_EVENT_SUBJECT

The payload for event subject EventKeys.Message_CAMPAIGN_SEND_EVENT_SUBJECT (org.motechproject.server.messagecampaign.send-campaign-message)

Parameters/Payload (originating from a CampaignRequest):
EventKeys.CAMPAIGN_NAME_KEY (CampaignName)
EventKeys.MESSAGE_KEY (MessageKey)
EventKeys.SCHEDULE_JOB_ID_KEY (JobID)
EventKeys.EXTERNAL_ID_KEY (ExternalID)



## Emitted events:
CampaignMessageHandler emits events with the key EventKeys.MESSAGE_CAMPAIGN_FIRED_EVENT_SUBJECT after handling EventKeys.MESSAGE_CAMPAIGN_SEND_EVENT_SUBJECT

The payload of event subject EventKeys.Message_MESSAGE_CAMPAIGN_FIRED_EVENT_SUBJECT (org.motechproject.server.messagecampaign.fired-campaign-message)

Parameters/Payload
EventKeys.CAMPAIGN_NAME_KEY (CampaignName) - used to find the campaign message, from the CAMPAIGN_SEND_EVENT_SUBJECT event
EventKeys.MESSAGE_KEY (MessageKey) - used from the CampaignRequest to find the message, from the CAMPAIGN_SEND_EVENT_SUBJECT event
EventKeys.SCHEDULE_JOB_ID_KEY (JobID) - from the CAMPAIGN_SEND_EVENT_SUBJECT event
EventKeys.EXTERNAL_ID_KEY (ExternalID) - user ID, from the CAMPAIGN_SEND_EVENT_SUBJECT event
EventKeys.MESSAGE_NAME_KEY (MessageName) - retrieved from the campaign message's name
EventKeys.MESSAGE_FORMATS (MessageFormats) - list retrieved from the campaign message's formats field
EventKeys.MESSAGE_LANGUAGES (MessageLanguages) - list retrieved from the campaign message's languages field

## Additional information:

The message key uniquely identifies campaign messages (even repeating messages have their own unique message key).
external ID is a user ID, identifying a patient, nurse, lab, facility, etc, from the campaign request.

The Job ID is a string constructed from EventKeys.BASE_SUBJECT, campaign name, external ID, and the message key, the latter three are from the campaign request
If the campaign name is Campaign1, externalID is 123 and the message key is MessageKey4, then the Job ID will be:
org.motechproject.server.messagecampaign.Campaign1.123.MessageKey4

Note that some characteristics of a campaign message (for example, repeatInterval from repeating messages) are not sent as part of an event payload.


## Graphical representation of the event flow through the message campaign module:

![image](http://motechdocumentation.wikispaces.com/file/view/campaignmessageflow.png/256634880/campaignmessageflow.png)
