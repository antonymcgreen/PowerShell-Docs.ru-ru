---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 3/13/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/start-sleep?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Sleep
ms.openlocfilehash: e4add39c09b6123aaf8c9302529346a6b1dec391
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227497"
---
# <span data-ttu-id="562f5-103">Start-Sleep</span><span class="sxs-lookup"><span data-stu-id="562f5-103">Start-Sleep</span></span>

## <span data-ttu-id="562f5-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="562f5-104">SYNOPSIS</span></span>
<span data-ttu-id="562f5-105">Приостанавливает действие в скрипте или сеансе на указанное время.</span><span class="sxs-lookup"><span data-stu-id="562f5-105">Suspends the activity in a script or session for the specified period of time.</span></span>

## <span data-ttu-id="562f5-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="562f5-106">SYNTAX</span></span>

### <span data-ttu-id="562f5-107">Секунд (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="562f5-107">Seconds (Default)</span></span>

```
Start-Sleep [-Seconds] <Int32> [<CommonParameters>]
```

### <span data-ttu-id="562f5-108">Миллисекунды</span><span class="sxs-lookup"><span data-stu-id="562f5-108">Milliseconds</span></span>

```
Start-Sleep -Milliseconds <Int32> [<CommonParameters>]
```

## <span data-ttu-id="562f5-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="562f5-109">DESCRIPTION</span></span>

<span data-ttu-id="562f5-110">`Start-Sleep`Командлет приостанавливает действие в скрипте или сеансе за указанный период времени.</span><span class="sxs-lookup"><span data-stu-id="562f5-110">The `Start-Sleep` cmdlet suspends the activity in a script or session for the specified period of time.</span></span>
<span data-ttu-id="562f5-111">Его можно использовать для выполнения многих задач, например ожидания завершения операции или приостановки перед повторением операции.</span><span class="sxs-lookup"><span data-stu-id="562f5-111">You can use it for many tasks, such as waiting for an operation to complete or pausing before repeating an operation.</span></span>

## <span data-ttu-id="562f5-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="562f5-112">EXAMPLES</span></span>

### <span data-ttu-id="562f5-113">Пример 1. спящий режим для всех команд в течение 15 секунд</span><span class="sxs-lookup"><span data-stu-id="562f5-113">Example 1: Sleep all commands for 15 seconds</span></span>

```powershell
Start-Sleep -s 15
```

<span data-ttu-id="562f5-114">Эта команда приостанавливает все команды в сеансе на 15 секунд.</span><span class="sxs-lookup"><span data-stu-id="562f5-114">This command makes all commands in the session sleep for 15 seconds.</span></span>

### <span data-ttu-id="562f5-115">Пример 2. спящий режим всех команд</span><span class="sxs-lookup"><span data-stu-id="562f5-115">Example 2: Sleep all commands</span></span>

```powershell
Start-Sleep -m 500
```

<span data-ttu-id="562f5-116">Эта команда приостанавливает все команды в сеансе на полсекунды (500 мс).</span><span class="sxs-lookup"><span data-stu-id="562f5-116">This command makes all the commands in the session sleep for one-half of a second (500 milliseconds).</span></span>

## <span data-ttu-id="562f5-117">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="562f5-117">PARAMETERS</span></span>

### <span data-ttu-id="562f5-118">– Миллисекунды</span><span class="sxs-lookup"><span data-stu-id="562f5-118">-Milliseconds</span></span>

<span data-ttu-id="562f5-119">Указывает, на какое время ресурс приостанавливается, в миллисекундах.</span><span class="sxs-lookup"><span data-stu-id="562f5-119">Specifies how long the resource sleeps in milliseconds.</span></span>
<span data-ttu-id="562f5-120">Параметр можно сократить на **m** .</span><span class="sxs-lookup"><span data-stu-id="562f5-120">The parameter can be abbreviated as **m** .</span></span>

```yaml
Type: System.Int32
Parameter Sets: Milliseconds
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="562f5-121">-Секунд</span><span class="sxs-lookup"><span data-stu-id="562f5-121">-Seconds</span></span>

<span data-ttu-id="562f5-122">Указывает, на какое время ресурс приостанавливается, в секундах.</span><span class="sxs-lookup"><span data-stu-id="562f5-122">Specifies how long the resource sleeps in seconds.</span></span>
<span data-ttu-id="562f5-123">Имя параметра (в **секундах** ) можно опустить или сократить до **s** .</span><span class="sxs-lookup"><span data-stu-id="562f5-123">You can omit the parameter name ( **Seconds** ), or you can abbreviate it as **s** .</span></span>

```yaml
Type: System.Int32
Parameter Sets: Seconds
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="562f5-124">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="562f5-124">CommonParameters</span></span>

<span data-ttu-id="562f5-125">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="562f5-125">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="562f5-126">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="562f5-126">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="562f5-127">Входные данные</span><span class="sxs-lookup"><span data-stu-id="562f5-127">INPUTS</span></span>

### <span data-ttu-id="562f5-128">System.Int32</span><span class="sxs-lookup"><span data-stu-id="562f5-128">System.Int32</span></span>

<span data-ttu-id="562f5-129">Количество секунд можно передать в `Start-Sleep` .</span><span class="sxs-lookup"><span data-stu-id="562f5-129">You can pipe the number of seconds to `Start-Sleep`.</span></span>

## <span data-ttu-id="562f5-130">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="562f5-130">OUTPUTS</span></span>

### <span data-ttu-id="562f5-131">Нет</span><span class="sxs-lookup"><span data-stu-id="562f5-131">None</span></span>

<span data-ttu-id="562f5-132">Этот командлет не возвращает никакие выходные данные.</span><span class="sxs-lookup"><span data-stu-id="562f5-132">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="562f5-133">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="562f5-133">NOTES</span></span>

- <span data-ttu-id="562f5-134">Также можно ссылаться `Start-Sleep` по встроенному псевдониму `sleep` .</span><span class="sxs-lookup"><span data-stu-id="562f5-134">You can also refer to `Start-Sleep` by its built-in alias, `sleep`.</span></span> <span data-ttu-id="562f5-135">Дополнительные сведения см. в разделе [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="562f5-135">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>
- <span data-ttu-id="562f5-136">`Ctrl+C` разрыв из `Start-Sleep` .</span><span class="sxs-lookup"><span data-stu-id="562f5-136">`Ctrl+C` breaks out of `Start-Sleep`.</span></span>
  - <span data-ttu-id="562f5-137">`Ctrl+C` не нарушает работу `[Threading.Thread]::Sleep` .</span><span class="sxs-lookup"><span data-stu-id="562f5-137">`Ctrl+C` does not break out of `[Threading.Thread]::Sleep`.</span></span> <span data-ttu-id="562f5-138">Дополнительные сведения см. в разделе [метод Thread. Sleep](/dotnet/api/system.threading.thread.sleep).</span><span class="sxs-lookup"><span data-stu-id="562f5-138">For more information, see [Thread.Sleep Method](/dotnet/api/system.threading.thread.sleep).</span></span>

## <span data-ttu-id="562f5-139">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="562f5-139">RELATED LINKS</span></span>
