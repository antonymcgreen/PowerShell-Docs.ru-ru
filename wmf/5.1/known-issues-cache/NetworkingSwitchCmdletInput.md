---
ms.date: 06/12/2017
keywords: wmf,powershell,установка
ms.topic: conceptual
contributor: vaibch
title: Сбой командлетов диспетчера сетевых коммутаторов
ms.openlocfilehash: a0f84c35974b6674faba4b0f19a28bd6e2490a96
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62084986"
---
# <a name="network-switch-manager-cmdlets-failure"></a><span data-ttu-id="0a352-103">Сбой командлетов диспетчера сетевых коммутаторов</span><span class="sxs-lookup"><span data-stu-id="0a352-103">Network Switch Manager Cmdlets Failure</span></span>

<span data-ttu-id="0a352-104">Командлеты диспетчера сетевых коммутаторов можно использовать для управления сетевыми коммутаторами по WSMAN.</span><span class="sxs-lookup"><span data-stu-id="0a352-104">The Network Switch Manager cmdlets can be used to manage network switches over WSMAN.</span></span>
<span data-ttu-id="0a352-105">Несколько командлетов этого модуля могут принимать значения из конвейеров.</span><span class="sxs-lookup"><span data-stu-id="0a352-105">A few cmdlets of this module are capable of accepting values from pipelines.</span></span>
<span data-ttu-id="0a352-106">В WMF 5.1 Preview командлеты, которые принимают значение из конвейера, не могут быть выполнены, если значения не переданы через конвейеры.</span><span class="sxs-lookup"><span data-stu-id="0a352-106">In WMF 5.1 Preview, the cmdlets that can accept value from pipeline fail to execute when the values are not passed through pipelines.</span></span>

<span data-ttu-id="0a352-107">Если параметр InputObject не используется, командлет должен по-прежнему работать без сбоев.</span><span class="sxs-lookup"><span data-stu-id="0a352-107">If "InputObject" parameter is not used, the cmdlet should continue to execute without failures.</span></span>

<span data-ttu-id="0a352-108">Список затронутых командлетов, например тех, которые могут принять значение для параметра InputObject из конвейера.</span><span class="sxs-lookup"><span data-stu-id="0a352-108">Here is the list of affected cmdlets i.e. these cmdlets can accept value for "InputObject" parameter from pipeline.</span></span>
<span data-ttu-id="0a352-109">Если это значение не передано из конвейера, произойдет сбой выполнения командлета.</span><span class="sxs-lookup"><span data-stu-id="0a352-109">If this value is not passed from pipeline the execution of cmdlet will fail.</span></span>

- <span data-ttu-id="0a352-110">Disable-NetworkSwitchEthernetPort</span><span class="sxs-lookup"><span data-stu-id="0a352-110">Disable-NetworkSwitchEthernetPort</span></span>
- <span data-ttu-id="0a352-111">Enable-NetworkSwitchEthernetPort</span><span class="sxs-lookup"><span data-stu-id="0a352-111">Enable-NetworkSwitchEthernetPort</span></span>
- <span data-ttu-id="0a352-112">Remove-NetworkSwitchEthernetPortIPAddress</span><span class="sxs-lookup"><span data-stu-id="0a352-112">Remove-NetworkSwitchEthernetPortIPAddress</span></span>
- <span data-ttu-id="0a352-113">Set-NetworkSwitchEthernetPortIPAddress</span><span class="sxs-lookup"><span data-stu-id="0a352-113">Set-NetworkSwitchEthernetPortIPAddress</span></span>
- <span data-ttu-id="0a352-114">Set-NetworkSwitchPortMode</span><span class="sxs-lookup"><span data-stu-id="0a352-114">Set-NetworkSwitchPortMode</span></span>
- <span data-ttu-id="0a352-115">Set-NetworkSwitchPortProperty</span><span class="sxs-lookup"><span data-stu-id="0a352-115">Set-NetworkSwitchPortProperty</span></span>
- <span data-ttu-id="0a352-116">Disable-NetworkSwitchFeature</span><span class="sxs-lookup"><span data-stu-id="0a352-116">Disable-NetworkSwitchFeature</span></span>
- <span data-ttu-id="0a352-117">Enable-NetworkSwitchFeature</span><span class="sxs-lookup"><span data-stu-id="0a352-117">Enable-NetworkSwitchFeature</span></span>
- <span data-ttu-id="0a352-118">Remove-NetworkSwitchVlan</span><span class="sxs-lookup"><span data-stu-id="0a352-118">Remove-NetworkSwitchVlan</span></span>
- <span data-ttu-id="0a352-119">Set-NetworkSwitchVlanProperty</span><span class="sxs-lookup"><span data-stu-id="0a352-119">Set-NetworkSwitchVlanProperty</span></span>

## <a name="resolution"></a><span data-ttu-id="0a352-120">Разрешение</span><span class="sxs-lookup"><span data-stu-id="0a352-120">Resolution</span></span>

<span data-ttu-id="0a352-121">Командлеты работают нормально, если значение параметра InputObject передается через конвейер.</span><span class="sxs-lookup"><span data-stu-id="0a352-121">The cmdlets work fine when the value of InputObject parameter are passed into it through pipeline.</span></span> <span data-ttu-id="0a352-122">Ниже приведены примеры, подходящие для командлетов выше.</span><span class="sxs-lookup"><span data-stu-id="0a352-122">A few examples that work for the above cmdlets are:</span></span>

- `Disable-NetworkSwitchEthernetPort`

  ```powershell
  $port = Get-CimInstance -Namespace root/interop -ClassName CIM_EthernetPort -CimSession $cimSession | Select-Object -First 1
  $port | Disable-NetworkSwitchEthernetPort -CimSession $cimSession
  ```

- `Enable-NetworkSwitchEthernetPort`

  ```powershell
  $port = Get-CimInstance -Namespace root/interop -ClassName CIM_EthernetPort -CimSession $cimSession | Select-Object -First 1
  $port | Enable-NetworkSwitchEthernetPort -CimSession $cimSession
  ```

- `Remove-NetworkSwitchEthernetPortIPAddress`

  ```powershell
  $port = Get-CimInstance -Namespace root/interop -ClassName CIM_EthernetPort -CimSession $cimSession | Select-Object -First 1
  $port | Remove-NetworkSwitchEthernetPortIPAddress -CimSession $cimSession
  ```

- `Set-NetworkSwitchEthernetPortIPAddress`

  ```powershell
  $port = Get-CimInstance -Namespace root/interop -ClassName CIM_EthernetPort -CimSession $cimSession | Select-Object -First 1
  $ipAddress = "192.168.10.1"
  $subnetAddress = "255.255.255.0"
  $port | Set-NetworkSwitchEthernetPortIPAddress -IpAddress $ipAddress -SubnetAddress $subnetAddress -CimSession $cimSession
  ```

- `Set-NetworkSwitchPortProperty`

  ```powershell
  $portProperties = @{Caption = "New Caption"}
  $port = Get-CimInstance -Namespace root/interop -ClassName CIM_EthernetPort -CimSession $cimSession | Select-Object -First 1
  $port | Set-NetworkSwitchPortProperty -Property $portProperties -CimSession $cimSession
  ```

- `Disable-NetworkSwitchFeature`

  ```powershell
  $feature = Get-CimInstance -Namespace root/interop -ClassName MSFT_Feature -CimSession $cimSession | Select-Object -First 1
  $feature | Disable-NetworkSwitchFeature -CimSession $cimSession
  ```

- `Enable-NetworkSwitchFeature`

  ```powershell
  $feature = Get-CimInstance -Namespace root/interop -ClassName MSFT_Feature -CimSession $cimSession | Select-Object -First 1
  $feature | Enable-NetworkSwitchFeature -CimSession $cimSession
  ```

- `Set-NetworkSwitchVlanProperty`

  ```powershell
  $properties = @{Caption = "New Caption"}
  $vlan = Get-CimInstance -ClassName CIM_NetworkVlan -Namespace root/interop -CimSession $cimSession | Select-Object -First 1
  $vlan | Set-NetworkSwitchVlanProperty -Property $properties -CimSession $cimSession
  ```