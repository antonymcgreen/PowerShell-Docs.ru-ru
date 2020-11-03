---
external help file: PSModule-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PowerShellGet
ms.date: 02/27/2020
online version: https://docs.microsoft.com/powershell/module/powershellget/get-installedmodule?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-InstalledModule
ms.openlocfilehash: e894e2f71e0a76badd05b86b42903d49aab4af0b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227266"
---
# <span data-ttu-id="e2531-103">Get-InstalledModule</span><span class="sxs-lookup"><span data-stu-id="e2531-103">Get-InstalledModule</span></span>

## <span data-ttu-id="e2531-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="e2531-104">SYNOPSIS</span></span>
<span data-ttu-id="e2531-105">Возвращает список модулей на компьютере, которые были установлены с помощью PowerShellGet.</span><span class="sxs-lookup"><span data-stu-id="e2531-105">Gets a list of modules on the computer that were installed by PowerShellGet.</span></span>

## <span data-ttu-id="e2531-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e2531-106">SYNTAX</span></span>

```
Get-InstalledModule [[-Name] <String[]>] [-MinimumVersion <String>] [-RequiredVersion <String>]
 [-MaximumVersion <String>] [-AllVersions] [-AllowPrerelease] [<CommonParameters>]
```

## <span data-ttu-id="e2531-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e2531-107">DESCRIPTION</span></span>

<span data-ttu-id="e2531-108">`Get-InstalledModule`Командлет получает модули PowerShell, установленные на компьютере с помощью PowerShellGet.</span><span class="sxs-lookup"><span data-stu-id="e2531-108">The `Get-InstalledModule` cmdlet gets PowerShell modules that are installed on a computer using PowerShellGet.</span></span> <span data-ttu-id="e2531-109">Чтобы просмотреть все модули, установленные в системе, используйте `Get-Module -ListAvailable` команду.</span><span class="sxs-lookup"><span data-stu-id="e2531-109">To see all modules installed on the system, use the `Get-Module -ListAvailable` command.</span></span>

## <span data-ttu-id="e2531-110">Примеры</span><span class="sxs-lookup"><span data-stu-id="e2531-110">EXAMPLES</span></span>

### <span data-ttu-id="e2531-111">Пример 1. получение всех установленных модулей</span><span class="sxs-lookup"><span data-stu-id="e2531-111">Example 1: Get all installed modules</span></span>

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

<span data-ttu-id="e2531-112">Эта команда возвращает все установленные модули.</span><span class="sxs-lookup"><span data-stu-id="e2531-112">This command gets all installed modules.</span></span>

### <span data-ttu-id="e2531-113">Пример 2. получение конкретных версий модуля</span><span class="sxs-lookup"><span data-stu-id="e2531-113">Example 2: Get specific versions of a module</span></span>

```powershell
Get-InstalledModule -Name "AzureRM.Automation" -MinimumVersion 1.0 -MaximumVersion 2.0
```

```Output
Version    Name                                Type       Repository     Description
-------    ----                                ----       ----------     -----------
1.0.1      AzureRM.Automation                  Module     PSGallery      Microsoft Azure PowerShell - Automation service cmdlets for Azure Resource Manager
```

<span data-ttu-id="e2531-114">Эта команда получает версии модуля AzureRM. Automation из версии 1,0 до версии 2,0.</span><span class="sxs-lookup"><span data-stu-id="e2531-114">This command gets versions of the AzureRM.Automation module from version 1.0 through version 2.0.</span></span>

## <span data-ttu-id="e2531-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e2531-115">PARAMETERS</span></span>

### <span data-ttu-id="e2531-116">-AllowPrerelease</span><span class="sxs-lookup"><span data-stu-id="e2531-116">-AllowPrerelease</span></span>

<span data-ttu-id="e2531-117">Включает в модули результатов, помеченные как предварительные выпуски.</span><span class="sxs-lookup"><span data-stu-id="e2531-117">Includes in the results modules marked as a prerelease.</span></span>

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

### <span data-ttu-id="e2531-118">-AllVersions</span><span class="sxs-lookup"><span data-stu-id="e2531-118">-AllVersions</span></span>

<span data-ttu-id="e2531-119">Указывает, что необходимо получить все доступные версии модуля.</span><span class="sxs-lookup"><span data-stu-id="e2531-119">Indicates that you want to get all available versions of a module.</span></span>
<span data-ttu-id="e2531-120">Параметр **AllVersions** нельзя использовать с параметрами **MinimumVersion** , **MaximumVersion** или **RequiredVersion** .</span><span class="sxs-lookup"><span data-stu-id="e2531-120">You cannot use the **AllVersions** parameter with the **MinimumVersion** , **MaximumVersion** , or **RequiredVersion** parameters.</span></span>

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

### <span data-ttu-id="e2531-121">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="e2531-121">-MaximumVersion</span></span>

<span data-ttu-id="e2531-122">Указывает максимальную или самую новую версию модуля для получения.</span><span class="sxs-lookup"><span data-stu-id="e2531-122">Specifies the maximum, or newest, version of a module to get.</span></span> <span data-ttu-id="e2531-123">Параметры **MaximumVersion** и **RequiredVersion** являются взаимоисключающими. в одной команде нельзя использовать оба параметра.</span><span class="sxs-lookup"><span data-stu-id="e2531-123">The **MaximumVersion** and **RequiredVersion** parameters are mutually exclusive; you cannot use both parameters in the same command.</span></span>

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

### <span data-ttu-id="e2531-124">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="e2531-124">-MinimumVersion</span></span>

<span data-ttu-id="e2531-125">Указывает минимальную версию одного модуля для получения.</span><span class="sxs-lookup"><span data-stu-id="e2531-125">Specifies the minimum version of a single module to get.</span></span> <span data-ttu-id="e2531-126">Параметры **MinimumVersion** и **RequiredVersion** являются взаимоисключающими. в одной команде нельзя использовать оба параметра.</span><span class="sxs-lookup"><span data-stu-id="e2531-126">The **MinimumVersion** and **RequiredVersion** parameters are mutually exclusive; you cannot use both parameters in the same command.</span></span>

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

### <span data-ttu-id="e2531-127">-Name</span><span class="sxs-lookup"><span data-stu-id="e2531-127">-Name</span></span>

<span data-ttu-id="e2531-128">Указывает массив имен модулей для получения.</span><span class="sxs-lookup"><span data-stu-id="e2531-128">Specifies an array of names of modules to get.</span></span>

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

### <span data-ttu-id="e2531-129">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="e2531-129">-RequiredVersion</span></span>

<span data-ttu-id="e2531-130">Указывает точную версию модуля для получения.</span><span class="sxs-lookup"><span data-stu-id="e2531-130">Specifies the exact version of a module to get.</span></span>

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

### <span data-ttu-id="e2531-131">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="e2531-131">CommonParameters</span></span>

<span data-ttu-id="e2531-132">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="e2531-132">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e2531-133">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="e2531-133">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="e2531-134">Входные данные</span><span class="sxs-lookup"><span data-stu-id="e2531-134">INPUTS</span></span>

## <span data-ttu-id="e2531-135">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="e2531-135">OUTPUTS</span></span>

### <span data-ttu-id="e2531-136">System. Management. Automation. PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="e2531-136">System.Management.Automation.PSCustomObject</span></span>

## <span data-ttu-id="e2531-137">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="e2531-137">NOTES</span></span>

## <span data-ttu-id="e2531-138">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="e2531-138">RELATED LINKS</span></span>
