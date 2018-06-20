---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Функция DSC для запроса сведений об узле с опрашивающего сервера.
ms.openlocfilehash: 069fc79a79fbd5f75bcce27f7f0bd95af0d7b1ad
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2018
ms.locfileid: "34225629"
---
# <a name="dsc-function-to-query-node-information-from-pull-server"></a><span data-ttu-id="cb320-103">Функция DSC для запроса сведений об узле с опрашивающего сервера.</span><span class="sxs-lookup"><span data-stu-id="cb320-103">DSC function to query node information from pull server.</span></span>

```powershell
function QueryNodeInformation
{
Param (
       [string] $Uri =
"http://localhost:7070/PSDSCComplianceServer.svc/Status",
       [string] $ContentType = "application/json"
     )

  Write-Host "Querying node information from pull server URI  = $Uri" -ForegroundColor Green

  Write-Host "Querying node status in content type  = $ContentType " -ForegroundColor Green

   $response = Invoke-WebRequest -Uri $Uri -Method Get -ContentType $ContentType -UseDefaultCredentials -Headers
    @{Accept = $ContentType}

   if($response.StatusCode -ne 200)
 {
     Write-Host "node information was not retrieved." -ForegroundColor Red
 }

 $jsonResponse = ConvertFrom-Json $response.Content

  return $jsonResponse
}
```

<span data-ttu-id="cb320-104">Замените параметр `Uri` на универсальный код ресурса (URI) опрашивающего сервера.</span><span class="sxs-lookup"><span data-stu-id="cb320-104">Replace the `Uri` parameter with the URI for your pull server.</span></span> <span data-ttu-id="cb320-105">Если вы хотите получать сведения об узле в формате XML, задайте для `ContentType` значение `application/xml`.</span><span class="sxs-lookup"><span data-stu-id="cb320-105">If you want the node information in XML format, set `ContentType` to `application/xml`.</span></span>

<span data-ttu-id="cb320-106">Чтобы извлечь сведения об узле из параметра `$json`, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="cb320-106">To retrieve the node information from the `$json` parameter, use the following:</span></span>

```powershell
$json = QueryNodeInformation –Uri http://localhost:7070/PSDSCComplianceServer.svc/Status

$json.value | Format-Table TargetName, ConfigurationId, ServerChecksum, NodeCompliant, LastComplianceTime, StatusCode
```