---
external help file: PSDiagnostics-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/27/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/stop-trace?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-Trace
ms.openlocfilehash: 7331c7ca1ece02757859e75eefddd5a662353beb
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93226509"
---
# <span data-ttu-id="8919b-103">Stop-Trace</span><span class="sxs-lookup"><span data-stu-id="8919b-103">Stop-Trace</span></span>

## <span data-ttu-id="8919b-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="8919b-104">SYNOPSIS</span></span>
<span data-ttu-id="8919b-105">Останавливает сеанс ведения журнала трассировки событий.</span><span class="sxs-lookup"><span data-stu-id="8919b-105">Stop an Event Trace logging session.</span></span>

## <span data-ttu-id="8919b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8919b-106">SYNTAX</span></span>

```
Stop-Trace [-SessionName] <Object> [-ETS] [<CommonParameters>]
```

## <span data-ttu-id="8919b-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="8919b-107">DESCRIPTION</span></span>

<span data-ttu-id="8919b-108">Этот командлет останавливает сеанс ведения журнала трассировки событий Windows.</span><span class="sxs-lookup"><span data-stu-id="8919b-108">This cmdlet stops a Windows Event Trace logging session.</span></span>

<span data-ttu-id="8919b-109">Этот командлет используется следующими командлетами:</span><span class="sxs-lookup"><span data-stu-id="8919b-109">This cmdlet is used by the following cmdlets:</span></span>

- `Disable-PSWSManCombinedTrace`
- `Disable-WSManTrace`

<span data-ttu-id="8919b-110">Этот командлет необходимо запустить из сеанса PowerShell с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="8919b-110">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="8919b-111">Примеры</span><span class="sxs-lookup"><span data-stu-id="8919b-111">EXAMPLES</span></span>

### <span data-ttu-id="8919b-112">Пример 1. Завершение сеанса ведения журнала трассировки WSMan</span><span class="sxs-lookup"><span data-stu-id="8919b-112">Example 1: Stop a WSMan Trace logging session</span></span>

```powershell
Stop-Trace -SessionName 'wsmlog'
```

## <span data-ttu-id="8919b-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8919b-113">PARAMETERS</span></span>

### <span data-ttu-id="8919b-114">-ETS</span><span class="sxs-lookup"><span data-stu-id="8919b-114">-ETS</span></span>
<span data-ttu-id="8919b-115">Отправка команд в сеансы трассировки событий напрямую без сохранения или планирования.</span><span class="sxs-lookup"><span data-stu-id="8919b-115">Send commands to Event Trace Sessions directly without saving or scheduling.</span></span>

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

### <span data-ttu-id="8919b-116">-SessionName</span><span class="sxs-lookup"><span data-stu-id="8919b-116">-SessionName</span></span>
<span data-ttu-id="8919b-117">Имя останавливаемого сеанса трассировки событий.</span><span class="sxs-lookup"><span data-stu-id="8919b-117">The name of the Event Trace session to be stopped.</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8919b-118">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="8919b-118">CommonParameters</span></span>
<span data-ttu-id="8919b-119">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="8919b-119">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="8919b-120">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="8919b-120">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="8919b-121">Входные данные</span><span class="sxs-lookup"><span data-stu-id="8919b-121">INPUTS</span></span>

### <span data-ttu-id="8919b-122">Нет</span><span class="sxs-lookup"><span data-stu-id="8919b-122">None</span></span>

## <span data-ttu-id="8919b-123">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="8919b-123">OUTPUTS</span></span>

### <span data-ttu-id="8919b-124">Нет</span><span class="sxs-lookup"><span data-stu-id="8919b-124">None</span></span>

## <span data-ttu-id="8919b-125">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="8919b-125">NOTES</span></span>

## <span data-ttu-id="8919b-126">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="8919b-126">RELATED LINKS</span></span>

[<span data-ttu-id="8919b-127">Трассировка событий</span><span class="sxs-lookup"><span data-stu-id="8919b-127">Event Tracing</span></span>](/windows/desktop/ETW/event-tracing-portal)

[<span data-ttu-id="8919b-128">Start-Trace</span><span class="sxs-lookup"><span data-stu-id="8919b-128">Start-Trace</span></span>](start-trace.md)

[<span data-ttu-id="8919b-129">Disable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="8919b-129">Disable-PSWSManCombinedTrace</span></span>](Disable-PSWSManCombinedTrace.md)

[<span data-ttu-id="8919b-130">Disable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="8919b-130">Disable-WSManTrace</span></span>](Disable-WSManTrace.md)

[<span data-ttu-id="8919b-131">Enable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="8919b-131">Enable-PSWSManCombinedTrace</span></span>](Enable-PSWSManCombinedTrace.md)

[<span data-ttu-id="8919b-132">Enable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="8919b-132">Enable-WSManTrace</span></span>](Enable-WSManTrace.md)

