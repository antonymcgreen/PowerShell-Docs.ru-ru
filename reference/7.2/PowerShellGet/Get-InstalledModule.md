---
external help file: PSModule-help.xml
Locale: en-US
Module Name: PowerShellGet
ms.date: 02/27/2020
online version: https://docs.microsoft.com/powershell/module/powershellget/get-installedmodule?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-InstalledModule
ms.openlocfilehash: 33621a89f846ca277c21aaf0ad8cd788b428da33
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99604292"
---
# <span data-ttu-id="9f8c9-102">Get-InstalledModule</span><span class="sxs-lookup"><span data-stu-id="9f8c9-102">Get-InstalledModule</span></span>

## <span data-ttu-id="9f8c9-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="9f8c9-103">SYNOPSIS</span></span>
<span data-ttu-id="9f8c9-104">Возвращает список модулей на компьютере, которые были установлены с помощью PowerShellGet.</span><span class="sxs-lookup"><span data-stu-id="9f8c9-104">Gets a list of modules on the computer that were installed by PowerShellGet.</span></span>

## <span data-ttu-id="9f8c9-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9f8c9-105">SYNTAX</span></span>

```
Get-InstalledModule [[-Name] <String[]>] [-MinimumVersion <String>] [-RequiredVersion <String>]
 [-MaximumVersion <String>] [-AllVersions] [-AllowPrerelease] [<CommonParameters>]
```

## <span data-ttu-id="9f8c9-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9f8c9-106">DESCRIPTION</span></span>

<span data-ttu-id="9f8c9-107">`Get-InstalledModule`Командлет получает модули PowerShell, установленные на компьютере с помощью PowerShellGet.</span><span class="sxs-lookup"><span data-stu-id="9f8c9-107">The `Get-InstalledModule` cmdlet gets PowerShell modules that are installed on a computer using PowerShellGet.</span></span> <span data-ttu-id="9f8c9-108">Чтобы просмотреть все модули, установленные в системе, используйте `Get-Module -ListAvailable` команду.</span><span class="sxs-lookup"><span data-stu-id="9f8c9-108">To see all modules installed on the system, use the `Get-Module -ListAvailable` command.</span></span>

## <span data-ttu-id="9f8c9-109">Примеры</span><span class="sxs-lookup"><span data-stu-id="9f8c9-109">EXAMPLES</span></span>

### <span data-ttu-id="9f8c9-110">Пример 1. получение всех установленных модулей</span><span class="sxs-lookup"><span data-stu-id="9f8c9-110">Example 1: Get all installed modules</span></span>

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

<span data-ttu-id="9f8c9-111">Эта команда возвращает все установленные модули.</span><span class="sxs-lookup"><span data-stu-id="9f8c9-111">This command gets all installed modules.</span></span>

### <span data-ttu-id="9f8c9-112">Пример 2. получение конкретных версий модуля</span><span class="sxs-lookup"><span data-stu-id="9f8c9-112">Example 2: Get specific versions of a module</span></span>

```powershell
Get-InstalledModule -Name "AzureRM.Automation" -MinimumVersion 1.0 -MaximumVersion 2.0
```

```Output
Version    Name                                Type       Repository     Description
-------    ----                                ----       ----------     -----------
1.0.1      AzureRM.Automation                  Module     PSGallery      Microsoft Azure PowerShell - Automation service cmdlets for Azure Resource Manager
```

<span data-ttu-id="9f8c9-113">Эта команда получает версии модуля AzureRM. Automation из версии 1,0 до версии 2,0.</span><span class="sxs-lookup"><span data-stu-id="9f8c9-113">This command gets versions of the AzureRM.Automation module from version 1.0 through version 2.0.</span></span>

## <span data-ttu-id="9f8c9-114">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9f8c9-114">PARAMETERS</span></span>

### <span data-ttu-id="9f8c9-115">-AllowPrerelease</span><span class="sxs-lookup"><span data-stu-id="9f8c9-115">-AllowPrerelease</span></span>

<span data-ttu-id="9f8c9-116">Включает в модули результатов, помеченные как предварительные выпуски.</span><span class="sxs-lookup"><span data-stu-id="9f8c9-116">Includes in the results modules marked as a prerelease.</span></span>

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

### <span data-ttu-id="9f8c9-117">-AllVersions</span><span class="sxs-lookup"><span data-stu-id="9f8c9-117">-AllVersions</span></span>

<span data-ttu-id="9f8c9-118">Указывает, что необходимо получить все доступные версии модуля.</span><span class="sxs-lookup"><span data-stu-id="9f8c9-118">Indicates that you want to get all available versions of a module.</span></span>
<span data-ttu-id="9f8c9-119">Параметр **AllVersions** нельзя использовать с параметрами **MinimumVersion**, **MaximumVersion** или **RequiredVersion** .</span><span class="sxs-lookup"><span data-stu-id="9f8c9-119">You cannot use the **AllVersions** parameter with the **MinimumVersion**, **MaximumVersion**, or **RequiredVersion** parameters.</span></span>

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

### <span data-ttu-id="9f8c9-120">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="9f8c9-120">-MaximumVersion</span></span>

<span data-ttu-id="9f8c9-121">Указывает максимальную или самую новую версию модуля для получения.</span><span class="sxs-lookup"><span data-stu-id="9f8c9-121">Specifies the maximum, or newest, version of a module to get.</span></span> <span data-ttu-id="9f8c9-122">Параметры **MaximumVersion** и **RequiredVersion** являются взаимоисключающими. в одной команде нельзя использовать оба параметра.</span><span class="sxs-lookup"><span data-stu-id="9f8c9-122">The **MaximumVersion** and **RequiredVersion** parameters are mutually exclusive; you cannot use both parameters in the same command.</span></span>

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

### <span data-ttu-id="9f8c9-123">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="9f8c9-123">-MinimumVersion</span></span>

<span data-ttu-id="9f8c9-124">Указывает минимальную версию одного модуля для получения.</span><span class="sxs-lookup"><span data-stu-id="9f8c9-124">Specifies the minimum version of a single module to get.</span></span> <span data-ttu-id="9f8c9-125">Параметры **MinimumVersion** и **RequiredVersion** являются взаимоисключающими. в одной команде нельзя использовать оба параметра.</span><span class="sxs-lookup"><span data-stu-id="9f8c9-125">The **MinimumVersion** and **RequiredVersion** parameters are mutually exclusive; you cannot use both parameters in the same command.</span></span>

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

### <span data-ttu-id="9f8c9-126">-Name</span><span class="sxs-lookup"><span data-stu-id="9f8c9-126">-Name</span></span>

<span data-ttu-id="9f8c9-127">Указывает массив имен модулей для получения.</span><span class="sxs-lookup"><span data-stu-id="9f8c9-127">Specifies an array of names of modules to get.</span></span>

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

### <span data-ttu-id="9f8c9-128">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="9f8c9-128">-RequiredVersion</span></span>

<span data-ttu-id="9f8c9-129">Указывает точную версию модуля для получения.</span><span class="sxs-lookup"><span data-stu-id="9f8c9-129">Specifies the exact version of a module to get.</span></span>

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

### <span data-ttu-id="9f8c9-130">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="9f8c9-130">CommonParameters</span></span>

<span data-ttu-id="9f8c9-131">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="9f8c9-131">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9f8c9-132">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="9f8c9-132">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="9f8c9-133">Входные данные</span><span class="sxs-lookup"><span data-stu-id="9f8c9-133">INPUTS</span></span>

### <span data-ttu-id="9f8c9-134">System.String[]</span><span class="sxs-lookup"><span data-stu-id="9f8c9-134">System.String[]</span></span>

### <span data-ttu-id="9f8c9-135">System.String</span><span class="sxs-lookup"><span data-stu-id="9f8c9-135">System.String</span></span>

## <span data-ttu-id="9f8c9-136">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="9f8c9-136">OUTPUTS</span></span>

### <span data-ttu-id="9f8c9-137">System. Management. Automation. PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="9f8c9-137">System.Management.Automation.PSCustomObject</span></span>

## <span data-ttu-id="9f8c9-138">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="9f8c9-138">NOTES</span></span>

## <span data-ttu-id="9f8c9-139">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="9f8c9-139">RELATED LINKS</span></span>

