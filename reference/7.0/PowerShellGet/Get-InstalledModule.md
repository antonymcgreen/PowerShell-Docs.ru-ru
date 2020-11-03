---
external help file: PSModule-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PowerShellGet
ms.date: 02/27/2020
online version: https://docs.microsoft.com/powershell/module/powershellget/get-installedmodule?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-InstalledModule
ms.openlocfilehash: 8c96b4cd56073a9185ca4b0f0f13b866b839931d
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93225786"
---
# <span data-ttu-id="e17af-103">Get-InstalledModule</span><span class="sxs-lookup"><span data-stu-id="e17af-103">Get-InstalledModule</span></span>

## <span data-ttu-id="e17af-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="e17af-104">SYNOPSIS</span></span>
<span data-ttu-id="e17af-105">Возвращает список модулей на компьютере, которые были установлены с помощью PowerShellGet.</span><span class="sxs-lookup"><span data-stu-id="e17af-105">Gets a list of modules on the computer that were installed by PowerShellGet.</span></span>

## <span data-ttu-id="e17af-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e17af-106">SYNTAX</span></span>

```
Get-InstalledModule [[-Name] <String[]>] [-MinimumVersion <String>] [-RequiredVersion <String>]
 [-MaximumVersion <String>] [-AllVersions] [-AllowPrerelease] [<CommonParameters>]
```

## <span data-ttu-id="e17af-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e17af-107">DESCRIPTION</span></span>

<span data-ttu-id="e17af-108">`Get-InstalledModule`Командлет получает модули PowerShell, установленные на компьютере с помощью PowerShellGet.</span><span class="sxs-lookup"><span data-stu-id="e17af-108">The `Get-InstalledModule` cmdlet gets PowerShell modules that are installed on a computer using PowerShellGet.</span></span> <span data-ttu-id="e17af-109">Чтобы просмотреть все модули, установленные в системе, используйте `Get-Module -ListAvailable` команду.</span><span class="sxs-lookup"><span data-stu-id="e17af-109">To see all modules installed on the system, use the `Get-Module -ListAvailable` command.</span></span>

## <span data-ttu-id="e17af-110">Примеры</span><span class="sxs-lookup"><span data-stu-id="e17af-110">EXAMPLES</span></span>

### <span data-ttu-id="e17af-111">Пример 1. получение всех установленных модулей</span><span class="sxs-lookup"><span data-stu-id="e17af-111">Example 1: Get all installed modules</span></span>

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

<span data-ttu-id="e17af-112">Эта команда возвращает все установленные модули.</span><span class="sxs-lookup"><span data-stu-id="e17af-112">This command gets all installed modules.</span></span>

### <span data-ttu-id="e17af-113">Пример 2. получение конкретных версий модуля</span><span class="sxs-lookup"><span data-stu-id="e17af-113">Example 2: Get specific versions of a module</span></span>

```powershell
Get-InstalledModule -Name "AzureRM.Automation" -MinimumVersion 1.0 -MaximumVersion 2.0
```

```Output
Version    Name                                Type       Repository     Description
-------    ----                                ----       ----------     -----------
1.0.1      AzureRM.Automation                  Module     PSGallery      Microsoft Azure PowerShell - Automation service cmdlets for Azure Resource Manager
```

<span data-ttu-id="e17af-114">Эта команда получает версии модуля AzureRM. Automation из версии 1,0 до версии 2,0.</span><span class="sxs-lookup"><span data-stu-id="e17af-114">This command gets versions of the AzureRM.Automation module from version 1.0 through version 2.0.</span></span>

## <span data-ttu-id="e17af-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e17af-115">PARAMETERS</span></span>

### <span data-ttu-id="e17af-116">-AllowPrerelease</span><span class="sxs-lookup"><span data-stu-id="e17af-116">-AllowPrerelease</span></span>

<span data-ttu-id="e17af-117">Включает в модули результатов, помеченные как предварительные выпуски.</span><span class="sxs-lookup"><span data-stu-id="e17af-117">Includes in the results modules marked as a prerelease.</span></span>

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

### <span data-ttu-id="e17af-118">-AllVersions</span><span class="sxs-lookup"><span data-stu-id="e17af-118">-AllVersions</span></span>

<span data-ttu-id="e17af-119">Указывает, что необходимо получить все доступные версии модуля.</span><span class="sxs-lookup"><span data-stu-id="e17af-119">Indicates that you want to get all available versions of a module.</span></span>
<span data-ttu-id="e17af-120">Параметр **AllVersions** нельзя использовать с параметрами **MinimumVersion** , **MaximumVersion** или **RequiredVersion** .</span><span class="sxs-lookup"><span data-stu-id="e17af-120">You cannot use the **AllVersions** parameter with the **MinimumVersion** , **MaximumVersion** , or **RequiredVersion** parameters.</span></span>

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

### <span data-ttu-id="e17af-121">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="e17af-121">-MaximumVersion</span></span>

<span data-ttu-id="e17af-122">Указывает максимальную или самую новую версию модуля для получения.</span><span class="sxs-lookup"><span data-stu-id="e17af-122">Specifies the maximum, or newest, version of a module to get.</span></span> <span data-ttu-id="e17af-123">Параметры **MaximumVersion** и **RequiredVersion** являются взаимоисключающими. в одной команде нельзя использовать оба параметра.</span><span class="sxs-lookup"><span data-stu-id="e17af-123">The **MaximumVersion** and **RequiredVersion** parameters are mutually exclusive; you cannot use both parameters in the same command.</span></span>

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

### <span data-ttu-id="e17af-124">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="e17af-124">-MinimumVersion</span></span>

<span data-ttu-id="e17af-125">Указывает минимальную версию одного модуля для получения.</span><span class="sxs-lookup"><span data-stu-id="e17af-125">Specifies the minimum version of a single module to get.</span></span> <span data-ttu-id="e17af-126">Параметры **MinimumVersion** и **RequiredVersion** являются взаимоисключающими. в одной команде нельзя использовать оба параметра.</span><span class="sxs-lookup"><span data-stu-id="e17af-126">The **MinimumVersion** and **RequiredVersion** parameters are mutually exclusive; you cannot use both parameters in the same command.</span></span>

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

### <span data-ttu-id="e17af-127">-Name</span><span class="sxs-lookup"><span data-stu-id="e17af-127">-Name</span></span>

<span data-ttu-id="e17af-128">Указывает массив имен модулей для получения.</span><span class="sxs-lookup"><span data-stu-id="e17af-128">Specifies an array of names of modules to get.</span></span>

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

### <span data-ttu-id="e17af-129">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="e17af-129">-RequiredVersion</span></span>

<span data-ttu-id="e17af-130">Указывает точную версию модуля для получения.</span><span class="sxs-lookup"><span data-stu-id="e17af-130">Specifies the exact version of a module to get.</span></span>

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

### <span data-ttu-id="e17af-131">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="e17af-131">CommonParameters</span></span>

<span data-ttu-id="e17af-132">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="e17af-132">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e17af-133">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="e17af-133">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="e17af-134">Входные данные</span><span class="sxs-lookup"><span data-stu-id="e17af-134">INPUTS</span></span>

### <span data-ttu-id="e17af-135">System.String[]</span><span class="sxs-lookup"><span data-stu-id="e17af-135">System.String[]</span></span>

### <span data-ttu-id="e17af-136">System.String</span><span class="sxs-lookup"><span data-stu-id="e17af-136">System.String</span></span>

## <span data-ttu-id="e17af-137">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="e17af-137">OUTPUTS</span></span>

### <span data-ttu-id="e17af-138">System. Management. Automation. PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="e17af-138">System.Management.Automation.PSCustomObject</span></span>

## <span data-ttu-id="e17af-139">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="e17af-139">NOTES</span></span>

## <span data-ttu-id="e17af-140">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="e17af-140">RELATED LINKS</span></span>
