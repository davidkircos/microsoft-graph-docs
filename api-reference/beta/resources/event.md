# event resource type

An event in a calendar.

## JSON representation

Here is a JSON representation of the resource

<!-- {
  "blockType": "resource",
  "optionalProperties": [
    "attachments",
    "calendar",
    "extensions",
    "instances"
  ],
  "@odata.type": "microsoft.graph.event"
}-->

```json
{
  "attendees": [{"@odata.type": "microsoft.graph.attendee"}],
  "body": {"@odata.type": "microsoft.graph.itemBody"},
  "bodyPreview": "string",
  "categories": ["string"],
  "changeKey": "string",
  "createdDateTime": "String (timestamp)",
  "end": {"@odata.type": "microsoft.graph.dateTimeTimeZone"},
  "hasAttachments": true,
  "iCalUId": "string",
  "id": "string (identifier)",
  "importance": "String",
  "isAllDay": true,
  "isCancelled": true,
  "isOrganizer": true,
  "isReminderOn": true,
  "lastModifiedDateTime": "String (timestamp)",
  "location": {"@odata.type": "microsoft.graph.location"},
  "onlineMeetingUrl": "string",
  "organizer": {"@odata.type": "microsoft.graph.recipient"},
  "originalEndTimeZone": "string",
  "originalStart": "String (timestamp)",
  "originalStartTimeZone": "string",
  "recurrence": {"@odata.type": "microsoft.graph.patternedRecurrence"},
  "reminderMinutesBeforeStart": 1024,
  "responseRequested": true,
  "responseStatus": {"@odata.type": "microsoft.graph.responseStatus"},
  "sensitivity": "String",
  "seriesMasterId": "string",
  "showAs": "String",
  "start": {"@odata.type": "microsoft.graph.dateTimeTimeZone"},
  "subject": "string",
  "type": "String",
  "webLink": "string"
}

```
## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|attendees|[Attendee](attendee.md) collection|The collection of attendees for the event.|
|body|[ItemBody](itembody.md)|The body of the message associated with the event.|
|bodyPreview|String|The preview of the message associated with the event.|
|categories|String collection|The categories associated with the event.|
|changeKey|String|Identifies the version of the event object. Every time the event is changed, ChangeKey changes as well. This allows Exchange to apply changes to the correct version of the object.|
|createdDateTime|DateTimeOffset|The Timestamp type represents date and time information using ISO 8601 format and is always in UTC time. For example, midnight UTC on Jan 1, 2014 would look like this: `'2014-01-01T00:00:00Z'`|
|end|[DateTimeTimeZone](datetimetimezone.md)|The date and time that the event ends.|
|hasAttachments|Boolean|Set to true if the event has attachments.|
|iCalUId|String|A unique identifier that is shared by all instances of an event across different calendars.|
|id|String| Read-only.|
|importance|String|The importance of the event: Low = 0, Normal = 1, High = 2. Possible values are: `Low`, `Normal`, `High`.|
|isAllDay|Boolean|Set to true if the event lasts all day.|
|isCancelled|Boolean|Set to true if the event has been canceled.|
|isOrganizer|Boolean|Set to true if the message sender is also the organizer.|
|isReminderOn|Boolean|Set to true if an alert is set to remind the user of the event.|
|lastModifiedDateTime|DateTimeOffset|The Timestamp type represents date and time information using ISO 8601 format and is always in UTC time. For example, midnight UTC on Jan 1, 2014 would look like this: `'2014-01-01T00:00:00Z'`|
|location|[Location](location.md)|The location of the event.|
|onlineMeetingUrl|String|A URL for an online meeting.|
|organizer|[Recipient](recipient.md)|The organizer of the event.|
|originalEndTimeZone|String|The end time zone that was set when the event was created.|
|originalStart|DateTimeOffset|The Timestamp type represents date and time information using ISO 8601 format and is always in UTC time. For example, midnight UTC on Jan 1, 2014 would look like this: `'2014-01-01T00:00:00Z'`|
|originalStartTimeZone|String|The start time zone that was set when the event was created.|
|recurrence|[PatternedRecurrence](patternedrecurrence.md)|The recurrence pattern for the event.|
|reminderMinutesBeforeStart|Int32|The number of minutes before the event start time that the reminder alert occurs.|
|responseRequested|Boolean|Set to true if the sender would like a response when the event is accepted or declined.|
|responseStatus|[ResponseStatus](responsestatus.md)|Indicates the type of response sent in response to an event message.|
|sensitivity|String| Possible values are: `Normal`, `Personal`, `Private`, `Confidential`.|
|seriesMasterId|String|The categories assigned to the item.|
|showAs|String|The status to show: Free = 0, Tentative = 1, Busy = 2, Oof = 3, WorkingElsewhere = 4, Unknown = -1. Possible values are: `Free`, `Tentative`, `Busy`, `Oof`, `WorkingElsewhere`, `Unknown`.|
|start|[DateTimeTimeZone](datetimetimezone.md)|The start time of the event.|
|subject|String|The text of the event's subject line.|
|type|String|The event type: SingleInstance = 0, Occurrence = 1, Exception = 2, SeriesMaster = 3. Possible values are: `SingleInstance`, `Occurrence`, `Exception`, `SeriesMaster`.|
|webLink|String|The URL to open the event in Outlook Web App.<br/><br/>The event will open in the browser if you are logged in to your mailbox via Outlook Web App. You will be prompted to login if you are not already logged in with the browser.<br/><br/>This URL can be accessed from within an iFrame.|

## Relationships
| Relationship | Type	|Description|
|:---------------|:--------|:----------|
|attachments|[Attachment](attachment.md) collection|The collection of [FileAttachment](fileattachment.md), [ItemAttachment](itemattachment.md), and [referenceAttachment](referenceAttachment.md) attachments for the event. Navigation property. Read-only. Nullable.|
|calendar|[Calendar](calendar.md)|The calendar that contains the event. Navigation property. Read-only.|
|extensions|[Extension](extension.md) collection|The collection of open type data extensions defined for the event. Read-only. Nullable.|
|instances|[Event](event.md) collection|The instances of the event. Navigation property. Read-only. Nullable.|
|multiValueExtendedProperties|[multiValueLegacyExtendedProperty](multivaluelegacyextendedproperty.md) collection| The collection of multi-value extended properties defined for the event. Read-only. Nullable.|
|singleValueExtendedProperties|[singleValueLegacyExtendedProperty](singlevaluelegacyextendedproperty.md) collection| The collection of single-value extended properties defined for the event. Read-only. Nullable.|


## Methods

| Method		   | Return Type	|Description|
|:---------------|:--------|:----------|
|[List events](../api/user_list_events.md)|[Event](event.md) collection |Retrieve a list of [event](../resources/event.md) objects in the user's mailbox. The list contains single instance meetings and series masters.|
|[Get event](../api/event_get.md) | [event](event.md) |Read properties and relationships of event object.|
|[Update](../api/event_update.md) | [event](event.md)	|Update event object. |
|[Delete](../api/event_delete.md) | None |Delete event object. |
|[cancel](../api/event_cancel.md) | None | Send cancellation message from the organizer to all the attendees and cancel the specified meeting. | 
|[accept](../api/event_accept.md)|None|Accept the specified event.|
|[tentativelyAccept](../api/event_tentativelyaccept.md)|None|Tentatively accept the specified event.|
|[decline](../api/event_decline.md)|None|Decline invitation to the specified event.|
|[forward](../api/event_forward.md)|None|Lets the organizer or attendee of a meeting event forward the meeting request to a new recipient.| 
|[dismissReminder](../api/event_dismissreminder.md)|None|Dismiss the reminder for the specified event.|
|[snoozeReminder](../api/event_snoozereminder.md)|None|Snooze the reminder for the specified event.|
|[List instances](../api/event_list_instances.md) |[Event](event.md) collection| Get a Event object collection.|
|[List attachments](../api/event_list_attachments.md) |[Attachment](attachment.md) collection| Get a Attachment object collection.|
|[Create Attachment](../api/event_post_attachments.md) |[Attachment](attachment.md)| Create a new Attachment by posting to the attachments collection.|
|[Create data extension](../api/opentypeextension_post_opentypeextension.md) |[openTypeExtension](opentypeextension.md)| Create an open type data extension and add custom properties in a new or existing instance of a resource.|
|[Get data extension](../api/opentypeextension_get.md) |[openTypeExtension](opentypeextension.md) collection| Get an **openTypeExtension** object or objects identified by name or fully qualified name.|


<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "event resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->
