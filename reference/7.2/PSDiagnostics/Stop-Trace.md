---
external help file: PSDiagnostics-help.xml
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/27/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/stop-trace?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-Trace
ms.openlocfilehash: 5727ae52326830fa16012722d0b801b7d43e50dd
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602484"
---
# <span data-ttu-id="4a022-102">Stop-Trace</span><span class="sxs-lookup"><span data-stu-id="4a022-102">Stop-Trace</span></span>

## <span data-ttu-id="4a022-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="4a022-103">SYNOPSIS</span></span>
<span data-ttu-id="4a022-104">Останавливает сеанс ведения журнала трассировки событий.</span><span class="sxs-lookup"><span data-stu-id="4a022-104">Stop an Event Trace logging session.</span></span>

## <span data-ttu-id="4a022-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4a022-105">SYNTAX</span></span>

```
Stop-Trace [-SessionName] <Object> [-ETS] [<CommonParameters>]
```

## <span data-ttu-id="4a022-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="4a022-106">DESCRIPTION</span></span>

<span data-ttu-id="4a022-107">Этот командлет останавливает сеанс ведения журнала трассировки событий Windows.</span><span class="sxs-lookup"><span data-stu-id="4a022-107">This cmdlet stops a Windows Event Trace logging session.</span></span>

<span data-ttu-id="4a022-108">Этот командлет используется следующими командлетами:</span><span class="sxs-lookup"><span data-stu-id="4a022-108">This cmdlet is used by the following cmdlets:</span></span>

- `Disable-PSWSManCombinedTrace`
- `Disable-WSManTrace`

<span data-ttu-id="4a022-109">Этот командлет необходимо запустить из сеанса PowerShell с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="4a022-109">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="4a022-110">Примеры</span><span class="sxs-lookup"><span data-stu-id="4a022-110">EXAMPLES</span></span>

### <span data-ttu-id="4a022-111">Пример 1. Завершение сеанса ведения журнала трассировки WSMan</span><span class="sxs-lookup"><span data-stu-id="4a022-111">Example 1: Stop a WSMan Trace logging session</span></span>

```powershell
Stop-Trace -SessionName 'wsmlog'
```

## <span data-ttu-id="4a022-112">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4a022-112">PARAMETERS</span></span>

### <span data-ttu-id="4a022-113">-ETS</span><span class="sxs-lookup"><span data-stu-id="4a022-113">-ETS</span></span>
<span data-ttu-id="4a022-114">Отправка команд в сеансы трассировки событий напрямую без сохранения или планирования.</span><span class="sxs-lookup"><span data-stu-id="4a022-114">Send commands to Event Trace Sessions directly without saving or scheduling.</span></span>

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

### <span data-ttu-id="4a022-115">-SessionName</span><span class="sxs-lookup"><span data-stu-id="4a022-115">-SessionName</span></span>
<span data-ttu-id="4a022-116">Имя останавливаемого сеанса трассировки событий.</span><span class="sxs-lookup"><span data-stu-id="4a022-116">The name of the Event Trace session to be stopped.</span></span>

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

### <span data-ttu-id="4a022-117">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="4a022-117">CommonParameters</span></span>
<span data-ttu-id="4a022-118">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="4a022-118">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4a022-119">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="4a022-119">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4a022-120">Входные данные</span><span class="sxs-lookup"><span data-stu-id="4a022-120">INPUTS</span></span>

### <span data-ttu-id="4a022-121">None</span><span class="sxs-lookup"><span data-stu-id="4a022-121">None</span></span>

## <span data-ttu-id="4a022-122">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="4a022-122">OUTPUTS</span></span>

### <span data-ttu-id="4a022-123">None</span><span class="sxs-lookup"><span data-stu-id="4a022-123">None</span></span>

## <span data-ttu-id="4a022-124">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="4a022-124">NOTES</span></span>

## <span data-ttu-id="4a022-125">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="4a022-125">RELATED LINKS</span></span>

[<span data-ttu-id="4a022-126">Трассировка событий</span><span class="sxs-lookup"><span data-stu-id="4a022-126">Event Tracing</span></span>](/windows/desktop/ETW/event-tracing-portal)

[<span data-ttu-id="4a022-127">Start-Trace</span><span class="sxs-lookup"><span data-stu-id="4a022-127">Start-Trace</span></span>](start-trace.md)

[<span data-ttu-id="4a022-128">Disable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="4a022-128">Disable-PSWSManCombinedTrace</span></span>](Disable-PSWSManCombinedTrace.md)

[<span data-ttu-id="4a022-129">Disable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="4a022-129">Disable-WSManTrace</span></span>](Disable-WSManTrace.md)

[<span data-ttu-id="4a022-130">Enable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="4a022-130">Enable-PSWSManCombinedTrace</span></span>](Enable-PSWSManCombinedTrace.md)

[<span data-ttu-id="4a022-131">Enable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="4a022-131">Enable-WSManTrace</span></span>](Enable-WSManTrace.md)

