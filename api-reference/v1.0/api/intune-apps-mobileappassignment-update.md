---
title: "Update mobileAppAssignment"
description: "Update the properties of a mobileAppAssignment object."
author: "dougeby"
localization_priority: Normal
ms.prod: "intune"
doc_type: apiPageType
---

# Update mobileAppAssignment

Namespace: microsoft.graph

> **Note:** The Microsoft Graph API for Intune requires an [active Intune license](https://go.microsoft.com/fwlink/?linkid=839381) for the tenant.

Update the properties of a [mobileAppAssignment](../resources/intune-apps-mobileappassignment.md) object.

## Prerequisites
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type|Permissions (from least to most privileged)|
|:---|:---|
|Delegated (work or school account)|DeviceManagementApps.ReadWrite.All|
|Delegated (personal Microsoft account)|Not supported.|
|Application|DeviceManagementApps.ReadWrite.All|

## HTTP Request
<!-- {
  "blockType": "ignored"
}
-->
``` http
PATCH /deviceAppManagement/mobileApps/{mobileAppId}/assignments/{mobileAppAssignmentId}
```

## Request headers
|Header|Value|
|:---|:---|
|Authorization|Bearer &lt;token&gt; Required.|
|Accept|application/json|

## Request body
In the request body, supply a JSON representation for the [mobileAppAssignment](../resources/intune-apps-mobileappassignment.md) object.

The following table shows the properties that are required when you create the [mobileAppAssignment](../resources/intune-apps-mobileappassignment.md).

|Property|Type|Description|
|:---|:---|:---|
|id|String|Key of the entity.|
|intent|[installIntent](../resources/intune-shared-installintent.md)|The install intent defined by the admin. Possible values are: `available`, `required`, `uninstall`, `availableWithoutEnrollment`.|
|target|[deviceAndAppManagementAssignmentTarget](../resources/intune-shared-deviceandappmanagementassignmenttarget.md)|The target group assignment defined by the admin.|
|settings|[mobileAppAssignmentSettings](../resources/intune-apps-mobileappassignmentsettings.md)|The settings for target assignment defined by the admin.|



## Response
If successful, this method returns a `200 OK` response code and an updated [mobileAppAssignment](../resources/intune-apps-mobileappassignment.md) object in the response body.

## Example

### Request
Here is an example of the request.
``` http
PATCH https://graph.microsoft.com/v1.0/deviceAppManagement/mobileApps/{mobileAppId}/assignments/{mobileAppAssignmentId}
Content-type: application/json
Content-length: 861

{
  "@odata.type": "#microsoft.graph.mobileAppAssignment",
  "intent": "required",
  "target": {
    "@odata.type": "microsoft.graph.allLicensedUsersAssignmentTarget"
  },
  "settings": {
    "@odata.type": "microsoft.graph.win32LobAppAssignmentSettings",
    "notifications": "showReboot",
    "restartSettings": {
      "@odata.type": "microsoft.graph.win32LobAppRestartSettings",
      "gracePeriodInMinutes": 4,
      "countdownDisplayBeforeRestartInMinutes": 6,
      "restartNotificationSnoozeDurationInMinutes": 10
    },
    "installTimeSettings": {
      "@odata.type": "microsoft.graph.mobileAppInstallTimeSettings",
      "useLocalTime": true,
      "startDateTime": "2016-12-31T23:58:46.7156189-08:00",
      "deadlineDateTime": "2017-01-01T00:00:21.0378955-08:00"
    },
    "deliveryOptimizationPriority": "foreground"
  }
}
```

### Response
Here is an example of the response. Note: The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.
``` http
HTTP/1.1 200 OK
Content-Type: application/json
Content-Length: 910

{
  "@odata.type": "#microsoft.graph.mobileAppAssignment",
  "id": "591620b7-20b7-5916-b720-1659b7201659",
  "intent": "required",
  "target": {
    "@odata.type": "microsoft.graph.allLicensedUsersAssignmentTarget"
  },
  "settings": {
    "@odata.type": "microsoft.graph.win32LobAppAssignmentSettings",
    "notifications": "showReboot",
    "restartSettings": {
      "@odata.type": "microsoft.graph.win32LobAppRestartSettings",
      "gracePeriodInMinutes": 4,
      "countdownDisplayBeforeRestartInMinutes": 6,
      "restartNotificationSnoozeDurationInMinutes": 10
    },
    "installTimeSettings": {
      "@odata.type": "microsoft.graph.mobileAppInstallTimeSettings",
      "useLocalTime": true,
      "startDateTime": "2016-12-31T23:58:46.7156189-08:00",
      "deadlineDateTime": "2017-01-01T00:00:21.0378955-08:00"
    },
    "deliveryOptimizationPriority": "foreground"
  }
}
```




