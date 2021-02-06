---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/10/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/start-sleep?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Sleep
ms.openlocfilehash: e4d06fdd1d5a616c24a4dd7bec10ea4dadea4062
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99604650"
---
# <span data-ttu-id="215dd-102">Start-Sleep</span><span class="sxs-lookup"><span data-stu-id="215dd-102">Start-Sleep</span></span>

## <span data-ttu-id="215dd-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="215dd-103">SYNOPSIS</span></span>
<span data-ttu-id="215dd-104">Приостанавливает действие в скрипте или сеансе на указанное время.</span><span class="sxs-lookup"><span data-stu-id="215dd-104">Suspends the activity in a script or session for the specified period of time.</span></span>

## <span data-ttu-id="215dd-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="215dd-105">SYNTAX</span></span>

### <span data-ttu-id="215dd-106">Секунд (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="215dd-106">Seconds (Default)</span></span>

```
Start-Sleep [-Seconds] <Double> [<CommonParameters>]
```

### <span data-ttu-id="215dd-107">Миллисекунды</span><span class="sxs-lookup"><span data-stu-id="215dd-107">Milliseconds</span></span>

```
Start-Sleep -Milliseconds <Int32> [<CommonParameters>]
```

## <span data-ttu-id="215dd-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="215dd-108">DESCRIPTION</span></span>

<span data-ttu-id="215dd-109">`Start-Sleep`Командлет приостанавливает действие в скрипте или сеансе за указанный период времени.</span><span class="sxs-lookup"><span data-stu-id="215dd-109">The `Start-Sleep` cmdlet suspends the activity in a script or session for the specified period of time.</span></span> <span data-ttu-id="215dd-110">Его можно использовать для выполнения многих задач, например ожидания завершения операции или приостановки перед повторением операции.</span><span class="sxs-lookup"><span data-stu-id="215dd-110">You can use it for many tasks, such as waiting for an operation to complete or pausing before repeating an operation.</span></span>

## <span data-ttu-id="215dd-111">Примеры</span><span class="sxs-lookup"><span data-stu-id="215dd-111">EXAMPLES</span></span>

### <span data-ttu-id="215dd-112">Пример 1. спящий режим для всех команд в течение 15 секунд</span><span class="sxs-lookup"><span data-stu-id="215dd-112">Example 1: Sleep all commands for 15 seconds</span></span>

```powershell
Start-Sleep -s 15
```

### <span data-ttu-id="215dd-113">Пример 2. спящий режим для всех команд в течение 1,5 секунд</span><span class="sxs-lookup"><span data-stu-id="215dd-113">Example 2: Sleep all commands for 1.5 seconds</span></span>

<span data-ttu-id="215dd-114">В этом примере все команды сеанса находятся в спящем режиме в течение одной и одной половины секунд.</span><span class="sxs-lookup"><span data-stu-id="215dd-114">This example makes all the commands in the session sleep for one and one-half of a seconds.</span></span>

```powershell
Start-Sleep -Seconds 1.5
```

## <span data-ttu-id="215dd-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="215dd-115">PARAMETERS</span></span>

### <span data-ttu-id="215dd-116">– Миллисекунды</span><span class="sxs-lookup"><span data-stu-id="215dd-116">-Milliseconds</span></span>

<span data-ttu-id="215dd-117">Указывает, на какое время ресурс приостанавливается, в миллисекундах.</span><span class="sxs-lookup"><span data-stu-id="215dd-117">Specifies how long the resource sleeps in milliseconds.</span></span> <span data-ttu-id="215dd-118">Параметр можно сократить на **m**.</span><span class="sxs-lookup"><span data-stu-id="215dd-118">The parameter can be abbreviated as **m**.</span></span>

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

### <span data-ttu-id="215dd-119">-Секунд</span><span class="sxs-lookup"><span data-stu-id="215dd-119">-Seconds</span></span>

<span data-ttu-id="215dd-120">Указывает, на какое время ресурс приостанавливается, в секундах.</span><span class="sxs-lookup"><span data-stu-id="215dd-120">Specifies how long the resource sleeps in seconds.</span></span> <span data-ttu-id="215dd-121">Имя параметра можно опустить или сократить до **s**.</span><span class="sxs-lookup"><span data-stu-id="215dd-121">You can omit the parameter name or you can abbreviate it as **s**.</span></span> <span data-ttu-id="215dd-122">Начиная с PowerShell 6.2.0, этот параметр теперь принимает дробные значения.</span><span class="sxs-lookup"><span data-stu-id="215dd-122">Beginning in PowerShell 6.2.0, this parameter now accepts fractional values.</span></span>

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

### <span data-ttu-id="215dd-123">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="215dd-123">CommonParameters</span></span>

<span data-ttu-id="215dd-124">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="215dd-124">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="215dd-125">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="215dd-125">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="215dd-126">Входные данные</span><span class="sxs-lookup"><span data-stu-id="215dd-126">INPUTS</span></span>

### <span data-ttu-id="215dd-127">System.Int32</span><span class="sxs-lookup"><span data-stu-id="215dd-127">System.Int32</span></span>

<span data-ttu-id="215dd-128">Количество секунд можно передать в `Start-Sleep` .</span><span class="sxs-lookup"><span data-stu-id="215dd-128">You can pipe the number of seconds to `Start-Sleep`.</span></span>

## <span data-ttu-id="215dd-129">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="215dd-129">OUTPUTS</span></span>

### <span data-ttu-id="215dd-130">None</span><span class="sxs-lookup"><span data-stu-id="215dd-130">None</span></span>

<span data-ttu-id="215dd-131">Этот командлет не возвращает никакие выходные данные.</span><span class="sxs-lookup"><span data-stu-id="215dd-131">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="215dd-132">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="215dd-132">NOTES</span></span>

- <span data-ttu-id="215dd-133">Также можно ссылаться `Start-Sleep` по встроенному псевдониму `sleep` .</span><span class="sxs-lookup"><span data-stu-id="215dd-133">You can also refer to `Start-Sleep` by its built-in alias, `sleep`.</span></span> <span data-ttu-id="215dd-134">Дополнительные сведения см. в разделе [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="215dd-134">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>
- <span data-ttu-id="215dd-135">`Ctrl+C` разрыв из `Start-Sleep` .</span><span class="sxs-lookup"><span data-stu-id="215dd-135">`Ctrl+C` breaks out of `Start-Sleep`.</span></span>
  - <span data-ttu-id="215dd-136">`Ctrl+C` не нарушает работу `[Threading.Thread]::Sleep` .</span><span class="sxs-lookup"><span data-stu-id="215dd-136">`Ctrl+C` does not break out of `[Threading.Thread]::Sleep`.</span></span> <span data-ttu-id="215dd-137">Дополнительные сведения см. в разделе [метод Thread. Sleep](/dotnet/api/system.threading.thread.sleep).</span><span class="sxs-lookup"><span data-stu-id="215dd-137">For more information, see [Thread.Sleep Method](/dotnet/api/system.threading.thread.sleep).</span></span>

## <span data-ttu-id="215dd-138">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="215dd-138">RELATED LINKS</span></span>

