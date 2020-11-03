---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 08/22/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/set-psdebug?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PSDebug
ms.openlocfilehash: a332ba5226f13b6af393c5ba52c4f3447e2799df
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93225601"
---
# <span data-ttu-id="aa645-103">Set-PSDebug</span><span class="sxs-lookup"><span data-stu-id="aa645-103">Set-PSDebug</span></span>

## <span data-ttu-id="aa645-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="aa645-104">SYNOPSIS</span></span>
<span data-ttu-id="aa645-105">Включает и выключает функции отладки сценариев, задает уровень трассировки и переключает строгий режим.</span><span class="sxs-lookup"><span data-stu-id="aa645-105">Turns script debugging features on and off, sets the trace level, and toggles strict mode.</span></span>

## <span data-ttu-id="aa645-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="aa645-106">SYNTAX</span></span>

### <span data-ttu-id="aa645-107">on</span><span class="sxs-lookup"><span data-stu-id="aa645-107">on</span></span>

```
Set-PSDebug [-Trace <Int32>] [-Step] [-Strict] [<CommonParameters>]
```

### <span data-ttu-id="aa645-108">off</span><span class="sxs-lookup"><span data-stu-id="aa645-108">off</span></span>

```
Set-PSDebug [-Off] [<CommonParameters>]
```

## <span data-ttu-id="aa645-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="aa645-109">DESCRIPTION</span></span>

<span data-ttu-id="aa645-110">`Set-PSDebug`Командлет включает и выключает функции отладки скриптов, устанавливает уровень трассировки и переключает в режим «в режиме».</span><span class="sxs-lookup"><span data-stu-id="aa645-110">The `Set-PSDebug` cmdlet turns script debugging features on and off, sets the trace level, and toggles strict mode.</span></span> <span data-ttu-id="aa645-111">По умолчанию функции отладки PowerShell отключены.</span><span class="sxs-lookup"><span data-stu-id="aa645-111">By default, the PowerShell debug features are off.</span></span>

<span data-ttu-id="aa645-112">Если параметр **трассировки** имеет значение `1` , каждая строка скрипта будет отслеживаться по мере выполнения.</span><span class="sxs-lookup"><span data-stu-id="aa645-112">When the **Trace** parameter has a value of `1`, each line of script is traced as it runs.</span></span> <span data-ttu-id="aa645-113">Если параметр имеет значение `2` , то также отслеживаются присваивания переменных, вызовы функций и вызовы скриптов.</span><span class="sxs-lookup"><span data-stu-id="aa645-113">When the parameter has a value of `2`, variable assignments, function calls, and script calls are also traced.</span></span> <span data-ttu-id="aa645-114">Если указан параметр **Step** , перед выполнением каждой строки скрипта выводится запрос.</span><span class="sxs-lookup"><span data-stu-id="aa645-114">If the **Step** parameter is specified, you're prompted before each line of the script runs.</span></span>

## <span data-ttu-id="aa645-115">Примеры</span><span class="sxs-lookup"><span data-stu-id="aa645-115">EXAMPLES</span></span>

### <span data-ttu-id="aa645-116">Пример 1. Задание уровня трассировки</span><span class="sxs-lookup"><span data-stu-id="aa645-116">Example 1: Set the trace level</span></span>

<span data-ttu-id="aa645-117">В этом примере устанавливается уровень трассировки `2` , а затем выполняется сценарий, отображающий числа 1, 2 и</span><span class="sxs-lookup"><span data-stu-id="aa645-117">This example sets the trace level to `2`, and then runs a script that displays the numbers 1, 2, and</span></span>
3.

```powershell
Set-PSDebug -Trace 2; foreach ($i in 1..3) {$i}
```

```Output
DEBUG:    1+ Set-PSDebug -Trace 2; foreach ($i in  >>>> 1..3) {$i}
DEBUG:     ! SET $foreach = 'IEnumerator'.
DEBUG:    1+ Set-PSDebug -Trace 2; foreach ( >>>> $i in 1..3) {$i}
DEBUG:     ! SET $i = '1'.
DEBUG:    1+ Set-PSDebug -Trace 2; foreach ($i in 1..3) { >>>> $i}
1
DEBUG:    1+ Set-PSDebug -Trace 2; foreach ( >>>> $i in 1..3) {$i}
DEBUG:     ! SET $i = '2'.
DEBUG:    1+ Set-PSDebug -Trace 2; foreach ($i in 1..3) { >>>> $i}
2
DEBUG:    1+ Set-PSDebug -Trace 2; foreach ( >>>> $i in 1..3) {$i}
DEBUG:     ! SET $i = '3'.
DEBUG:    1+ Set-PSDebug -Trace 2; foreach ($i in 1..3) { >>>> $i}
3
DEBUG:    1+ Set-PSDebug -Trace 2; foreach ( >>>> $i in 1..3) {$i}
DEBUG:     ! SET $foreach = ''.
```

### <span data-ttu-id="aa645-118">Пример 2. Включение пошагового выполнения</span><span class="sxs-lookup"><span data-stu-id="aa645-118">Example 2: Turn on stepping</span></span>

<span data-ttu-id="aa645-119">В этом примере включается пошаговая отладка, а затем выполняется сценарий, отображающий числа 1, 2 и 3.</span><span class="sxs-lookup"><span data-stu-id="aa645-119">This example turns on stepping, and then runs a script that displays the numbers 1, 2, and 3.</span></span>

```powershell
Set-PSDebug -Step; foreach ($i in 1..3) {$i}
```

```Output
Continue with this operation?
   1+ Set-PSDebug -Step; foreach ($i in  >>>> 1..3) {$i}
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): A
DEBUG:    1+ Set-PSDebug -Step; foreach ($i in  >>>> 1..3) {$i}
1
2
3
```

### <span data-ttu-id="aa645-120">Пример 3. Использование режима "в режиме"</span><span class="sxs-lookup"><span data-stu-id="aa645-120">Example 3: Use strict mode</span></span>

<span data-ttu-id="aa645-121">В этом примере PowerShell помещается в режиме с максимальным доступом и пытается получить доступ к переменной, которой не назначено значение.</span><span class="sxs-lookup"><span data-stu-id="aa645-121">This example puts PowerShell in strict mode and attempts to access a variable that doesn't have an assigned value.</span></span>

```powershell
Set-PSDebug -Strict; $NewVar
```

```Output
The variable '$NewVar' cannot be retrieved because it has not been set.
At line:1 char:22
+ Set-PSDebug -Strict; $NewVar
```

### <span data-ttu-id="aa645-122">Пример 4. Отключение функций отладки</span><span class="sxs-lookup"><span data-stu-id="aa645-122">Example 4: Turn off debug features</span></span>

<span data-ttu-id="aa645-123">В этом примере отключаются все функции отладки, а затем выполняется сценарий, отображающий числа 1, 2 и 3.</span><span class="sxs-lookup"><span data-stu-id="aa645-123">This example turns off all debugging features, and then runs a script that displays the numbers 1, 2, and 3.</span></span>

```powershell
Set-PSDebug -Off; foreach ($i in 1..3) {$i}
```

```Output
1
2
3
```

## <span data-ttu-id="aa645-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="aa645-124">PARAMETERS</span></span>

### <span data-ttu-id="aa645-125">-Выкл.</span><span class="sxs-lookup"><span data-stu-id="aa645-125">-Off</span></span>

<span data-ttu-id="aa645-126">Отключает все функции отладки сценариев.</span><span class="sxs-lookup"><span data-stu-id="aa645-126">Turns off all script debugging features.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: off
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aa645-127">Шаг</span><span class="sxs-lookup"><span data-stu-id="aa645-127">-Step</span></span>

<span data-ttu-id="aa645-128">Включает пошаговое выполнение сценария.</span><span class="sxs-lookup"><span data-stu-id="aa645-128">Turns on script stepping.</span></span> <span data-ttu-id="aa645-129">Перед выполнением каждой строки PowerShell предлагает прекратить, продолжить или ввести новый уровень интерпретатора для проверки состояния сценария.</span><span class="sxs-lookup"><span data-stu-id="aa645-129">Before each line runs, PowerShell prompts you to stop, continue, or enter a new interpreter level to inspect the state of the script.</span></span>

<span data-ttu-id="aa645-130">При указании параметра **Step** автоматически устанавливается уровень трассировки `1` .</span><span class="sxs-lookup"><span data-stu-id="aa645-130">Specifying the **Step** parameter automatically sets a trace level of `1`.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: on
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aa645-131">— Не ограничивать</span><span class="sxs-lookup"><span data-stu-id="aa645-131">-Strict</span></span>

<span data-ttu-id="aa645-132">Указывает, что переменным должно быть присвоено значение, прежде чем ссылаться на них в скрипте.</span><span class="sxs-lookup"><span data-stu-id="aa645-132">Specifies that variables must be assigned a value before being referenced in a script.</span></span> <span data-ttu-id="aa645-133">Если ссылка на переменную указана перед присвоением значения, PowerShell возвращает ошибку исключения.</span><span class="sxs-lookup"><span data-stu-id="aa645-133">If a variable is referenced before a value is assigned, PowerShell returns an exception error.</span></span> <span data-ttu-id="aa645-134">Это равносильно `Set-StrictMode -Version 1`.</span><span class="sxs-lookup"><span data-stu-id="aa645-134">This is equivalent to `Set-StrictMode -Version 1`.</span></span> <span data-ttu-id="aa645-135">Дополнительные сведения см. в разделе [Set-StrictMode](Set-StrictMode.md).</span><span class="sxs-lookup"><span data-stu-id="aa645-135">For more information, see [Set-StrictMode](Set-StrictMode.md).</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: on
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aa645-136">-Trace</span><span class="sxs-lookup"><span data-stu-id="aa645-136">-Trace</span></span>

<span data-ttu-id="aa645-137">Задает уровень трассировки для каждой строки в скрипте.</span><span class="sxs-lookup"><span data-stu-id="aa645-137">Specifies the trace level for each line in a script.</span></span> <span data-ttu-id="aa645-138">Каждая строка отслеживается по мере выполнения.</span><span class="sxs-lookup"><span data-stu-id="aa645-138">Each line is traced as it's run.</span></span>

<span data-ttu-id="aa645-139">Для этого параметра допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="aa645-139">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="aa645-140">0: отключить трассировку скрипта.</span><span class="sxs-lookup"><span data-stu-id="aa645-140">0: Turn script tracing off.</span></span>
- <span data-ttu-id="aa645-141">1: трассировка строк скрипта при их выполнении.</span><span class="sxs-lookup"><span data-stu-id="aa645-141">1: Trace script lines as they run.</span></span>
- <span data-ttu-id="aa645-142">2: трассировка строк скрипта, назначения переменных, вызовы функций и скрипты.</span><span class="sxs-lookup"><span data-stu-id="aa645-142">2: Trace script lines, variable assignments, function calls, and scripts.</span></span>

```yaml
Type: System.Int32
Parameter Sets: on
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aa645-143">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="aa645-143">CommonParameters</span></span>

<span data-ttu-id="aa645-144">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="aa645-144">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="aa645-145">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="aa645-145">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="aa645-146">Входные данные</span><span class="sxs-lookup"><span data-stu-id="aa645-146">INPUTS</span></span>

### <span data-ttu-id="aa645-147">Нет</span><span class="sxs-lookup"><span data-stu-id="aa645-147">None</span></span>

<span data-ttu-id="aa645-148">Вы не можете конвейерировать входные данные для этого командлета.</span><span class="sxs-lookup"><span data-stu-id="aa645-148">You can't pipeline input to this cmdlet.</span></span>

## <span data-ttu-id="aa645-149">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="aa645-149">OUTPUTS</span></span>

### <span data-ttu-id="aa645-150">Нет</span><span class="sxs-lookup"><span data-stu-id="aa645-150">None</span></span>

<span data-ttu-id="aa645-151">Этот командлет не возвращает никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="aa645-151">This cmdlet doesn't return any output.</span></span>

## <span data-ttu-id="aa645-152">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="aa645-152">NOTES</span></span>

## <span data-ttu-id="aa645-153">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="aa645-153">RELATED LINKS</span></span>

[<span data-ttu-id="aa645-154">about_Debuggers</span><span class="sxs-lookup"><span data-stu-id="aa645-154">about_Debuggers</span></span>](./About/about_Debuggers.md)

[<span data-ttu-id="aa645-155">Debug-Process</span><span class="sxs-lookup"><span data-stu-id="aa645-155">Debug-Process</span></span>](../Microsoft.PowerShell.Management/Debug-Process.md)

[<span data-ttu-id="aa645-156">Set-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="aa645-156">Set-PSBreakpoint</span></span>](../Microsoft.PowerShell.Utility/Set-PSBreakpoint.md)

[<span data-ttu-id="aa645-157">Set-StrictMode</span><span class="sxs-lookup"><span data-stu-id="aa645-157">Set-StrictMode</span></span>](Set-StrictMode.md)

[<span data-ttu-id="aa645-158">Write-Debug</span><span class="sxs-lookup"><span data-stu-id="aa645-158">Write-Debug</span></span>](../Microsoft.PowerShell.Utility/Write-Debug.md)
