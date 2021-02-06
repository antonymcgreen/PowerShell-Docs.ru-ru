---
external help file: PSModule-help.xml
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/powershellget/get-installedscript?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-InstalledScript
ms.openlocfilehash: fe5fc0feb34fda87dab987f33140992a346017a1
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99605297"
---
# <span data-ttu-id="df01f-102">Get-InstalledScript</span><span class="sxs-lookup"><span data-stu-id="df01f-102">Get-InstalledScript</span></span>

## <span data-ttu-id="df01f-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="df01f-103">SYNOPSIS</span></span>
<span data-ttu-id="df01f-104">Возвращает установленный скрипт.</span><span class="sxs-lookup"><span data-stu-id="df01f-104">Gets an installed script.</span></span>

## <span data-ttu-id="df01f-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="df01f-105">SYNTAX</span></span>

```
Get-InstalledScript [[-Name] <String[]>] [-MinimumVersion <String>] [-RequiredVersion <String>]
 [-MaximumVersion <String>] [-AllowPrerelease] [<CommonParameters>]
```

## <span data-ttu-id="df01f-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="df01f-106">DESCRIPTION</span></span>

<span data-ttu-id="df01f-107">Командлет **Get-InstalledScript** получает установленные скрипты для областей CurrentUser и ALLUSERS.</span><span class="sxs-lookup"><span data-stu-id="df01f-107">The **Get-InstalledScript** cmdlet gets installed scripts for CurrentUser and AllUsers scopes.</span></span>

## <span data-ttu-id="df01f-108">Примеры</span><span class="sxs-lookup"><span data-stu-id="df01f-108">EXAMPLES</span></span>

### <span data-ttu-id="df01f-109">Пример 1. получение всех установленных скриптов</span><span class="sxs-lookup"><span data-stu-id="df01f-109">Example 1: Get all installed scripts</span></span>

```
PS C:\> Get-InstalledScript
Version    Name                                Type       Repository           Description
-------    ----                                ----       ----------           -----------
2.5        Required-Script1                    Script     local1               Description for the Required-Script1 script
2.5        Required-Script2                    Script     local1               Description for the Required-Script2 script
2.5        Required-Script3                    Script     local1               Description for the Required-Script3 script
2.0        Script-WithDependencies1            Script     local1               Description for the Script-WithDependencies1 script
```

<span data-ttu-id="df01f-110">Эта команда возвращает все установленные скрипты.</span><span class="sxs-lookup"><span data-stu-id="df01f-110">This command gets all installed scripts.</span></span>

### <span data-ttu-id="df01f-111">Пример 2. Получение установленных скриптов по имени</span><span class="sxs-lookup"><span data-stu-id="df01f-111">Example 2: Get installed scripts by name</span></span>

```
PS C:\> Get-InstalledScript -Name "Required-Scri*"
Version    Name                                Type       Repository           Description
-------    ----                                ----       ----------           -----------
2.5        Required-Script1                    Script     local1               Description for the Required-Script1 script
2.5        Required-Script2                    Script     local1               Description for the Required-Script2 script
2.5        Required-Script3                    Script     local1               Description for the Required-Script3 script
```

<span data-ttu-id="df01f-112">Эта команда получает скрипты, в которых имя начинается с Required-Скри.</span><span class="sxs-lookup"><span data-stu-id="df01f-112">This command gets scripts where the name begins with Required-Scri.</span></span>

## <span data-ttu-id="df01f-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="df01f-113">PARAMETERS</span></span>

### <span data-ttu-id="df01f-114">-AllowPrerelease</span><span class="sxs-lookup"><span data-stu-id="df01f-114">-AllowPrerelease</span></span>

<span data-ttu-id="df01f-115">Включает в скрипты результатов, помеченные как предварительные.</span><span class="sxs-lookup"><span data-stu-id="df01f-115">Includes in the results scripts marked as a prerelease.</span></span>

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

### <span data-ttu-id="df01f-116">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="df01f-116">-MaximumVersion</span></span>

<span data-ttu-id="df01f-117">Указывает максимальную или последнюю версию скрипта для получения.</span><span class="sxs-lookup"><span data-stu-id="df01f-117">Specifies the maximum, or latest, version of a script to get.</span></span>
<span data-ttu-id="df01f-118">Параметры *MaximumVersion* и *RequiredVersion* являются взаимоисключающими. в одной команде нельзя использовать оба параметра.</span><span class="sxs-lookup"><span data-stu-id="df01f-118">The *MaximumVersion* and *RequiredVersion* parameters are mutually exclusive; you cannot use both parameters in the same command.</span></span>

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

### <span data-ttu-id="df01f-119">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="df01f-119">-MinimumVersion</span></span>

<span data-ttu-id="df01f-120">Указывает минимальную версию скрипта для получения.</span><span class="sxs-lookup"><span data-stu-id="df01f-120">Specifies the minimum version of a script to get.</span></span>
<span data-ttu-id="df01f-121">Параметры *MinimumVersion* и *RequiredVersion* являются взаимоисключающими. в одной команде нельзя использовать оба параметра.</span><span class="sxs-lookup"><span data-stu-id="df01f-121">The *MinimumVersion* and *RequiredVersion* parameters are mutually exclusive; you cannot use both parameters in the same command.</span></span>

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

### <span data-ttu-id="df01f-122">-Name</span><span class="sxs-lookup"><span data-stu-id="df01f-122">-Name</span></span>

<span data-ttu-id="df01f-123">Указывает массив имен получаемых скриптов.</span><span class="sxs-lookup"><span data-stu-id="df01f-123">Specifies an array of names of scripts to get.</span></span>
<span data-ttu-id="df01f-124">Подстановочные знаки принимаются.</span><span class="sxs-lookup"><span data-stu-id="df01f-124">Wildcards are accepted.</span></span>

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

### <span data-ttu-id="df01f-125">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="df01f-125">-RequiredVersion</span></span>

<span data-ttu-id="df01f-126">Указывает точную версию скрипта для получения.</span><span class="sxs-lookup"><span data-stu-id="df01f-126">Specifies the exact version of a script to get.</span></span>

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

### <span data-ttu-id="df01f-127">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="df01f-127">CommonParameters</span></span>

<span data-ttu-id="df01f-128">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="df01f-128">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="df01f-129">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="df01f-129">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="df01f-130">Входные данные</span><span class="sxs-lookup"><span data-stu-id="df01f-130">INPUTS</span></span>

### <span data-ttu-id="df01f-131">System.String[]</span><span class="sxs-lookup"><span data-stu-id="df01f-131">System.String[]</span></span>

### <span data-ttu-id="df01f-132">System.String</span><span class="sxs-lookup"><span data-stu-id="df01f-132">System.String</span></span>

## <span data-ttu-id="df01f-133">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="df01f-133">OUTPUTS</span></span>

### <span data-ttu-id="df01f-134">System.Object</span><span class="sxs-lookup"><span data-stu-id="df01f-134">System.Object</span></span>

## <span data-ttu-id="df01f-135">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="df01f-135">NOTES</span></span>

## <span data-ttu-id="df01f-136">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="df01f-136">RELATED LINKS</span></span>

[<span data-ttu-id="df01f-137">Install-Script</span><span class="sxs-lookup"><span data-stu-id="df01f-137">Install-Script</span></span>](Install-Script.md)

[<span data-ttu-id="df01f-138">Удаление скрипта</span><span class="sxs-lookup"><span data-stu-id="df01f-138">Uninstall-Script</span></span>](Uninstall-Script.md)

