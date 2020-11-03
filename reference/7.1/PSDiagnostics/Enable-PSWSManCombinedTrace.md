---
external help file: PSDiagnostics-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/29/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/enable-pswsmancombinedtrace?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-PSWSManCombinedTrace
ms.openlocfilehash: 0999c59ab2e27b066dc6afa0b21cce029a9419e1
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93226514"
---
# <span data-ttu-id="aa37a-103">Enable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="aa37a-103">Enable-PSWSManCombinedTrace</span></span>

## <span data-ttu-id="aa37a-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="aa37a-104">SYNOPSIS</span></span>
<span data-ttu-id="aa37a-105">Запустите сеанс ведения журнала с включенными поставщиками WSMan и PowerShell.</span><span class="sxs-lookup"><span data-stu-id="aa37a-105">Start a logging session with the WSMan and PowerShell providers enabled.</span></span>

## <span data-ttu-id="aa37a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="aa37a-106">SYNTAX</span></span>

```
Enable-PSWSManCombinedTrace [-DoNotOverwriteExistingTrace] [<CommonParameters>]
```

## <span data-ttu-id="aa37a-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="aa37a-107">DESCRIPTION</span></span>

<span data-ttu-id="aa37a-108">Этот командлет запускает сеанс ведения журнала со следующими включенными поставщиками PowerShell:</span><span class="sxs-lookup"><span data-stu-id="aa37a-108">This cmdlet starts a logging session with the following PowerShell providers enabled:</span></span>

- <span data-ttu-id="aa37a-109">Microsoft-Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="aa37a-109">Microsoft-Windows-PowerShell</span></span>
- <span data-ttu-id="aa37a-110">Microsoft-Windows — WinRM</span><span class="sxs-lookup"><span data-stu-id="aa37a-110">Microsoft-Windows-WinRM</span></span>

<span data-ttu-id="aa37a-111">Сеанс называется "Пстраце".</span><span class="sxs-lookup"><span data-stu-id="aa37a-111">The session is named 'PSTrace'.</span></span>

<span data-ttu-id="aa37a-112">Этот командлет использует `Start-Trace` командлет.</span><span class="sxs-lookup"><span data-stu-id="aa37a-112">This cmdlet uses the `Start-Trace` cmdlet.</span></span>

<span data-ttu-id="aa37a-113">Этот командлет необходимо запустить из сеанса PowerShell с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="aa37a-113">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="aa37a-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="aa37a-114">EXAMPLES</span></span>

### <span data-ttu-id="aa37a-115">Пример 1. Запуск Объединенного сеанса ведения журнала</span><span class="sxs-lookup"><span data-stu-id="aa37a-115">Example 1: Start a combined logging session</span></span>

```powershell
Enable-PSWSManCombinedTrace
```

## <span data-ttu-id="aa37a-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="aa37a-116">PARAMETERS</span></span>

### <span data-ttu-id="aa37a-117">-Донотовервритиксистингтраце</span><span class="sxs-lookup"><span data-stu-id="aa37a-117">-DoNotOverwriteExistingTrace</span></span>

<span data-ttu-id="aa37a-118">По умолчанию события записываются в "$pshome \Трацес\пстраце.ЕТЛ".</span><span class="sxs-lookup"><span data-stu-id="aa37a-118">By default, the events are written to "$pshome\Traces\PSTrace.etl".</span></span> <span data-ttu-id="aa37a-119">При использовании этого параметра командлет создает уникальное имя файла: "$pshome \Трацес\ PSTrace_ {GUID}. ETL".</span><span class="sxs-lookup"><span data-stu-id="aa37a-119">When this parameter is used, the cmdlet creates a unique filename: "$pshome\Traces\PSTrace_{guid}.etl"</span></span>

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

### <span data-ttu-id="aa37a-120">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="aa37a-120">CommonParameters</span></span>

<span data-ttu-id="aa37a-121">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="aa37a-121">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="aa37a-122">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="aa37a-122">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="aa37a-123">Входные данные</span><span class="sxs-lookup"><span data-stu-id="aa37a-123">INPUTS</span></span>

### <span data-ttu-id="aa37a-124">Нет</span><span class="sxs-lookup"><span data-stu-id="aa37a-124">None</span></span>

## <span data-ttu-id="aa37a-125">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="aa37a-125">OUTPUTS</span></span>

### <span data-ttu-id="aa37a-126">Нет</span><span class="sxs-lookup"><span data-stu-id="aa37a-126">None</span></span>

## <span data-ttu-id="aa37a-127">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="aa37a-127">NOTES</span></span>

## <span data-ttu-id="aa37a-128">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="aa37a-128">RELATED LINKS</span></span>

[<span data-ttu-id="aa37a-129">Трассировка событий</span><span class="sxs-lookup"><span data-stu-id="aa37a-129">Event Tracing</span></span>](/windows/desktop/ETW/event-tracing-portal)

[<span data-ttu-id="aa37a-130">Start-Trace</span><span class="sxs-lookup"><span data-stu-id="aa37a-130">Start-Trace</span></span>](start-trace.md)

[<span data-ttu-id="aa37a-131">Disable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="aa37a-131">Disable-PSWSManCombinedTrace</span></span>](Disable-PSWSManCombinedTrace.md)

