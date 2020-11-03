---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-timezone?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-TimeZone
ms.openlocfilehash: 6b275867a626965ce7210cadf7fa3c618cfaa145
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228185"
---
# <span data-ttu-id="1a226-103">Get-TimeZone</span><span class="sxs-lookup"><span data-stu-id="1a226-103">Get-TimeZone</span></span>

## <span data-ttu-id="1a226-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="1a226-104">SYNOPSIS</span></span>
<span data-ttu-id="1a226-105">Возвращает текущий часовой пояс или список доступных часовых поясов.</span><span class="sxs-lookup"><span data-stu-id="1a226-105">Gets the current time zone or a list of available time zones.</span></span>

## <span data-ttu-id="1a226-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1a226-106">SYNTAX</span></span>

### <span data-ttu-id="1a226-107">Имя (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="1a226-107">Name (Default)</span></span>

```
Get-TimeZone [[-Name] <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="1a226-108">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="1a226-108">Id</span></span>

```
Get-TimeZone -Id <String[]> [<CommonParameters>]
```

### <span data-ttu-id="1a226-109">ListAvailable</span><span class="sxs-lookup"><span data-stu-id="1a226-109">ListAvailable</span></span>

```
Get-TimeZone [-ListAvailable] [<CommonParameters>]
```

## <span data-ttu-id="1a226-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1a226-110">DESCRIPTION</span></span>

<span data-ttu-id="1a226-111">Командлет **Get-TimeZone** получает текущий часовой пояс или список доступных часовых поясов.</span><span class="sxs-lookup"><span data-stu-id="1a226-111">The **Get-TimeZone** cmdlet gets the current time zone or a list of available time zones.</span></span>

## <span data-ttu-id="1a226-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="1a226-112">EXAMPLES</span></span>

### <span data-ttu-id="1a226-113">Пример 1. Получение текущего часового пояса</span><span class="sxs-lookup"><span data-stu-id="1a226-113">Example 1: Get the current time zone</span></span>

```
PS C:\> Get-TimeZone
Pacific Standard Time
```

<span data-ttu-id="1a226-114">Эта команда возвращает текущий часовой пояс.</span><span class="sxs-lookup"><span data-stu-id="1a226-114">This command gets the current time zone.</span></span>

### <span data-ttu-id="1a226-115">Пример 2. получение часовых поясов, соответствующих указанной строке</span><span class="sxs-lookup"><span data-stu-id="1a226-115">Example 2: Get time zones that match a specified string</span></span>

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

<span data-ttu-id="1a226-116">Эта команда возвращает все часовые пояса, соответствующие указанному подстановочному знаку.</span><span class="sxs-lookup"><span data-stu-id="1a226-116">This command gets all time zones that match the specified wildcard.</span></span>

### <span data-ttu-id="1a226-117">Пример 3. получение всех доступных часовых поясов</span><span class="sxs-lookup"><span data-stu-id="1a226-117">Example 3: Get all available time zones</span></span>

```
PS C:\> Get-TimeZone -ListAvailable
```

<span data-ttu-id="1a226-118">Эта команда возвращает все доступные часовые пояса.</span><span class="sxs-lookup"><span data-stu-id="1a226-118">This command gets all available time zones.</span></span>

## <span data-ttu-id="1a226-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1a226-119">PARAMETERS</span></span>

### <span data-ttu-id="1a226-120">-Id</span><span class="sxs-lookup"><span data-stu-id="1a226-120">-Id</span></span>

<span data-ttu-id="1a226-121">Указывает в виде массива строк идентификатор или идентификаторы часовых поясов, которые получает этот командлет.</span><span class="sxs-lookup"><span data-stu-id="1a226-121">Specifies, as a string array, the ID or IDs of the time zones that this cmdlet gets.</span></span>

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

### <span data-ttu-id="1a226-122">-ListAvailable</span><span class="sxs-lookup"><span data-stu-id="1a226-122">-ListAvailable</span></span>

<span data-ttu-id="1a226-123">Указывает, что этот командлет получает все доступные часовые пояса.</span><span class="sxs-lookup"><span data-stu-id="1a226-123">Indicates that this cmdlet gets all available time zones.</span></span>

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

### <span data-ttu-id="1a226-124">-Name</span><span class="sxs-lookup"><span data-stu-id="1a226-124">-Name</span></span>

<span data-ttu-id="1a226-125">Указывает в виде массива строк имя или имена часовых поясов, которые получает этот командлет.</span><span class="sxs-lookup"><span data-stu-id="1a226-125">Specifies, as a string array, the name or names of the time zones that this cmdlet gets.</span></span>

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

### <span data-ttu-id="1a226-126">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="1a226-126">CommonParameters</span></span>

<span data-ttu-id="1a226-127">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="1a226-127">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="1a226-128">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="1a226-128">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="1a226-129">Входные данные</span><span class="sxs-lookup"><span data-stu-id="1a226-129">INPUTS</span></span>

### <span data-ttu-id="1a226-130">System.String[]</span><span class="sxs-lookup"><span data-stu-id="1a226-130">System.String[]</span></span>

## <span data-ttu-id="1a226-131">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="1a226-131">OUTPUTS</span></span>

### <span data-ttu-id="1a226-132">System. TimeZoneInfo []</span><span class="sxs-lookup"><span data-stu-id="1a226-132">System.TimeZoneInfo[]</span></span>

## <span data-ttu-id="1a226-133">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="1a226-133">NOTES</span></span>

## <span data-ttu-id="1a226-134">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="1a226-134">RELATED LINKS</span></span>

[<span data-ttu-id="1a226-135">Set-TimeZone</span><span class="sxs-lookup"><span data-stu-id="1a226-135">Set-TimeZone</span></span>](Set-TimeZone.md)
