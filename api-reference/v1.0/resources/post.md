# post resource type
Represents an individual Post item within a [conversationThread](conversationthread.md) entity.

A new post is created when you:
- [Reply to an existing post](../api/post_reply.md) 
- [Reply to an existing thread](../api/conversationthread_reply.md) 
- [Create a thread in a new conversation](../api/group_post_threads.md)
- [Create a new conversation](../api/group_post_conversations.md)
 
## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|[List posts](../api/conversationthread_list_posts.md) | [post](post.md) |Get the posts of the specified thread. |
|[Get post](../api/post_get.md) | [post](post.md) |Get the properties and relationships of a post in a specified thread.|
|[Reply](../api/post_reply.md)|None|Reply to a post and add a new post to the specified thread in a group conversation.|
|[Forward](../api/post_forward.md)|None|Forward a post to a recipient.|
|[List attachments](../api/post_list_attachments.md) |[attachment](attachment.md) collection| Get a list of Attachment objects attached to a post.|
|[Create Attachment](../api/post_post_attachments.md) |[attachment](attachment.md)| Add an attachment to a post. |
|[Create data extension](../api/opentypeextension_post_opentypeextension.md) |[openTypeExtension](opentypeextension.md)| Create an open type data extension and add custom properties in a new or existing instance of a resource.|
|[Get data extension](../api/opentypeextension_get.md) |[openTypeExtension](opentypeextension.md) collection| Get an **openTypeExtension** object or objects identified by name or fully qualified name.|

## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|body|[itemBody](itembody.md)|The contents of the post. This is a default property. This property can be null.|
|categories|String collection|The categories associated with the post.|
|changeKey|String|Identifies the version of the post. Every time the post is changed, ChangeKey changes as well. This allows Exchange to apply changes to the correct version of the object.|
|conversationId|String|Unique ID of the conversation. Read-only.|
|conversationThreadId|String|Unique ID of the conversation thread. Read-only.|
|createdDateTime|DateTimeOffset|Specifies when the post was created. The DateTimeOffset type represents date and time information using ISO 8601 format and is always in UTC time. For example, midnight UTC on Jan 1, 2014 would look like this: `'2014-01-01T00:00:00Z'`|
|from|[recipient](recipient.md)|Used in delegate access scenarios. Indicates who posted the message on behalf of another user. This is a default property.|
|hasAttachments|Boolean|Indicates whether the post has at least one attachment. This is a default property.|
|id|String| Read-only.|
|lastModifiedDateTime|DateTimeOffset|Specifies when the post was last modified. The DateTimeOffset type represents date and time information using ISO 8601 format and is always in UTC time. For example, midnight UTC on Jan 1, 2014 would look like this: `'2014-01-01T00:00:00Z'`|
|newParticipants|[recipient](recipient.md) collection|Conversation participants that were added to the thread as part of this post.|
|receivedDateTime|DateTimeOffset|Specifies when the post was received. The DateTimeOffset type represents date and time information using ISO 8601 format and is always in UTC time. For example, midnight UTC on Jan 1, 2014 would look like this: `'2014-01-01T00:00:00Z'`|
|sender|[recipient](recipient.md)|Contains the address of the sender. The value of Sender is assumed to be the address of the authenticated user in the case when Sender is not specified. This is a default property.|

## Relationships
| Relationship | Type	|Description|
|:---------------|:--------|:----------|
|attachments|[Attachment](attachment.md) collection| Read-only. Nullable.|
|extensions|[Extension](extension.md) collection|The collection of open type data extensions defined for the contact. Read-only. Nullable.|
|inReplyTo|[post](post.md)| Read-only.|
|multiValueExtendedProperties|[multiValueLegacyExtendedProperty](multivaluelegacyextendedproperty.md) collection| The collection of multi-value extended properties defined for the post. Read-only. Nullable.|
|singleValueExtendedProperties|[singleValueLegacyExtendedProperty](singlevaluelegacyextendedproperty.md) collection| The collection of single-value extended properties defined for the post. Read-only. Nullable.|


## JSON representation

Here is a JSON representation of the resource

<!-- {
  "blockType": "resource",
  "optionalProperties": [
    "attachments",
    "inReplyTo"
  ],
  "@odata.type": "microsoft.graph.post"
}-->

```json
{
  "body": {"@odata.type": "microsoft.graph.itemBody"},
  "categories": ["string"],
  "changeKey": "string",
  "conversationId": "string",
  "conversationThreadId": "string",
  "createdDateTime": "String (timestamp)",
  "from": {"@odata.type": "microsoft.graph.recipient"},
  "hasAttachments": true,
  "id": "string (identifier)",
  "lastModifiedDateTime": "String (timestamp)",
  "newParticipants": [{"@odata.type": "microsoft.graph.recipient"}],
  "receivedDateTime": "String (timestamp)",
  "sender": {"@odata.type": "microsoft.graph.recipient"}
}

```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "post resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->
