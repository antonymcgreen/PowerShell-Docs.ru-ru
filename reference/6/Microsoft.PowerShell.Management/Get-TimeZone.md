---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-timezone?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-TimeZone
ms.openlocfilehash: 0a2beb778001267beda0b23afaf1264b0440a5e5
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2020
ms.locfileid: "94343987"
---
# <span data-ttu-id="47bcc-103">Get-TimeZone</span><span class="sxs-lookup"><span data-stu-id="47bcc-103">Get-TimeZone</span></span>

## <span data-ttu-id="47bcc-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="47bcc-104">SYNOPSIS</span></span>
<span data-ttu-id="47bcc-105">Возвращает текущий часовой пояс или список доступных часовых поясов.</span><span class="sxs-lookup"><span data-stu-id="47bcc-105">Gets the current time zone or a list of available time zones.</span></span>

## <span data-ttu-id="47bcc-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="47bcc-106">SYNTAX</span></span>

### <span data-ttu-id="47bcc-107">Имя (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="47bcc-107">Name (Default)</span></span>

```
Get-TimeZone [[-Name] <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="47bcc-108">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="47bcc-108">Id</span></span>

```
Get-TimeZone -Id <String[]> [<CommonParameters>]
```

### <span data-ttu-id="47bcc-109">ListAvailable</span><span class="sxs-lookup"><span data-stu-id="47bcc-109">ListAvailable</span></span>

```
Get-TimeZone [-ListAvailable] [<CommonParameters>]
```

## <span data-ttu-id="47bcc-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="47bcc-110">DESCRIPTION</span></span>

<span data-ttu-id="47bcc-111">Командлет **Get-TimeZone** получает текущий часовой пояс или список доступных часовых поясов.</span><span class="sxs-lookup"><span data-stu-id="47bcc-111">The **Get-TimeZone** cmdlet gets the current time zone or a list of available time zones.</span></span>

## <span data-ttu-id="47bcc-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="47bcc-112">EXAMPLES</span></span>

### <span data-ttu-id="47bcc-113">Пример 1. Получение текущего часового пояса</span><span class="sxs-lookup"><span data-stu-id="47bcc-113">Example 1: Get the current time zone</span></span>

```
PS C:\> Get-TimeZone
Pacific Standard Time
```

<span data-ttu-id="47bcc-114">Эта команда возвращает текущий часовой пояс.</span><span class="sxs-lookup"><span data-stu-id="47bcc-114">This command gets the current time zone.</span></span>

### <span data-ttu-id="47bcc-115">Пример 2. получение часовых поясов, соответствующих указанной строке</span><span class="sxs-lookup"><span data-stu-id="47bcc-115">Example 2: Get time zones that match a specified string</span></span>

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

<span data-ttu-id="47bcc-116">Эта команда возвращает все часовые пояса, соответствующие указанному подстановочному знаку.</span><span class="sxs-lookup"><span data-stu-id="47bcc-116">This command gets all time zones that match the specified wildcard.</span></span>

### <span data-ttu-id="47bcc-117">Пример 3. получение всех доступных часовых поясов</span><span class="sxs-lookup"><span data-stu-id="47bcc-117">Example 3: Get all available time zones</span></span>

```
PS C:\> Get-TimeZone -ListAvailable
```

<span data-ttu-id="47bcc-118">Эта команда возвращает все доступные часовые пояса.</span><span class="sxs-lookup"><span data-stu-id="47bcc-118">This command gets all available time zones.</span></span>

## <span data-ttu-id="47bcc-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="47bcc-119">PARAMETERS</span></span>

### <span data-ttu-id="47bcc-120">-Id</span><span class="sxs-lookup"><span data-stu-id="47bcc-120">-Id</span></span>

<span data-ttu-id="47bcc-121">Указывает в виде массива строк идентификатор или идентификаторы часовых поясов, которые получает этот командлет.</span><span class="sxs-lookup"><span data-stu-id="47bcc-121">Specifies, as a string array, the ID or IDs of the time zones that this cmdlet gets.</span></span>

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

### <span data-ttu-id="47bcc-122">-ListAvailable</span><span class="sxs-lookup"><span data-stu-id="47bcc-122">-ListAvailable</span></span>

<span data-ttu-id="47bcc-123">Указывает, что этот командлет получает все доступные часовые пояса.</span><span class="sxs-lookup"><span data-stu-id="47bcc-123">Indicates that this cmdlet gets all available time zones.</span></span>

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

### <span data-ttu-id="47bcc-124">-Name</span><span class="sxs-lookup"><span data-stu-id="47bcc-124">-Name</span></span>

<span data-ttu-id="47bcc-125">Указывает в виде массива строк имя или имена часовых поясов, которые получает этот командлет.</span><span class="sxs-lookup"><span data-stu-id="47bcc-125">Specifies, as a string array, the name or names of the time zones that this cmdlet gets.</span></span>

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

### <span data-ttu-id="47bcc-126">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="47bcc-126">CommonParameters</span></span>

<span data-ttu-id="47bcc-127">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="47bcc-127">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="47bcc-128">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="47bcc-128">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="47bcc-129">Входные данные</span><span class="sxs-lookup"><span data-stu-id="47bcc-129">INPUTS</span></span>

### <span data-ttu-id="47bcc-130">System.String[]</span><span class="sxs-lookup"><span data-stu-id="47bcc-130">System.String[]</span></span>

## <span data-ttu-id="47bcc-131">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="47bcc-131">OUTPUTS</span></span>

### <span data-ttu-id="47bcc-132">System. TimeZoneInfo []</span><span class="sxs-lookup"><span data-stu-id="47bcc-132">System.TimeZoneInfo[]</span></span>

## <span data-ttu-id="47bcc-133">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="47bcc-133">NOTES</span></span>

<span data-ttu-id="47bcc-134">Этот командлет доступен только на платформах Windows.</span><span class="sxs-lookup"><span data-stu-id="47bcc-134">This cmdlet is only available on Windows platforms.</span></span>

## <span data-ttu-id="47bcc-135">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="47bcc-135">RELATED LINKS</span></span>

[<span data-ttu-id="47bcc-136">Set-TimeZone</span><span class="sxs-lookup"><span data-stu-id="47bcc-136">Set-TimeZone</span></span>](Set-TimeZone.md)
