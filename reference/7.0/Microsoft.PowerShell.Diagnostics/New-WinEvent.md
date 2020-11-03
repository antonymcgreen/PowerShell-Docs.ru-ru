---
external help file: Microsoft.PowerShell.Commands.Diagnostics.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Diagnostics
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.diagnostics/new-winevent?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-WinEvent
ms.openlocfilehash: 8e64c3e3a782fadf1669f1310d1615f3a014ccee
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93225666"
---
# <span data-ttu-id="dee09-103">New-WinEvent</span><span class="sxs-lookup"><span data-stu-id="dee09-103">New-WinEvent</span></span>

## <span data-ttu-id="dee09-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="dee09-104">SYNOPSIS</span></span>
<span data-ttu-id="dee09-105">Создает новое событие Windows для указанного поставщика событий.</span><span class="sxs-lookup"><span data-stu-id="dee09-105">Creates a new Windows event for the specified event provider.</span></span>

## <span data-ttu-id="dee09-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="dee09-106">SYNTAX</span></span>

```
New-WinEvent [-ProviderName] <String> [-Id] <Int32> [-Version <Byte>] [[-Payload] <Object[]>]
 [<CommonParameters>]
```

## <span data-ttu-id="dee09-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="dee09-107">DESCRIPTION</span></span>

<span data-ttu-id="dee09-108">Командлет **New-WinEvent** создает событие "Трассировка событий Windows (ETW)" для поставщика событий.</span><span class="sxs-lookup"><span data-stu-id="dee09-108">The **New-WinEvent** cmdlet creates an Event Tracing for Windows (ETW) event for an event provider.</span></span>
<span data-ttu-id="dee09-109">С помощью этого командлета можно добавлять события в каналы ETW из PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dee09-109">You can use this cmdlet to add events to ETW channels from PowerShell.</span></span>

## <span data-ttu-id="dee09-110">Примеры</span><span class="sxs-lookup"><span data-stu-id="dee09-110">EXAMPLES</span></span>

### <span data-ttu-id="dee09-111">Пример 1</span><span class="sxs-lookup"><span data-stu-id="dee09-111">Example 1</span></span>

```powershell
PS C:\> New-WinEvent -ProviderName Microsoft-Windows-PowerShell -Id 45090 -Payload @("Workflow", "Running")
```

<span data-ttu-id="dee09-112">В этой команде командлет **New-WinEvent** используется для создания события 45090 для поставщика Microsoft-Windows-PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dee09-112">This command uses the **New-WinEvent** cmdlet to create event 45090 for the Microsoft-Windows-PowerShell provider.</span></span>

## <span data-ttu-id="dee09-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="dee09-113">PARAMETERS</span></span>

### <span data-ttu-id="dee09-114">-Id</span><span class="sxs-lookup"><span data-stu-id="dee09-114">-Id</span></span>

<span data-ttu-id="dee09-115">Указывает идентификатор события, зарегистрированный посредством манифеста инструментария.</span><span class="sxs-lookup"><span data-stu-id="dee09-115">Specifies an event id that was registered through an instrumentation manifest.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="dee09-116">Полезные данные</span><span class="sxs-lookup"><span data-stu-id="dee09-116">-Payload</span></span>

<span data-ttu-id="dee09-117">Указывает сообщение события.</span><span class="sxs-lookup"><span data-stu-id="dee09-117">Specifies the message for the event.</span></span> <span data-ttu-id="dee09-118">Когда событие записывается в журнал событий, полезные данные сохраняются в свойстве **Message** объекта события.</span><span class="sxs-lookup"><span data-stu-id="dee09-118">When the event is written to an event log, the payload is stored in the **Message** property of the event object.</span></span>

<span data-ttu-id="dee09-119">Если указанные полезные данные не соответствуют полезной нагрузке в определении события, PowerShell выдает предупреждение, но команда по-прежнему выполняется.</span><span class="sxs-lookup"><span data-stu-id="dee09-119">When the specified payload does not match the payload in the event definition, PowerShell generates a warning, but the command still succeeds.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="dee09-120">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="dee09-120">-ProviderName</span></span>

<span data-ttu-id="dee09-121">Указывает поставщика событий, который записывает событие в журнал событий, например Microsoft-Windows-PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dee09-121">Specifies the event provider that writes the event to an event log, such as "Microsoft-Windows-PowerShell".</span></span> <span data-ttu-id="dee09-122">Поставщик событий ETW — это логическая сущность, которая записывает события в сеансы ETW.</span><span class="sxs-lookup"><span data-stu-id="dee09-122">An ETW event provider is a logical entity that writes events to ETW sessions.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="dee09-123">-Version</span><span class="sxs-lookup"><span data-stu-id="dee09-123">-Version</span></span>

<span data-ttu-id="dee09-124">Указывает номер версии события.</span><span class="sxs-lookup"><span data-stu-id="dee09-124">Specifies the version number of the event.</span></span> <span data-ttu-id="dee09-125">Введите номер события.</span><span class="sxs-lookup"><span data-stu-id="dee09-125">Type the event number.</span></span> <span data-ttu-id="dee09-126">PowerShell преобразует число в требуемый тип Byte.</span><span class="sxs-lookup"><span data-stu-id="dee09-126">PowerShell converts the number to the required Byte type.</span></span>

<span data-ttu-id="dee09-127">Этот параметр позволяет указать событие, если определены разные версии одного и того же события.</span><span class="sxs-lookup"><span data-stu-id="dee09-127">This parameter lets you specify an event when different versions of the same event are defined.</span></span>

```yaml
Type: System.Byte
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="dee09-128">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="dee09-128">CommonParameters</span></span>

<span data-ttu-id="dee09-129">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="dee09-129">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="dee09-130">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="dee09-130">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="dee09-131">Входные данные</span><span class="sxs-lookup"><span data-stu-id="dee09-131">INPUTS</span></span>

### <span data-ttu-id="dee09-132">Нет</span><span class="sxs-lookup"><span data-stu-id="dee09-132">None</span></span>

<span data-ttu-id="dee09-133">Этот командлет не принимает входные данные по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="dee09-133">This cmdlet does not take input from the pipeline.</span></span>

## <span data-ttu-id="dee09-134">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="dee09-134">OUTPUTS</span></span>

### <span data-ttu-id="dee09-135">Нет</span><span class="sxs-lookup"><span data-stu-id="dee09-135">None</span></span>

<span data-ttu-id="dee09-136">Этот командлет не создает никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="dee09-136">This cmdlet does to generate any output.</span></span>

## <span data-ttu-id="dee09-137">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="dee09-137">NOTES</span></span>

* <span data-ttu-id="dee09-138">После того как поставщик записывает данные в журнал событий, можно использовать командлет Get-WinEvent, чтобы получить событие из журнала.</span><span class="sxs-lookup"><span data-stu-id="dee09-138">After the provider writes the even to an eventlog, you can use the Get-WinEvent cmdlet to get the event from the event log.</span></span>

## <span data-ttu-id="dee09-139">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="dee09-139">RELATED LINKS</span></span>

[<span data-ttu-id="dee09-140">Get-WinEvent</span><span class="sxs-lookup"><span data-stu-id="dee09-140">Get-WinEvent</span></span>](Get-WinEvent.md)
