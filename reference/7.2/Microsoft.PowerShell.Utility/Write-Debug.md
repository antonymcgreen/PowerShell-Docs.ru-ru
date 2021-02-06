---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/write-debug?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-Debug
ms.openlocfilehash: 3d23f76dbf8e1c9a21805a4914038c8c4f319852
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603962"
---
# <span data-ttu-id="3e7eb-102">Write-Debug</span><span class="sxs-lookup"><span data-stu-id="3e7eb-102">Write-Debug</span></span>

## <span data-ttu-id="3e7eb-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="3e7eb-103">SYNOPSIS</span></span>
<span data-ttu-id="3e7eb-104">Выводит сообщение отладки на консоль.</span><span class="sxs-lookup"><span data-stu-id="3e7eb-104">Writes a debug message to the console.</span></span>

## <span data-ttu-id="3e7eb-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3e7eb-105">SYNTAX</span></span>

```
Write-Debug [-Message] <String> [<CommonParameters>]
```

## <span data-ttu-id="3e7eb-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3e7eb-106">DESCRIPTION</span></span>

<span data-ttu-id="3e7eb-107">`Write-Debug`Командлет записывает сообщения отладки на узел из скрипта или команды.</span><span class="sxs-lookup"><span data-stu-id="3e7eb-107">The `Write-Debug` cmdlet writes debug messages to the host from a script or command.</span></span>

<span data-ttu-id="3e7eb-108">По умолчанию сообщения отладки не отображаются в консоли, но их можно отобразить с помощью параметра **отладки** или `$DebugPreference` переменной.</span><span class="sxs-lookup"><span data-stu-id="3e7eb-108">By default, debug messages are not displayed in the console, but you can display them by using the **Debug** parameter or the `$DebugPreference` variable.</span></span>

## <span data-ttu-id="3e7eb-109">Примеры</span><span class="sxs-lookup"><span data-stu-id="3e7eb-109">EXAMPLES</span></span>

### <span data-ttu-id="3e7eb-110">Пример 1. понимание $DebugPreference</span><span class="sxs-lookup"><span data-stu-id="3e7eb-110">Example 1: Understand $DebugPreference</span></span>

<span data-ttu-id="3e7eb-111">В этом примере записывается сообщение отладки.</span><span class="sxs-lookup"><span data-stu-id="3e7eb-111">This example writes a debug message.</span></span>

```powershell
Write-Debug "Cannot open file."
```

<span data-ttu-id="3e7eb-112">Значение по умолчанию `$DebugPreference` — **SilentlyContinue**.</span><span class="sxs-lookup"><span data-stu-id="3e7eb-112">The default value of `$DebugPreference` is **SilentlyContinue**.</span></span> <span data-ttu-id="3e7eb-113">Поэтому сообщение не отображается в консоли.</span><span class="sxs-lookup"><span data-stu-id="3e7eb-113">Therefore, the message is not displayed in the console.</span></span>

### <span data-ttu-id="3e7eb-114">Пример 2. изменение значения $DebugPreference</span><span class="sxs-lookup"><span data-stu-id="3e7eb-114">Example 2: Change the value of $DebugPreference</span></span>

<span data-ttu-id="3e7eb-115">В этом примере показан результат изменения значения `$DebugPreference` переменной.</span><span class="sxs-lookup"><span data-stu-id="3e7eb-115">This example shows the effect of changing the value of the `$DebugPreference` variable.</span></span> <span data-ttu-id="3e7eb-116">Сначала мы отображаем текущее значение `$DebugPreference` и попытались написать сообщение отладки.</span><span class="sxs-lookup"><span data-stu-id="3e7eb-116">First, we display the current value of `$DebugPreference` and attempt to write a debug message.</span></span> <span data-ttu-id="3e7eb-117">Затем мы изменим значение `$DebugPreference` на **Continue**, что позволяет отображать сообщения отладки.</span><span class="sxs-lookup"><span data-stu-id="3e7eb-117">Then we change the value of `$DebugPreference` to **Continue**, which allows debug messages to be displayed.</span></span>

```
PS> $DebugPreference
SilentlyContinue
PS> Write-Debug "Cannot open file."
PS>
PS> $DebugPreference = "Continue"
PS> Write-Debug "Cannot open file."
DEBUG: Cannot open file.
```

<span data-ttu-id="3e7eb-118">Дополнительные сведения о `$DebugPreference` см. в разделе [about_Preference_Variables](/powershell/module/Microsoft.PowerShell.Core/About/about_Preference_Variables).</span><span class="sxs-lookup"><span data-stu-id="3e7eb-118">For more information about `$DebugPreference`, see [about_Preference_Variables](/powershell/module/Microsoft.PowerShell.Core/About/about_Preference_Variables).</span></span>

### <span data-ttu-id="3e7eb-119">Пример 3. Переопределение $DebugPreference с помощью параметра Debug</span><span class="sxs-lookup"><span data-stu-id="3e7eb-119">Example 3: Use the Debug parameter to override $DebugPreference</span></span>

<span data-ttu-id="3e7eb-120">`Test-Debug`Функция записывает значение `$DebugPreference` переменной в узел PowerShell и в поток отладки.</span><span class="sxs-lookup"><span data-stu-id="3e7eb-120">The `Test-Debug` function writes the value of the `$DebugPreference` variable to the PowerShell host and to the Debug stream.</span></span> <span data-ttu-id="3e7eb-121">В этом примере мы используем параметр **Debug** для переопределения `$DebugPreference` значения.</span><span class="sxs-lookup"><span data-stu-id="3e7eb-121">In this example, we use the **Debug** parameter to override the `$DebugPreference` value.</span></span>

```powershell
function Test-Debug {
    [CmdletBinding()]
    param()
    Write-Debug ('$DebugPreference is ' + $DebugPreference)
    Write-Host ('$DebugPreference is ' + $DebugPreference)
}
```

```
PS> Test-Debug
$DebugPreference is SilentlyContinue

PS> Test-Debug -Debug
DEBUG: $DebugPreference is Continue
$DebugPreference is Continue
PS> $DebugPreference
SilentlyContinue
```

<span data-ttu-id="3e7eb-122">Обратите внимание, что `$DebugPreference` при использовании параметра **Debug** значение изменяется.</span><span class="sxs-lookup"><span data-stu-id="3e7eb-122">Notice that the value of `$DebugPreference` changes when you use the **Debug** parameter.</span></span> <span data-ttu-id="3e7eb-123">Это изменение влияет только на область действия функции.</span><span class="sxs-lookup"><span data-stu-id="3e7eb-123">This change only affects the scope of the function.</span></span> <span data-ttu-id="3e7eb-124">Это значение не затрагивается за пределами функции.</span><span class="sxs-lookup"><span data-stu-id="3e7eb-124">The value is not affected outside the function.</span></span>

<span data-ttu-id="3e7eb-125">Дополнительные сведения об общем параметре **Debug** см. в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="3e7eb-125">For more information about the **Debug** common parameter, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="3e7eb-126">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3e7eb-126">PARAMETERS</span></span>

### <span data-ttu-id="3e7eb-127">-Message</span><span class="sxs-lookup"><span data-stu-id="3e7eb-127">-Message</span></span>

<span data-ttu-id="3e7eb-128">Задает сообщение отладки для отправки на консоль.</span><span class="sxs-lookup"><span data-stu-id="3e7eb-128">Specifies the debug message to send to the console.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Msg

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="3e7eb-129">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="3e7eb-129">CommonParameters</span></span>

<span data-ttu-id="3e7eb-130">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="3e7eb-130">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="3e7eb-131">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="3e7eb-131">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="3e7eb-132">Входные данные</span><span class="sxs-lookup"><span data-stu-id="3e7eb-132">INPUTS</span></span>

### <span data-ttu-id="3e7eb-133">System.String</span><span class="sxs-lookup"><span data-stu-id="3e7eb-133">System.String</span></span>

<span data-ttu-id="3e7eb-134">Строку, содержащую сообщение отладки, можно передать в `Write-Debug` .</span><span class="sxs-lookup"><span data-stu-id="3e7eb-134">You can pipe a string that contains a debug message to `Write-Debug`.</span></span>

## <span data-ttu-id="3e7eb-135">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="3e7eb-135">OUTPUTS</span></span>

### <span data-ttu-id="3e7eb-136">None</span><span class="sxs-lookup"><span data-stu-id="3e7eb-136">None</span></span>

<span data-ttu-id="3e7eb-137">`Write-Debug` выполняет запись только в поток отладки.</span><span class="sxs-lookup"><span data-stu-id="3e7eb-137">`Write-Debug` only writes to the debug stream.</span></span> <span data-ttu-id="3e7eb-138">Он не записывает никакие объекты в конвейер.</span><span class="sxs-lookup"><span data-stu-id="3e7eb-138">It does not write any objects to the pipeline.</span></span>

## <span data-ttu-id="3e7eb-139">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="3e7eb-139">NOTES</span></span>

## <span data-ttu-id="3e7eb-140">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="3e7eb-140">RELATED LINKS</span></span>

[<span data-ttu-id="3e7eb-141">О потоках вывода</span><span class="sxs-lookup"><span data-stu-id="3e7eb-141">about_Output_Streams</span></span>](../Microsoft.PowerShell.Core/About/about_Output_Streams.md)

[<span data-ttu-id="3e7eb-142">about_Redirection</span><span class="sxs-lookup"><span data-stu-id="3e7eb-142">about_Redirection</span></span>](../Microsoft.PowerShell.Core/About/about_Redirection.md)

[<span data-ttu-id="3e7eb-143">Write-Error</span><span class="sxs-lookup"><span data-stu-id="3e7eb-143">Write-Error</span></span>](Write-Error.md)

[<span data-ttu-id="3e7eb-144">Write-Host</span><span class="sxs-lookup"><span data-stu-id="3e7eb-144">Write-Host</span></span>](Write-Host.md)

[<span data-ttu-id="3e7eb-145">Write-Output</span><span class="sxs-lookup"><span data-stu-id="3e7eb-145">Write-Output</span></span>](Write-Output.md)

[<span data-ttu-id="3e7eb-146">Write-Progress</span><span class="sxs-lookup"><span data-stu-id="3e7eb-146">Write-Progress</span></span>](Write-Progress.md)

[<span data-ttu-id="3e7eb-147">Write-Verbose</span><span class="sxs-lookup"><span data-stu-id="3e7eb-147">Write-Verbose</span></span>](Write-Verbose.md)

[<span data-ttu-id="3e7eb-148">Write-Warning</span><span class="sxs-lookup"><span data-stu-id="3e7eb-148">Write-Warning</span></span>](Write-Warning.md)
