---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Импорт определенной версии установленного ресурса
ms.openlocfilehash: 5ed81e11aa67eb6590d958647f48a33b1b5f1c0e
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "71953991"
---
# <a name="import-a-specific-version-of-an-installed-resource"></a><span data-ttu-id="570ea-103">Импорт определенной версии установленного ресурса</span><span class="sxs-lookup"><span data-stu-id="570ea-103">Import a specific version of an installed resource</span></span>

> <span data-ttu-id="570ea-104">Область применения: Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="570ea-104">Applies To: Windows PowerShell 5.0</span></span>

<span data-ttu-id="570ea-105">В PowerShell 5.0 отдельные версии ресурсов DSC можно устанавливать на компьютере параллельно.</span><span class="sxs-lookup"><span data-stu-id="570ea-105">In PowerShell 5.0, separate versions of DSC resources can be installed on a computer side by side.</span></span> <span data-ttu-id="570ea-106">Модуль ресурсов может хранить отдельные версии ресурса в папке с именем версии.</span><span class="sxs-lookup"><span data-stu-id="570ea-106">A resource module can store separate versions of a resource in version named folders.</span></span>

## <a name="installing-separate-resource-versions-side-by-side"></a><span data-ttu-id="570ea-107">Параллельная установка отдельных версий ресурса</span><span class="sxs-lookup"><span data-stu-id="570ea-107">Installing separate resource versions side by side</span></span>

<span data-ttu-id="570ea-108">Параметры **MinimumVersion**, **MaximumVersion** и **RequiredVersion** командлета [Install-Module](/powershell/module/PowershellGet/Install-Module) можно использовать, чтобы указать версию модуля для установки.</span><span class="sxs-lookup"><span data-stu-id="570ea-108">You can use the **MinimumVersion**, **MaximumVersion**, and **RequiredVersion** parameters of the [Install-Module](/powershell/module/PowershellGet/Install-Module) cmdlet to specify which version of a module to install.</span></span> <span data-ttu-id="570ea-109">Вызов командлета **Install-Module** без указания версии устанавливает последнюю версию.</span><span class="sxs-lookup"><span data-stu-id="570ea-109">Calling **Install-Module** without specifying a version installs the most recent version.</span></span>

<span data-ttu-id="570ea-110">Например, существует несколько версий модуля **xFailOverCluster**, каждая из которых содержит ресурс **xCluster**.</span><span class="sxs-lookup"><span data-stu-id="570ea-110">For example, there are multiple versions of the **xFailOverCluster** module, each of which contains an **xCluster** resource.</span></span> <span data-ttu-id="570ea-111">Вызов командлета **Install-Module** без указания номера версии устанавливает последнюю версию модуля.</span><span class="sxs-lookup"><span data-stu-id="570ea-111">Calling **Install-Module** without specifying the version number installs the most recent version of the module.</span></span>

```powershell
PS> Install-Module xFailOverCluster
PS> Get-DscResource xCluster
```

```output
ImplementedAs   Name                      ModuleName                     Version    Properties
-------------   ----                      ----------                     -------    ----------
PowerShell      xCluster                  xFailOverCluster               1.2.0.0    {DomainAdministratorCredential, ...
```

<span data-ttu-id="570ea-112">Чтобы установить определенную версию модуля, укажите **RequiredVersion** 1.1.0.0.</span><span class="sxs-lookup"><span data-stu-id="570ea-112">To install a specific version of a module, specify a **RequiredVersion** of 1.1.0.0.</span></span> <span data-ttu-id="570ea-113">При этом указанная версия устанавливается параллельно с установленной версией.</span><span class="sxs-lookup"><span data-stu-id="570ea-113">This installs the specified version side by side with the installed version.</span></span>

```powershell
PS> Install-Module xFailOverCluster -RequiredVersion 1.1
```

<span data-ttu-id="570ea-114">Теперь при использовании `Get-DSCResource` отображаются обе установленные версии модуля.</span><span class="sxs-lookup"><span data-stu-id="570ea-114">Now, you see both version of the module listed when you use `Get-DSCResource`.</span></span>

```powershell
PS> Get-DscResource xCluster
```

```output
ImplementedAs   Name                      ModuleName                     Version    Properties
-------------   ----                      ----------                     -------    ----------
PowerShell      xCluster                  xFailOverCluster               1.1        {DomainAdministratorCredential, Name, ...
PowerShell      xCluster                  xFailOverCluster               1.2.0.0    {DomainAdministratorCredential, Name, ...
```

## <a name="specifying-a-resource-version-in-a-configuration"></a><span data-ttu-id="570ea-115">Указание версии ресурса в конфигурации</span><span class="sxs-lookup"><span data-stu-id="570ea-115">Specifying a resource version in a configuration</span></span>

<span data-ttu-id="570ea-116">Если на компьютере установлены отдельные версии ресурсов, необходимо указать версию нужного ресурса при его использовании в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="570ea-116">If you have separate resource versions installed on a computer, you must specify the version of that resource when you use it in a configuration.</span></span> <span data-ttu-id="570ea-117">Это делается путем указания параметра **ModuleVersion** ключевого слова **Import-DscResource**.</span><span class="sxs-lookup"><span data-stu-id="570ea-117">You do this by specifying the **ModuleVersion** parameter of the **Import-DscResource** keyword.</span></span> <span data-ttu-id="570ea-118">Если не указать версию модуля ресурсов для ресурса, имеющего несколько установленных версий, конфигурация породит ошибку.</span><span class="sxs-lookup"><span data-stu-id="570ea-118">If you fail to specify the version of a resource module of a resource of which you have more than one version installed, the configuration generates an error.</span></span>

<span data-ttu-id="570ea-119">В конфигурации ниже показано, как указать версию ресурса для вызова:</span><span class="sxs-lookup"><span data-stu-id="570ea-119">The following configuration shows how to specify the version of the resource to call:</span></span>

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

><span data-ttu-id="570ea-120">Примечание. Параметр ModuleVersion ключевого слова Import-DscResource недоступен в PowerShell 4.0.</span><span class="sxs-lookup"><span data-stu-id="570ea-120">Note: The ModuleVersion parameter of Import-DscResource is not available in PowerShell 4.0.</span></span> <span data-ttu-id="570ea-121">В PowerShell 4.0 версию модуля можно задать, передав объект спецификации модуля в параметр ModuleName ключевого слова Import-DscResource.</span><span class="sxs-lookup"><span data-stu-id="570ea-121">In PowerShell 4.0, you can specify a module version by passing a module specification object to the ModuleName parameter of Import-DscResource.</span></span> <span data-ttu-id="570ea-122">Объект спецификации модуля представляет собой хэш-таблицу, содержащую ключи ModuleName и RequiredVersion.</span><span class="sxs-lookup"><span data-stu-id="570ea-122">A module specification object is a hash table that contains ModuleName and RequiredVersion  keys.</span></span> <span data-ttu-id="570ea-123">Например:</span><span class="sxs-lookup"><span data-stu-id="570ea-123">For example:</span></span>

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

<span data-ttu-id="570ea-124">Этот способ также будет работать в PowerShell 5.0, однако рекомендуется использовать параметр **ModuleVersion**.</span><span class="sxs-lookup"><span data-stu-id="570ea-124">This will also work in PowerShell 5.0, but it is recommended that you use the **ModuleVersion** parameter.</span></span>

## <a name="see-also"></a><span data-ttu-id="570ea-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="570ea-125">See also</span></span>

- [<span data-ttu-id="570ea-126">Конфигурации DSC</span><span class="sxs-lookup"><span data-stu-id="570ea-126">DSC Configurations</span></span>](configurations.md)
- [<span data-ttu-id="570ea-127">Ресурсы DSC</span><span class="sxs-lookup"><span data-stu-id="570ea-127">DSC Resources</span></span>](../resources/resources.md)
