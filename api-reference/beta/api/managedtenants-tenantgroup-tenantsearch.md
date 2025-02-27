---
title: "tenantGroup: tenantSearch"
description: "Searches for the specified managed tenants across tenant groups."
author: "idwilliams"
ms.localizationpriority: medium
ms.prod: "multi-tenant-management"
doc_type: apiPageType
---

# tenantGroup: tenantSearch
Namespace: microsoft.graph.managedTenants

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Searches for the specified managed tenants across tenant groups.

[!INCLUDE [national-cloud-support](../../includes/global-only.md)]

## Permissions
Choose the permission or permissions marked as least privileged for this API. Use a higher privileged permission or permissions [only if your app requires it](/graph/permissions-overview#best-practices-for-using-microsoft-graph-permissions). For details about delegated and application permissions, see [Permission types](/graph/permissions-overview#permission-types). To learn more about these permissions, see the [permissions reference](/graph/permissions-reference).

<!-- { "blockType": "permissions", "name": "managedtenants_tenantgroup_tenantsearch" } -->
[!INCLUDE [permissions-table](../includes/permissions/managedtenants-tenantgroup-tenantsearch-permissions.md)]

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
POST /tenantRelationships/managedTenants/tenantGroups/tenantSearch
```

## Request headers
|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required. Learn more about [authentication and authorization](/graph/auth/auth-concepts).|
|Content-Type|application/json. Required.|

## Request body
In the request body, supply JSON representation of the parameters.

The following table shows the parameters that can be used with this action.

|Parameter|Type|Description|
|:---|:---|:---|
|tenantId|String|The Microsoft Entra tenant identifier for the [managed tenant](../resources/managedtenants-tenant.md).|



## Response

If successful, this action returns a `200 OK` response code and a [microsoft.graph.managedTenants.tenantGroup](../resources/managedtenants-tenantgroup.md) collection in the response body.

## Examples

### Request

# [HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "tenantgroup_tenantsearch"
}
-->
``` http
POST https://graph.microsoft.com/beta/tenantRelationships/managedTenants/tenantGroups/tenantSearch
Content-Type: application/json

{
  "tenantId": "String"
}
```

# [C#](#tab/csharp)
[!INCLUDE [sample-code](../includes/snippets/csharp/tenantgroup-tenantsearch-csharp-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [CLI](#tab/cli)
[!INCLUDE [sample-code](../includes/snippets/cli/tenantgroup-tenantsearch-cli-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Go](#tab/go)
[!INCLUDE [sample-code](../includes/snippets/go/tenantgroup-tenantsearch-go-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Java](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/tenantgroup-tenantsearch-java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/tenantgroup-tenantsearch-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PHP](#tab/php)
[!INCLUDE [sample-code](../includes/snippets/php/tenantgroup-tenantsearch-php-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PowerShell](#tab/powershell)
[!INCLUDE [sample-code](../includes/snippets/powershell/tenantgroup-tenantsearch-powershell-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Python](#tab/python)
[!INCLUDE [sample-code](../includes/snippets/python/tenantgroup-tenantsearch-python-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

### Response
>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "Collection(microsoft.graph.managedTenants.tenantGroup)"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "@odata.context": "https://graph.microsoft.com/beta/$metadata#tenantGroups",
  "value": [
    {
      "id": "2e6a0c9f-986d-480e-ad4b-bdfddc047aba",
      "displayName": "Default",
      "allTenantsIncluded": true,
      "tenantIds": [],
      "managementIntents": [
        {
          "managementIntentId": "586895ab-8a59-4b79-be25-b06949a819bb",
          "managementIntentDisplayName": "Default Baseline",
          "managementTemplates": [
            {
              "managementTemplateId": "e5834405-43d2-4815-867d-3dd600308d1c",
              "displayName": "Baseline - Block Legacy Authentication",
              "category": "identity"
            },
            {
              "managementTemplateId": "12524106-036f-457f-b7a6-b003509d29c8",
              "displayName": "Baseline - Require MFA for Admins",
              "category": "identity"
            },
            {
              "managementTemplateId": "21230aa5-d5a9-4403-b179-baf2de242aca",
              "displayName": "Baseline - Require MFA for end users",
              "category": "identity"
            },
            {
              "managementTemplateId": "e2cadc41-a08f-45e7-8eb1-942d224dfb9a",
              "displayName": "Baseline - Enroll devices in MEM",
              "category": "devices"
            },
            {
              "managementTemplateId": "31d57d29-2d54-4074-84bd-51c008c2e6b2",
              "displayName": "Baseline - Setup Compliance Policy for Windows 10 devices",
              "category": "devices"
            },
            {
              "managementTemplateId": "b2d6d189-ea31-4cf8-b75e-41210c583127",
              "displayName": "Baseline - Setup Microsoft Defender Antivirus Policy for Windows 10 devices",
              "category": "devices"
            }
          ]
        }
      ],
      "managementActions": []
    }
  ]
}
```
