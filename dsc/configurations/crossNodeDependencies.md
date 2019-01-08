---
ms.date: 12/12/2018
keywords: dsc,powershell,конфигурация,установка
title: Указание межузловых зависимостей
ms.openlocfilehash: 1bdfbd9f8a94809d6bf410eff525e1c877fb6aad
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 12/14/2018
ms.locfileid: "53402200"
---
# <a name="specifying-cross-node-dependencies"></a>Указание межузловых зависимостей

> Область применения. Windows PowerShell 5.0

DSC предоставляет специальные ресурсы, **WaitForAll**, **WaitForAny** и **WaitForSome**, которые можно использовать в конфигурациях для указания зависимостей от конфигураций на других узлах. Поведение этих ресурсов описано ниже.

- **WaitForAll**: Выполняется успешно, если указанный ресурс находится в нужном состоянии на всех целевых узлах, определенных в **NodeName** свойство.
- **WaitForAny**: Выполняется успешно, если указанный ресурс находится в нужном состоянии на хотя бы один из целевых узлов, определенных в **NodeName** свойство.
- **WaitForSome**: Указывает **NodeCount** свойства в дополнение к **NodeName** свойство. Ресурс выполняется успешно, если он находится в нужном состоянии на минимальном количестве узлов (определяется свойством **NodeCount**), заданных свойством **NodeName**.

## <a name="syntax"></a>Синтаксис

**WaitForAll** и **WaitForAny** ресурсы используют тот же синтаксис. Замените \<ResourceType\> в примере ниже с помощью **WaitForAny** или **WaitForAll**.
Как и **DependsOn** ключевое слово, вам потребуется формата имени как «[ResourceType] ResourceName». Если ресурс относится к отдельным [конфигурации](configurations.md), включают **ConfigurationName** в форматируемую строку «[ResourceType] ResourceName:: [ConfigurationName]:: [ConfigurationName]». **NodeName** компьютером, или узел, на котором нужно подождать текущего ресурса.

```
<ResourceType> [string] #ResourceName
{
    ResourceName = [string]
    NodeName = [string]
    [ DependsOn = [string[]] ]
    [ PsDscRunAsCredential = [PSCredential]]
    [ RetryCount = [Uint32] ]
    [ RetryIntervalSec = [Uint64] ]
    [ ThrottleLimit = [Uint32]]
}
```

**WaitForSome** ресурсов имеет схожий синтаксис в приведенном выше примере, но добавляет **NodeCount** ключ. **NodeCount** указывает, сколько узлов, следует ожидать текущий ресурс.

```
WaitForSome [String] #ResourceName
{
    NodeCount = [UInt32]
    NodeName = [string[]]
    ResourceName = [string]
    [DependsOn = [string[]]]
    [PsDscRunAsCredential = [PSCredential]]
    [RetryCount = [UInt32]]
    [RetryIntervalSec = [UInt64]]
    [ThrottleLimit = [UInt32]]
}
```

Все **WaitForXXXX** совместно использовать следующие разделы синтаксиса.

|  Свойство |  Описание || RetryIntervalSec | Количество секунд перед повторной попыткой. Минимальное значение — 1. | | RetryCount | Максимальное число повторных попыток. | | ThrottleLimit | Количество одновременно подключаемых компьютеров. Значение по умолчанию — `New-CimSession` по умолчанию. | | DependsOn | Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса. Дополнительные сведения см. в разделе [DependsOn](resource-depends-on.md)|| PsDscRunAsCredential | См. в разделе [с помощью DSC с учетными данными пользователя](./runAsUser.md) |


## <a name="using-waitforxxxx-resources"></a>Использование ресурсов WaitForXXXX

Каждый **WaitForXXXX** ресурс ожидает указанные ресурсы для выполнения на указанном узле. Другие ресурсы в той же конфигурации можно затем *зависят от* **WaitForXXXX** ресурсов с помощью **DependsOn** ключ.

Например, в следующей конфигурации целевой узел ожидает завершения выполнения ресурса **xADDomain** на узле **MyDC** не более чем с 30 повторными попытками (с интервалом 15 секунд), прежде чем присоединиться к домену.

```powershell
Configuration JoinDomain
{
    Import-DscResource -Module xComputerManagement, xActiveDirectory

    Node myDC
    {
        WindowsFeature InstallAD
        {
            Ensure = 'Present'
            Name = 'AD-Domain-Services'
        }

        xADDomain NewDomain
        {
            DomainName = 'Contoso.com'
            DomainAdministratorCredential = (Get-Credential)
            SafemodeAdministratorPassword = (Get-Credential)
            DatabasePath = "C:\Windows\NTDS"
            LogPath = "C:\Windows\NTDS"
            SysvolPath = "C:\Windows\Sysvol"
        }
    }

    Node myDomainJoinedServer
    {
        WaitForAll DC
        {
            ResourceName      = '[xADDomain]NewDomain'
            NodeName          = 'MyDC'
            RetryIntervalSec  = 15
            RetryCount        = 30
        }

        xComputer JoinDomain
        {
            Name             = 'myPC'
            DomainName       = 'Contoso.com'
            Credential       = (Get-Credential)
            DependsOn        ='[WaitForAll]DC'
        }
    }
}
```

При компиляции конфигурации создаются два MOF-файлы. Применить оба MOF-файлы на целевые узлы с помощью [Start-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) командлета

>**Примечание**. По умолчанию WaitForXXX ресурсы одну попытку и далее завершаются со сбоем. Несмотря на то, что это не обязательно, обычно требуется указать **RetryCount** и **RetryIntervalSec**.

## <a name="see-also"></a>См. также

- [Конфигурации DSC](configurations.md)
- [Использовать зависимости ресурсов](resource-depends-on.md)
- [Ресурсы DSC](../resources/resources.md)
- [Настройка локального диспетчера конфигураций](../managing-nodes/metaConfig.md)
