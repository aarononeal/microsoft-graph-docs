---
title: "List teamworkTagMembers"
description: "Get a list of the members of a standard tag in a team and their properties."
author: "RamjotSingh"
ms.localizationpriority: medium
ms.prod: "microsoft-teams"
doc_type: apiPageType
---

# List members in a teamworkTag
Namespace: microsoft.graph

Get a list of the [members](../resources/teamworktagmember.md) of a standard tag in a team and their properties.

## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type|Permissions (from most to least privileged)|
|:---|:---|
|Delegated (work or school account)|TeamworkTag.Read, TeamworkTag.ReadWrite|
|Delegated (personal Microsoft account)|Not supported.|
|Application|TeamworkTag.Read.All, TeamworkTag.ReadWrite.All|

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
GET /teams/{team-id}/tags/{teamworkTag-id}/members
```

## Optional query parameters
This method supports the `$filter` [OData query parameter](/graph/query-parameters) to help customize the response.

## Request headers
|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|

## Request body
Do not supply a request body for this method.

## Response

If successful, this method returns a `200 OK` response code and a collection of [teamworkTagMember](../resources/teamworktagmember.md) objects in the response body.

## Examples

### Request

The following is an example of a request.

<!-- {
  "blockType": "request",
  "name": "list_teamworktagmember",
  "sampleKeys": ["53c53217-fe77-4383-bc5a-ed4937a1aecd", "MjQzMmI1N2ItMGFiZC00M2RiLWFhN2ItMTZlYWRkMTE1ZDM0IyM3ZDg4M2Q4Yi1hMTc5LTRkZDctOTNiMy1hOGQzZGUxYTIxMmUjI3RhY29VSjN2RGk=="]
}
-->
``` http
GET https://graph.microsoft.com/v1.0/teams/53c53217-fe77-4383-bc5a-ed4937a1aecd/tags/MjQzMmI1N2ItMGFiZC00M2RiLWFhN2ItMTZlYWRkMTE1ZDM0IyM3ZDg4M2Q4Yi1hMTc5LTRkZDctOTNiMy1hOGQzZGUxYTIxMmUjI3RhY29VSjN2RGk==/members
```

### Response

The following is an example of the response.

>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.teamworkTagMember",
  "isCollection": true
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "value": [
    {
      "@odata.type": "#microsoft.graph.teamworkTagMember",
      "id": "MjQzMmI1N2ItMGFiZC00M2RiLWFhN2ItMTZlYWRkMTE1ZDM0IyNlYjY1M2Y5Mi04MzczLTRkZTYtYmZlYy01YjRkMjE2YjZhZGUjI2QzYjJiM2ViLWM0N2YtNDViOS05NWYyLWIyZjJlZjYyMTVjZQ==",
      "displayName": "Grady Archie",
      "tenantId": "18be64a9-c73a-4862-bccc-76c31ef09b9d",
      "userId": "92f6952f-61ca-4a94-8910-508a240bc167"
    },
    {
      "@odata.type": "#microsoft.graph.teamworkTagMember",
      "id": "MjQzMmI1N2ItMGFiZC00M2RiLWFhN2ItMTZlYWRkMTE1ZDM0IyNlYjY1M2Y5Mi04MzczLTRkZTYtYmZlYy01YjRkMjE2YjZhZGUjI2QzYjJiM2ViLMW0N2YtNDViOS05NWYyLWIyZjJlZjYyGHVjZQ==",
      "displayName": "Lee Gu",
      "tenantId": "18be64a9-c73a-4862-bccc-76c31ef09b9d",    
      "userId": "945fe02a-5dc1-4d28-bf5c-30a6147fe842"
    }
  ]
}
```
