---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/10/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/start-sleep?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Sleep
ms.openlocfilehash: 535cad057db406eaa48259288e34da6da4ed1cbb
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93225738"
---
# <span data-ttu-id="66976-103">Start-Sleep</span><span class="sxs-lookup"><span data-stu-id="66976-103">Start-Sleep</span></span>

## <span data-ttu-id="66976-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="66976-104">SYNOPSIS</span></span>
<span data-ttu-id="66976-105">Приостанавливает действие в скрипте или сеансе на указанное время.</span><span class="sxs-lookup"><span data-stu-id="66976-105">Suspends the activity in a script or session for the specified period of time.</span></span>

## <span data-ttu-id="66976-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="66976-106">SYNTAX</span></span>

### <span data-ttu-id="66976-107">Секунд (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="66976-107">Seconds (Default)</span></span>

```
Start-Sleep [-Seconds] <Double> [<CommonParameters>]
```

### <span data-ttu-id="66976-108">Миллисекунды</span><span class="sxs-lookup"><span data-stu-id="66976-108">Milliseconds</span></span>

```
Start-Sleep -Milliseconds <Int32> [<CommonParameters>]
```

## <span data-ttu-id="66976-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="66976-109">DESCRIPTION</span></span>

<span data-ttu-id="66976-110">`Start-Sleep`Командлет приостанавливает действие в скрипте или сеансе за указанный период времени.</span><span class="sxs-lookup"><span data-stu-id="66976-110">The `Start-Sleep` cmdlet suspends the activity in a script or session for the specified period of time.</span></span> <span data-ttu-id="66976-111">Его можно использовать для выполнения многих задач, например ожидания завершения операции или приостановки перед повторением операции.</span><span class="sxs-lookup"><span data-stu-id="66976-111">You can use it for many tasks, such as waiting for an operation to complete or pausing before repeating an operation.</span></span>

## <span data-ttu-id="66976-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="66976-112">EXAMPLES</span></span>

### <span data-ttu-id="66976-113">Пример 1. спящий режим для всех команд в течение 15 секунд</span><span class="sxs-lookup"><span data-stu-id="66976-113">Example 1: Sleep all commands for 15 seconds</span></span>

```powershell
Start-Sleep -s 15
```

### <span data-ttu-id="66976-114">Пример 2. спящий режим для всех команд в течение 1,5 секунд</span><span class="sxs-lookup"><span data-stu-id="66976-114">Example 2: Sleep all commands for 1.5 seconds</span></span>

<span data-ttu-id="66976-115">В этом примере все команды сеанса находятся в спящем режиме в течение одной и одной половины секунд.</span><span class="sxs-lookup"><span data-stu-id="66976-115">This example makes all the commands in the session sleep for one and one-half of a seconds.</span></span>

```powershell
Start-Sleep -Seconds 1.5
```

## <span data-ttu-id="66976-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="66976-116">PARAMETERS</span></span>

### <span data-ttu-id="66976-117">– Миллисекунды</span><span class="sxs-lookup"><span data-stu-id="66976-117">-Milliseconds</span></span>

<span data-ttu-id="66976-118">Указывает, на какое время ресурс приостанавливается, в миллисекундах.</span><span class="sxs-lookup"><span data-stu-id="66976-118">Specifies how long the resource sleeps in milliseconds.</span></span> <span data-ttu-id="66976-119">Параметр можно сократить на **m** .</span><span class="sxs-lookup"><span data-stu-id="66976-119">The parameter can be abbreviated as **m** .</span></span>

```yaml
Type: System.Int32
Parameter Sets: Milliseconds
Aliases: ms

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="66976-120">-Секунд</span><span class="sxs-lookup"><span data-stu-id="66976-120">-Seconds</span></span>

<span data-ttu-id="66976-121">Указывает, на какое время ресурс приостанавливается, в секундах.</span><span class="sxs-lookup"><span data-stu-id="66976-121">Specifies how long the resource sleeps in seconds.</span></span> <span data-ttu-id="66976-122">Имя параметра можно опустить или сократить до **s** .</span><span class="sxs-lookup"><span data-stu-id="66976-122">You can omit the parameter name or you can abbreviate it as **s** .</span></span> <span data-ttu-id="66976-123">Начиная с PowerShell 6.2.0, этот параметр теперь принимает дробные значения.</span><span class="sxs-lookup"><span data-stu-id="66976-123">Beginning in PowerShell 6.2.0, this parameter now accepts fractional values.</span></span>

```yaml
Type: System.Double
Parameter Sets: Seconds
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="66976-124">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="66976-124">CommonParameters</span></span>

<span data-ttu-id="66976-125">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="66976-125">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="66976-126">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="66976-126">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="66976-127">Входные данные</span><span class="sxs-lookup"><span data-stu-id="66976-127">INPUTS</span></span>

### <span data-ttu-id="66976-128">System.Int32</span><span class="sxs-lookup"><span data-stu-id="66976-128">System.Int32</span></span>

<span data-ttu-id="66976-129">Количество секунд можно передать в `Start-Sleep` .</span><span class="sxs-lookup"><span data-stu-id="66976-129">You can pipe the number of seconds to `Start-Sleep`.</span></span>

## <span data-ttu-id="66976-130">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="66976-130">OUTPUTS</span></span>

### <span data-ttu-id="66976-131">Нет</span><span class="sxs-lookup"><span data-stu-id="66976-131">None</span></span>

<span data-ttu-id="66976-132">Этот командлет не возвращает никакие выходные данные.</span><span class="sxs-lookup"><span data-stu-id="66976-132">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="66976-133">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="66976-133">NOTES</span></span>

- <span data-ttu-id="66976-134">Также можно ссылаться `Start-Sleep` по встроенному псевдониму `sleep` .</span><span class="sxs-lookup"><span data-stu-id="66976-134">You can also refer to `Start-Sleep` by its built-in alias, `sleep`.</span></span> <span data-ttu-id="66976-135">Дополнительные сведения см. в разделе [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="66976-135">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>
- <span data-ttu-id="66976-136">`Ctrl+C` разрыв из `Start-Sleep` .</span><span class="sxs-lookup"><span data-stu-id="66976-136">`Ctrl+C` breaks out of `Start-Sleep`.</span></span>
  - <span data-ttu-id="66976-137">`Ctrl+C` не нарушает работу `[Threading.Thread]::Sleep` .</span><span class="sxs-lookup"><span data-stu-id="66976-137">`Ctrl+C` does not break out of `[Threading.Thread]::Sleep`.</span></span> <span data-ttu-id="66976-138">Дополнительные сведения см. в разделе [метод Thread. Sleep](/dotnet/api/system.threading.thread.sleep).</span><span class="sxs-lookup"><span data-stu-id="66976-138">For more information, see [Thread.Sleep Method](/dotnet/api/system.threading.thread.sleep).</span></span>

## <span data-ttu-id="66976-139">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="66976-139">RELATED LINKS</span></span>
