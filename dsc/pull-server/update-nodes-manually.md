---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Обновление узлов на опрашиваемом сервере
ms.openlocfilehash: 4333a5bf82ef45f22a062942ebe93409433623f5
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 12/14/2018
ms.locfileid: "53402152"
---
# <a name="update-nodes-from-a-pull-server"></a><span data-ttu-id="8d394-103">Обновление узлов на опрашиваемом сервере</span><span class="sxs-lookup"><span data-stu-id="8d394-103">Update Nodes from a Pull Server</span></span>

<span data-ttu-id="8d394-104">В следующих разделах предполагается, что вы уже настроили опрашивающего сервера.</span><span class="sxs-lookup"><span data-stu-id="8d394-104">The sections below assume that you have already set up a Pull Server.</span></span> <span data-ttu-id="8d394-105">Если ваш сервер на включение внесенных изменений не установлен, можно использовать со следующими руководствами:</span><span class="sxs-lookup"><span data-stu-id="8d394-105">If you have not set up your Pull Server, you can use the following guides:</span></span>

- [<span data-ttu-id="8d394-106">Настройка опрашиваемого SMB-сервера DSC</span><span class="sxs-lookup"><span data-stu-id="8d394-106">Set up a DSC SMB Pull Server</span></span>](pullServerSmb.md)
- [<span data-ttu-id="8d394-107">Настройка опрашиваемого HTTP-сервера DSC</span><span class="sxs-lookup"><span data-stu-id="8d394-107">Set up a DSC HTTP Pull Server</span></span>](pullServer.md)

<span data-ttu-id="8d394-108">Каждого целевого узла можно настроить для загрузки конфигураций, ресурсов и даже сообщить о своем состоянии.</span><span class="sxs-lookup"><span data-stu-id="8d394-108">Each target node can be configured to download configurations, resources, and even report its status.</span></span> <span data-ttu-id="8d394-109">В этой статье показано, как передать ресурсы, чтобы они были доступны, которые требуется загрузить и настроить клиенты для загрузки ресурсов автоматически.</span><span class="sxs-lookup"><span data-stu-id="8d394-109">This article will show you how to upload resources so they are available to be downloaded, and configure clients to download resources automatically.</span></span> <span data-ttu-id="8d394-110">Когда узел получает назначенной конфигурации, с помощью **на включение внесенных изменений** или **Push** (v5), он автоматически скачивает все ресурсы, требования конфигурации из местоположения, указанного в LCM.</span><span class="sxs-lookup"><span data-stu-id="8d394-110">When the Node's receives an assigned Configuration, through **Pull** or **Push** (v5), it automatically downloads any resources required by the Configuration from the location specified in the LCM.</span></span>

## <a name="using-the-update-dscconfiguration-cmdlet"></a><span data-ttu-id="8d394-111">С помощью командлета Update-DSCConfiguration</span><span class="sxs-lookup"><span data-stu-id="8d394-111">Using the Update-DSCConfiguration cmdlet</span></span>

<span data-ttu-id="8d394-112">Начиная с PowerShell 5.0 [Update-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/update-dscconfiguration) командлета, заставляет узел, чтобы обновить свою конфигурацию из опрашивающего сервера, настроенные в LCM.</span><span class="sxs-lookup"><span data-stu-id="8d394-112">Beginning in PowerShell 5.0, the [Update-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/update-dscconfiguration) cmdlet, forces a Node to update its configuration from the Pull Server configured in the LCM.</span></span>

```powershell
Update-DSCConfiguration -ComputerName "Server01"
```

## <a name="using-invoke-cimmethod"></a><span data-ttu-id="8d394-113">С помощью Invoke-CIMMethod</span><span class="sxs-lookup"><span data-stu-id="8d394-113">Using Invoke-CIMMethod</span></span>

<span data-ttu-id="8d394-114">В PowerShell 4.0, вы можете вручную по-прежнему принудительно опрашивающий клиент, чтобы обновить его конфигурацию с помощью [Invoke-CIMMethod](/powershell/module/cimcmdlets/invoke-cimmethod).</span><span class="sxs-lookup"><span data-stu-id="8d394-114">In PowerShell 4.0, you can still manually force a Pull Client to update its Configuration using [Invoke-CIMMethod](/powershell/module/cimcmdlets/invoke-cimmethod).</span></span> <span data-ttu-id="8d394-115">Следующий пример создает сеанс CIM с помощью указанных учетных данных и вызывает необходимый метод CIM удаляет сеанс.</span><span class="sxs-lookup"><span data-stu-id="8d394-115">The following example creates a CIM session with specified credentials, invokes the appropriate CIM method, and removes the session.</span></span>

```powershell
$cimSession = New-CimSession -ComputerName "Server01" -Credential $(Get-Credential)
Invoke-CimMethod -CimSession $cimSession -Namespace 'root/microsoft/windows/desiredstateconfiguration' -Class 'MSFT_DscLocalConfigurationManager' -MethodName 'PerformRequiredConfigurationChecks' -Arguments @{ 'Flags' = [uint32]1 } -Verbose
$cimSession | Remove-CimSession
```

## <a name="see-also"></a><span data-ttu-id="8d394-116">См. также</span><span class="sxs-lookup"><span data-stu-id="8d394-116">See Also</span></span>

[<span data-ttu-id="8d394-117">PerformRequiredConfigurationChecks</span><span class="sxs-lookup"><span data-stu-id="8d394-117">PerformRequiredConfigurationChecks</span></span>](/powershell/dsc/msft-dsclocalconfigurationmanager-performrequiredconfigurationchecks)
