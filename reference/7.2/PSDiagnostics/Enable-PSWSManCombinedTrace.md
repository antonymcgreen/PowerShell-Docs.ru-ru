---
external help file: PSDiagnostics-help.xml
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/29/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/enable-pswsmancombinedtrace?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-PSWSManCombinedTrace
ms.openlocfilehash: ef333edaa091e96df11a8288e9b16f133614c1e0
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602503"
---
# <span data-ttu-id="e6d42-102">Enable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="e6d42-102">Enable-PSWSManCombinedTrace</span></span>

## <span data-ttu-id="e6d42-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="e6d42-103">SYNOPSIS</span></span>
<span data-ttu-id="e6d42-104">Запустите сеанс ведения журнала с включенными поставщиками WSMan и PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e6d42-104">Start a logging session with the WSMan and PowerShell providers enabled.</span></span>

## <span data-ttu-id="e6d42-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e6d42-105">SYNTAX</span></span>

```
Enable-PSWSManCombinedTrace [-DoNotOverwriteExistingTrace] [<CommonParameters>]
```

## <span data-ttu-id="e6d42-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e6d42-106">DESCRIPTION</span></span>

<span data-ttu-id="e6d42-107">Этот командлет запускает сеанс ведения журнала со следующими включенными поставщиками PowerShell:</span><span class="sxs-lookup"><span data-stu-id="e6d42-107">This cmdlet starts a logging session with the following PowerShell providers enabled:</span></span>

- <span data-ttu-id="e6d42-108">Microsoft-Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e6d42-108">Microsoft-Windows-PowerShell</span></span>
- <span data-ttu-id="e6d42-109">Microsoft-Windows — WinRM</span><span class="sxs-lookup"><span data-stu-id="e6d42-109">Microsoft-Windows-WinRM</span></span>

<span data-ttu-id="e6d42-110">Сеанс называется "Пстраце".</span><span class="sxs-lookup"><span data-stu-id="e6d42-110">The session is named 'PSTrace'.</span></span>

<span data-ttu-id="e6d42-111">Этот командлет использует `Start-Trace` командлет.</span><span class="sxs-lookup"><span data-stu-id="e6d42-111">This cmdlet uses the `Start-Trace` cmdlet.</span></span>

<span data-ttu-id="e6d42-112">Этот командлет необходимо запустить из сеанса PowerShell с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="e6d42-112">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="e6d42-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="e6d42-113">EXAMPLES</span></span>

### <span data-ttu-id="e6d42-114">Пример 1. Запуск Объединенного сеанса ведения журнала</span><span class="sxs-lookup"><span data-stu-id="e6d42-114">Example 1: Start a combined logging session</span></span>

```powershell
Enable-PSWSManCombinedTrace
```

## <span data-ttu-id="e6d42-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e6d42-115">PARAMETERS</span></span>

### <span data-ttu-id="e6d42-116">-Донотовервритиксистингтраце</span><span class="sxs-lookup"><span data-stu-id="e6d42-116">-DoNotOverwriteExistingTrace</span></span>

<span data-ttu-id="e6d42-117">По умолчанию события записываются в "$pshome \Трацес\пстраце.ЕТЛ".</span><span class="sxs-lookup"><span data-stu-id="e6d42-117">By default, the events are written to "$pshome\Traces\PSTrace.etl".</span></span> <span data-ttu-id="e6d42-118">При использовании этого параметра командлет создает уникальное имя файла: "$pshome \Трацес\ PSTrace_ {GUID}. ETL".</span><span class="sxs-lookup"><span data-stu-id="e6d42-118">When this parameter is used, the cmdlet creates a unique filename: "$pshome\Traces\PSTrace_{guid}.etl"</span></span>

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

### <span data-ttu-id="e6d42-119">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="e6d42-119">CommonParameters</span></span>

<span data-ttu-id="e6d42-120">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="e6d42-120">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e6d42-121">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="e6d42-121">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e6d42-122">Входные данные</span><span class="sxs-lookup"><span data-stu-id="e6d42-122">INPUTS</span></span>

### <span data-ttu-id="e6d42-123">None</span><span class="sxs-lookup"><span data-stu-id="e6d42-123">None</span></span>

## <span data-ttu-id="e6d42-124">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="e6d42-124">OUTPUTS</span></span>

### <span data-ttu-id="e6d42-125">None</span><span class="sxs-lookup"><span data-stu-id="e6d42-125">None</span></span>

## <span data-ttu-id="e6d42-126">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="e6d42-126">NOTES</span></span>

## <span data-ttu-id="e6d42-127">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="e6d42-127">RELATED LINKS</span></span>

[<span data-ttu-id="e6d42-128">Трассировка событий</span><span class="sxs-lookup"><span data-stu-id="e6d42-128">Event Tracing</span></span>](/windows/desktop/ETW/event-tracing-portal)

[<span data-ttu-id="e6d42-129">Start-Trace</span><span class="sxs-lookup"><span data-stu-id="e6d42-129">Start-Trace</span></span>](start-trace.md)

[<span data-ttu-id="e6d42-130">Disable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="e6d42-130">Disable-PSWSManCombinedTrace</span></span>](Disable-PSWSManCombinedTrace.md)

