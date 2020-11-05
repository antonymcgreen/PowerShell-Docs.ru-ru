---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Обновление узлов на опрашиваемом сервере
description: В этой статье описывается, как обновить управляемые узлы DSC с опрашиваемого сервера.
ms.openlocfilehash: 7256a0e1fdfaa8e56150c4f7299640bc95b82cee
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92656763"
---
# <a name="update-nodes-from-a-pull-server"></a><span data-ttu-id="950f6-104">Обновление узлов на опрашиваемом сервере</span><span class="sxs-lookup"><span data-stu-id="950f6-104">Update Nodes from a Pull Server</span></span>

<span data-ttu-id="950f6-105">В следующих разделах предполагается, что вы уже настроили опрашиваемый сервер.</span><span class="sxs-lookup"><span data-stu-id="950f6-105">The sections below assume that you have already set up a Pull Server.</span></span> <span data-ttu-id="950f6-106">Если вы не настроили опрашиваемый сервер, можно воспользоваться следующими руководствами.</span><span class="sxs-lookup"><span data-stu-id="950f6-106">If you have not set up your Pull Server, you can use the following guides:</span></span>

- [<span data-ttu-id="950f6-107">Настройка опрашиваемого SMB-сервера DSC</span><span class="sxs-lookup"><span data-stu-id="950f6-107">Set up a DSC SMB Pull Server</span></span>](pullServerSmb.md)
- [<span data-ttu-id="950f6-108">Настройка опрашиваемого HTTP-сервера DSC</span><span class="sxs-lookup"><span data-stu-id="950f6-108">Set up a DSC HTTP Pull Server</span></span>](pullServer.md)

<span data-ttu-id="950f6-109">Для каждого целевого узла можно настроить скачивание конфигураций, ресурсов и даже отчет о состоянии.</span><span class="sxs-lookup"><span data-stu-id="950f6-109">Each target node can be configured to download configurations, resources, and even report its status.</span></span> <span data-ttu-id="950f6-110">В этой статье показано, как передать ресурсы, чтобы они были доступны для загрузки, и настроить клиенты, чтобы ресурсы загружались автоматически.</span><span class="sxs-lookup"><span data-stu-id="950f6-110">This article will show you how to upload resources so they are available to be downloaded, and configure clients to download resources automatically.</span></span> <span data-ttu-id="950f6-111">Когда Узел получает назначенную конфигурацию с помощью команды **получить** или **отправить** (v5), он автоматически загружает любые ресурсы, требуемые конфигурацией, из расположения, указанного в LCM.</span><span class="sxs-lookup"><span data-stu-id="950f6-111">When the Node's receives an assigned Configuration, through **Pull** or **Push** (v5), it automatically downloads any resources required by the Configuration from the location specified in the LCM.</span></span>

## <a name="using-the-update-dscconfiguration-cmdlet"></a><span data-ttu-id="950f6-112">Использование командлета Update-DSCConfiguration</span><span class="sxs-lookup"><span data-stu-id="950f6-112">Using the Update-DSCConfiguration cmdlet</span></span>

<span data-ttu-id="950f6-113">Начиная с PowerShell 5.0, командлет [Update-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/update-dscconfiguration) принуждает узел обновлять свою конфигурацию с опрашиваемого сервера, настроенного в LCM.</span><span class="sxs-lookup"><span data-stu-id="950f6-113">Beginning in PowerShell 5.0, the [Update-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/update-dscconfiguration) cmdlet, forces a Node to update its configuration from the Pull Server configured in the LCM.</span></span>

```powershell
Update-DSCConfiguration -ComputerName "Server01"
```

## <a name="using-invoke-cimmethod"></a><span data-ttu-id="950f6-114">Использование Invoke-CimMethod</span><span class="sxs-lookup"><span data-stu-id="950f6-114">Using Invoke-CIMMethod</span></span>

<span data-ttu-id="950f6-115">В PowerShell 4.0 вы по прежнему можете вручную заставить клиента — получателя данных обновить свою конфигурацию, используя [Invoke-CIMMethod](/powershell/module/cimcmdlets/invoke-cimmethod).</span><span class="sxs-lookup"><span data-stu-id="950f6-115">In PowerShell 4.0, you can still manually force a Pull Client to update its Configuration using [Invoke-CIMMethod](/powershell/module/cimcmdlets/invoke-cimmethod).</span></span> <span data-ttu-id="950f6-116">В следующем примере создается сеанс CIM с указанными учетными данными, который вызывает соответствующий метод CIM и удаляет сеанс.</span><span class="sxs-lookup"><span data-stu-id="950f6-116">The following example creates a CIM session with specified credentials, invokes the appropriate CIM method, and removes the session.</span></span>

```powershell
$cimSession = New-CimSession -ComputerName "Server01" -Credential $(Get-Credential)
Invoke-CimMethod -CimSession $cimSession -Namespace 'root/microsoft/windows/desiredstateconfiguration' -Class 'MSFT_DscLocalConfigurationManager' -MethodName 'PerformRequiredConfigurationChecks' -Arguments @{ 'Flags' = [uint32]1 } -Verbose
$cimSession | Remove-CimSession
```

## <a name="see-also"></a><span data-ttu-id="950f6-117">См. также</span><span class="sxs-lookup"><span data-stu-id="950f6-117">See Also</span></span>

[<span data-ttu-id="950f6-118">PerformRequiredConfigurationChecks</span><span class="sxs-lookup"><span data-stu-id="950f6-118">PerformRequiredConfigurationChecks</span></span>](../reference/mof-classes/msft-dsclocalconfigurationmanager-performrequiredconfigurationchecks.md)
