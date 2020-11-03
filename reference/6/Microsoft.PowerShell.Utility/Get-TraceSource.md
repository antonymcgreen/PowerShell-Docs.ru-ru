---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-tracesource?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-TraceSource
ms.openlocfilehash: d136dd46eaceb65b5c512e3ff5c98e13d685d45e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228982"
---
# <span data-ttu-id="d2857-103">Get-TraceSource</span><span class="sxs-lookup"><span data-stu-id="d2857-103">Get-TraceSource</span></span>

## <span data-ttu-id="d2857-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="d2857-104">SYNOPSIS</span></span>
<span data-ttu-id="d2857-105">Возвращает компоненты PowerShell, инструментированные для трассировки.</span><span class="sxs-lookup"><span data-stu-id="d2857-105">Gets PowerShell components that are instrumented for tracing.</span></span>

## <span data-ttu-id="d2857-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d2857-106">SYNTAX</span></span>

```
Get-TraceSource [[-Name] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="d2857-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d2857-107">DESCRIPTION</span></span>

<span data-ttu-id="d2857-108">Командлет **Get-TraceSource** получает источники трассировки для компонентов PowerShell, которые используются в данный момент.</span><span class="sxs-lookup"><span data-stu-id="d2857-108">The **Get-TraceSource** cmdlet gets the trace sources for PowerShell components that are currently in use.</span></span>
<span data-ttu-id="d2857-109">Данные можно использовать для определения компонентов PowerShell, которые можно отслеживать.</span><span class="sxs-lookup"><span data-stu-id="d2857-109">You can use the data to determine which PowerShell components you can trace.</span></span>
<span data-ttu-id="d2857-110">При трассировке компонент создает подробные сообщения о каждом шаге внутренней обработки.</span><span class="sxs-lookup"><span data-stu-id="d2857-110">When tracing, the component generates detailed messages about each step in its internal processing.</span></span>
<span data-ttu-id="d2857-111">Разработчики используют данные трассировки для мониторинга потока данных, выполнения программ и ошибок.</span><span class="sxs-lookup"><span data-stu-id="d2857-111">Developers use the trace data to monitor data flow, program execution, and errors.</span></span>

<span data-ttu-id="d2857-112">Командлеты трассировки были разработаны для разработчиков PowerShell, но они доступны всем пользователям.</span><span class="sxs-lookup"><span data-stu-id="d2857-112">The tracing cmdlets were designed for PowerShell developers, but they are available to all users.</span></span>

## <span data-ttu-id="d2857-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="d2857-113">EXAMPLES</span></span>

### <span data-ttu-id="d2857-114">Пример 1. получение источников трассировки по имени</span><span class="sxs-lookup"><span data-stu-id="d2857-114">Example 1: Get trace sources by name</span></span>

```
PS C:\> Get-TraceSource -Name "*provider*"
```

<span data-ttu-id="d2857-115">Эта команда возвращает все источники трассировки с именами, которые включают в себя поставщик.</span><span class="sxs-lookup"><span data-stu-id="d2857-115">This command gets all of the trace sources that have names that include provider.</span></span>

### <span data-ttu-id="d2857-116">Пример 2. получение всех источников трассировки</span><span class="sxs-lookup"><span data-stu-id="d2857-116">Example 2: Get all trace sources</span></span>

```
PS C:\> Get-TraceSource
```

<span data-ttu-id="d2857-117">Эта команда возвращает все компоненты PowerShell, которые можно отслеживать.</span><span class="sxs-lookup"><span data-stu-id="d2857-117">This command gets all of the PowerShell components that can be traced.</span></span>

## <span data-ttu-id="d2857-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d2857-118">PARAMETERS</span></span>

### <span data-ttu-id="d2857-119">-Name</span><span class="sxs-lookup"><span data-stu-id="d2857-119">-Name</span></span>

<span data-ttu-id="d2857-120">Указывает получаемые источники трассировки.</span><span class="sxs-lookup"><span data-stu-id="d2857-120">Specifies the trace sources to get.</span></span>
<span data-ttu-id="d2857-121">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="d2857-121">Wildcards are permitted.</span></span>
<span data-ttu-id="d2857-122">*Имя параметра является* необязательным.</span><span class="sxs-lookup"><span data-stu-id="d2857-122">The parameter name *Name* is optional.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="d2857-123">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="d2857-123">CommonParameters</span></span>

<span data-ttu-id="d2857-124">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="d2857-124">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d2857-125">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="d2857-125">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d2857-126">Входные данные</span><span class="sxs-lookup"><span data-stu-id="d2857-126">INPUTS</span></span>

### <span data-ttu-id="d2857-127">System.String</span><span class="sxs-lookup"><span data-stu-id="d2857-127">System.String</span></span>

<span data-ttu-id="d2857-128">Строку, содержащую имя источника трассировки, можно передать в командлет **Get-TraceSource** по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="d2857-128">You can pipe a string that contains the name of a trace source to **Get-TraceSource** .</span></span>

## <span data-ttu-id="d2857-129">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="d2857-129">OUTPUTS</span></span>

### <span data-ttu-id="d2857-130">System. Management. Automation. Пстрацесаурце</span><span class="sxs-lookup"><span data-stu-id="d2857-130">System.Management.Automation.PSTraceSource</span></span>

<span data-ttu-id="d2857-131">Командлет **Get-TraceSource** возвращает объекты, представляющие источники трассировки.</span><span class="sxs-lookup"><span data-stu-id="d2857-131">**Get-TraceSource** returns objects that represent the trace sources.</span></span>

## <span data-ttu-id="d2857-132">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="d2857-132">NOTES</span></span>

## <span data-ttu-id="d2857-133">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="d2857-133">RELATED LINKS</span></span>

[<span data-ttu-id="d2857-134">Set-TraceSource</span><span class="sxs-lookup"><span data-stu-id="d2857-134">Set-TraceSource</span></span>](Set-TraceSource.md)

[<span data-ttu-id="d2857-135">Trace-Command</span><span class="sxs-lookup"><span data-stu-id="d2857-135">Trace-Command</span></span>](Trace-Command.md)
