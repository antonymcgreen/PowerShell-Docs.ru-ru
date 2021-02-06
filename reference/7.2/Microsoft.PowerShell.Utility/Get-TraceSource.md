---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-tracesource?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-TraceSource
ms.openlocfilehash: c196d00359c9b20b5dc1fefc0ab2b94655703f6f
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601612"
---
# <span data-ttu-id="ab443-102">Get-TraceSource</span><span class="sxs-lookup"><span data-stu-id="ab443-102">Get-TraceSource</span></span>

## <span data-ttu-id="ab443-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="ab443-103">SYNOPSIS</span></span>
<span data-ttu-id="ab443-104">Возвращает компоненты PowerShell, инструментированные для трассировки.</span><span class="sxs-lookup"><span data-stu-id="ab443-104">Gets PowerShell components that are instrumented for tracing.</span></span>

## <span data-ttu-id="ab443-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ab443-105">SYNTAX</span></span>

```
Get-TraceSource [[-Name] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="ab443-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ab443-106">DESCRIPTION</span></span>

<span data-ttu-id="ab443-107">Командлет **Get-TraceSource** получает источники трассировки для компонентов PowerShell, которые используются в данный момент.</span><span class="sxs-lookup"><span data-stu-id="ab443-107">The **Get-TraceSource** cmdlet gets the trace sources for PowerShell components that are currently in use.</span></span>
<span data-ttu-id="ab443-108">Данные можно использовать для определения компонентов PowerShell, которые можно отслеживать.</span><span class="sxs-lookup"><span data-stu-id="ab443-108">You can use the data to determine which PowerShell components you can trace.</span></span>
<span data-ttu-id="ab443-109">При трассировке компонент создает подробные сообщения о каждом шаге внутренней обработки.</span><span class="sxs-lookup"><span data-stu-id="ab443-109">When tracing, the component generates detailed messages about each step in its internal processing.</span></span>
<span data-ttu-id="ab443-110">Разработчики используют данные трассировки для мониторинга потока данных, выполнения программ и ошибок.</span><span class="sxs-lookup"><span data-stu-id="ab443-110">Developers use the trace data to monitor data flow, program execution, and errors.</span></span>

<span data-ttu-id="ab443-111">Командлеты трассировки были разработаны для разработчиков PowerShell, но они доступны всем пользователям.</span><span class="sxs-lookup"><span data-stu-id="ab443-111">The tracing cmdlets were designed for PowerShell developers, but they are available to all users.</span></span>

## <span data-ttu-id="ab443-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="ab443-112">EXAMPLES</span></span>

### <span data-ttu-id="ab443-113">Пример 1. получение источников трассировки по имени</span><span class="sxs-lookup"><span data-stu-id="ab443-113">Example 1: Get trace sources by name</span></span>

```
PS C:\> Get-TraceSource -Name "*provider*"
```

<span data-ttu-id="ab443-114">Эта команда возвращает все источники трассировки с именами, которые включают в себя поставщик.</span><span class="sxs-lookup"><span data-stu-id="ab443-114">This command gets all of the trace sources that have names that include provider.</span></span>

### <span data-ttu-id="ab443-115">Пример 2. получение всех источников трассировки</span><span class="sxs-lookup"><span data-stu-id="ab443-115">Example 2: Get all trace sources</span></span>

```
PS C:\> Get-TraceSource
```

<span data-ttu-id="ab443-116">Эта команда возвращает все компоненты PowerShell, которые можно отслеживать.</span><span class="sxs-lookup"><span data-stu-id="ab443-116">This command gets all of the PowerShell components that can be traced.</span></span>

## <span data-ttu-id="ab443-117">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ab443-117">PARAMETERS</span></span>

### <span data-ttu-id="ab443-118">-Name</span><span class="sxs-lookup"><span data-stu-id="ab443-118">-Name</span></span>

<span data-ttu-id="ab443-119">Указывает получаемые источники трассировки.</span><span class="sxs-lookup"><span data-stu-id="ab443-119">Specifies the trace sources to get.</span></span>
<span data-ttu-id="ab443-120">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="ab443-120">Wildcards are permitted.</span></span>
<span data-ttu-id="ab443-121">*Имя параметра является* необязательным.</span><span class="sxs-lookup"><span data-stu-id="ab443-121">The parameter name *Name* is optional.</span></span>

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

### <span data-ttu-id="ab443-122">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="ab443-122">CommonParameters</span></span>

<span data-ttu-id="ab443-123">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="ab443-123">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ab443-124">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="ab443-124">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ab443-125">Входные данные</span><span class="sxs-lookup"><span data-stu-id="ab443-125">INPUTS</span></span>

### <span data-ttu-id="ab443-126">System.String</span><span class="sxs-lookup"><span data-stu-id="ab443-126">System.String</span></span>

<span data-ttu-id="ab443-127">Строку, содержащую имя источника трассировки, можно передать в командлет **Get-TraceSource** по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="ab443-127">You can pipe a string that contains the name of a trace source to **Get-TraceSource**.</span></span>

## <span data-ttu-id="ab443-128">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="ab443-128">OUTPUTS</span></span>

### <span data-ttu-id="ab443-129">System. Management. Automation. Пстрацесаурце</span><span class="sxs-lookup"><span data-stu-id="ab443-129">System.Management.Automation.PSTraceSource</span></span>

<span data-ttu-id="ab443-130">Командлет **Get-TraceSource** возвращает объекты, представляющие источники трассировки.</span><span class="sxs-lookup"><span data-stu-id="ab443-130">**Get-TraceSource** returns objects that represent the trace sources.</span></span>

## <span data-ttu-id="ab443-131">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="ab443-131">NOTES</span></span>

## <span data-ttu-id="ab443-132">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="ab443-132">RELATED LINKS</span></span>

[<span data-ttu-id="ab443-133">Set-TraceSource</span><span class="sxs-lookup"><span data-stu-id="ab443-133">Set-TraceSource</span></span>](Set-TraceSource.md)

[<span data-ttu-id="ab443-134">Trace-Command</span><span class="sxs-lookup"><span data-stu-id="ab443-134">Trace-Command</span></span>](Trace-Command.md)

