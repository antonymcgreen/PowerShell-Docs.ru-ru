---
ms.date: 02/03/2020
keywords: powershell,core
title: История выпусков модулей и командлетов
description: В этой статье перечислены модули и командлеты, поставляемые с различными версиями PowerShell.
ms.openlocfilehash: e79735e516c9aaa485c6513fb80de623014f06f5
ms.sourcegitcommit: 2fc6ee49a70bda4c59135136bd5cc7782836a124
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/18/2020
ms.locfileid: "94810357"
---
# <a name="release-history-of-modules-and-cmdlets"></a>История выпусков модулей и командлетов

В этой статье перечислены модули и командлеты, поставляемые с различными версиями PowerShell. Это сводка сведений, найденных в заметках о выпуске. Более подробные сведения можно найти в заметках о выпуске:

- [Новые возможности PowerShell 7.0](what-s-new-in-powershell-70.md)

Это выполняемая работа. Помогите нам сохранить эту информацию в актуальном состоянии.

## <a name="module-release-history"></a>История выпусков модуля

|         Имя модуля / версия PS          |   5.1   |   6.x   |   7.0   |   7.1   |     Примечание     |
| ----------------------------------------- | :-----: | :-----: | :-----: | :-----: | ------------ |
| CimCmdlets                                | &check; | &check; | &check; | &check; | Только Windows |
| ISE (появилось в 2.0)                   | &check; |         |         |         | Только Windows |
| Microsoft.PowerShell.Archive              | &check; | &check; | &check; | &check; |              |
| Microsoft.PowerShell.Core                 | &check; | &check; | &check; | &check; |              |
| Microsoft.PowerShell.Diagnostics          | &check; | &check; | &check; | &check; | Только Windows |
| Microsoft.PowerShell.Host                 | &check; | &check; | &check; | &check; |              |
| Microsoft.PowerShell.LocalAccounts        | &check; |         |         |         | Только Windows |
| Microsoft.PowerShell.Management           | &check; | &check; | &check; | &check; |              |
| Microsoft.PowerShell.ODataUtils           | &check; |         |         |         | Только Windows |
| Microsoft.PowerShell.Operation.Validation | &check; |         |         |         | Только Windows |
| Microsoft.PowerShell.Security             | &check; | &check; | &check; | &check; |              |
| Microsoft.PowerShell.Utility              | &check; | &check; | &check; | &check; |              |
| Microsoft.WsMan.Management                | &check; | &check; | &check; | &check; | Только Windows |
| PackageManagement                         | &check; | &check; | &check; | &check; |              |
| PowershellGet                             | &check; | &check; | &check; | &check; |              |
| PSDesiredStateConfiguration               | &check; | &check; | &check; | &check; |              |
| PSDiagnostics                             | &check; | &check; | &check; | &check; | Только Windows |
| PSReadline 1.x                            | &check; |         |         |         | Только Windows |
| PSReadline 2.0                            |         | &check; | &check; |         |              |
| PSReadline 2.1                            |         |         |         | &check; |              |
| PSScheduledJob                            | &check; |         |         |         | Только Windows |
| PSWorkflow                                | &check; |         |         |         | Только Windows |
| PSWorkflowUtility                         | &check; |         |         |         | Только Windows |
| ThreadJob                                 |         | &check; | &check; | &check; | Можно установить в PowerShell 5.1 |

## <a name="cmdlet-release-history"></a>История выпусков командлета

### <a name="cimcmdlets"></a>CimCmdlets

|         Имя командлета         |   5.1   |   6.x   |   7.0   |   7.1   |     Примечание     |
| --------------------------- | :-----: | :-----: | :-----: | :-----: | ------------ |
| Export-BinaryMiLog          | &check; | &check; | &check; | &check; | Только Windows |
| Get-CimAssociatedInstance   | &check; | &check; | &check; | &check; | Только Windows |
| Get-CimClass                | &check; | &check; | &check; | &check; | Только Windows |
| Get-CimInstance             | &check; | &check; | &check; | &check; | Только Windows |
| Get-CimSession              | &check; | &check; | &check; | &check; | Только Windows |
| Import-BinaryMiLog          | &check; | &check; | &check; | &check; | Только Windows |
| Invoke-CimMethod            | &check; | &check; | &check; | &check; | Только Windows |
| New-CimInstance             | &check; | &check; | &check; | &check; | Только Windows |
| New-CimSession              | &check; | &check; | &check; | &check; | Только Windows |
| New-CimSessionOption        | &check; | &check; | &check; | &check; | Только Windows |
| Register-CimIndicationEvent | &check; | &check; | &check; | &check; | Только Windows |
| Remove-CimInstance          | &check; | &check; | &check; | &check; | Только Windows |
| Remove-CimSession           | &check; | &check; | &check; | &check; | Только Windows |
| Set-CimInstance             | &check; | &check; | &check; | &check; | Только Windows |

### <a name="ise-introduced-in-20"></a>ISE (появилось в 2.0)

|    Имя командлета    |   5.1   | 6.x  |  7.0  |  7.1  |     Примечание     |
| ----------------- | :-----: | :--- | :---: | :---: | ------------ |
| Get-IseSnippet    | &check; |      |       |       | Только Windows |
| Import-IseSnippet | &check; |      |       |       | Только Windows |
| New-IseSnippet    | &check; |      |       |       | Только Windows |

### <a name="microsoftpowershellarchive"></a>Microsoft.PowerShell.Archive

|   Имя командлета    |   5.1   |   6.x   |   7.0   |   7.1   | Примечание |
| ---------------- | :-----: | :-----: | :-----: | :-----: | ---- |
| Compress-Archive | &check; | &check; | &check; | &check; |      |
| Expand-Archive   | &check; | &check; | &check; | &check; |      |

### <a name="microsoftpowershellcore"></a>Microsoft.PowerShell.Core

|            Имя командлета            |   5.1   |   6.x   |   7.0   |   7.1   |            Примечание            |
| --------------------------------- | :-----: | :-----: | :-----: | :-----: | -------------------------- |
| Add-History                       | &check; | &check; | &check; | &check; |                            |
| Add-PSSnapin                      | &check; |         |         |         | Только Windows               |
| Clear-History                     | &check; | &check; | &check; | &check; |                            |
| Clear-Host;                        | &check; | &check; | &check; | &check; |                            |
| Connect-PSSession                 | &check; | &check; | &check; | &check; | Только Windows               |
| Debug-Job                         | &check; | &check; | &check; | &check; |                            |
| Disable-ExperimentalFeature       |         |   6.2   | &check; | &check; |                            |
| Disable-PSRemoting                | &check; | &check; | &check; | &check; | Только Windows               |
| Disable-PSSessionConfiguration    | &check; | &check; | &check; | &check; | Только Windows               |
| Disconnect-PSSession              | &check; | &check; | &check; | &check; | Только Windows               |
| Enable-ExperimentalFeature        |         |   6.2   | &check; | &check; |                            |
| Enable-PSRemoting                 | &check; | &check; | &check; | &check; | Только Windows               |
| Enable-PSSessionConfiguration     | &check; | &check; | &check; | &check; | Только Windows               |
| Enter-PSHostProcess               | &check; | &check; | &check; | &check; | Добавлена поддержка Linux в 6.2 |
| Enter-PSSession                   | &check; | &check; | &check; | &check; |                            |
| Exit-PSHostProcess                | &check; | &check; | &check; | &check; | Добавлена поддержка Linux в 6.2 |
| Exit-PSSession;                    | &check; | &check; | &check; | &check; |                            |
| Export-Console                    | &check; |         |         |         | Только Windows               |
| Export-ModuleMember               | &check; | &check; | &check; | &check; |                            |
| ForEach-Object                    | &check; | &check; | &check; | &check; |                            |
| Get-Command;                       | &check; | &check; | &check; | &check; |                            |
| Get-ExperimentalFeature           |         |   6.2   | &check; | &check; |                            |
| Get-Help                          | &check; | &check; | &check; | &check; |                            |
| Get-History                       | &check; | &check; | &check; | &check; |                            |
| Get-Job.                           | &check; | &check; | &check; | &check; |                            |
| Get-Module                        | &check; | &check; | &check; | &check; |                            |
| Get-PSHostProcessInfo             | &check; | &check; | &check; | &check; | Добавлена поддержка Linux в 6.2 |
| Get-PSSession                     | &check; | &check; | &check; | &check; |                            |
| Get-PSSessionCapability           | &check; | &check; | &check; | &check; |                            |
| Get-PSSessionConfiguration        | &check; | &check; | &check; | &check; |                            |
| Get-PSSnapin                      | &check; |         |         |         | Только Windows               |
| Get-Verb                          | &check; |         |         |         | Перенесено в Microsoft.PowerShell.Utility 6.0+ |
| Import-Module                     | &check; | &check; | &check; | &check; |                            |
| Invoke-Command                    | &check; | &check; | &check; | &check; |                            |
| Invoke-History                    | &check; | &check; | &check; | &check; |                            |
| New-Module                        | &check; | &check; | &check; | &check; |                            |
| New-ModuleManifest                | &check; | &check; | &check; | &check; |                            |
| New-PSRoleCapabilityFile          | &check; | &check; | &check; | &check; |                            |
| New-PSSession                     | &check; | &check; | &check; | &check; |                            |
| New-PSSessionConfigurationFile    | &check; | &check; | &check; | &check; | Только Windows               |
| New-PSSessionOption               | &check; | &check; | &check; | &check; |                            |
| New-PSTransportOption             | &check; | &check; | &check; | &check; |                            |
| Out-Default;                       | &check; | &check; | &check; | &check; |                            |
| Out-Host                          | &check; | &check; | &check; | &check; |                            |
| Out-Null                          | &check; | &check; | &check; | &check; |                            |
| Receive-Job.                       | &check; | &check; | &check; | &check; |                            |
| Receive-PSSession                 | &check; | &check; | &check; | &check; | Только Windows               |
| Register-ArgumentCompleter        | &check; | &check; | &check; | &check; |                            |
| Register-PSSessionConfiguration   | &check; | &check; | &check; | &check; | Только Windows               |
| Remove-Job                        | &check; | &check; | &check; | &check; |                            |
| Remove-Module                     | &check; | &check; | &check; | &check; |                            |
| Remove-PSSession                  | &check; | &check; | &check; | &check; |                            |
| Remove-PSSnapin                   | &check; |         |         |         | Только Windows               |
| Resume-Job                        | &check; |         |         |         |                            |
| Save-Help                         | &check; | &check; | &check; | &check; |                            |
| Set-PSDebug                       | &check; | &check; | &check; | &check; |                            |
| Set-PSSessionConfiguration        | &check; | &check; | &check; | &check; | Только Windows               |
| Set-StrictMode                    | &check; | &check; | &check; | &check; |                            |
| Start-Job                         | &check; | &check; | &check; | &check; |                            |
| Stop-Job.                          | &check; | &check; | &check; | &check; |                            |
| Suspend-Job                       | &check; |         |         |         | Только Windows               |
| Test-ModuleManifest               | &check; | &check; | &check; | &check; |                            |
| Test-PSSessionConfigurationFile   | &check; | &check; | &check; | &check; | Только Windows               |
| Unregister-PSSessionConfiguration | &check; | &check; | &check; | &check; | Только Windows               |
| Update-Help                       | &check; | &check; | &check; | &check; |                            |
| Wait-Job                          | &check; | &check; | &check; | &check; |                            |
| Where-Object                      | &check; | &check; | &check; | &check; |                            |

### <a name="microsoftpowershelldiagnostics"></a>Microsoft.PowerShell.Diagnostics

|  Имя командлета   |   5.1   |   6.x   |   7.0   |   7.1   |     Примечание     |
| -------------- | :-----: | :-----: | :-----: | :-----: | ------------ |
| Export-Counter | &check; |         |         |         | Только Windows |
| Get-Counter    | &check; |         | &check; | &check; | Только Windows |
| Get-WinEvent   | &check; | &check; | &check; | &check; | Только Windows |
| Import-Counter | &check; |         |         |         | Только Windows |
| New-WinEvent   | &check; | &check; | &check; | &check; | Только Windows |

### <a name="microsoftpowershellhost"></a>Microsoft.PowerShell.Host

|   Имя командлета    |   5.1   |   6.x   |   7.0   |   7.1   | Примечание |
| ---------------- | :-----: | :-----: | :-----: | :-----: | ---- |
| Start-Transcript | &check; | &check; | &check; | &check; |      |
| Stop-Transcript  | &check; | &check; | &check; | &check; |      |

### <a name="microsoftpowershelllocalaccounts"></a>Microsoft.PowerShell.LocalAccounts

|       Имя командлета       |   5.1   | 6.x  |  7.0  |  7.1  |     Примечание     |
| ----------------------- | :-----: | :--- | :---: | :---: | ------------ |
| Add-LocalGroupMember    | &check; |      |       |       | Только Windows |
| Disable-LocalUser       | &check; |      |       |       | Только Windows |
| Enable-LocalUser        | &check; |      |       |       | Только Windows |
| Get-LocalGroup          | &check; |      |       |       | Только Windows |
| Get-LocalGroupMember    | &check; |      |       |       | Только Windows |
| Get-LocalUser           | &check; |      |       |       | Только Windows |
| New-LocalGroup          | &check; |      |       |       | Только Windows |
| New-LocalUser           | &check; |      |       |       | Только Windows |
| Remove-LocalGroup       | &check; |      |       |       | Только Windows |
| Remove-LocalGroupMember | &check; |      |       |       | Только Windows |
| Remove-LocalUser        | &check; |      |       |       | Только Windows |
| Rename-LocalGroup       | &check; |      |       |       | Только Windows |
| Rename-LocalUser        | &check; |      |       |       | Только Windows |
| Set-LocalGroup          | &check; |      |       |       | Только Windows |
| Set-LocalUser           | &check; |      |       |       | Только Windows |

### <a name="microsoftpowershellmanagement"></a>Microsoft.PowerShell.Management

|          Имя командлета          |   5.1   |   6.x   |   7.0   |   7.1   |               Примечание               |
| ----------------------------- | :-----: | :-----: | :-----: | :-----: | -------------------------------- |
| Add-Computer                  | &check; |         |         |         | Только Windows                     |
| Add-Content                   | &check; | &check; | &check; | &check; |                                  |
| Checkpoint-Computer           | &check; |         |         |         | Только Windows                     |
| Clear-Content                 | &check; | &check; | &check; | &check; |                                  |
| Clear-EventLog                | &check; |         |         |         | Только Windows                     |
| Clear-Item                    | &check; | &check; | &check; | &check; |                                  |
| Clear-ItemProperty            | &check; | &check; | &check; | &check; |                                  |
| Clear-RecycleBin              | &check; |         | &check; | &check; | Только Windows                     |
| Complete-Transaction          | &check; |         |         |         | Только Windows                     |
| Convert-Path                  | &check; | &check; | &check; | &check; |                                  |
| Copy-Item                     | &check; | &check; | &check; | &check; |                                  |
| Copy-ItemProperty             | &check; | &check; | &check; | &check; |                                  |
| Debug-Process                 | &check; | &check; | &check; | &check; |                                  |
| Disable-ComputerRestore       | &check; |         |         |         | Только Windows                     |
| Enable-ComputerRestore        | &check; |         |         |         | Только Windows                     |
| Get-ChildItem                 | &check; | &check; | &check; | &check; |                                  |
| Get-Clipboard                 | &check; |         | &check; | &check; | Не поддерживается в macOS.           |
| Get-ComputerInfo              | &check; | &check; | &check; | &check; | Только Windows                     |
| Get-ComputerRestorePoint      | &check; |         |         |         | Только Windows                     |
| Get-Content                   | &check; | &check; | &check; | &check; |                                  |
| Get-ControlPanelItem          | &check; |         |         |         | Только Windows                     |
| Get-EventLog                  | &check; |         |         |         | Только Windows                     |
| Get-HotFix                    | &check; |         | &check; | &check; | Только Windows                     |
| Get-Item                      | &check; | &check; | &check; | &check; |                                  |
| Get-ItemProperty              | &check; | &check; | &check; | &check; |                                  |
| Get-ItemPropertyValue         | &check; | &check; | &check; | &check; |                                  |
| Get-Location                  | &check; | &check; | &check; | &check; |                                  |
| Get-Process                   | &check; | &check; | &check; | &check; |                                  |
| Get-PSDrive                   | &check; | &check; | &check; | &check; |                                  |
| Get-PSProvider                | &check; | &check; | &check; | &check; |                                  |
| Get-Service                   | &check; | &check; | &check; | &check; | Только Windows                     |
| Get-TimeZone                  | &check; | &check; | &check; | &check; | Только Windows                     |
| Get-Transaction               | &check; |         |         |         | Только Windows                     |
| Get-WmiObject                 | &check; |         |         |         | Только Windows                     |
| Invoke-Item                   | &check; | &check; | &check; | &check; |                                  |
| Invoke-WmiMethod              | &check; |         |         |         | Только Windows                     |
| Join-Path                     | &check; | &check; | &check; | &check; |                                  |
| Limit-EventLog                | &check; |         |         |         | Только Windows                     |
| Move-Item                     | &check; | &check; | &check; | &check; |                                  |
| Move-ItemProperty             | &check; | &check; | &check; | &check; |                                  |
| New-EventLog                  | &check; |         |         |         | Только Windows                     |
| New-Item                      | &check; | &check; | &check; | &check; |                                  |
| New-ItemProperty              | &check; | &check; | &check; | &check; |                                  |
| New-PSDrive                   | &check; | &check; | &check; | &check; |                                  |
| New-Service                   | &check; | &check; | &check; | &check; | Только Windows                     |
| New-WebServiceProxy           | &check; |         |         |         | Только Windows                     |
| Pop-Location                  | &check; | &check; | &check; | &check; |                                  |
| Push-Location                 | &check; | &check; | &check; | &check; |                                  |
| Register-WmiEvent             | &check; |         |         |         | Только Windows                     |
| Remove-Computer               | &check; |         |         |         | Только Windows                     |
| Remove-EventLog               | &check; |         |         |         | Только Windows                     |
| Remove-Item                   | &check; | &check; | &check; | &check; |                                  |
| Remove-ItemProperty           | &check; | &check; | &check; | &check; |                                  |
| Remove-PSDrive                | &check; | &check; | &check; | &check; |                                  |
| Remove-Service                |         | &check; | &check; | &check; | Только Windows                     |
| Remove-WmiObject              | &check; |         |         |         | Только Windows                     |
| Rename-Computer               | &check; | &check; | &check; | &check; | Только Windows                     |
| Rename-Item                   | &check; | &check; | &check; | &check; |                                  |
| Rename-ItemProperty           | &check; | &check; | &check; | &check; |                                  |
| Reset-ComputerMachinePassword | &check; |         |         |         | Только Windows                     |
| Resolve-Path                  | &check; | &check; | &check; | &check; |                                  |
| Restart-Computer              | &check; | &check; | &check; | &check; | Добавлена поддержка для Linux/macOS в 7.1. |
| Restart-Service               | &check; | &check; | &check; | &check; | Только Windows                     |
| Restore-Computer              | &check; |         |         |         | Только Windows                     |
| Resume-Service                | &check; | &check; | &check; | &check; | Только Windows                     |
| Set-Clipboard                 | &check; |         | &check; | &check; |                                  |
| Set-Content                   | &check; | &check; | &check; | &check; |                                  |
| Set-Item                      | &check; | &check; | &check; | &check; |                                  |
| Set-ItemProperty              | &check; | &check; | &check; | &check; |                                  |
| Set-Location                  | &check; | &check; | &check; | &check; |                                  |
| Set-Service                   | &check; | &check; | &check; | &check; | Только Windows                     |
| Set-TimeZone                  | &check; | &check; | &check; | &check; | Только Windows                     |
| Set-WmiInstance               | &check; |         |         |         | Только Windows                     |
| Show-ControlPanelItem         | &check; |         |         |         | Только Windows                     |
| Show-EventLog                 | &check; |         |         |         | Только Windows                     |
| Split-Path                    | &check; | &check; | &check; | &check; |                                  |
| Start-Process                 | &check; | &check; | &check; | &check; |                                  |
| Start-Service                 | &check; | &check; | &check; | &check; | Только Windows                     |
| Start-Transaction             | &check; |         |         |         | Только Windows                     |
| Stop-Computer                 | &check; | &check; | &check; | &check; | Добавлена поддержка для Linux/macOS в 7.1. |
| Stop-Process                  | &check; | &check; | &check; | &check; |                                  |
| Stop-Service                  | &check; | &check; | &check; | &check; | Только Windows                     |
| Suspend-Service               | &check; | &check; | &check; | &check; | Только Windows                     |
| Test-ComputerSecureChannel    | &check; |         |         |         | Только Windows                     |
| Test-Connection               | &check; | &check; | &check; | &check; |                                  |
| Test-Path                     | &check; | &check; | &check; | &check; |                                  |
| Undo-Transaction              | &check; |         |         |         | Только Windows                     |
| Use-Transaction               | &check; |         |         |         | Только Windows                     |
| Wait-Process                  | &check; | &check; | &check; | &check; | Не работает в Linux и macOS     |
| Write-EventLog                | &check; |         |         |         | Только Windows                     |

### <a name="microsoftpowershellodatautils"></a>Microsoft.PowerShell.ODataUtils

|        Имя командлета        |   5.1   | 6.x  |  7.0  |  7.1  |     Примечание     |
| ------------------------- | :-----: | :--- | :---: | :---: | ------------ |
| Export-ODataEndpointProxy | &check; |      |       |       | Только Windows |

### <a name="microsoftpowershelloperationvalidation"></a>Microsoft.PowerShell.Operation.Validation

|        Имя командлета         |   5.1   | 6.x  |  7.0  |  7.1  |     Примечание     |
| -------------------------- | :-----: | :--- | :---: | :---: | ------------ |
| Get-OperationValidation    | &check; |      |       |       | Только Windows |
| Invoke-OperationValidation | &check; |      |       |       | Только Windows |

### <a name="microsoftpowershellsecurity"></a>Microsoft.PowerShell.Security

|        Имя командлета        |   5.1   |   6.x   |   7.0   |   7.1   |                  Примечание                   |
| ------------------------- | :-----: | :-----: | :-----: | :-----: | --------------------------------------- |
| ConvertFrom-SecureString  | &check; | &check; | &check; | &check; |                                         |
| ConvertTo-SecureString    | &check; | &check; | &check; | &check; |                                         |
| Get-Acl                   | &check; | &check; | &check; | &check; | Только Windows                            |
| Get-AuthenticodeSignature | &check; | &check; | &check; | &check; | Только Windows                            |
| Get-CmsMessage            | &check; | &check; | &check; | &check; | Поддержка для Linux и macOS добавлена в версии 7.1    |
| Get-Credential            | &check; | &check; | &check; | &check; |                                         |
| Get-ExecutionPolicy       | &check; | &check; | &check; | &check; | Возвращает **Неограниченный** в Linux/macOS |
| Get-PfxCertificate        | &check; | &check; | &check; | &check; |                                         |
| New-FileCatalog           | &check; | &check; | &check; | &check; | Только Windows                            |
| Protect-CmsMessage        | &check; | &check; | &check; | &check; | Поддержка для Linux и macOS добавлена в версии 7.1    |
| Set-Acl                   | &check; | &check; | &check; | &check; | Только Windows                            |
| Set-AuthenticodeSignature | &check; | &check; | &check; | &check; | Только Windows                            |
| Set-ExecutionPolicy       | &check; | &check; | &check; | &check; | Не выполняет никаких действий в Linux и macOS             |
| Test-FileCatalog          | &check; | &check; | &check; | &check; | Только Windows                            |
| Unprotect-CmsMessage      | &check; | &check; | &check; | &check; | Поддержка для Linux и macOS добавлена в версии 7.1    |

### <a name="microsoftpowershellutility"></a>Microsoft.PowerShell.Utility

|        Имя командлета        |   5.1   |   6.x   |   7.0   |   7.1   |                   Примечание                    |
| ------------------------- | :-----: | :-----: | :-----: | :-----: | ----------------------------------------- |
| Add-Member                | &check; | &check; | &check; | &check; |                                           |
| Add-Type                  | &check; | &check; | &check; | &check; |                                           |
| Clear-Variable            | &check; | &check; | &check; | &check; |                                           |
| Compare-Object            | &check; | &check; | &check; | &check; |                                           |
| ConvertFrom-Csv           | &check; | &check; | &check; | &check; |                                           |
| ConvertFrom-Json          | &check; | &check; | &check; | &check; |                                           |
| ConvertFrom-Markdown      |         |   6.1   | &check; | &check; |                                           |
| ConvertFrom-SddlString    | &check; | &check; | &check; | &check; | Только Windows                              |
| ConvertFrom-String        | &check; |         |         |         |                                           |
| ConvertFrom-StringData    | &check; | &check; | &check; | &check; |                                           |
| Convert-String            | &check; |         |         |         |                                           |
| ConvertTo-Csv             | &check; | &check; | &check; | &check; |                                           |
| ConvertTo-Html            | &check; | &check; | &check; | &check; |                                           |
| ConvertTo-Json            | &check; | &check; | &check; | &check; |                                           |
| ConvertTo-Xml             | &check; | &check; | &check; | &check; |                                           |
| Debug-Runspace            | &check; | &check; | &check; | &check; |                                           |
| Disable-PSBreakpoint      | &check; | &check; | &check; | &check; |                                           |
| Disable-RunspaceDebug     | &check; | &check; | &check; | &check; |                                           |
| Enable-PSBreakpoint       | &check; | &check; | &check; | &check; |                                           |
| Enable-RunspaceDebug      | &check; | &check; | &check; | &check; |                                           |
| Export-Alias              | &check; | &check; | &check; | &check; |                                           |
| Export-Clixml             | &check; | &check; | &check; | &check; |                                           |
| Export-Csv                | &check; | &check; | &check; | &check; |                                           |
| Export-FormatData         | &check; | &check; | &check; | &check; |                                           |
| Export-PSSession          | &check; | &check; | &check; | &check; |                                           |
| Format-Custom             | &check; | &check; | &check; | &check; |                                           |
| Format-Hex                | &check; | &check; | &check; | &check; |                                           |
| Format-List               | &check; | &check; | &check; | &check; |                                           |
| Format-Table              | &check; | &check; | &check; | &check; |                                           |
| Format-Wide               | &check; | &check; | &check; | &check; |                                           |
| Get-Alias                 | &check; | &check; | &check; | &check; |                                           |
| Get-Culture               | &check; | &check; | &check; | &check; |                                           |
| Get-Date                  | &check; | &check; | &check; | &check; |                                           |
| Get-Error                 |         |         | &check; | &check; |                                           |
| Get-Event                 | &check; | &check; | &check; | &check; | Нет доступных источников событий в Linux и macOS |
| Get-EventSubscriber       | &check; | &check; | &check; | &check; |                                           |
| Get-FileHash              | &check; | &check; | &check; | &check; |                                           |
| Get-FormatData;            | &check; | &check; | &check; | &check; |                                           |
| Get-Host                  | &check; | &check; | &check; | &check; |                                           |
| Get-MarkdownOption        |         |   6.1   | &check; | &check; |                                           |
| Get-Member                | &check; | &check; | &check; | &check; |                                           |
| Get-PSBreakpoint          | &check; | &check; | &check; | &check; |                                           |
| Get-PSCallStack           | &check; | &check; | &check; | &check; |                                           |
| Get-Random                | &check; | &check; | &check; | &check; |                                           |
| Get-Runspace              | &check; | &check; | &check; | &check; |                                           |
| Get-RunspaceDebug         | &check; | &check; | &check; | &check; |                                           |
| Get-TraceSource           | &check; | &check; | &check; | &check; |                                           |
| Get-TypeData              | &check; | &check; | &check; | &check; |                                           |
| Get-UICulture             | &check; | &check; | &check; | &check; |                                           |
| Get-Unique                | &check; | &check; | &check; | &check; |                                           |
| Get-Uptime                |         | &check; | &check; | &check; |                                           |
| Get-Variable              | &check; | &check; | &check; | &check; |                                           |
| Get-Verb                  |         | &check; | &check; | &check; | Перенесено из Microsoft.PowerShelll.Core     |
| Group-Object              | &check; | &check; | &check; | &check; |                                           |
| Import-Alias              | &check; | &check; | &check; | &check; |                                           |
| Import-Clixml             | &check; | &check; | &check; | &check; |                                           |
| Import-Csv                | &check; | &check; | &check; | &check; |                                           |
| Import-LocalizedData      | &check; | &check; | &check; | &check; |                                           |
| Import-PowerShellDataFile | &check; | &check; | &check; | &check; |                                           |
| Import-PSSession          | &check; | &check; | &check; | &check; |                                           |
| Invoke-Expression         | &check; | &check; | &check; | &check; |                                           |
| Invoke-RestMethod         | &check; | &check; | &check; | &check; |                                           |
| Invoke-WebRequest         | &check; | &check; | &check; | &check; |                                           |
| Join-String               |         | &check; | &check; | &check; |                                           |
| Measure-Command           | &check; | &check; | &check; | &check; |                                           |
| Measure-Object;            | &check; | &check; | &check; | &check; |                                           |
| New-Alias                 | &check; | &check; | &check; | &check; |                                           |
| New-Event                 | &check; | &check; | &check; | &check; | Нет доступных источников событий в Linux и macOS |
| New-Guid                  | &check; | &check; | &check; | &check; |                                           |
| New-Object                | &check; | &check; | &check; | &check; |                                           |
| New-TemporaryFile         | &check; | &check; | &check; | &check; |                                           |
| New-TimeSpan              | &check; | &check; | &check; | &check; |                                           |
| New-Variable              | &check; | &check; | &check; | &check; |                                           |
| Out-File                  | &check; | &check; | &check; | &check; |                                           |
| Out-GridView              | &check; |         | &check; | &check; | Только Windows                              |
| Out-Printer               | &check; |         | &check; | &check; | Только Windows                              |
| Out-String                | &check; | &check; | &check; | &check; |                                           |
| Read-Host                 | &check; | &check; | &check; | &check; |                                           |
| Register-EngineEvent      | &check; | &check; | &check; | &check; | Нет доступных источников событий в Linux и macOS |
| Register-ObjectEvent      | &check; | &check; | &check; | &check; |                                           |
| Remove-Alias              |         | &check; | &check; | &check; |                                           |
| Remove-Event              | &check; | &check; | &check; | &check; | Нет доступных источников событий в Linux и macOS |
| Remove-PSBreakpoint       | &check; | &check; | &check; | &check; |                                           |
| Remove-TypeData           | &check; | &check; | &check; | &check; |                                           |
| Remove-Variable           | &check; | &check; | &check; | &check; |                                           |
| Select-Object;             | &check; | &check; | &check; | &check; |                                           |
| Select-String             | &check; | &check; | &check; | &check; |                                           |
| Select-Xml                | &check; | &check; | &check; | &check; |                                           |
| Send-MailMessage          | &check; | &check; | &check; | &check; |                                           |
| Set-Alias                 | &check; | &check; | &check; | &check; |                                           |
| Set-Date                  | &check; | &check; | &check; | &check; |                                           |
| Set-MarkdownOption        |         |   6.1   | &check; | &check; |                                           |
| Set-PSBreakpoint          | &check; | &check; | &check; | &check; |                                           |
| Set-TraceSource           | &check; | &check; | &check; | &check; |                                           |
| Set-Variable              | &check; | &check; | &check; | &check; |                                           |
| Show-Command              | &check; |         | &check; | &check; | Только Windows                              |
| Show-Markdown             |         |   6.1   | &check; | &check; |                                           |
| Sort-Object               | &check; | &check; | &check; | &check; |                                           |
| Start-Sleep               | &check; | &check; | &check; | &check; |                                           |
| Tee-Object                | &check; | &check; | &check; | &check; |                                           |
| Test-Json                 |         | &check; | &check; | &check; |                                           |
| Trace-Command             | &check; | &check; | &check; | &check; |                                           |
| Unblock-File              | &check; | &check; | &check; | &check; | Добавлена поддержка для macOS в 7.0            |
| Unregister-Event          | &check; | &check; | &check; | &check; | Нет доступных источников событий в Linux и macOS |
| Update-FormatData         | &check; | &check; | &check; | &check; |                                           |
| Update-List               | &check; |         | &check; | &check; |                                           |
| Update-TypeData           | &check; | &check; | &check; | &check; |                                           |
| Wait-Debugger             | &check; | &check; | &check; | &check; |                                           |
| Wait-Event                | &check; | &check; | &check; | &check; |                                           |
| Write-Debug               | &check; | &check; | &check; | &check; |                                           |
| Write-Error               | &check; | &check; | &check; | &check; |                                           |
| Write-Host                | &check; | &check; | &check; | &check; |                                           |
| Write-Information         | &check; | &check; | &check; | &check; |                                           |
| Write-Output              | &check; | &check; | &check; | &check; |                                           |
| Write-Progress            | &check; | &check; | &check; | &check; |                                           |
| Write-Verbose             | &check; | &check; | &check; | &check; |                                           |
| Write-Warning             | &check; | &check; | &check; | &check; |                                           |

### <a name="microsoftwsmanmanagement"></a>Microsoft.WsMan.Management

|      Имя командлета       |   5.1   |   6.x   |   7.0   |   7.1   |     Примечание     |
| ---------------------- | :-----: | :-----: | :-----: | :-----: | ------------ |
| Connect-WSMan          | &check; | &check; | &check; | &check; | Только Windows |
| Disable-WSManCredSSP   | &check; | &check; | &check; | &check; | Только Windows |
| Disconnect-WSMan       | &check; | &check; | &check; | &check; | Только Windows |
| Enable-WSManCredSSP    | &check; | &check; | &check; | &check; | Только Windows |
| Get-WSManCredSSP       | &check; | &check; | &check; | &check; | Только Windows |
| Get-WSManInstance      | &check; | &check; | &check; | &check; | Только Windows |
| Invoke-WSManAction     | &check; | &check; | &check; | &check; | Только Windows |
| New-WSManInstance      | &check; | &check; | &check; | &check; | Только Windows |
| New-WSManSessionOption | &check; | &check; | &check; | &check; | Только Windows |
| Remove-WSManInstance   | &check; | &check; | &check; | &check; | Только Windows |
| Set-WSManInstance      | &check; | &check; | &check; | &check; | Только Windows |
| Set-WSManQuickConfig   | &check; | &check; | &check; | &check; | Только Windows |
| Test-WSMan             | &check; | &check; | &check; | &check; | Только Windows |

### <a name="packagemanagement"></a>PackageManagement

|       Имя командлета        |   5.1   |   6.x   |   7.0   |   7.1   | Примечание |
| ------------------------ | :-----: | :-----: | :-----: | :-----: | ---- |
| Find-Package             | &check; | &check; | &check; | &check; |      |
| Find-PackageProvider     | &check; | &check; | &check; | &check; |      |
| Get-Package              | &check; | &check; | &check; | &check; |      |
| Get-PackageProvider      | &check; | &check; | &check; | &check; |      |
| Get-PackageSource        | &check; | &check; | &check; | &check; |      |
| Import-PackageProvider   | &check; | &check; | &check; | &check; |      |
| Install-Package          | &check; | &check; | &check; | &check; |      |
| Install-PackageProvider  | &check; | &check; | &check; | &check; |      |
| Register-PackageSource   | &check; | &check; | &check; | &check; |      |
| Save-Package             | &check; | &check; | &check; | &check; |      |
| Set-PackageSource        | &check; | &check; | &check; | &check; |      |
| Uninstall-Package        | &check; | &check; | &check; | &check; |      |
| Unregister-PackageSource | &check; | &check; | &check; | &check; |      |

### <a name="powershellget"></a>PowershellGet

|           Имя командлета           |   5.1   |   6.x   |   7.0   |   7.1   | Примечание |
| ------------------------------- | :-----: | :-----: | :-----: | :-----: | ---- |
| Find-Command                    | &check; | &check; | &check; | &check; |      |
| Find-DscResource                | &check; | &check; | &check; | &check; |      |
| Find-Module                     | &check; | &check; | &check; | &check; |      |
| Find-RoleCapability             | &check; | &check; | &check; | &check; |      |
| Find-Script                     | &check; | &check; | &check; | &check; |      |
| Get-CredsFromCredentialProvider |         | &check; | &check; | &check; |      |
| Get-InstalledModule             | &check; | &check; | &check; | &check; |      |
| Get-InstalledScript             | &check; | &check; | &check; | &check; |      |
| Get-PSRepository                | &check; | &check; | &check; | &check; |      |
| Install-Module                  | &check; | &check; | &check; | &check; |      |
| Install-Script                  | &check; | &check; | &check; | &check; |      |
| New-ScriptFileInfo              | &check; | &check; | &check; | &check; |      |
| Publish-Module                  | &check; | &check; | &check; | &check; |      |
| Publish-Script                  | &check; | &check; | &check; | &check; |      |
| Register-PSRepository           | &check; | &check; | &check; | &check; |      |
| Save-Module                     | &check; | &check; | &check; | &check; |      |
| Save-Script                     | &check; | &check; | &check; | &check; |      |
| Set-PSRepository                | &check; | &check; | &check; | &check; |      |
| Test-ScriptFileInfo             | &check; | &check; | &check; | &check; |      |
| Uninstall-Module                | &check; | &check; | &check; | &check; |      |
| Uninstall-Script                | &check; | &check; | &check; | &check; |      |
| Unregister-PSRepository         | &check; | &check; | &check; | &check; |      |
| Update-Module                   | &check; | &check; | &check; | &check; |      |
| Update-ModuleManifest           | &check; | &check; | &check; | &check; |      |
| Update-Script                   | &check; | &check; | &check; | &check; |      |
| Update-ScriptFileInfo           | &check; | &check; | &check; | &check; |      |

### <a name="psdesiredstateconfiguration"></a>PSDesiredStateConfiguration

|                Имя командлета                 |   5.1   |   6.x   |   7.0   |   7.1   |     Примечание     |
| ------------------------------------------ | :-----: | :-----: | :-----: | :-----: | ------------ |
| Disable-DscDebug                           | &check; |         |         |         | Только Windows |
| Enable-DscDebug                            | &check; |         |         |         | Только Windows |
| Get-DscConfiguration                       | &check; |         |         |         | Только Windows |
| Get-DscConfigurationStatus                 | &check; |         |         |         | Только Windows |
| Get-DscLocalConfigurationManager           | &check; |         |         |         | Только Windows |
| Get-DscResource                            | &check; | &check; | &check; | &check; |              |
| Invoke-DscResource                         | &check; |         | &check; | &check; |              |
| New-DSCCheckSum                            | &check; | &check; | &check; | &check; |              |
| Publish-DscConfiguration                   | &check; |         |         |         | Только Windows |
| Remove-DscConfigurationDocument            | &check; |         |         |         | Только Windows |
| Restore-DscConfiguration                   | &check; |         |         |         | Только Windows |
| Set-DscLocalConfigurationManager           | &check; |         |         |         | Только Windows |
| Start-DscConfiguration                     | &check; |         |         |         | Только Windows |
| Stop-DscConfiguration                      | &check; |         |         |         | Только Windows |
| Test-DscConfiguration                      | &check; |         |         |         | Только Windows |
| Update-DscConfiguration                    | &check; |         |         |         | Только Windows |

### <a name="psdiagnostics"></a>PSDiagnostics

|         Имя командлета          |   5.1   |   6.x   |   7.0   |   7.1   |     Примечание     |
| ---------------------------- | :-----: | :-----: | :-----: | :-----: | ------------ |
| Disable-PSTrace              | &check; |   6.2   | &check; | &check; | Только Windows |
| Disable-PSWSManCombinedTrace | &check; |   6.2   | &check; | &check; | Только Windows |
| Disable-WSManTrace           | &check; | &check; | &check; | &check; | Только Windows |
| Enable-PSTrace               | &check; | &check; | &check; | &check; | Только Windows |
| Enable-PSWSManCombinedTrace  | &check; | &check; | &check; | &check; | Только Windows |
| Enable-WSManTrace            | &check; |   6.2   | &check; | &check; | Только Windows |
| Get-LogProperties            | &check; |   6.2   | &check; | &check; | Только Windows |
| Set-LogProperties            | &check; |   6.2   | &check; | &check; | Только Windows |
| Start-Trace                  | &check; |   6.2   | &check; | &check; | Только Windows |
| Stop-Trace                   | &check; |   6.2   | &check; | &check; | Только Windows |

### <a name="psreadline"></a>PSReadline

|         Имя командлета         |   5.1   |   6.x   |   7.0   |   7.1   | Примечание |
| --------------------------- | :-----: | :-----: | :-----: | :-----: | ---- |
| Get-PSReadlineKeyHandler    | &check; | &check; | &check; | &check; |      |
| Get-PSReadlineOption        | &check; | &check; | &check; | &check; |      |
| PSConsoleHostReadline       | &check; | &check; | &check; | &check; |      |
| Remove-PSReadlineKeyHandler | &check; | &check; | &check; | &check; |      |
| Set-PSReadlineKeyHandler    | &check; | &check; | &check; | &check; |      |
| Set-PSReadlineOption        | &check; | &check; | &check; | &check; |      |

### <a name="psscheduledjob"></a>PSScheduledJob

|       Имя командлета       |   5.1   | 6.x  |  7.0  |  7.1  |     Примечание     |
| ----------------------- | :-----: | :--- | :---: | :---: | ------------ |
| Add-JobTrigger          | &check; |      |       |       | Только Windows |
| Disable-JobTrigger      | &check; |      |       |       | Только Windows |
| Disable-ScheduledJob    | &check; |      |       |       | Только Windows |
| Enable-JobTrigger       | &check; |      |       |       | Только Windows |
| Enable-ScheduledJob     | &check; |      |       |       | Только Windows |
| Get-JobTrigger          | &check; |      |       |       | Только Windows |
| Get-ScheduledJob        | &check; |      |       |       | Только Windows |
| Get-ScheduledJobOption  | &check; |      |       |       | Только Windows |
| New-JobTrigger          | &check; |      |       |       | Только Windows |
| New-ScheduledJobOption  | &check; |      |       |       | Только Windows |
| Register-ScheduledJob   | &check; |      |       |       | Только Windows |
| Remove-JobTrigger       | &check; |      |       |       | Только Windows |
| Set-JobTrigger          | &check; |      |       |       | Только Windows |
| Set-ScheduledJob        | &check; |      |       |       | Только Windows |
| Set-ScheduledJobOption  | &check; |      |       |       | Только Windows |
| Unregister-ScheduledJob | &check; |      |       |       | Только Windows |

### <a name="psworkflow--psworkflowutility"></a>PSWorkflow & PSWorkflowUtility

|          Имя командлета          |   5.1   | 6.x  |  7.0  |  7.1  |     Примечание     |
| ----------------------------- | :-----: | :--- | :---: | :---: | ------------ |
| New-PSWorkflowExecutionOption | &check; |      |       |       | Только Windows |
| New-PSWorkflowSession         | &check; |      |       |       | Только Windows |
| Invoke-AsWorkflow             | &check; |      |       |       | Только Windows |

### <a name="threadjob"></a>ThreadJob

|   Имя командлета   |  5.1  |   6.x   |   7.0   |   7.1   | Примечание |
| --------------- | :---: | :-----: | :-----: | :-----: | ---- |
| Start-ThreadJob |       | &check; | &check; | &check; | Можно установить в PowerShell 5.1 |
