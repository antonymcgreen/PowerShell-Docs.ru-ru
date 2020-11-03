---
external help file: PSModule-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PowerShellGet
ms.date: 02/27/2020
online version: https://docs.microsoft.com/powershell/module/powershellget/get-installedmodule?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-InstalledModule
ms.openlocfilehash: 9d4ec71a5f754b1fba090129d026d38bd32a8bc1
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228517"
---
# <span data-ttu-id="be6ff-103">Get-InstalledModule</span><span class="sxs-lookup"><span data-stu-id="be6ff-103">Get-InstalledModule</span></span>

## <span data-ttu-id="be6ff-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="be6ff-104">SYNOPSIS</span></span>
<span data-ttu-id="be6ff-105">Возвращает список модулей на компьютере, которые были установлены с помощью PowerShellGet.</span><span class="sxs-lookup"><span data-stu-id="be6ff-105">Gets a list of modules on the computer that were installed by PowerShellGet.</span></span>

## <span data-ttu-id="be6ff-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="be6ff-106">SYNTAX</span></span>

```
Get-InstalledModule [[-Name] <String[]>] [-MinimumVersion <String>] [-RequiredVersion <String>]
 [-MaximumVersion <String>] [-AllVersions] [-AllowPrerelease] [<CommonParameters>]
```

## <span data-ttu-id="be6ff-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="be6ff-107">DESCRIPTION</span></span>

<span data-ttu-id="be6ff-108">`Get-InstalledModule`Командлет получает модули PowerShell, установленные на компьютере с помощью PowerShellGet.</span><span class="sxs-lookup"><span data-stu-id="be6ff-108">The `Get-InstalledModule` cmdlet gets PowerShell modules that are installed on a computer using PowerShellGet.</span></span> <span data-ttu-id="be6ff-109">Чтобы просмотреть все модули, установленные в системе, используйте `Get-Module -ListAvailable` команду.</span><span class="sxs-lookup"><span data-stu-id="be6ff-109">To see all modules installed on the system, use the `Get-Module -ListAvailable` command.</span></span>

## <span data-ttu-id="be6ff-110">Примеры</span><span class="sxs-lookup"><span data-stu-id="be6ff-110">EXAMPLES</span></span>

### <span data-ttu-id="be6ff-111">Пример 1. получение всех установленных модулей</span><span class="sxs-lookup"><span data-stu-id="be6ff-111">Example 1: Get all installed modules</span></span>

```powershell
Get-InstalledModule
```

```Output
Version    Name                                Type       Repository     Description
-------    ----                                ----       ----------     -----------
2.0.0      PSGTEST-UploadMultipleVersionOfP... Module     GalleryINT     Module for DAC functionality
1.3.5      AzureAutomationDebug                Module     PSGallery      Module for debugging Azure Automation runbooks, emulating AA native cmdlets
1.0.1      AzureRM.Automation                  Module     PSGallery      Microsoft Azure PowerShell - Automation service cmdlets for Azure Resource Manager
```

<span data-ttu-id="be6ff-112">Эта команда возвращает все установленные модули.</span><span class="sxs-lookup"><span data-stu-id="be6ff-112">This command gets all installed modules.</span></span>

### <span data-ttu-id="be6ff-113">Пример 2. получение конкретных версий модуля</span><span class="sxs-lookup"><span data-stu-id="be6ff-113">Example 2: Get specific versions of a module</span></span>

```powershell
Get-InstalledModule -Name "AzureRM.Automation" -MinimumVersion 1.0 -MaximumVersion 2.0
```

```Output
Version    Name                                Type       Repository     Description
-------    ----                                ----       ----------     -----------
1.0.1      AzureRM.Automation                  Module     PSGallery      Microsoft Azure PowerShell - Automation service cmdlets for Azure Resource Manager
```

<span data-ttu-id="be6ff-114">Эта команда получает версии модуля AzureRM. Automation из версии 1,0 до версии 2,0.</span><span class="sxs-lookup"><span data-stu-id="be6ff-114">This command gets versions of the AzureRM.Automation module from version 1.0 through version 2.0.</span></span>

## <span data-ttu-id="be6ff-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="be6ff-115">PARAMETERS</span></span>

### <span data-ttu-id="be6ff-116">-AllowPrerelease</span><span class="sxs-lookup"><span data-stu-id="be6ff-116">-AllowPrerelease</span></span>

<span data-ttu-id="be6ff-117">Включает в модули результатов, помеченные как предварительные выпуски.</span><span class="sxs-lookup"><span data-stu-id="be6ff-117">Includes in the results modules marked as a prerelease.</span></span>

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

### <span data-ttu-id="be6ff-118">-AllVersions</span><span class="sxs-lookup"><span data-stu-id="be6ff-118">-AllVersions</span></span>

<span data-ttu-id="be6ff-119">Указывает, что необходимо получить все доступные версии модуля.</span><span class="sxs-lookup"><span data-stu-id="be6ff-119">Indicates that you want to get all available versions of a module.</span></span>
<span data-ttu-id="be6ff-120">Параметр **AllVersions** нельзя использовать с параметрами **MinimumVersion** , **MaximumVersion** или **RequiredVersion** .</span><span class="sxs-lookup"><span data-stu-id="be6ff-120">You cannot use the **AllVersions** parameter with the **MinimumVersion** , **MaximumVersion** , or **RequiredVersion** parameters.</span></span>

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

### <span data-ttu-id="be6ff-121">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="be6ff-121">-MaximumVersion</span></span>

<span data-ttu-id="be6ff-122">Указывает максимальную или самую новую версию модуля для получения.</span><span class="sxs-lookup"><span data-stu-id="be6ff-122">Specifies the maximum, or newest, version of a module to get.</span></span> <span data-ttu-id="be6ff-123">Параметры **MaximumVersion** и **RequiredVersion** являются взаимоисключающими. в одной команде нельзя использовать оба параметра.</span><span class="sxs-lookup"><span data-stu-id="be6ff-123">The **MaximumVersion** and **RequiredVersion** parameters are mutually exclusive; you cannot use both parameters in the same command.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="be6ff-124">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="be6ff-124">-MinimumVersion</span></span>

<span data-ttu-id="be6ff-125">Указывает минимальную версию одного модуля для получения.</span><span class="sxs-lookup"><span data-stu-id="be6ff-125">Specifies the minimum version of a single module to get.</span></span> <span data-ttu-id="be6ff-126">Параметры **MinimumVersion** и **RequiredVersion** являются взаимоисключающими. в одной команде нельзя использовать оба параметра.</span><span class="sxs-lookup"><span data-stu-id="be6ff-126">The **MinimumVersion** and **RequiredVersion** parameters are mutually exclusive; you cannot use both parameters in the same command.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="be6ff-127">-Name</span><span class="sxs-lookup"><span data-stu-id="be6ff-127">-Name</span></span>

<span data-ttu-id="be6ff-128">Указывает массив имен модулей для получения.</span><span class="sxs-lookup"><span data-stu-id="be6ff-128">Specifies an array of names of modules to get.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="be6ff-129">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="be6ff-129">-RequiredVersion</span></span>

<span data-ttu-id="be6ff-130">Указывает точную версию модуля для получения.</span><span class="sxs-lookup"><span data-stu-id="be6ff-130">Specifies the exact version of a module to get.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="be6ff-131">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="be6ff-131">CommonParameters</span></span>

<span data-ttu-id="be6ff-132">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="be6ff-132">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="be6ff-133">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="be6ff-133">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="be6ff-134">Входные данные</span><span class="sxs-lookup"><span data-stu-id="be6ff-134">INPUTS</span></span>

### <span data-ttu-id="be6ff-135">System.String[]</span><span class="sxs-lookup"><span data-stu-id="be6ff-135">System.String[]</span></span>

### <span data-ttu-id="be6ff-136">System.String</span><span class="sxs-lookup"><span data-stu-id="be6ff-136">System.String</span></span>

## <span data-ttu-id="be6ff-137">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="be6ff-137">OUTPUTS</span></span>

### <span data-ttu-id="be6ff-138">System. Management. Automation. PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="be6ff-138">System.Management.Automation.PSCustomObject</span></span>

## <span data-ttu-id="be6ff-139">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="be6ff-139">NOTES</span></span>

## <span data-ttu-id="be6ff-140">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="be6ff-140">RELATED LINKS</span></span>

