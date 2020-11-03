---
external help file: PSDiagnostics-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/29/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/enable-pswsmancombinedtrace?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-PSWSManCombinedTrace
ms.openlocfilehash: f6b14ea6cda7d83792f7b51b854471a2cb62bfb5
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93225502"
---
# <span data-ttu-id="e84f1-103">Enable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="e84f1-103">Enable-PSWSManCombinedTrace</span></span>

## <span data-ttu-id="e84f1-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="e84f1-104">SYNOPSIS</span></span>
<span data-ttu-id="e84f1-105">Запустите сеанс ведения журнала с включенными поставщиками WSMan и PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e84f1-105">Start a logging session with the WSMan and PowerShell providers enabled.</span></span>

## <span data-ttu-id="e84f1-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e84f1-106">SYNTAX</span></span>

```
Enable-PSWSManCombinedTrace [-DoNotOverwriteExistingTrace] [<CommonParameters>]
```

## <span data-ttu-id="e84f1-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e84f1-107">DESCRIPTION</span></span>

<span data-ttu-id="e84f1-108">Этот командлет запускает сеанс ведения журнала со следующими включенными поставщиками PowerShell:</span><span class="sxs-lookup"><span data-stu-id="e84f1-108">This cmdlet starts a logging session with the following PowerShell providers enabled:</span></span>

- <span data-ttu-id="e84f1-109">Microsoft-Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e84f1-109">Microsoft-Windows-PowerShell</span></span>
- <span data-ttu-id="e84f1-110">Microsoft-Windows — WinRM</span><span class="sxs-lookup"><span data-stu-id="e84f1-110">Microsoft-Windows-WinRM</span></span>

<span data-ttu-id="e84f1-111">Сеанс называется "Пстраце".</span><span class="sxs-lookup"><span data-stu-id="e84f1-111">The session is named 'PSTrace'.</span></span>

<span data-ttu-id="e84f1-112">Этот командлет использует `Start-Trace` командлет.</span><span class="sxs-lookup"><span data-stu-id="e84f1-112">This cmdlet uses the `Start-Trace` cmdlet.</span></span>

<span data-ttu-id="e84f1-113">Этот командлет необходимо запустить из сеанса PowerShell с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="e84f1-113">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="e84f1-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="e84f1-114">EXAMPLES</span></span>

### <span data-ttu-id="e84f1-115">Пример 1. Запуск Объединенного сеанса ведения журнала</span><span class="sxs-lookup"><span data-stu-id="e84f1-115">Example 1: Start a combined logging session</span></span>

```powershell
Enable-PSWSManCombinedTrace
```

## <span data-ttu-id="e84f1-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e84f1-116">PARAMETERS</span></span>

### <span data-ttu-id="e84f1-117">-Донотовервритиксистингтраце</span><span class="sxs-lookup"><span data-stu-id="e84f1-117">-DoNotOverwriteExistingTrace</span></span>

<span data-ttu-id="e84f1-118">По умолчанию события записываются в "$pshome \Трацес\пстраце.ЕТЛ".</span><span class="sxs-lookup"><span data-stu-id="e84f1-118">By default, the events are written to "$pshome\Traces\PSTrace.etl".</span></span> <span data-ttu-id="e84f1-119">При использовании этого параметра командлет создает уникальное имя файла: "$pshome \Трацес\ PSTrace_ {GUID}. ETL".</span><span class="sxs-lookup"><span data-stu-id="e84f1-119">When this parameter is used, the cmdlet creates a unique filename: "$pshome\Traces\PSTrace_{guid}.etl"</span></span>

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

### <span data-ttu-id="e84f1-120">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="e84f1-120">CommonParameters</span></span>

<span data-ttu-id="e84f1-121">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="e84f1-121">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e84f1-122">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="e84f1-122">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e84f1-123">Входные данные</span><span class="sxs-lookup"><span data-stu-id="e84f1-123">INPUTS</span></span>

### <span data-ttu-id="e84f1-124">Нет</span><span class="sxs-lookup"><span data-stu-id="e84f1-124">None</span></span>

## <span data-ttu-id="e84f1-125">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="e84f1-125">OUTPUTS</span></span>

### <span data-ttu-id="e84f1-126">Нет</span><span class="sxs-lookup"><span data-stu-id="e84f1-126">None</span></span>

## <span data-ttu-id="e84f1-127">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="e84f1-127">NOTES</span></span>

## <span data-ttu-id="e84f1-128">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="e84f1-128">RELATED LINKS</span></span>

[<span data-ttu-id="e84f1-129">Трассировка событий</span><span class="sxs-lookup"><span data-stu-id="e84f1-129">Event Tracing</span></span>](/windows/desktop/ETW/event-tracing-portal)

[<span data-ttu-id="e84f1-130">Start-Trace</span><span class="sxs-lookup"><span data-stu-id="e84f1-130">Start-Trace</span></span>](start-trace.md)

[<span data-ttu-id="e84f1-131">Disable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="e84f1-131">Disable-PSWSManCombinedTrace</span></span>](Disable-PSWSManCombinedTrace.md)
