---
external help file: Microsoft.PowerShell.Commands.Diagnostics.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Diagnostics
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.diagnostics/new-winevent?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-WinEvent
ms.openlocfilehash: 5b4b150a1c02e5d0689b44db9b2a984e297db766
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600198"
---
# <span data-ttu-id="91f10-102">New-WinEvent</span><span class="sxs-lookup"><span data-stu-id="91f10-102">New-WinEvent</span></span>

## <span data-ttu-id="91f10-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="91f10-103">SYNOPSIS</span></span>
<span data-ttu-id="91f10-104">Создает новое событие Windows для указанного поставщика событий.</span><span class="sxs-lookup"><span data-stu-id="91f10-104">Creates a new Windows event for the specified event provider.</span></span>

## <span data-ttu-id="91f10-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="91f10-105">SYNTAX</span></span>

```
New-WinEvent [-ProviderName] <String> [-Id] <Int32> [-Version <Byte>] [[-Payload] <Object[]>]
 [<CommonParameters>]
```

## <span data-ttu-id="91f10-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="91f10-106">DESCRIPTION</span></span>

<span data-ttu-id="91f10-107">Командлет **New-WinEvent** создает событие "Трассировка событий Windows (ETW)" для поставщика событий.</span><span class="sxs-lookup"><span data-stu-id="91f10-107">The **New-WinEvent** cmdlet creates an Event Tracing for Windows (ETW) event for an event provider.</span></span>
<span data-ttu-id="91f10-108">С помощью этого командлета можно добавлять события в каналы ETW из PowerShell.</span><span class="sxs-lookup"><span data-stu-id="91f10-108">You can use this cmdlet to add events to ETW channels from PowerShell.</span></span>

## <span data-ttu-id="91f10-109">Примеры</span><span class="sxs-lookup"><span data-stu-id="91f10-109">EXAMPLES</span></span>

### <span data-ttu-id="91f10-110">Пример 1</span><span class="sxs-lookup"><span data-stu-id="91f10-110">Example 1</span></span>

```powershell
PS C:\> New-WinEvent -ProviderName Microsoft-Windows-PowerShell -Id 45090 -Payload @("Workflow", "Running")
```

<span data-ttu-id="91f10-111">В этой команде командлет **New-WinEvent** используется для создания события 45090 для поставщика Microsoft-Windows-PowerShell.</span><span class="sxs-lookup"><span data-stu-id="91f10-111">This command uses the **New-WinEvent** cmdlet to create event 45090 for the Microsoft-Windows-PowerShell provider.</span></span>

## <span data-ttu-id="91f10-112">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="91f10-112">PARAMETERS</span></span>

### <span data-ttu-id="91f10-113">-Id</span><span class="sxs-lookup"><span data-stu-id="91f10-113">-Id</span></span>

<span data-ttu-id="91f10-114">Указывает идентификатор события, зарегистрированный посредством манифеста инструментария.</span><span class="sxs-lookup"><span data-stu-id="91f10-114">Specifies an event id that was registered through an instrumentation manifest.</span></span>

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

### <span data-ttu-id="91f10-115">Полезные данные</span><span class="sxs-lookup"><span data-stu-id="91f10-115">-Payload</span></span>

<span data-ttu-id="91f10-116">Указывает сообщение события.</span><span class="sxs-lookup"><span data-stu-id="91f10-116">Specifies the message for the event.</span></span> <span data-ttu-id="91f10-117">Когда событие записывается в журнал событий, полезные данные сохраняются в свойстве **Message** объекта события.</span><span class="sxs-lookup"><span data-stu-id="91f10-117">When the event is written to an event log, the payload is stored in the **Message** property of the event object.</span></span>

<span data-ttu-id="91f10-118">Если указанные полезные данные не соответствуют полезной нагрузке в определении события, PowerShell выдает предупреждение, но команда по-прежнему выполняется.</span><span class="sxs-lookup"><span data-stu-id="91f10-118">When the specified payload does not match the payload in the event definition, PowerShell generates a warning, but the command still succeeds.</span></span>

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

### <span data-ttu-id="91f10-119">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="91f10-119">-ProviderName</span></span>

<span data-ttu-id="91f10-120">Указывает поставщика событий, который записывает событие в журнал событий, например Microsoft-Windows-PowerShell.</span><span class="sxs-lookup"><span data-stu-id="91f10-120">Specifies the event provider that writes the event to an event log, such as "Microsoft-Windows-PowerShell".</span></span> <span data-ttu-id="91f10-121">Поставщик событий ETW — это логическая сущность, которая записывает события в сеансы ETW.</span><span class="sxs-lookup"><span data-stu-id="91f10-121">An ETW event provider is a logical entity that writes events to ETW sessions.</span></span>

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

### <span data-ttu-id="91f10-122">-Version</span><span class="sxs-lookup"><span data-stu-id="91f10-122">-Version</span></span>

<span data-ttu-id="91f10-123">Указывает номер версии события.</span><span class="sxs-lookup"><span data-stu-id="91f10-123">Specifies the version number of the event.</span></span> <span data-ttu-id="91f10-124">Введите номер события.</span><span class="sxs-lookup"><span data-stu-id="91f10-124">Type the event number.</span></span> <span data-ttu-id="91f10-125">PowerShell преобразует число в требуемый тип Byte.</span><span class="sxs-lookup"><span data-stu-id="91f10-125">PowerShell converts the number to the required Byte type.</span></span>

<span data-ttu-id="91f10-126">Этот параметр позволяет указать событие, если определены разные версии одного и того же события.</span><span class="sxs-lookup"><span data-stu-id="91f10-126">This parameter lets you specify an event when different versions of the same event are defined.</span></span>

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

### <span data-ttu-id="91f10-127">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="91f10-127">CommonParameters</span></span>

<span data-ttu-id="91f10-128">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="91f10-128">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="91f10-129">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="91f10-129">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="91f10-130">Входные данные</span><span class="sxs-lookup"><span data-stu-id="91f10-130">INPUTS</span></span>

### <span data-ttu-id="91f10-131">None</span><span class="sxs-lookup"><span data-stu-id="91f10-131">None</span></span>

<span data-ttu-id="91f10-132">Этот командлет не принимает входные данные по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="91f10-132">This cmdlet does not take input from the pipeline.</span></span>

## <span data-ttu-id="91f10-133">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="91f10-133">OUTPUTS</span></span>

### <span data-ttu-id="91f10-134">None</span><span class="sxs-lookup"><span data-stu-id="91f10-134">None</span></span>

<span data-ttu-id="91f10-135">Этот командлет не создает никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="91f10-135">This cmdlet does to generate any output.</span></span>

## <span data-ttu-id="91f10-136">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="91f10-136">NOTES</span></span>

* <span data-ttu-id="91f10-137">После того как поставщик записывает данные в журнал событий, можно использовать командлет Get-WinEvent, чтобы получить событие из журнала.</span><span class="sxs-lookup"><span data-stu-id="91f10-137">After the provider writes the even to an eventlog, you can use the Get-WinEvent cmdlet to get the event from the event log.</span></span>

## <span data-ttu-id="91f10-138">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="91f10-138">RELATED LINKS</span></span>

[<span data-ttu-id="91f10-139">Get-WinEvent</span><span class="sxs-lookup"><span data-stu-id="91f10-139">Get-WinEvent</span></span>](Get-WinEvent.md)

