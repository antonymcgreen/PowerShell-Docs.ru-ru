---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-tracesource?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-TraceSource
ms.openlocfilehash: 024fa690ff9ddd4eae2d7fd6203e83f56fef6cd7
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93226038"
---
# <span data-ttu-id="ce45a-103">Get-TraceSource</span><span class="sxs-lookup"><span data-stu-id="ce45a-103">Get-TraceSource</span></span>

## <span data-ttu-id="ce45a-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="ce45a-104">SYNOPSIS</span></span>
<span data-ttu-id="ce45a-105">Возвращает компоненты PowerShell, инструментированные для трассировки.</span><span class="sxs-lookup"><span data-stu-id="ce45a-105">Gets PowerShell components that are instrumented for tracing.</span></span>

## <span data-ttu-id="ce45a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ce45a-106">SYNTAX</span></span>

```
Get-TraceSource [[-Name] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="ce45a-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ce45a-107">DESCRIPTION</span></span>

<span data-ttu-id="ce45a-108">Командлет **Get-TraceSource** получает источники трассировки для компонентов PowerShell, которые используются в данный момент.</span><span class="sxs-lookup"><span data-stu-id="ce45a-108">The **Get-TraceSource** cmdlet gets the trace sources for PowerShell components that are currently in use.</span></span>
<span data-ttu-id="ce45a-109">Данные можно использовать для определения компонентов PowerShell, которые можно отслеживать.</span><span class="sxs-lookup"><span data-stu-id="ce45a-109">You can use the data to determine which PowerShell components you can trace.</span></span>
<span data-ttu-id="ce45a-110">При трассировке компонент создает подробные сообщения о каждом шаге внутренней обработки.</span><span class="sxs-lookup"><span data-stu-id="ce45a-110">When tracing, the component generates detailed messages about each step in its internal processing.</span></span>
<span data-ttu-id="ce45a-111">Разработчики используют данные трассировки для мониторинга потока данных, выполнения программ и ошибок.</span><span class="sxs-lookup"><span data-stu-id="ce45a-111">Developers use the trace data to monitor data flow, program execution, and errors.</span></span>

<span data-ttu-id="ce45a-112">Командлеты трассировки были разработаны для разработчиков PowerShell, но они доступны всем пользователям.</span><span class="sxs-lookup"><span data-stu-id="ce45a-112">The tracing cmdlets were designed for PowerShell developers, but they are available to all users.</span></span>

## <span data-ttu-id="ce45a-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="ce45a-113">EXAMPLES</span></span>

### <span data-ttu-id="ce45a-114">Пример 1. получение источников трассировки по имени</span><span class="sxs-lookup"><span data-stu-id="ce45a-114">Example 1: Get trace sources by name</span></span>

```
PS C:\> Get-TraceSource -Name "*provider*"
```

<span data-ttu-id="ce45a-115">Эта команда возвращает все источники трассировки с именами, которые включают в себя поставщик.</span><span class="sxs-lookup"><span data-stu-id="ce45a-115">This command gets all of the trace sources that have names that include provider.</span></span>

### <span data-ttu-id="ce45a-116">Пример 2. получение всех источников трассировки</span><span class="sxs-lookup"><span data-stu-id="ce45a-116">Example 2: Get all trace sources</span></span>

```
PS C:\> Get-TraceSource
```

<span data-ttu-id="ce45a-117">Эта команда возвращает все компоненты PowerShell, которые можно отслеживать.</span><span class="sxs-lookup"><span data-stu-id="ce45a-117">This command gets all of the PowerShell components that can be traced.</span></span>

## <span data-ttu-id="ce45a-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ce45a-118">PARAMETERS</span></span>

### <span data-ttu-id="ce45a-119">-Name</span><span class="sxs-lookup"><span data-stu-id="ce45a-119">-Name</span></span>

<span data-ttu-id="ce45a-120">Указывает получаемые источники трассировки.</span><span class="sxs-lookup"><span data-stu-id="ce45a-120">Specifies the trace sources to get.</span></span>
<span data-ttu-id="ce45a-121">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="ce45a-121">Wildcards are permitted.</span></span>
<span data-ttu-id="ce45a-122">*Имя параметра является* необязательным.</span><span class="sxs-lookup"><span data-stu-id="ce45a-122">The parameter name *Name* is optional.</span></span>

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

### <span data-ttu-id="ce45a-123">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="ce45a-123">CommonParameters</span></span>

<span data-ttu-id="ce45a-124">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="ce45a-124">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ce45a-125">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="ce45a-125">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ce45a-126">Входные данные</span><span class="sxs-lookup"><span data-stu-id="ce45a-126">INPUTS</span></span>

### <span data-ttu-id="ce45a-127">System.String</span><span class="sxs-lookup"><span data-stu-id="ce45a-127">System.String</span></span>

<span data-ttu-id="ce45a-128">Строку, содержащую имя источника трассировки, можно передать в командлет **Get-TraceSource** по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="ce45a-128">You can pipe a string that contains the name of a trace source to **Get-TraceSource**.</span></span>

## <span data-ttu-id="ce45a-129">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="ce45a-129">OUTPUTS</span></span>

### <span data-ttu-id="ce45a-130">System. Management. Automation. Пстрацесаурце</span><span class="sxs-lookup"><span data-stu-id="ce45a-130">System.Management.Automation.PSTraceSource</span></span>

<span data-ttu-id="ce45a-131">Командлет **Get-TraceSource** возвращает объекты, представляющие источники трассировки.</span><span class="sxs-lookup"><span data-stu-id="ce45a-131">**Get-TraceSource** returns objects that represent the trace sources.</span></span>

## <span data-ttu-id="ce45a-132">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="ce45a-132">NOTES</span></span>

## <span data-ttu-id="ce45a-133">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="ce45a-133">RELATED LINKS</span></span>

[<span data-ttu-id="ce45a-134">Set-TraceSource</span><span class="sxs-lookup"><span data-stu-id="ce45a-134">Set-TraceSource</span></span>](Set-TraceSource.md)

[<span data-ttu-id="ce45a-135">Trace-Command</span><span class="sxs-lookup"><span data-stu-id="ce45a-135">Trace-Command</span></span>](Trace-Command.md)
