---
ms.date: 1/17/2019
keywords: dsc,powershell,конфигурация,установка
title: Перезагрузка узла
ms.openlocfilehash: 33ecd98aa62c3dc94a8ff2213fd3e68bf0c05cb7
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "55680744"
---
# <a name="reboot-a-node"></a>Перезагрузка узла

> [!NOTE]
> В этом разделе рассказывается о том, как перезагрузить узел. В порядке для перезагрузки для успешной работы **ActionAfterReboot** и **RebootNodeIfNeeded** необходимо правильно настроить параметры локального диспетчера Конфигураций.
> Чтобы прочитать о параметры локального диспетчера конфигураций, см. в разделе [настройки локального диспетчера конфигураций](../managing-nodes/metaConfig.md), или [настройки локального диспетчера конфигураций (версия 4)](../managing-nodes/metaConfig4.md).

Узлы можно перезагрузить из ресурса, с помощью `$global:DSCMachineStatus` флаг. Установка для этого флага `1` в `Set-TargetResource` функция принудительно выполняет LCM перепускать узел непосредственно после **задать** метод текущего ресурса. С помощью этого флага **xPendingReboot** ресурсов обнаруживает, если ожидается перезагрузка за пределами DSC.

Ваш [конфигураций](configurations.md) может выполнять действия, требующие перезагрузки узла. Сюда могут входить такие как вещи:

- Windows: обновления
- Установка программного обеспечения
- Переименовывает файл
- Переименование компьютера

**XPendingReboot** ресурс проверяет расположения конкретного компьютера, чтобы определить, если ожидается перезагрузка. Если узел требуется перезагрузка за пределами DSC, **xPendingReboot** наборов ресурсов `$global:DSCMachineStatus` флаг `1` Принудительная перезагрузка и устранению такого состояния ожидания.

> [!NOTE]
> Любой ресурс DSC можно настроить LCM будет перезапустить узел, установив этот флаг в `Set-TargetResource` функции. Дополнительные сведения см. в разделе [написание пользовательских ресурсов DSC с использованием MOF](../resources/authoringResourceMOF.md).

## <a name="syntax"></a>Синтаксис

```
xPendingReboot [String] #ResourceName
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
| SkipComponentBasedServicing | После перезагрузки Skip, активируемой компонентом Component-Based Servicing. |
| SkipWindowsUpdate | Пропустить перезагрузки инициируется обновления Windows.|
| SkipPendingFileRename | Пропустить ожидающих файл переименование после перезагрузки. |
| SkipCcmClientSDK | Пропустить перезагрузки инициируется клиента Configuration Manager. |
| SkipComputerRename | Пропустить перезагрузки активированное, переименования компьютера. |
| PsDscRunAsCredential | Поддерживается в версии 5. Ресурс выполняется в контексте указанного пользователя. |
| DependsOn | Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса. Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — **ResourceName**, а его тип — **ResourceType**, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`. Дополнительные сведения см. в разделе [с помощью DependsOn](resource-depends-on.md)|

## <a name="example"></a>Пример

В следующем примере устанавливаются с помощью Microsoft Exchange [xExchange](https://github.com/PowerShell/xExchange) ресурсов.
На протяжении установки **xPendingReboot** перепускать узел используется ресурс.

> [!NOTE]
> В этом примере требуются учетные данные учетной записи, имеющей права на добавление сервера Exchange в лесу. Дополнительные сведения об использовании учетных данных в DSC см. в разделе [обработка учетных данных в DSC](../configurations/configDataCredentials.md)

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
    Import-DscResource -Module xPendingReboot

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
        xPendingReboot BeforeExchangeInstall
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
            DependsOn  = '[xPendingReboot]BeforeExchangeInstall'
        }

        # See if a reboot is required after installing Exchange
        xPendingReboot AfterExchangeInstall
        {
            Name      = 'AfterExchangeInstall'
            DependsOn = '[xExchInstall]InstallExchange'
        }
    }
}
```

> [!NOTE]
> В этом примере предполагается, что вы настроили локальный диспетчер конфигураций для разрешения перезагрузок и продолжить настройку после перезагрузки.

## <a name="where-to-download"></a>Где можно скачать

Вы можете загрузить ресурсы, используемые в этом разделе, в следующих расположениях, или с помощью коллекции PowerShell.

- [xPendingReboot](https://github.com/PowerShell/xPendingReboot)
- [xExchange](https://github.com/PowerShell/xExchange)
