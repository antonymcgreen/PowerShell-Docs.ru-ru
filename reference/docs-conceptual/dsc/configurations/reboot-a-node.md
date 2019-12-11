---
ms.date: 01/17/2019
keywords: dsc,powershell,конфигурация,установка
title: Перезагрузка узла
ms.openlocfilehash: 22c63fab9b6646f522f8531b46a43a94ff883552
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "71954031"
---
# <a name="reboot-a-node"></a>Перезагрузка узла

> [!NOTE]
> В этом разделе рассказывается о том, как перезагрузить узел. Для успешной перезагрузки необходимо правильно настроить параметры **ActionAfterReboot** и **RebootNodeIfNeeded** локального диспетчера конфигураций.
> Описание параметров локального диспетчера конфигураций см. в разделе [Настройка локального диспетчера конфигураций](../managing-nodes/metaConfig.md) или [Настройка локального диспетчера конфигураций (версия 4)](../managing-nodes/metaConfig4.md).

Узлы можно перезагрузить из ресурса с помощью флага `$global:DSCMachineStatus`. Установка этого флага как `1` в функции `Set-TargetResource` принуждает LCM перезапускать узел непосредственно после метода **Set** текущего ресурса. При указании этого флага ресурс **PendingReboot** в модуле ресурсов DSC [ComputerManagementDsc](https://github.com/PowerShell/ComputerManagementDsc) обнаруживает, что ожидается перезагрузка за пределами DSC.

Ваши [конфигурации](configurations.md) могут выполнять действия, требующие перезагрузки узла. Сюда могут входить такие вещи, как:

- обновления Windows;
- установка ПО;
- переименование файлов;
- переименование компьютеров.

Ресурс **PendingReboot** проверяет конкретные места на компьютере, чтобы определить, ожидается ли перезагрузка. Если узлу требуется перезагрузка за пределами DSC, ресурс **PendingReboot** задает флаг `$global:DSCMachineStatus` как `1`, вызывая принудительную перезагрузку и устраняя состояние ожидания.

> [!NOTE]
> Любой ресурс DSC может заставить LCM перезапустить узел, установив этот флаг в функции `Set-TargetResource`. Дополнительные сведения см. в разделе [Написание пользовательских ресурсов DSC с использованием MOF](../resources/authoringResourceMOF.md).

## <a name="syntax"></a>Синтаксис

```
PendingReboot [String] #ResourceName
{
    Name = [string]
    [DependsOn = [string[]]]
    [PsDscRunAsCredential = [PSCredential]]
    [SkipCcmClientSDK = [bool]]
    [SkipComponentBasedServicing = [bool]]
    [SkipPendingComputerRename = [bool]]
    [SkipPendingFileRename = [bool]]
    [SkipWindowsUpdate = [bool]]
}
```

## <a name="properties"></a>Свойства

| Свойство | Описание |
| --- | --- |
| Name| Обязательный параметр, который должен быть уникальным для каждого экземпляра ресурса в конфигурации.|
| SkipComponentBasedServicing | Пропускать перезагрузки, активируемые компонентом Component-Based Servicing. |
| SkipWindowsUpdate | Пропускать перезагрузки, активируемые обновлениями Windows.|
| SkipPendingFileRename | Пропускать перезагрузки, активируемые переименованием файлов. |
| SkipCcmClientSDK | Пропускать перезагрузки, активируемые клиентами Configuration Manager. |
| SkipComputerRename | Пропускать перезагрузки, активируемые переименованием компьютера. |
| PSDSCRunAsCredential | Поддерживается в версии 5. Ресурс выполняется в контексте указанного пользователя. |
| DependsOn | Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса. Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — **ResourceName**, а его тип — **ResourceType**, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`. Дополнительные сведения см. в разделе [Использование DependsOn](resource-depends-on.md).|

## <a name="example"></a>Пример

В следующем примере Microsoft Exchange устанавливается с помощью ресурса [xExchange](https://github.com/PowerShell/xExchange).
На протяжении установки ресурс **PendingReboot** используется для перезагрузки узла.

> [!NOTE]
> В этом примере требуются учетные данные учетной записи, имеющей права на добавление сервера Exchange в лесе. Дополнительные сведения об использовании учетных данных в DSC см. в разделе [Обработка учетных данных в DSC](../configurations/configDataCredentials.md).

```powershell
$ConfigurationData = @{
    AllNodes = @(
        @{
            NodeName                    = '*'
            PSDSCAllowPlainTextPassword = $true
        },
        @{
            NodeName = 'DSCPULL-1'
        }
    )
}

Configuration Example
{
    param
    (
        [Parameter(Mandatory = $true)]
        [System.Management.Automation.PSCredential]
        $ExchangeAdminCredential
    )

    Import-DscResource -Module xExchange
    Import-DscResource -Module ComputerManagementDsc

    Node $AllNodes.NodeName
    {
        # Copy the Exchange setup files locally
        File ExchangeBinaries
        {
            Ensure          = 'Present'
            Type            = 'Directory'
            Recurse         = $true
            SourcePath      = '\\rras-1\Binaries\E15CU6'
            DestinationPath = 'C:\Binaries\E15CU6'
        }

        # Check if a reboot is needed before installing Exchange
        PendingReboot BeforeExchangeInstall
        {
            Name       = 'BeforeExchangeInstall'
            DependsOn  = '[File]ExchangeBinaries'
        }

        # Do the Exchange install
        xExchInstall InstallExchange
        {
            Path       = 'C:\Binaries\E15CU6\Setup.exe'
            Arguments  = '/mode:Install /role:Mailbox /Iacceptexchangeserverlicenseterms'
            Credential = $ExchangeAdminCredential
            DependsOn  = '[PendingReboot]BeforeExchangeInstall'
        }

        # See if a reboot is required after installing Exchange
        PendingReboot AfterExchangeInstall
        {
            Name      = 'AfterExchangeInstall'
            DependsOn = '[xExchInstall]InstallExchange'
        }
    }
}
```

> [!NOTE]
> В этом примере предполагается, что вы настроили локальный диспетчер конфигураций, разрешив перезагрузки, и продолжили настройку после перезагрузки.

## <a name="where-to-download"></a>Где скачать

Вы можете скачать ресурсы, используемые в этом разделе, в следующих расположениях или с помощью коллекции PowerShell.

- [ComputerManagementDsc](https://github.com/PowerShell/ComputerManagementDsc)
- [xExchange](https://github.com/PowerShell/xExchange)
