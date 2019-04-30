---
ms.date: 12/12/2018
keywords: dsc,powershell,конфигурация,установка
title: Указание межузловых зависимостей
ms.openlocfilehash: 1bdfbd9f8a94809d6bf410eff525e1c877fb6aad
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62080209"
---
# <a name="specifying-cross-node-dependencies"></a>Указание межузловых зависимостей

> Область применения. Windows PowerShell 5.0

DSC предоставляет специальные ресурсы, **WaitForAll**, **WaitForAny** и **WaitForSome**, которые можно использовать в конфигурациях для указания зависимостей от конфигураций на других узлах. Поведение этих ресурсов описано ниже.

- **WaitForAll**. Успешное выполнение, если указанный ресурс находится в нужном состоянии на всех целевых узлах, определенных в свойстве **NodeName**.
- **WaitForAny**. Успешное выполнение, если указанный ресурс находится в нужном состоянии как минимум на одном из целевых узлов, определенных в свойстве **NodeName**.
- **WaitForSome**. Указывает свойство **NodeCount** в дополнение к свойству **NodeName**. Ресурс выполняется успешно, если он находится в нужном состоянии на минимальном количестве узлов (определяется свойством **NodeCount**), заданных свойством **NodeName**.

## <a name="syntax"></a>Синтаксис

Ресурсы **WaitForAll** и **WaitForAny** используют одинаковый синтаксис. Замените \<ResourceType\> в примере ниже на **WaitForAny** или **WaitForAll**.
Необходимо отформатировать имя [ResourceType]ResourceName подобно ключевому слову **DependsOn**. Если ресурс принадлежит отдельной [конфигурации](configurations.md), включите **ConfigurationName** в отформатированную строку [ResourceType]ResourceName::[ConfigurationName]::[ConfigurationName]. **NodeName** является компьютером или узлом, на котором ожидается текущий ресурс.

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

Ресурс **WaitForSome** имеет подобный приведенному выше примеру синтаксис, но содержит ключ **NodeCount**. Ключ **NodeCount** указывает количество узлов, на которых следует ожидать текущий ресурс.

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

Все ресурсы **WaitForXXXX** используют следующие разделы синтаксиса.

| Свойство | Описание | | RetryIntervalSec| Количество секунд перед повторной попыткой. Минимальное значение — 1.| | RetryCount| Максимальное число повторных попыток.| | ThrottleLimit| Количество одновременно подключаемых компьютеров. Значение по умолчанию — `New-CimSession`.| | DependsOn | Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса. Дополнительные сведения см. в статье [Использование зависимостей ресурсов с DependsOn](resource-depends-on.md)| | PsDscRunAsCredential | См. в статье [Использование учетных данных с ресурсами DSC](./runAsUser.md) |


## <a name="using-waitforxxxx-resources"></a>Использование ресурсов WaitForXXXX

Каждый ресурс **WaitForXXXX** ожидает выполнения указанных ресурсов на указанном узле. После этого другие ресурсы в той же конфигурации могут *зависеть от* ресурса **WaitForXXXX** с помощью ключа **DependsOn**.

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

При компиляции конфигурации создаются два MOF-файла. Примените их на целевые узлы с помощью командлета [Start-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration)

>**Примечание**. По умолчанию ресурсы WaitForXXX выполняют одну попытку, а затем выдают ошибку. Хотя это необязательно, обычно требуется указать **RetryCount** и **RetryIntervalSec**.

## <a name="see-also"></a>См. также

- [Конфигурации DSC](configurations.md)
- [Использование зависимостей ресурсов с DependsOn](resource-depends-on.md)
- [Ресурсы DSC](../resources/resources.md)
- [Настройка локального диспетчера конфигураций](../managing-nodes/metaConfig.md)
