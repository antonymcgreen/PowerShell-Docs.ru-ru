---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PackageManagement
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/packagemanagement/import-packageprovider?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-PackageProvider
ms.openlocfilehash: 1ff00ea134c442e2bdb926d12ebbfa02098d6104
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227306"
---
# <span data-ttu-id="2151e-103">Import-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="2151e-103">Import-PackageProvider</span></span>

## <span data-ttu-id="2151e-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="2151e-104">SYNOPSIS</span></span>
<span data-ttu-id="2151e-105">Добавляет поставщики пакетов Управление пакетами в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="2151e-105">Adds Package Management package providers to the current session.</span></span>

## <span data-ttu-id="2151e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2151e-106">SYNTAX</span></span>

```
Import-PackageProvider [-Name] <String[]> [-RequiredVersion <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-Force] [-ForceBootstrap] [<CommonParameters>]
```

## <span data-ttu-id="2151e-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2151e-107">DESCRIPTION</span></span>

<span data-ttu-id="2151e-108">`Import-PackageProvider`Командлет добавляет один или несколько поставщиков пакетов в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="2151e-108">The `Import-PackageProvider` cmdlet adds one or more package providers to the current session.</span></span>
<span data-ttu-id="2151e-109">Импортируемый поставщик должен быть установлен на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="2151e-109">The provider that you import must be installed on the local computer.</span></span>

<span data-ttu-id="2151e-110">Чтобы получить список доступных поставщиков, выполните команду `Get-PackageProvider -ListAvailable` .</span><span class="sxs-lookup"><span data-stu-id="2151e-110">To get a list of available providers, run `Get-PackageProvider -ListAvailable`.</span></span>
<span data-ttu-id="2151e-111">Обратите внимание, что имя поставщика пакета может отличаться от имени модуля.</span><span class="sxs-lookup"><span data-stu-id="2151e-111">Note that a package provider name can be different from its module name.</span></span>

<span data-ttu-id="2151e-112">Из соображений безопасности **PackageManagement** требует, чтобы поставщики на основе C# содержали `provider.manifest` .</span><span class="sxs-lookup"><span data-stu-id="2151e-112">Due to security reasons, **PackageManagement** requires C#-based providers to contain a `provider.manifest`.</span></span> <span data-ttu-id="2151e-113">Дополнительные сведения о создании поставщика с `provider.manifest` внедренным см. в разделе `.csproj` файлы проекта в [https://github.com/oneget/oneget](https://github.com/oneget/oneget) .</span><span class="sxs-lookup"><span data-stu-id="2151e-113">For more information on how to build a provider with `provider.manifest` injected, see the `.csproj` project files on [https://github.com/oneget/oneget](https://github.com/oneget/oneget).</span></span>

## <span data-ttu-id="2151e-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="2151e-114">EXAMPLES</span></span>

### <span data-ttu-id="2151e-115">Пример 1. Импорт поставщика пакетов с локального компьютера</span><span class="sxs-lookup"><span data-stu-id="2151e-115">Example 1: Import a package provider from the local computer</span></span>

```powershell
PS C:\> Import-PackageProvider -Name "Nuget"
```

<span data-ttu-id="2151e-116">Эта команда импортирует поставщик NuGet после установки на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="2151e-116">This command imports the Nuget provider after it has been installed on the local computer.</span></span>

### <span data-ttu-id="2151e-117">Пример 2. импорт определенной версии поставщика пакетов</span><span class="sxs-lookup"><span data-stu-id="2151e-117">Example 2: Import a specific version of a package provider</span></span>

```powershell
PS C:\> Find-PackageProvider -Name "Nuget" -AllVersions
Install-PackageProvider -Name "Nuget" -RequiredVersion "2.8.5.201" -Force
Get-PackageProvider -ListAvailable
Import-PackageProvider -Name "Nuget" -RequiredVersion "2.8.5.201" -Verbose
```

<span data-ttu-id="2151e-118">Эта команда находит, устанавливает и импортирует определенную версию поставщика пакетов NuGet.</span><span class="sxs-lookup"><span data-stu-id="2151e-118">This command finds, installs, and imports a specific version of the Nuget package provider.</span></span>

## <span data-ttu-id="2151e-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2151e-119">PARAMETERS</span></span>

### <span data-ttu-id="2151e-120">-Force</span><span class="sxs-lookup"><span data-stu-id="2151e-120">-Force</span></span>

<span data-ttu-id="2151e-121">Принудительное выполнение команды без запроса на подтверждение пользователем.</span><span class="sxs-lookup"><span data-stu-id="2151e-121">Forces the command to run without asking for user confirmation.</span></span>
<span data-ttu-id="2151e-122">Повторно импортирует поставщик пакетов.</span><span class="sxs-lookup"><span data-stu-id="2151e-122">Re-imports a package provider.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2151e-123">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="2151e-123">-ForceBootstrap</span></span>

<span data-ttu-id="2151e-124">Указывает, что этот командлет заставляет систему управления пакетами автоматически установить поставщик пакетов.</span><span class="sxs-lookup"><span data-stu-id="2151e-124">Indicates that this cmdlet forces Package Management to automatically install the package provider.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2151e-125">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="2151e-125">-MaximumVersion</span></span>

<span data-ttu-id="2151e-126">Указывает максимально допустимую версию поставщика пакета, который требуется импортировать.</span><span class="sxs-lookup"><span data-stu-id="2151e-126">Specifies the maximum allowed version of the package provider that you want to import.</span></span> <span data-ttu-id="2151e-127">Если этот параметр не добавлен, `Import-PackageProvider` импортирует самую новую доступную версию поставщика.</span><span class="sxs-lookup"><span data-stu-id="2151e-127">If you do not add this parameter, `Import-PackageProvider` imports the highest available version of the provider.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2151e-128">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="2151e-128">-MinimumVersion</span></span>

<span data-ttu-id="2151e-129">Указывает минимально допустимую версию поставщика пакета, который требуется импортировать.</span><span class="sxs-lookup"><span data-stu-id="2151e-129">Specifies the minimum allowed version of the package provider that you want to import.</span></span> <span data-ttu-id="2151e-130">Если этот параметр не добавлен, `Import-PackageProvider` импортирует самую новую доступную версию пакета, которая также соответствует любой максимальной версии, указанной с помощью параметра *MaximumVersion* .</span><span class="sxs-lookup"><span data-stu-id="2151e-130">If you do not add this parameter, `Import-PackageProvider` imports the highest available version of the package that also satisfies any maximum version that is specified using the *MaximumVersion* parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2151e-131">-Name</span><span class="sxs-lookup"><span data-stu-id="2151e-131">-Name</span></span>

<span data-ttu-id="2151e-132">Указывает одно или несколько имен поставщиков пакетов.</span><span class="sxs-lookup"><span data-stu-id="2151e-132">Specifies one or more package provider names.</span></span> <span data-ttu-id="2151e-133">Использовать подстановочные знаки запрещено.</span><span class="sxs-lookup"><span data-stu-id="2151e-133">Wildcards are not permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="2151e-134">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="2151e-134">-RequiredVersion</span></span>

<span data-ttu-id="2151e-135">Указывает точную версию поставщика пакета, который требуется импортировать.</span><span class="sxs-lookup"><span data-stu-id="2151e-135">Specifies the exact version of the package provider that you want to import.</span></span> <span data-ttu-id="2151e-136">Если этот параметр не добавлен, `Import-PackageProvider` импортирует самую новую доступную версию поставщика, которая также соответствует максимальной версии, указанной в параметре **MaximumVersion** .</span><span class="sxs-lookup"><span data-stu-id="2151e-136">If you do not add this parameter, `Import-PackageProvider` imports the highest available version of the provider that also satisfies any maximum version specified using the **MaximumVersion** parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2151e-137">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="2151e-137">CommonParameters</span></span>

<span data-ttu-id="2151e-138">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="2151e-138">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2151e-139">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="2151e-139">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2151e-140">Входные данные</span><span class="sxs-lookup"><span data-stu-id="2151e-140">INPUTS</span></span>

### <span data-ttu-id="2151e-141">Microsoft. PackageManagement. Реализация. PackageProvider</span><span class="sxs-lookup"><span data-stu-id="2151e-141">Microsoft.PackageManagement.Implementation.PackageProvider</span></span>

<span data-ttu-id="2151e-142">Объект **PackageProvider** , возвращаемый, можно передать `Get-PackageProvider` в `Import-PackageProvider` .</span><span class="sxs-lookup"><span data-stu-id="2151e-142">You can pipe a **PackageProvider** object returned by `Get-PackageProvider` into `Import-PackageProvider`.</span></span>

## <span data-ttu-id="2151e-143">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="2151e-143">OUTPUTS</span></span>

## <span data-ttu-id="2151e-144">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="2151e-144">NOTES</span></span>

## <span data-ttu-id="2151e-145">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="2151e-145">RELATED LINKS</span></span>

[<span data-ttu-id="2151e-146">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="2151e-146">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="2151e-147">Unregister-PackageSource</span><span class="sxs-lookup"><span data-stu-id="2151e-147">Unregister-PackageSource</span></span>](Unregister-PackageSource.md)

[<span data-ttu-id="2151e-148">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="2151e-148">Get-PackageSource</span></span>](Get-PackageSource.md)

[<span data-ttu-id="2151e-149">Register-PackageSource</span><span class="sxs-lookup"><span data-stu-id="2151e-149">Register-PackageSource</span></span>](Register-PackageSource.md)

[<span data-ttu-id="2151e-150">Get-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="2151e-150">Get-PackageProvider</span></span>](Get-PackageProvider.md)
