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
# <a name="update-nodes-from-a-pull-server"></a>Обновление узлов на опрашиваемом сервере

В следующих разделах предполагается, что вы уже настроили опрашивающего сервера. Если ваш сервер на включение внесенных изменений не установлен, можно использовать со следующими руководствами:

- [Настройка опрашиваемого SMB-сервера DSC](pullServerSmb.md)
- [Настройка опрашиваемого HTTP-сервера DSC](pullServer.md)

Каждого целевого узла можно настроить для загрузки конфигураций, ресурсов и даже сообщить о своем состоянии. В этой статье показано, как передать ресурсы, чтобы они были доступны, которые требуется загрузить и настроить клиенты для загрузки ресурсов автоматически. Когда узел получает назначенной конфигурации, с помощью **на включение внесенных изменений** или **Push** (v5), он автоматически скачивает все ресурсы, требования конфигурации из местоположения, указанного в LCM.

## <a name="using-the-update-dscconfiguration-cmdlet"></a>С помощью командлета Update-DSCConfiguration

Начиная с PowerShell 5.0 [Update-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/update-dscconfiguration) командлета, заставляет узел, чтобы обновить свою конфигурацию из опрашивающего сервера, настроенные в LCM.

```powershell
Update-DSCConfiguration -ComputerName "Server01"
```

## <a name="using-invoke-cimmethod"></a>С помощью Invoke-CIMMethod

В PowerShell 4.0, вы можете вручную по-прежнему принудительно опрашивающий клиент, чтобы обновить его конфигурацию с помощью [Invoke-CIMMethod](/powershell/module/cimcmdlets/invoke-cimmethod). Следующий пример создает сеанс CIM с помощью указанных учетных данных и вызывает необходимый метод CIM удаляет сеанс.

```powershell
$cimSession = New-CimSession -ComputerName "Server01" -Credential $(Get-Credential)
Invoke-CimMethod -CimSession $cimSession -Namespace 'root/microsoft/windows/desiredstateconfiguration' -Class 'MSFT_DscLocalConfigurationManager' -MethodName 'PerformRequiredConfigurationChecks' -Arguments @{ 'Flags' = [uint32]1 } -Verbose
$cimSession | Remove-CimSession
```

## <a name="see-also"></a>См. также

[PerformRequiredConfigurationChecks](/powershell/dsc/msft-dsclocalconfigurationmanager-performrequiredconfigurationchecks)
