---
title: Совместимость модулей PowerShell 7
ms.date: 02/03/2020
ms.openlocfilehash: 02095b8233b6fc7b6d2a30bcb841bfd831a50031
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "78935193"
---
# <a name="powershell-7-module-compatibility"></a>Совместимость модулей PowerShell 7

В этой статье содержится список модулей PowerShell, опубликованных корпорацией Майкрософт. Эти модули обеспечивают управление различными продуктами и службами Майкрософт, а также их поддержку. Они были обновлены для работы с PowerShell 7 без дополнительных требований или протестированы на совместимость с PowerShell 7. Список будет обновляться по мере появления и тестирования дополнительных модулей.

Если вы хотите поделиться дополнительной информацией или сведениями о проблемах, связанных с определенными модулями, создайте проблему в [репозитории WindowsCompatibility](https://github.com/PowerShell/WindowsCompatibility).

## <a name="windows-management-modules"></a>Модули управления Windows

Модули управления Windows устанавливаются по-разному в зависимости от выпуска Windows и способа упаковки модуля для этого выпуска.

В Windows Server выполните командлет [Install-WindowsFeature](/powershell/module/servermanager/install-windowsfeature) с правами администратора, указав имя компонента. Пример:

```powershell
Install-WindowsFeature -Name ActiveDirectory
```

В Windows 10 модули управления Windows доступны в виде **дополнительных компонентов Windows** или **возможностей Windows**. Приведенные ниже команды должны выполняться с повышенными привилегиями с помощью команды **Запуск от имени администратора**.


- Дополнительные компоненты Windows

  Чтобы получить список дополнительных компонентов, выполните следующую команду:

  ```powershell
  Get-WindowsOptionalFeature -Online
  ```

  Чтобы установить компонент, выполните следующую команду:

  ```powershell
  Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Hyper-V-Management-PowerShell
  ```

  Дополнительные сведения см. в разделах:

  - [Get-WindowsOptionalFeature](/powershell/module/dism/get-windowsoptionalfeature)
  - [Enable-WindowsOptionalFeature](/powershell/module/dism/enable-windowsoptionalfeature)

- Возможности Windows

  Чтобы получить список возможностей Windows, выполните следующую команду:

  ```powershell
  Get-WindowsCapability -online
  ```

  Обратите внимание, что имя пакета возможностей заканчивается на `~~~~0.0.1.0`. Для установки возможности необходимо использовать полное имя:

  ```powershell
  Add-WindowsCapability -Online -Name Rsat.ServerManager.Tools~~~~0.0.1.0
  ```

  Дополнительные сведения см. в разделах:

  - [Get-WindowsCapability](/powershell/module/dism/get-windowscapability)
  - [Add-WindowsCapability](/powershell/module/dism/add-windowscapability)

### <a name="module-list"></a>Список модулей

| Имя модуля                        | Состояние                               | Поддерживаемая ОС                       |
| ---------------------------------- | ------------------------------------ | ---------------------------------- |
| ActiveDirectory                    | Встроенная совместимость                  | Windows Server 1809 или более поздней версии с RSAT-AD-PowerShell<br>Windows 10 1809 или более поздней версии с Rsat.ActiveDirectory.DS-LDS.Tools |
| ADFS                               | Проверка уровня совместимости не проводилась    |                                    |
| AppBackgroundTask                  | Встроенная совместимость                  | Windows 10 1903 или более поздней версии                   |
| AppLocker                          | Проверка уровня совместимости не проводилась    |                                    |
| AppvClient                         | Проверка уровня совместимости не проводилась    |                                    |
| Appx                               | Встроенная совместимость                  | Windows Server 1809 или более поздней версии<br>Windows 10 1809 или более поздней версии |
| AssignedAccess                     | Встроенная совместимость                  | Windows 10 1809 или более поздней версии                   |
| BestPractices                      | Проверка уровня совместимости не проводилась    |                                    |
| BitLocker                          | Встроенная совместимость                  | Windows Server 1809 или более поздней версии с BitLocker<br>Windows 10 1809 или более поздней версии |
| BitsTransfer                       | Встроенная совместимость                  | Windows Server 20H1<br>Windows 10 20H1 |
| BootEventCollector                 | Проверка уровня совместимости не проводилась    |                                        |
| BranchCache                        | Встроенная совместимость                  | Windows Server 1809 или более поздней версии<br>Windows 10 1809 или более поздней версии |
| CimCmdlets                         | Встроенная совместимость                  | Встроен в PowerShell 7 |
| ClusterAwareUpdating               | Проверка уровня совместимости не проводилась    |                         |
| ConfigCI                           | Проверка уровня совместимости не проводилась    |                         |
| Defender                           | Встроенная совместимость                  | Windows Server 1809 или более поздней версии<br>Windows 10 1809 или более поздней версии  |
| DeliveryOptimization               | Встроенная совместимость                  | Windows Server 1903 или более поздней версии<br>Windows 10 1903 или более поздней версии  |
| DFSN                               | Встроенная совместимость                  | Windows Server 1809 или более поздней версии с FS-DFS-Namespace<br>Windows 10 1809 или более поздней версии с Rsat.FailoverCluster.Management.Tools |
| DFSR                               | Проверка уровня совместимости не проводилась    |                                   |
| DhcpServer                         | Проверка уровня совместимости не проводилась    |                                   |
| DirectAccessClientComponents       | Встроенная совместимость                  | Windows Server 1809 или более поздней версии<br>Windows 10 1809 или более поздней версии  |
| Dism                               | Встроенная совместимость                  | Windows Server 1903 или более поздней версии<br>Windows 10 1903 или более поздней версии  |
| DnsClient                          | Встроенная совместимость                  | Windows Server 1809 или более поздней версии<br>Windows 10 1809 или более поздней версии  |
| DnsServer                          | Встроенная совместимость                  | Windows Server 1809 или более поздней версии с DNS или RSAT-DNS-Server<br>Windows 10 1809 или более поздней версии с Rsat.Dns.Tools |
| EventTracingManagement             | Встроенная совместимость                  | Windows Server 1809 или более поздней версии<br>Windows 10 1809 или более поздней версии  |
| FailoverClusters                   | Проверка уровня совместимости не проводилась    |                                  |
| FailoverClusterSet                 | Проверка уровня совместимости не проводилась    |                                  |
| FileServerResourceManager          | Встроенная совместимость                  | Windows Server 1809 или более поздней версии с FS-Resource-Manager |
| GroupPolicy                        | Проверка уровня совместимости не проводилась    |                                               |
| HgsClient                          | Встроенная совместимость                  | Windows Server 1903 или более поздней версии с Hyper-V или RSAT-Shielded-VM-Tools<br>Windows 10 1903 или более поздней версии с Rsat.Shielded.VM.Tools |
| HgsDiagnostics                     | Встроенная совместимость                  | Windows Server 1809 или более поздней версии с Hyper-V или RSAT-Shielded-VM-Tools<br>Windows 10 1809 или более поздней версии с Rsat.Shielded.VM.Tools |
| Hyper-V                            | Встроенная совместимость                  | Windows Server 1809 или более поздней версии с Hyper-V-PowerShell<br>Windows 10 1809 или более поздней версии с Microsoft-Hyper-V-Management-PowerShell |
| IISAdministration                  | Проверка уровня совместимости не проводилась    |                                               |
| International                      | Встроенная совместимость                  | Windows Server 1903 или более поздней версии<br>Windows 10 1903 или более поздней версии      |
| IpamServer                         | Проверка уровня совместимости не проводилась    |                                               |
| iSCSI                              | Проверка уровня совместимости не проводилась    |                                               |
| IscsiTarget                        | Проверка уровня совместимости не проводилась    |                                               |
| ISE                                | Проверка уровня совместимости не проводилась    |                                               |
| Kds                                | Встроенная совместимость                  | Windows Server 20H1<br>Windows 10 20H1        |
| Microsoft.PowerShell.Archive       | Встроенная совместимость                  | Встроен в PowerShell 7                       |
| Microsoft.PowerShell.Diagnostics   | Встроенная совместимость                  | Встроен в PowerShell 7                       |
| Microsoft.PowerShell.Host          | Встроенная совместимость                  | Встроен в PowerShell 7                       |
| Microsoft.PowerShell.LocalAccounts | Встроенная совместимость                  | Windows Server 1809 или более поздней версии<br>Windows 10 1809 или более поздней версии      |
| Microsoft.PowerShell.Management    | Встроенная совместимость                  | Встроен в PowerShell 7                       |
| Microsoft.PowerShell.ODataUtils    | Проверка уровня совместимости не проводилась    |                                               |
| Microsoft.PowerShell.Security      | Встроенная совместимость                  | Встроен в PowerShell 7                       |
| Microsoft.PowerShell.Utility       | Встроенная совместимость                  | Встроен в PowerShell 7                       |
| Microsoft.WSMan.Management         | Встроенная совместимость                  | Встроен в PowerShell 7                       |
| MMAgent                            | Встроенная совместимость                  | Windows Server 1809 или более поздней версии<br>Windows 10 1809 или более поздней версии      |
| MPIO                               | Встроенная совместимость                  | Windows Server 1809 или более поздней версии с Multipath-IO        |
| MsDtc                              | Проверка уровня совместимости не проводилась    |                                               |
| NetAdapter                         | Встроенная совместимость                  | Windows Server 1809 или более поздней версии<br>Windows 10 1809 или более поздней версии      |
| NetConnection                      | Встроенная совместимость                  | Windows Server 1809 или более поздней версии<br>Windows 10 1809 или более поздней версии      |
| NetEventPacketCapture              | Встроенная совместимость                  | Windows Server 1809 или более поздней версии<br>Windows 10 1809 или более поздней версии      |
| NetLbfo                            | Встроенная совместимость                  | Windows Server 1809 или более поздней версии<br>Windows 10 1809 или более поздней версии      |
| NetLldpAgent                       | Проверка уровня совместимости не проводилась    |                                               |
| NetNat                             | Встроенная совместимость                  | Windows Server 1809 или более поздней версии<br>Windows 10 1809 или более поздней версии      |
| NetQos                             | Встроенная совместимость                  | Windows Server 1809 или более поздней версии<br>Windows 10 1809 или более поздней версии      |
| NetSecurity                        | Встроенная совместимость                  | Windows Server 1809 или более поздней версии<br>Windows 10 1809 или более поздней версии      |
| NetSwitchTeam                      | Встроенная совместимость                  | Windows Server 1809 или более поздней версии<br>Windows 10 1809 или более поздней версии      |
| NetTCPIP                           | Встроенная совместимость                  | Windows Server 1809 или более поздней версии<br>Windows 10 1809 или более поздней версии      |
| NetWNV                             | Проверка уровня совместимости не проводилась    |                                               |
| NetworkConnectivityStatus          | Встроенная совместимость                  | Windows Server 1809 или более поздней версии<br>Windows 10 1809 или более поздней версии      |
| NetworkController                  | Проверка уровня совместимости не проводилась    |                                               |
| NetworkControllerDiagnostics       | Проверка уровня совместимости не проводилась    |                                               |
| NetworkLoadBalancingClusters       | Проверка уровня совместимости не проводилась    |                                               |
| NetworkSwitchManager               | Встроенная совместимость                  | Windows Server 1809 или более поздней версии<br>Windows 10 1809 или более поздней версии      |
| NetworkTransition                  | Встроенная совместимость                  | Windows Server 1809 или более поздней версии<br>Windows 10 1809 или более поздней версии      |
| NFS                                | Встроенная совместимость                  | Windows Server 1809 или более поздней версии<br>Windows 10 1809 или более поздней версии с Rsat.ServerManager.Tools |
| PackageManagement                  | Встроенная совместимость                  | Встроен в PowerShell 7                       |
| PcsvDevice                         | Встроенная совместимость                  | Windows Server 1809 или более поздней версии<br>Windows 10 1809 или более поздней версии      |
| PersistentMemory                   | Проверка уровня совместимости не проводилась    |                                               |
| PKI                                | Проверка уровня совместимости не проводилась    |                                               |
| PnpDevice                          | Встроенная совместимость                  | Windows Server 1809 или более поздней версии<br>Windows 10 1809 или более поздней версии      |
| PowerShellGet                      | Встроенная совместимость                  | Встроен в PowerShell 7                       |
| PrintManagement                    | Встроенная совместимость                  | Windows Server 1903 или более поздней версии с Print-Services<br>Windows 10 1903 или более поздней версии  |
| ProcessMitigations                 | Встроенная совместимость                  | Windows Server 1903 или более поздней версии<br>Windows 10 1903 или более поздней версии      |
| Подготовка                       | Проверка уровня совместимости не проводилась    |                                               |
| PSDesiredStateConfiguration        | Частично                            | Встроен в PowerShell 7                       |
| PSDiagnostics                      | Встроенная совместимость                  | Встроен в PowerShell 7                       |
| PSScheduledJob                     | Не работает с уровнем совместимости | Встроен в PowerShell 5.1                     |
| PSWorkflow                         | Проверка уровня совместимости не проводилась    |                                               |
| PSWorkflowUtility                  | Проверка уровня совместимости не проводилась    |                                               |
| RemoteAccess                       | Проверка уровня совместимости не проводилась    |                                               |
| RemoteDesktop                      | Проверка уровня совместимости не проводилась    |                                               |
| ScheduledTasks                     | Встроенная совместимость                  | Windows Server 1809 или более поздней версии<br>Windows 10 1809 или более поздней версии      |
| SecureBoot                         | Встроенная совместимость                  | Windows Server 1809 или более поздней версии<br>Windows 10 1809 или более поздней версии      |
| ServerCore                         | Проверка уровня совместимости не проводилась    |                                               |
| ServerManager                      | Проверка уровня совместимости не проводилась    |                                               |
| ServerManagerTasks                 | Проверка уровня совместимости не проводилась    |                                               |
| ShieldedVMDataFile                 | Встроенная совместимость                  | Windows Server 1903 или более поздней версии с RSAT-Shielded-VM-Tools<br>Windows 10 1903 или более поздней версии с Rsat.Shielded.VM.Tools |
| ShieldedVMProvisioning             | Встроенная совместимость                  | Windows Server 1809 или более поздней версии с HostGuardian<br>Windows 10 1809 или более поздней версии с HostGuardian  |
| ShieldedVMTemplate                 | Встроенная совместимость                  | Windows Server 1809 или более поздней версии с RSAT-Shielded-VM-Tools<br>Windows 10 1809 или более поздней версии с Rsat.Shielded.VM.Tools |
| SmbShare                           | Встроенная совместимость                  | Windows Server 1809 или более поздней версии<br>Windows 10 1809 или более поздней версии      |
| SmbWitness                         | Встроенная совместимость                  | Windows Server 1809 или более поздней версии<br>Windows 10 1809 или более поздней версии      |
| SMISConfig                         | Встроенная совместимость                  | Windows Server 1903 или более поздней версии с WindowsStorageManagementService |
| SMS                                | Проверка уровня совместимости не проводилась    |                                               |
| SoftwareInventoryLogging           | Встроенная совместимость                  | Windows Server 1809 или более поздней версии                          |
| StartLayout                        | Встроенная совместимость                  | Windows Server 1809 или более поздней версии с Desktop Experience<br>Windows 10 1809 или более поздней версии |
| Память                            | Встроенная совместимость                  | Windows Server 1809 или более поздней версии<br>Windows 10 1809 или более поздней версии      |
| StorageBusCache                    | Проверка уровня совместимости не проводилась    |                                               |
| StorageMigrationService            | Проверка уровня совместимости не проводилась    |                                               |
| StorageQOS                         | Встроенная совместимость                  | Windows Server 1809 или более поздней версии с RSAT-Clustering-PowerShell<br>Windows 10 1809 или более поздней версии с Rsat.FailoverCluster.Management.Tools |
| StorageReplica                     | Проверка уровня совместимости не проводилась    |                                               |
| SyncShare                          | Встроенная совместимость                  | Windows Server 1809 или более поздней версии с FS-SyncShareService |
| SystemInsights                     | Проверка уровня совместимости не проводилась    |                                               |
| TLS                                | Проверка уровня совместимости не проводилась    |                                               |
| TroubleshootingPack                | Встроенная совместимость                  | Windows 10 1903 или более поздней версии                              |
| TrustedPlatformModule              | Встроенная совместимость                  | Windows Server 1809 или более поздней версии<br>Windows 10 1809 или более поздней версии      |
| UEV                                | Встроенная совместимость                  | Windows Server ??будущая версия сервера с возможностями рабочего стола??<br>Windows 10 1903 или более поздней версии |
| UpdateServices                     | Не работает с уровнем совместимости |                                               |
| VpnClient                          | Встроенная совместимость                  | Windows Server 1809 или более поздней версии<br>Windows 10 1809 или более поздней версии      |
| Wdac                               | Встроенная совместимость                  | Windows Server 1809 или более поздней версии<br>Windows 10 1809 или более поздней версии      |
| WebAdministration                  | Проверка уровня совместимости не проводилась    |                                               |
| WHEA                               | Встроенная совместимость                  | Windows Server 1903 или более поздней версии<br>Windows 10 1903 или более поздней версии      |
| WindowsDeveloperLicense            | Встроенная совместимость                  | Windows Server 1809 или более поздней версии с Desktop Experience<br>Windows 10 1809 или более поздней версии |
| WindowsErrorReporting              | Встроенная совместимость                  | Windows Server 1809 или более поздней версии<br>Windows 10 1809 или более поздней версии      |
| WindowsSearch                      | Встроенная совместимость                  | Windows 10 1903 или более поздней версии                              |
| WindowsServerBackup                | Встроенная совместимость                  | Windows Server 19H2 с Windows-Server-Backup |
| WindowsUpdate                      | Встроенная совместимость                  | Windows Server 1809 или более поздней версии<br>Windows 10 1809 или более поздней версии       |
| WindowsUpdateProvider              | Встроенная совместимость                  | Windows Server 1809 или более поздней версии<br>Windows 10 1809 или более поздней версии       |
