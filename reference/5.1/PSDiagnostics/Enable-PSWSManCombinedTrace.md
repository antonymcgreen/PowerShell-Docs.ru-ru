---
external help file: PSDiagnostics-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/29/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/enable-pswsmancombinedtrace?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-PSWSManCombinedTrace
ms.openlocfilehash: f67b5d9fe8da48cca5fd4ec7d2056a4702d3ff16
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227434"
---
# <span data-ttu-id="68ebf-103">Enable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="68ebf-103">Enable-PSWSManCombinedTrace</span></span>

## <span data-ttu-id="68ebf-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="68ebf-104">SYNOPSIS</span></span>
<span data-ttu-id="68ebf-105">Запустите сеанс ведения журнала с включенными поставщиками WSMan и PowerShell.</span><span class="sxs-lookup"><span data-stu-id="68ebf-105">Start a logging session with the WSMan and PowerShell providers enabled.</span></span>

## <span data-ttu-id="68ebf-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="68ebf-106">SYNTAX</span></span>

```
Enable-PSWSManCombinedTrace [-DoNotOverwriteExistingTrace] [<CommonParameters>]
```

## <span data-ttu-id="68ebf-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="68ebf-107">DESCRIPTION</span></span>

<span data-ttu-id="68ebf-108">Этот командлет запускает сеанс ведения журнала со следующими включенными поставщиками PowerShell:</span><span class="sxs-lookup"><span data-stu-id="68ebf-108">This cmdlet starts a logging session with the following PowerShell providers enabled:</span></span>

- <span data-ttu-id="68ebf-109">Microsoft-Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="68ebf-109">Microsoft-Windows-PowerShell</span></span>
- <span data-ttu-id="68ebf-110">Microsoft-Windows — WinRM</span><span class="sxs-lookup"><span data-stu-id="68ebf-110">Microsoft-Windows-WinRM</span></span>

<span data-ttu-id="68ebf-111">Сеанс называется "Пстраце".</span><span class="sxs-lookup"><span data-stu-id="68ebf-111">The session is named 'PSTrace'.</span></span>

<span data-ttu-id="68ebf-112">Этот командлет использует `Start-Trace` командлет.</span><span class="sxs-lookup"><span data-stu-id="68ebf-112">This cmdlet uses the `Start-Trace` cmdlet.</span></span>

<span data-ttu-id="68ebf-113">Этот командлет необходимо запустить из сеанса PowerShell с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="68ebf-113">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="68ebf-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="68ebf-114">EXAMPLES</span></span>

### <span data-ttu-id="68ebf-115">Пример 1. Запуск Объединенного сеанса ведения журнала</span><span class="sxs-lookup"><span data-stu-id="68ebf-115">Example 1: Start a combined logging session</span></span>

```powershell
Enable-PSWSManCombinedTrace
```

## <span data-ttu-id="68ebf-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="68ebf-116">PARAMETERS</span></span>

### <span data-ttu-id="68ebf-117">-Донотовервритиксистингтраце</span><span class="sxs-lookup"><span data-stu-id="68ebf-117">-DoNotOverwriteExistingTrace</span></span>

<span data-ttu-id="68ebf-118">По умолчанию события записываются в "$pshome \Трацес\пстраце.ЕТЛ".</span><span class="sxs-lookup"><span data-stu-id="68ebf-118">By default, the events are written to "$pshome\Traces\PSTrace.etl".</span></span> <span data-ttu-id="68ebf-119">При использовании этого параметра командлет создает уникальное имя файла: "$pshome \Трацес\ PSTrace_ {GUID}. ETL".</span><span class="sxs-lookup"><span data-stu-id="68ebf-119">When this parameter is used, the cmdlet creates a unique filename: "$pshome\Traces\PSTrace_{guid}.etl"</span></span>

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="68ebf-120">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="68ebf-120">CommonParameters</span></span>

<span data-ttu-id="68ebf-121">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="68ebf-121">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="68ebf-122">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="68ebf-122">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="68ebf-123">Входные данные</span><span class="sxs-lookup"><span data-stu-id="68ebf-123">INPUTS</span></span>

### <span data-ttu-id="68ebf-124">Нет</span><span class="sxs-lookup"><span data-stu-id="68ebf-124">None</span></span>

## <span data-ttu-id="68ebf-125">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="68ebf-125">OUTPUTS</span></span>

### <span data-ttu-id="68ebf-126">System.Object</span><span class="sxs-lookup"><span data-stu-id="68ebf-126">System.Object</span></span>

## <span data-ttu-id="68ebf-127">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="68ebf-127">NOTES</span></span>

## <span data-ttu-id="68ebf-128">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="68ebf-128">RELATED LINKS</span></span>

[<span data-ttu-id="68ebf-129">Трассировка событий</span><span class="sxs-lookup"><span data-stu-id="68ebf-129">Event Tracing</span></span>](/windows/desktop/ETW/event-tracing-portal)

[<span data-ttu-id="68ebf-130">Start-Trace</span><span class="sxs-lookup"><span data-stu-id="68ebf-130">Start-Trace</span></span>](start-trace.md)

[<span data-ttu-id="68ebf-131">Disable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="68ebf-131">Disable-PSWSManCombinedTrace</span></span>](Disable-PSWSManCombinedTrace.md)
