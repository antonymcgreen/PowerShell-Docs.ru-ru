---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Импорт определенной версии установленного ресурса
description: В этой статье описывается, как установить и импортировать в конфигурации определенные версии модулей ресурсов.
ms.openlocfilehash: bb7b3273a5a3fed94fecd90dd3ea1e623fbc332b
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92645054"
---
# <a name="import-a-specific-version-of-an-installed-resource"></a><span data-ttu-id="8c216-104">Импорт определенной версии установленного ресурса</span><span class="sxs-lookup"><span data-stu-id="8c216-104">Import a specific version of an installed resource</span></span>

> <span data-ttu-id="8c216-105">Область применения: Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="8c216-105">Applies To: Windows PowerShell 5.0</span></span>

<span data-ttu-id="8c216-106">В PowerShell 5.0 отдельные версии ресурсов DSC можно устанавливать на компьютере параллельно.</span><span class="sxs-lookup"><span data-stu-id="8c216-106">In PowerShell 5.0, separate versions of DSC resources can be installed on a computer side by side.</span></span> <span data-ttu-id="8c216-107">Модуль ресурсов может хранить отдельные версии ресурса в папке с именем версии.</span><span class="sxs-lookup"><span data-stu-id="8c216-107">A resource module can store separate versions of a resource in version named folders.</span></span>

## <a name="installing-separate-resource-versions-side-by-side"></a><span data-ttu-id="8c216-108">Параллельная установка отдельных версий ресурса</span><span class="sxs-lookup"><span data-stu-id="8c216-108">Installing separate resource versions side by side</span></span>

<span data-ttu-id="8c216-109">Параметры **MinimumVersion** , **MaximumVersion** и **RequiredVersion** командлета [Install-Module](/powershell/module/PowershellGet/Install-Module) можно использовать, чтобы указать версию модуля для установки.</span><span class="sxs-lookup"><span data-stu-id="8c216-109">You can use the **MinimumVersion** , **MaximumVersion** , and **RequiredVersion** parameters of the [Install-Module](/powershell/module/PowershellGet/Install-Module) cmdlet to specify which version of a module to install.</span></span> <span data-ttu-id="8c216-110">Вызов командлета **Install-Module** без указания версии устанавливает последнюю версию.</span><span class="sxs-lookup"><span data-stu-id="8c216-110">Calling **Install-Module** without specifying a version installs the most recent version.</span></span>

<span data-ttu-id="8c216-111">Например, существует несколько версий модуля **xFailOverCluster** , каждая из которых содержит ресурс **xCluster**.</span><span class="sxs-lookup"><span data-stu-id="8c216-111">For example, there are multiple versions of the **xFailOverCluster** module, each of which contains an **xCluster** resource.</span></span> <span data-ttu-id="8c216-112">Вызов командлета **Install-Module** без указания номера версии устанавливает последнюю версию модуля.</span><span class="sxs-lookup"><span data-stu-id="8c216-112">Calling **Install-Module** without specifying the version number installs the most recent version of the module.</span></span>

```powershell
PS> Install-Module xFailOverCluster
PS> Get-DscResource xCluster
```

```Output
ImplementedAs   Name          ModuleName           Version    Properties
-------------   ----          ----------           -------    ----------
PowerShell      xCluster      xFailOverCluster     1.2.0.0    {DomainAdministratorCredential, ...
```

<span data-ttu-id="8c216-113">Чтобы установить определенную версию модуля, укажите **RequiredVersion** 1.1.0.0.</span><span class="sxs-lookup"><span data-stu-id="8c216-113">To install a specific version of a module, specify a **RequiredVersion** of 1.1.0.0.</span></span> <span data-ttu-id="8c216-114">При этом указанная версия устанавливается параллельно с установленной версией.</span><span class="sxs-lookup"><span data-stu-id="8c216-114">This installs the specified version side by side with the installed version.</span></span>

```powershell
PS> Install-Module xFailOverCluster -RequiredVersion 1.1
```

<span data-ttu-id="8c216-115">Теперь при использовании `Get-DSCResource` отображаются обе установленные версии модуля.</span><span class="sxs-lookup"><span data-stu-id="8c216-115">Now, you see both version of the module listed when you use `Get-DSCResource`.</span></span>

```powershell
PS> Get-DscResource xCluster
```

```Output
ImplementedAs   Name          ModuleName            Version    Properties
-------------   ----          ----------            -------    ----------
PowerShell      xCluster      xFailOverCluster      1.1        {DomainAdministratorCredential, Name, ...
PowerShell      xCluster      xFailOverCluster      1.2.0.0    {DomainAdministratorCredential, Name, ...
```

## <a name="specifying-a-resource-version-in-a-configuration"></a><span data-ttu-id="8c216-116">Указание версии ресурса в конфигурации</span><span class="sxs-lookup"><span data-stu-id="8c216-116">Specifying a resource version in a configuration</span></span>

<span data-ttu-id="8c216-117">Если на компьютере установлены отдельные версии ресурсов, необходимо указать версию нужного ресурса при его использовании в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="8c216-117">If you have separate resource versions installed on a computer, you must specify the version of that resource when you use it in a configuration.</span></span> <span data-ttu-id="8c216-118">Это делается путем указания параметра **ModuleVersion** ключевого слова **Import-DscResource**.</span><span class="sxs-lookup"><span data-stu-id="8c216-118">You do this by specifying the **ModuleVersion** parameter of the **Import-DscResource** keyword.</span></span> <span data-ttu-id="8c216-119">Если не указать версию модуля ресурсов для ресурса, имеющего несколько установленных версий, конфигурация породит ошибку.</span><span class="sxs-lookup"><span data-stu-id="8c216-119">If you fail to specify the version of a resource module of a resource of which you have more than one version installed, the configuration generates an error.</span></span>

<span data-ttu-id="8c216-120">В конфигурации ниже показано, как указать версию ресурса для вызова:</span><span class="sxs-lookup"><span data-stu-id="8c216-120">The following configuration shows how to specify the version of the resource to call:</span></span>

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

<span data-ttu-id="8c216-121">Параметр ModuleVersion ключевого слова Import-DscResource недоступен в PowerShell 4.0.</span><span class="sxs-lookup"><span data-stu-id="8c216-121">The ModuleVersion parameter of Import-DscResource is not available in PowerShell 4.0.</span></span> <span data-ttu-id="8c216-122">В PowerShell 4.0 версию модуля можно задать, передав объект спецификации модуля в параметр ModuleName ключевого слова Import-DscResource.</span><span class="sxs-lookup"><span data-stu-id="8c216-122">In PowerShell 4.0, you can specify a module version by passing a module specification object to the ModuleName parameter of Import-DscResource.</span></span> <span data-ttu-id="8c216-123">Объект спецификации модуля представляет собой хэш-таблицу, содержащую ключи ModuleName и RequiredVersion.</span><span class="sxs-lookup"><span data-stu-id="8c216-123">A module specification object is a hash table that contains ModuleName and RequiredVersion keys.</span></span> <span data-ttu-id="8c216-124">Пример:</span><span class="sxs-lookup"><span data-stu-id="8c216-124">For example:</span></span>

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

<span data-ttu-id="8c216-125">Этот способ также будет работать в PowerShell 5.0, однако рекомендуется использовать параметр **ModuleVersion**.</span><span class="sxs-lookup"><span data-stu-id="8c216-125">This will also work in PowerShell 5.0, but it is recommended that you use the **ModuleVersion** parameter.</span></span>

## <a name="see-also"></a><span data-ttu-id="8c216-126">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="8c216-126">See also</span></span>

- [<span data-ttu-id="8c216-127">Конфигурации DSC</span><span class="sxs-lookup"><span data-stu-id="8c216-127">DSC Configurations</span></span>](configurations.md)
- [<span data-ttu-id="8c216-128">Ресурсы DSC</span><span class="sxs-lookup"><span data-stu-id="8c216-128">DSC Resources</span></span>](../resources/resources.md)
