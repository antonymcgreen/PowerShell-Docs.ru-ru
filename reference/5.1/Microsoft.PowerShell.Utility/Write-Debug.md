---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/write-debug?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-Debug
ms.openlocfilehash: 7e622367f1753fc15bed26fe083e9f343fd82b85
ms.sourcegitcommit: 16883bb67e34b3915798070f60f974bf85160bd3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "93232838"
---
# <span data-ttu-id="0632f-103">Write-Debug</span><span class="sxs-lookup"><span data-stu-id="0632f-103">Write-Debug</span></span>

## <span data-ttu-id="0632f-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="0632f-104">SYNOPSIS</span></span>
<span data-ttu-id="0632f-105">Выводит сообщение отладки на консоль.</span><span class="sxs-lookup"><span data-stu-id="0632f-105">Writes a debug message to the console.</span></span>

## <span data-ttu-id="0632f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0632f-106">SYNTAX</span></span>

```
Write-Debug [-Message] <String> [<CommonParameters>]
```

## <span data-ttu-id="0632f-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0632f-107">DESCRIPTION</span></span>

<span data-ttu-id="0632f-108">`Write-Debug`Командлет записывает сообщения отладки на узел из скрипта или команды.</span><span class="sxs-lookup"><span data-stu-id="0632f-108">The `Write-Debug` cmdlet writes debug messages to the host from a script or command.</span></span>

<span data-ttu-id="0632f-109">По умолчанию сообщения отладки не отображаются в консоли, но их можно отобразить с помощью параметра **отладки** или `$DebugPreference` переменной.</span><span class="sxs-lookup"><span data-stu-id="0632f-109">By default, debug messages are not displayed in the console, but you can display them by using the **Debug** parameter or the `$DebugPreference` variable.</span></span>

## <span data-ttu-id="0632f-110">Примеры</span><span class="sxs-lookup"><span data-stu-id="0632f-110">EXAMPLES</span></span>

### <span data-ttu-id="0632f-111">Пример 1. понимание $DebugPreference</span><span class="sxs-lookup"><span data-stu-id="0632f-111">Example 1: Understand $DebugPreference</span></span>

<span data-ttu-id="0632f-112">В этом примере записывается сообщение отладки.</span><span class="sxs-lookup"><span data-stu-id="0632f-112">This example writes a debug message.</span></span>

```powershell
Write-Debug "Cannot open file."
```

<span data-ttu-id="0632f-113">Значение по умолчанию `$DebugPreference` — **SilentlyContinue**.</span><span class="sxs-lookup"><span data-stu-id="0632f-113">The default value of `$DebugPreference` is **SilentlyContinue**.</span></span> <span data-ttu-id="0632f-114">Поэтому сообщение не отображается в консоли.</span><span class="sxs-lookup"><span data-stu-id="0632f-114">Therefore, the message is not displayed in the console.</span></span>

### <span data-ttu-id="0632f-115">Пример 2. изменение значения $DebugPreference</span><span class="sxs-lookup"><span data-stu-id="0632f-115">Example 2: Change the value of $DebugPreference</span></span>

<span data-ttu-id="0632f-116">В этом примере показан результат изменения значения `$DebugPreference` переменной.</span><span class="sxs-lookup"><span data-stu-id="0632f-116">This example shows the effect of changing the value of the `$DebugPreference` variable.</span></span> <span data-ttu-id="0632f-117">Сначала мы отображаем текущее значение `$DebugPreference` и попытались написать сообщение отладки.</span><span class="sxs-lookup"><span data-stu-id="0632f-117">First, we display the current value of `$DebugPreference` and attempt to write a debug message.</span></span> <span data-ttu-id="0632f-118">Затем мы изменим значение `$DebugPreference` на **Continue** , что позволяет отображать сообщения отладки.</span><span class="sxs-lookup"><span data-stu-id="0632f-118">Then we change the value of `$DebugPreference` to **Continue** , which allows debug messages to be displayed.</span></span>

```
PS> $DebugPreference
SilentlyContinue
PS> Write-Debug "Cannot open file."
PS>
PS> $DebugPreference = "Continue"
PS> Write-Debug "Cannot open file."
DEBUG: Cannot open file.
```

<span data-ttu-id="0632f-119">Дополнительные сведения о `$DebugPreference` см. в разделе [about_Preference_Variables](/powershell/module/Microsoft.PowerShell.Core/About/about_Preference_Variables).</span><span class="sxs-lookup"><span data-stu-id="0632f-119">For more information about `$DebugPreference`, see [about_Preference_Variables](/powershell/module/Microsoft.PowerShell.Core/About/about_Preference_Variables).</span></span>

### <span data-ttu-id="0632f-120">Пример 3. Переопределение $DebugPreference с помощью параметра Debug</span><span class="sxs-lookup"><span data-stu-id="0632f-120">Example 3: Use the Debug parameter to override $DebugPreference</span></span>

<span data-ttu-id="0632f-121">`Test-Debug`Функция записывает значение `$DebugPreference` переменной в узел PowerShell и в поток отладки.</span><span class="sxs-lookup"><span data-stu-id="0632f-121">The `Test-Debug` function writes the value of the `$DebugPreference` variable to the PowerShell host and to the Debug stream.</span></span> <span data-ttu-id="0632f-122">В этом примере мы используем параметр **Debug** для переопределения `$DebugPreference` значения.</span><span class="sxs-lookup"><span data-stu-id="0632f-122">In this example, we use the **Debug** parameter to override the `$DebugPreference` value.</span></span>

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
DEBUG: $DebugPreference is Inquire

Confirm
Continue with this operation?
[Y] Yes  [A] Yes to All  [H] Halt Command  [?] Help (default is "Y"):
$DebugPreference is Inquire
PS> $DebugPreference
SilentlyContinue
```

<span data-ttu-id="0632f-123">Обратите внимание, что `$DebugPreference` при использовании параметра **Debug** значение изменяется.</span><span class="sxs-lookup"><span data-stu-id="0632f-123">Notice that the value of `$DebugPreference` changes when you use the **Debug** parameter.</span></span> <span data-ttu-id="0632f-124">Это изменение влияет только на область действия функции.</span><span class="sxs-lookup"><span data-stu-id="0632f-124">This change only affects the scope of the function.</span></span> <span data-ttu-id="0632f-125">Это значение не затрагивается за пределами функции.</span><span class="sxs-lookup"><span data-stu-id="0632f-125">The value is not affected outside the function.</span></span>

> [!NOTE]
> <span data-ttu-id="0632f-126">Если значение параметра `$DebugPreference` является **запросом** , PowerShell останавливает выполнение, чтобы задать продолжение выполнения.</span><span class="sxs-lookup"><span data-stu-id="0632f-126">When the value of `$DebugPreference` is **Inquire** , PowerShell halts execution to ask if execution should continue.</span></span>

<span data-ttu-id="0632f-127">Дополнительные сведения об общем параметре **Debug** см. в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="0632f-127">For more information about the **Debug** common parameter, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0632f-128">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0632f-128">PARAMETERS</span></span>

### <span data-ttu-id="0632f-129">-Message</span><span class="sxs-lookup"><span data-stu-id="0632f-129">-Message</span></span>

<span data-ttu-id="0632f-130">Задает сообщение отладки для отправки на консоль.</span><span class="sxs-lookup"><span data-stu-id="0632f-130">Specifies the debug message to send to the console.</span></span>

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

### <span data-ttu-id="0632f-131">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="0632f-131">CommonParameters</span></span>

<span data-ttu-id="0632f-132">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="0632f-132">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0632f-133">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="0632f-133">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0632f-134">Входные данные</span><span class="sxs-lookup"><span data-stu-id="0632f-134">INPUTS</span></span>

### <span data-ttu-id="0632f-135">System.String</span><span class="sxs-lookup"><span data-stu-id="0632f-135">System.String</span></span>

<span data-ttu-id="0632f-136">Строку, содержащую сообщение отладки, можно передать в `Write-Debug` .</span><span class="sxs-lookup"><span data-stu-id="0632f-136">You can pipe a string that contains a debug message to `Write-Debug`.</span></span>

## <span data-ttu-id="0632f-137">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="0632f-137">OUTPUTS</span></span>

### <span data-ttu-id="0632f-138">Нет</span><span class="sxs-lookup"><span data-stu-id="0632f-138">None</span></span>

<span data-ttu-id="0632f-139">`Write-Debug` выполняет запись только в поток отладки.</span><span class="sxs-lookup"><span data-stu-id="0632f-139">`Write-Debug` only writes to the debug stream.</span></span> <span data-ttu-id="0632f-140">Он не записывает никакие объекты в конвейер.</span><span class="sxs-lookup"><span data-stu-id="0632f-140">It does not write any objects to the pipeline.</span></span>

## <span data-ttu-id="0632f-141">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="0632f-141">NOTES</span></span>

## <span data-ttu-id="0632f-142">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="0632f-142">RELATED LINKS</span></span>

[<span data-ttu-id="0632f-143">about_Output_Streams</span><span class="sxs-lookup"><span data-stu-id="0632f-143">about_Output_Streams</span></span>](../Microsoft.PowerShell.Core/About/about_Output_Streams.md)

[<span data-ttu-id="0632f-144">about_Redirection</span><span class="sxs-lookup"><span data-stu-id="0632f-144">about_Redirection</span></span>](../Microsoft.PowerShell.Core/About/about_Redirection.md)

[<span data-ttu-id="0632f-145">Ошибка записи</span><span class="sxs-lookup"><span data-stu-id="0632f-145">Write-Error</span></span>](Write-Error.md)

[<span data-ttu-id="0632f-146">Write-Host</span><span class="sxs-lookup"><span data-stu-id="0632f-146">Write-Host</span></span>](Write-Host.md)

[<span data-ttu-id="0632f-147">Write-Output</span><span class="sxs-lookup"><span data-stu-id="0632f-147">Write-Output</span></span>](Write-Output.md)

[<span data-ttu-id="0632f-148">Write-Progress</span><span class="sxs-lookup"><span data-stu-id="0632f-148">Write-Progress</span></span>](Write-Progress.md)

[<span data-ttu-id="0632f-149">Write-Verbose</span><span class="sxs-lookup"><span data-stu-id="0632f-149">Write-Verbose</span></span>](Write-Verbose.md)

[<span data-ttu-id="0632f-150">Write-Warning</span><span class="sxs-lookup"><span data-stu-id="0632f-150">Write-Warning</span></span>](Write-Warning.md)
