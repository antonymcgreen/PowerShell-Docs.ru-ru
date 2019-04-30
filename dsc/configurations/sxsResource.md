---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Импорт определенной версии установленного ресурса
ms.openlocfilehash: 5ed81e11aa67eb6590d958647f48a33b1b5f1c0e
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62080006"
---
# <a name="import-a-specific-version-of-an-installed-resource"></a>Импорт определенной версии установленного ресурса

> Область применения. Windows PowerShell 5.0

В PowerShell 5.0 отдельные версии ресурсов DSC можно устанавливать на компьютере параллельно. Модуль ресурсов может хранить отдельные версии ресурса в папке с именем версии.

## <a name="installing-separate-resource-versions-side-by-side"></a>Параллельная установка отдельных версий ресурса

Параметры **MinimumVersion**, **MaximumVersion** и **RequiredVersion** командлета [Install-Module](/powershell/module/PowershellGet/Install-Module) можно использовать, чтобы указать версию модуля для установки. Вызов командлета **Install-Module** без указания версии устанавливает последнюю версию.

Например, существует несколько версий модуля **xFailOverCluster**, каждая из которых содержит ресурс **xCluster**. Вызов командлета **Install-Module** без указания номера версии устанавливает последнюю версию модуля.

```powershell
PS> Install-Module xFailOverCluster
PS> Get-DscResource xCluster
```

```output
ImplementedAs   Name                      ModuleName                     Version    Properties
-------------   ----                      ----------                     -------    ----------
PowerShell      xCluster                  xFailOverCluster               1.2.0.0    {DomainAdministratorCredential, ...
```

Чтобы установить определенную версию модуля, укажите **RequiredVersion** 1.1.0.0. При этом указанная версия устанавливается параллельно с установленной версией.

```powershell
PS> Install-Module xFailOverCluster -RequiredVersion 1.1
```

Теперь при использовании `Get-DSCResource` отображаются обе установленные версии модуля.

```powershell
PS> Get-DscResource xCluster
```

```output
ImplementedAs   Name                      ModuleName                     Version    Properties
-------------   ----                      ----------                     -------    ----------
PowerShell      xCluster                  xFailOverCluster               1.1        {DomainAdministratorCredential, Name, ...
PowerShell      xCluster                  xFailOverCluster               1.2.0.0    {DomainAdministratorCredential, Name, ...
```

## <a name="specifying-a-resource-version-in-a-configuration"></a>Указание версии ресурса в конфигурации

Если на компьютере установлены отдельные версии ресурсов, необходимо указать версию нужного ресурса при его использовании в конфигурации. Это делается путем указания параметра **ModuleVersion** ключевого слова **Import-DscResource**. Если не указать версию модуля ресурсов для ресурса, имеющего несколько установленных версий, конфигурация породит ошибку.

В конфигурации ниже показано, как указать версию ресурса для вызова:

```powershell
configuration VersionTest
{
    Import-DscResource -ModuleName xFailOverCluster -ModuleVersion 1.1

    Node 'localhost'
    {
       xCluster ClusterTest
       {
            Name                          = 'TestCluster'
            StaticIPAddress               = '10.0.0.3'
            DomainAdministratorCredential = Get-Credential
        }
     }
}
```

>Примечание. Параметр ModuleVersion ключевого слова Import-DscResource недоступен в PowerShell 4.0. В PowerShell 4.0 версию модуля можно задать, передав объект спецификации модуля в параметр ModuleName ключевого слова Import-DscResource. Объект спецификации модуля представляет собой хэш-таблицу, содержащую ключи ModuleName и RequiredVersion. Например:

```powershell
configuration VersionTest
{
    Import-DscResource -ModuleName (@{ModuleName='xFailOverCluster'; RequiredVersion='1.1'} )

    Node 'localhost'
    {
       xCluster ClusterTest
       {
            Name                          = 'TestCluster'
            StaticIPAddress               = '10.0.0.3'
            DomainAdministratorCredential = Get-Credential
        }
     }
}
```

Этот способ также будет работать в PowerShell 5.0, однако рекомендуется использовать параметр **ModuleVersion**.

## <a name="see-also"></a>См. также:

- [Конфигурации DSC](configurations.md)
- [Ресурсы DSC](../resources/resources.md)
