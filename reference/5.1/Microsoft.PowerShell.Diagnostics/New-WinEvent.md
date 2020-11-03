---
external help file: Microsoft.PowerShell.Commands.Diagnostics.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Diagnostics
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.diagnostics/new-winevent?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-WinEvent
ms.openlocfilehash: 202d1792769dcdcda7a156621bfc50c89a1a92ac
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93226638"
---
# <span data-ttu-id="97b26-103">New-WinEvent</span><span class="sxs-lookup"><span data-stu-id="97b26-103">New-WinEvent</span></span>

## <span data-ttu-id="97b26-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="97b26-104">SYNOPSIS</span></span>

<span data-ttu-id="97b26-105">Создает новое событие Windows для указанного поставщика событий.</span><span class="sxs-lookup"><span data-stu-id="97b26-105">Creates a new Windows event for the specified event provider.</span></span>

## <span data-ttu-id="97b26-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="97b26-106">SYNTAX</span></span>

```
New-WinEvent [-ProviderName] <String> [-Id] <Int32> [-Version <Byte>] [[-Payload] <Object[]>]
 [<CommonParameters>]
```

## <span data-ttu-id="97b26-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="97b26-107">DESCRIPTION</span></span>

<span data-ttu-id="97b26-108">Командлет **New-WinEvent** создает событие "Трассировка событий Windows (ETW)" для поставщика событий.</span><span class="sxs-lookup"><span data-stu-id="97b26-108">The **New-WinEvent** cmdlet creates an Event Tracing for Windows (ETW) event for an event provider.</span></span>
<span data-ttu-id="97b26-109">С помощью этого командлета можно добавлять события в каналы ETW из Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="97b26-109">You can use this cmdlet to add events to ETW channels from Windows PowerShell.</span></span>

## <span data-ttu-id="97b26-110">Примеры</span><span class="sxs-lookup"><span data-stu-id="97b26-110">EXAMPLES</span></span>

### <span data-ttu-id="97b26-111">Пример 1</span><span class="sxs-lookup"><span data-stu-id="97b26-111">Example 1</span></span>

```powershell
PS C:\> New-WinEvent -ProviderName Microsoft-Windows-PowerShell -Id 45090 -Payload @("Workflow", "Running")
```

<span data-ttu-id="97b26-112">В этой команде командлет **New-WinEvent** используется для создания события 45090 для поставщика Microsoft-Windows-PowerShell.</span><span class="sxs-lookup"><span data-stu-id="97b26-112">This command uses the **New-WinEvent** cmdlet to create event 45090 for the Microsoft-Windows-PowerShell provider.</span></span>

## <span data-ttu-id="97b26-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="97b26-113">PARAMETERS</span></span>

### <span data-ttu-id="97b26-114">-Id</span><span class="sxs-lookup"><span data-stu-id="97b26-114">-Id</span></span>

<span data-ttu-id="97b26-115">Указывает идентификатор события, зарегистрированный посредством манифеста инструментария.</span><span class="sxs-lookup"><span data-stu-id="97b26-115">Specifies an event id that was registered through an instrumentation manifest.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="97b26-116">Полезные данные</span><span class="sxs-lookup"><span data-stu-id="97b26-116">-Payload</span></span>

<span data-ttu-id="97b26-117">Указывает сообщение события.</span><span class="sxs-lookup"><span data-stu-id="97b26-117">Specifies the message for the event.</span></span> <span data-ttu-id="97b26-118">Когда событие записывается в журнал событий, полезные данные сохраняются в свойстве **Message** объекта события.</span><span class="sxs-lookup"><span data-stu-id="97b26-118">When the event is written to an event log, the payload is stored in the **Message** property of the event object.</span></span>

<span data-ttu-id="97b26-119">Если указанные полезные данные не соответствуют полезным данным в определении события, среда Windows PowerShell создает предупреждение, но команда завершается успешно.</span><span class="sxs-lookup"><span data-stu-id="97b26-119">When the specified payload does not match the payload in the event definition, Windows PowerShell generates a warning, but the command still succeeds.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="97b26-120">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="97b26-120">-ProviderName</span></span>

<span data-ttu-id="97b26-121">Указывает поставщика событий, который записывает событие в журнал событий, например Microsoft-Windows-PowerShell.</span><span class="sxs-lookup"><span data-stu-id="97b26-121">Specifies the event provider that writes the event to an event log, such as "Microsoft-Windows-PowerShell".</span></span> <span data-ttu-id="97b26-122">Поставщик событий ETW — это логическая сущность, которая записывает события в сеансы ETW.</span><span class="sxs-lookup"><span data-stu-id="97b26-122">An ETW event provider is a logical entity that writes events to ETW sessions.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="97b26-123">-Version</span><span class="sxs-lookup"><span data-stu-id="97b26-123">-Version</span></span>

<span data-ttu-id="97b26-124">Указывает номер версии события.</span><span class="sxs-lookup"><span data-stu-id="97b26-124">Specifies the version number of the event.</span></span> <span data-ttu-id="97b26-125">Введите номер события.</span><span class="sxs-lookup"><span data-stu-id="97b26-125">Type the event number.</span></span> <span data-ttu-id="97b26-126">Среда Windows PowerShell преобразует номер в требуемый тип Byte.</span><span class="sxs-lookup"><span data-stu-id="97b26-126">Windows PowerShell converts the number to the required Byte type.</span></span>

<span data-ttu-id="97b26-127">Этот параметр позволяет указать событие, если определены разные версии одного и того же события.</span><span class="sxs-lookup"><span data-stu-id="97b26-127">This parameter lets you specify an event when different versions of the same event are defined.</span></span>

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

### <span data-ttu-id="97b26-128">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="97b26-128">CommonParameters</span></span>

<span data-ttu-id="97b26-129">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="97b26-129">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="97b26-130">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="97b26-130">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="97b26-131">Входные данные</span><span class="sxs-lookup"><span data-stu-id="97b26-131">INPUTS</span></span>

### <span data-ttu-id="97b26-132">Нет</span><span class="sxs-lookup"><span data-stu-id="97b26-132">None</span></span>

<span data-ttu-id="97b26-133">Этот командлет не принимает входные данные по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="97b26-133">This cmdlet does not take input from the pipeline.</span></span>

## <span data-ttu-id="97b26-134">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="97b26-134">OUTPUTS</span></span>

### <span data-ttu-id="97b26-135">Нет</span><span class="sxs-lookup"><span data-stu-id="97b26-135">None</span></span>

<span data-ttu-id="97b26-136">Этот командлет не создает никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="97b26-136">This cmdlet does to generate any output.</span></span>

## <span data-ttu-id="97b26-137">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="97b26-137">NOTES</span></span>

* <span data-ttu-id="97b26-138">После того как поставщик записывает данные в журнал событий, можно использовать командлет Get-WinEvent, чтобы получить событие из журнала.</span><span class="sxs-lookup"><span data-stu-id="97b26-138">After the provider writes the even to an eventlog, you can use the Get-WinEvent cmdlet to get the event from the event log.</span></span>

## <span data-ttu-id="97b26-139">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="97b26-139">RELATED LINKS</span></span>

[<span data-ttu-id="97b26-140">Get-WinEvent</span><span class="sxs-lookup"><span data-stu-id="97b26-140">Get-WinEvent</span></span>](Get-WinEvent.md)
