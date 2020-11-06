---
external help file: PSDiagnostics-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/29/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/enable-pswsmancombinedtrace?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-PSWSManCombinedTrace
ms.openlocfilehash: cfe73dea98cdf858f1364e1daf434334b57a62cd
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93229206"
---
# <span data-ttu-id="3fa0c-103">Enable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="3fa0c-103">Enable-PSWSManCombinedTrace</span></span>

## <span data-ttu-id="3fa0c-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="3fa0c-104">SYNOPSIS</span></span>
<span data-ttu-id="3fa0c-105">Запустите сеанс ведения журнала с включенными поставщиками WSMan и PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3fa0c-105">Start a logging session with the WSMan and PowerShell providers enabled.</span></span>

## <span data-ttu-id="3fa0c-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3fa0c-106">SYNTAX</span></span>

```
Enable-PSWSManCombinedTrace [-DoNotOverwriteExistingTrace] [<CommonParameters>]
```

## <span data-ttu-id="3fa0c-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3fa0c-107">DESCRIPTION</span></span>

<span data-ttu-id="3fa0c-108">Этот командлет запускает сеанс ведения журнала со следующими включенными поставщиками PowerShell:</span><span class="sxs-lookup"><span data-stu-id="3fa0c-108">This cmdlet starts a logging session with the following PowerShell providers enabled:</span></span>

- <span data-ttu-id="3fa0c-109">Microsoft-Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3fa0c-109">Microsoft-Windows-PowerShell</span></span>
- <span data-ttu-id="3fa0c-110">Microsoft-Windows — WinRM</span><span class="sxs-lookup"><span data-stu-id="3fa0c-110">Microsoft-Windows-WinRM</span></span>

<span data-ttu-id="3fa0c-111">Сеанс называется "Пстраце".</span><span class="sxs-lookup"><span data-stu-id="3fa0c-111">The session is named 'PSTrace'.</span></span>

<span data-ttu-id="3fa0c-112">Этот командлет использует `Start-Trace` командлет.</span><span class="sxs-lookup"><span data-stu-id="3fa0c-112">This cmdlet uses the `Start-Trace` cmdlet.</span></span>

<span data-ttu-id="3fa0c-113">Этот командлет необходимо запустить из сеанса PowerShell с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="3fa0c-113">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="3fa0c-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="3fa0c-114">EXAMPLES</span></span>

### <span data-ttu-id="3fa0c-115">Пример 1. Запуск Объединенного сеанса ведения журнала</span><span class="sxs-lookup"><span data-stu-id="3fa0c-115">Example 1: Start a combined logging session</span></span>

```powershell
Enable-PSWSManCombinedTrace
```

## <span data-ttu-id="3fa0c-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3fa0c-116">PARAMETERS</span></span>

### <span data-ttu-id="3fa0c-117">-Донотовервритиксистингтраце</span><span class="sxs-lookup"><span data-stu-id="3fa0c-117">-DoNotOverwriteExistingTrace</span></span>

<span data-ttu-id="3fa0c-118">По умолчанию события записываются в "$pshome \Трацес\пстраце.ЕТЛ".</span><span class="sxs-lookup"><span data-stu-id="3fa0c-118">By default, the events are written to "$pshome\Traces\PSTrace.etl".</span></span> <span data-ttu-id="3fa0c-119">При использовании этого параметра командлет создает уникальное имя файла: "$pshome \Трацес\ PSTrace_ {GUID}. ETL".</span><span class="sxs-lookup"><span data-stu-id="3fa0c-119">When this parameter is used, the cmdlet creates a unique filename: "$pshome\Traces\PSTrace_{guid}.etl"</span></span>

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

### <span data-ttu-id="3fa0c-120">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="3fa0c-120">CommonParameters</span></span>

<span data-ttu-id="3fa0c-121">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="3fa0c-121">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="3fa0c-122">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="3fa0c-122">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="3fa0c-123">Входные данные</span><span class="sxs-lookup"><span data-stu-id="3fa0c-123">INPUTS</span></span>

### <span data-ttu-id="3fa0c-124">Нет</span><span class="sxs-lookup"><span data-stu-id="3fa0c-124">None</span></span>

## <span data-ttu-id="3fa0c-125">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="3fa0c-125">OUTPUTS</span></span>

### <span data-ttu-id="3fa0c-126">Нет</span><span class="sxs-lookup"><span data-stu-id="3fa0c-126">None</span></span>

## <span data-ttu-id="3fa0c-127">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="3fa0c-127">NOTES</span></span>

## <span data-ttu-id="3fa0c-128">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="3fa0c-128">RELATED LINKS</span></span>

[<span data-ttu-id="3fa0c-129">Трассировка событий</span><span class="sxs-lookup"><span data-stu-id="3fa0c-129">Event Tracing</span></span>](/windows/desktop/ETW/event-tracing-portal)

[<span data-ttu-id="3fa0c-130">Start-Trace</span><span class="sxs-lookup"><span data-stu-id="3fa0c-130">Start-Trace</span></span>](start-trace.md)

[<span data-ttu-id="3fa0c-131">Disable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="3fa0c-131">Disable-PSWSManCombinedTrace</span></span>](Disable-PSWSManCombinedTrace.md)