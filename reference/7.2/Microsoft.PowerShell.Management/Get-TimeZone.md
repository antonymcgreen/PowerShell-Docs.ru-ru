---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-timezone?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-TimeZone
ms.openlocfilehash: 22034eeac6988478a5f2ff87b2582cc5e1acc1c0
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99604479"
---
# <span data-ttu-id="b1414-102">Get-TimeZone</span><span class="sxs-lookup"><span data-stu-id="b1414-102">Get-TimeZone</span></span>

## <span data-ttu-id="b1414-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="b1414-103">SYNOPSIS</span></span>
<span data-ttu-id="b1414-104">Возвращает текущий часовой пояс или список доступных часовых поясов.</span><span class="sxs-lookup"><span data-stu-id="b1414-104">Gets the current time zone or a list of available time zones.</span></span>

## <span data-ttu-id="b1414-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b1414-105">SYNTAX</span></span>

### <span data-ttu-id="b1414-106">Имя (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="b1414-106">Name (Default)</span></span>

```
Get-TimeZone [[-Name] <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="b1414-107">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="b1414-107">Id</span></span>

```
Get-TimeZone -Id <String[]> [<CommonParameters>]
```

### <span data-ttu-id="b1414-108">ListAvailable</span><span class="sxs-lookup"><span data-stu-id="b1414-108">ListAvailable</span></span>

```
Get-TimeZone [-ListAvailable] [<CommonParameters>]
```

## <span data-ttu-id="b1414-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b1414-109">DESCRIPTION</span></span>

<span data-ttu-id="b1414-110">Командлет **Get-TimeZone** получает текущий часовой пояс или список доступных часовых поясов.</span><span class="sxs-lookup"><span data-stu-id="b1414-110">The **Get-TimeZone** cmdlet gets the current time zone or a list of available time zones.</span></span>

## <span data-ttu-id="b1414-111">Примеры</span><span class="sxs-lookup"><span data-stu-id="b1414-111">EXAMPLES</span></span>

### <span data-ttu-id="b1414-112">Пример 1. Получение текущего часового пояса</span><span class="sxs-lookup"><span data-stu-id="b1414-112">Example 1: Get the current time zone</span></span>

```
PS C:\> Get-TimeZone
Pacific Standard Time
```

<span data-ttu-id="b1414-113">Эта команда возвращает текущий часовой пояс.</span><span class="sxs-lookup"><span data-stu-id="b1414-113">This command gets the current time zone.</span></span>

### <span data-ttu-id="b1414-114">Пример 2. получение часовых поясов, соответствующих указанной строке</span><span class="sxs-lookup"><span data-stu-id="b1414-114">Example 2: Get time zones that match a specified string</span></span>

```
PS C:\> Get-TimeZone -Name "*pac*"
Pacific Standard Time (Mexico)

(UTC-08:00) Pacific Time (US &amp; Canada)

Pacific Standard Time

SA Pacific Standard Time

Pacific SA Standard Time

West Pacific Standard Time

Central Pacific Standard Time
```

<span data-ttu-id="b1414-115">Эта команда возвращает все часовые пояса, соответствующие указанному подстановочному знаку.</span><span class="sxs-lookup"><span data-stu-id="b1414-115">This command gets all time zones that match the specified wildcard.</span></span>

### <span data-ttu-id="b1414-116">Пример 3. получение всех доступных часовых поясов</span><span class="sxs-lookup"><span data-stu-id="b1414-116">Example 3: Get all available time zones</span></span>

```
PS C:\> Get-TimeZone -ListAvailable
```

<span data-ttu-id="b1414-117">Эта команда возвращает все доступные часовые пояса.</span><span class="sxs-lookup"><span data-stu-id="b1414-117">This command gets all available time zones.</span></span>

## <span data-ttu-id="b1414-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b1414-118">PARAMETERS</span></span>

### <span data-ttu-id="b1414-119">-Id</span><span class="sxs-lookup"><span data-stu-id="b1414-119">-Id</span></span>

<span data-ttu-id="b1414-120">Указывает в виде массива строк идентификатор или идентификаторы часовых поясов, которые получает этот командлет.</span><span class="sxs-lookup"><span data-stu-id="b1414-120">Specifies, as a string array, the ID or IDs of the time zones that this cmdlet gets.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Id
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b1414-121">-ListAvailable</span><span class="sxs-lookup"><span data-stu-id="b1414-121">-ListAvailable</span></span>

<span data-ttu-id="b1414-122">Указывает, что этот командлет получает все доступные часовые пояса.</span><span class="sxs-lookup"><span data-stu-id="b1414-122">Indicates that this cmdlet gets all available time zones.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ListAvailable
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b1414-123">-Name</span><span class="sxs-lookup"><span data-stu-id="b1414-123">-Name</span></span>

<span data-ttu-id="b1414-124">Указывает в виде массива строк имя или имена часовых поясов, которые получает этот командлет.</span><span class="sxs-lookup"><span data-stu-id="b1414-124">Specifies, as a string array, the name or names of the time zones that this cmdlet gets.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Name
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="b1414-125">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="b1414-125">CommonParameters</span></span>

<span data-ttu-id="b1414-126">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b1414-126">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b1414-127">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="b1414-127">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b1414-128">Входные данные</span><span class="sxs-lookup"><span data-stu-id="b1414-128">INPUTS</span></span>

### <span data-ttu-id="b1414-129">System.String[]</span><span class="sxs-lookup"><span data-stu-id="b1414-129">System.String[]</span></span>

## <span data-ttu-id="b1414-130">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="b1414-130">OUTPUTS</span></span>

### <span data-ttu-id="b1414-131">System. TimeZoneInfo []</span><span class="sxs-lookup"><span data-stu-id="b1414-131">System.TimeZoneInfo[]</span></span>

## <span data-ttu-id="b1414-132">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="b1414-132">NOTES</span></span>

<span data-ttu-id="b1414-133">Этот командлет доступен только на платформах Windows.</span><span class="sxs-lookup"><span data-stu-id="b1414-133">This cmdlet is only available on Windows platforms.</span></span>

## <span data-ttu-id="b1414-134">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="b1414-134">RELATED LINKS</span></span>

[<span data-ttu-id="b1414-135">Set-TimeZone</span><span class="sxs-lookup"><span data-stu-id="b1414-135">Set-TimeZone</span></span>](Set-TimeZone.md)
