---
external help file: PSModule-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/powershellget/get-installedscript?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-InstalledScript
ms.openlocfilehash: a90ece844d5a271402537f17c601bf2e36b5ed8c
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93225782"
---
# <span data-ttu-id="14d26-103">Get-InstalledScript</span><span class="sxs-lookup"><span data-stu-id="14d26-103">Get-InstalledScript</span></span>

## <span data-ttu-id="14d26-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="14d26-104">SYNOPSIS</span></span>
<span data-ttu-id="14d26-105">Возвращает установленный скрипт.</span><span class="sxs-lookup"><span data-stu-id="14d26-105">Gets an installed script.</span></span>

## <span data-ttu-id="14d26-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="14d26-106">SYNTAX</span></span>

```
Get-InstalledScript [[-Name] <String[]>] [-MinimumVersion <String>] [-RequiredVersion <String>]
 [-MaximumVersion <String>] [-AllowPrerelease] [<CommonParameters>]
```

## <span data-ttu-id="14d26-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="14d26-107">DESCRIPTION</span></span>

<span data-ttu-id="14d26-108">Командлет **Get-InstalledScript** получает установленные скрипты для областей CurrentUser и ALLUSERS.</span><span class="sxs-lookup"><span data-stu-id="14d26-108">The **Get-InstalledScript** cmdlet gets installed scripts for CurrentUser and AllUsers scopes.</span></span>

## <span data-ttu-id="14d26-109">Примеры</span><span class="sxs-lookup"><span data-stu-id="14d26-109">EXAMPLES</span></span>

### <span data-ttu-id="14d26-110">Пример 1. получение всех установленных скриптов</span><span class="sxs-lookup"><span data-stu-id="14d26-110">Example 1: Get all installed scripts</span></span>

```
PS C:\> Get-InstalledScript
Version    Name                                Type       Repository           Description
-------    ----                                ----       ----------           -----------
2.5        Required-Script1                    Script     local1               Description for the Required-Script1 script
2.5        Required-Script2                    Script     local1               Description for the Required-Script2 script
2.5        Required-Script3                    Script     local1               Description for the Required-Script3 script
2.0        Script-WithDependencies1            Script     local1               Description for the Script-WithDependencies1 script
```

<span data-ttu-id="14d26-111">Эта команда возвращает все установленные скрипты.</span><span class="sxs-lookup"><span data-stu-id="14d26-111">This command gets all installed scripts.</span></span>

### <span data-ttu-id="14d26-112">Пример 2. Получение установленных скриптов по имени</span><span class="sxs-lookup"><span data-stu-id="14d26-112">Example 2: Get installed scripts by name</span></span>

```
PS C:\> Get-InstalledScript -Name "Required-Scri*"
Version    Name                                Type       Repository           Description
-------    ----                                ----       ----------           -----------
2.5        Required-Script1                    Script     local1               Description for the Required-Script1 script
2.5        Required-Script2                    Script     local1               Description for the Required-Script2 script
2.5        Required-Script3                    Script     local1               Description for the Required-Script3 script
```

<span data-ttu-id="14d26-113">Эта команда получает скрипты, в которых имя начинается с Required-Скри.</span><span class="sxs-lookup"><span data-stu-id="14d26-113">This command gets scripts where the name begins with Required-Scri.</span></span>

## <span data-ttu-id="14d26-114">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="14d26-114">PARAMETERS</span></span>

### <span data-ttu-id="14d26-115">-AllowPrerelease</span><span class="sxs-lookup"><span data-stu-id="14d26-115">-AllowPrerelease</span></span>

<span data-ttu-id="14d26-116">Включает в скрипты результатов, помеченные как предварительные.</span><span class="sxs-lookup"><span data-stu-id="14d26-116">Includes in the results scripts marked as a prerelease.</span></span>

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

### <span data-ttu-id="14d26-117">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="14d26-117">-MaximumVersion</span></span>

<span data-ttu-id="14d26-118">Указывает максимальную или последнюю версию скрипта для получения.</span><span class="sxs-lookup"><span data-stu-id="14d26-118">Specifies the maximum, or latest, version of a script to get.</span></span>
<span data-ttu-id="14d26-119">Параметры *MaximumVersion* и *RequiredVersion* являются взаимоисключающими. в одной команде нельзя использовать оба параметра.</span><span class="sxs-lookup"><span data-stu-id="14d26-119">The *MaximumVersion* and *RequiredVersion* parameters are mutually exclusive; you cannot use both parameters in the same command.</span></span>

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

### <span data-ttu-id="14d26-120">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="14d26-120">-MinimumVersion</span></span>

<span data-ttu-id="14d26-121">Указывает минимальную версию скрипта для получения.</span><span class="sxs-lookup"><span data-stu-id="14d26-121">Specifies the minimum version of a script to get.</span></span>
<span data-ttu-id="14d26-122">Параметры *MinimumVersion* и *RequiredVersion* являются взаимоисключающими. в одной команде нельзя использовать оба параметра.</span><span class="sxs-lookup"><span data-stu-id="14d26-122">The *MinimumVersion* and *RequiredVersion* parameters are mutually exclusive; you cannot use both parameters in the same command.</span></span>

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

### <span data-ttu-id="14d26-123">-Name</span><span class="sxs-lookup"><span data-stu-id="14d26-123">-Name</span></span>

<span data-ttu-id="14d26-124">Указывает массив имен получаемых скриптов.</span><span class="sxs-lookup"><span data-stu-id="14d26-124">Specifies an array of names of scripts to get.</span></span>
<span data-ttu-id="14d26-125">Подстановочные знаки принимаются.</span><span class="sxs-lookup"><span data-stu-id="14d26-125">Wildcards are accepted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="14d26-126">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="14d26-126">-RequiredVersion</span></span>

<span data-ttu-id="14d26-127">Указывает точную версию скрипта для получения.</span><span class="sxs-lookup"><span data-stu-id="14d26-127">Specifies the exact version of a script to get.</span></span>

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

### <span data-ttu-id="14d26-128">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="14d26-128">CommonParameters</span></span>

<span data-ttu-id="14d26-129">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="14d26-129">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="14d26-130">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="14d26-130">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="14d26-131">Входные данные</span><span class="sxs-lookup"><span data-stu-id="14d26-131">INPUTS</span></span>

### <span data-ttu-id="14d26-132">System.String[]</span><span class="sxs-lookup"><span data-stu-id="14d26-132">System.String[]</span></span>

### <span data-ttu-id="14d26-133">System.String</span><span class="sxs-lookup"><span data-stu-id="14d26-133">System.String</span></span>

## <span data-ttu-id="14d26-134">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="14d26-134">OUTPUTS</span></span>

### <span data-ttu-id="14d26-135">System.Object</span><span class="sxs-lookup"><span data-stu-id="14d26-135">System.Object</span></span>

## <span data-ttu-id="14d26-136">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="14d26-136">NOTES</span></span>

## <span data-ttu-id="14d26-137">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="14d26-137">RELATED LINKS</span></span>

[<span data-ttu-id="14d26-138">Install-Script</span><span class="sxs-lookup"><span data-stu-id="14d26-138">Install-Script</span></span>](Install-Script.md)

[<span data-ttu-id="14d26-139">Uninstall-Script</span><span class="sxs-lookup"><span data-stu-id="14d26-139">Uninstall-Script</span></span>](Uninstall-Script.md)
