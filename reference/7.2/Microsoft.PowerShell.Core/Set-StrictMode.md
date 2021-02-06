---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 04/09/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/set-strictmode?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-StrictMode
ms.openlocfilehash: 58261830ca65da295aeb85cda22d0a78762e2502
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99605072"
---
# <span data-ttu-id="de8f7-102">Set-StrictMode</span><span class="sxs-lookup"><span data-stu-id="de8f7-102">Set-StrictMode</span></span>

## <span data-ttu-id="de8f7-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="de8f7-103">SYNOPSIS</span></span>
<span data-ttu-id="de8f7-104">Устанавливает и применяет правила кодирования в выражениях, сценариях и блоках сценариев.</span><span class="sxs-lookup"><span data-stu-id="de8f7-104">Establishes and enforces coding rules in expressions, scripts, and script blocks.</span></span>

## <span data-ttu-id="de8f7-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="de8f7-105">SYNTAX</span></span>

### <span data-ttu-id="de8f7-106">Версия (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="de8f7-106">Version (Default)</span></span>

```
Set-StrictMode -Version <Version> [<CommonParameters>]
```

### <span data-ttu-id="de8f7-107">Выключено</span><span class="sxs-lookup"><span data-stu-id="de8f7-107">Off</span></span>

```
Set-StrictMode [-Off] [<CommonParameters>]
```

## <span data-ttu-id="de8f7-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="de8f7-108">DESCRIPTION</span></span>

<span data-ttu-id="de8f7-109">`Set-StrictMode`Командлет настраивает в режиме ограниченного режима для текущей области и всех дочерних областей, включает и выключает ее.</span><span class="sxs-lookup"><span data-stu-id="de8f7-109">The `Set-StrictMode` cmdlet configures strict mode for the current scope and all child scopes, and turns it on and off.</span></span> <span data-ttu-id="de8f7-110">Если режим строгого режима включен, PowerShell создает завершающую ошибку, если содержимое выражения, скрипта или блока скрипта нарушает основные рекомендации по написанию кода.</span><span class="sxs-lookup"><span data-stu-id="de8f7-110">When strict mode is on, PowerShell generates a terminating error when the content of an expression, script, or script block violates basic best-practice coding rules.</span></span>

<span data-ttu-id="de8f7-111">Используйте параметр **Version** , чтобы определить, какие правила кодирования применяются.</span><span class="sxs-lookup"><span data-stu-id="de8f7-111">Use the **Version** parameter to determine which coding rules are enforced.</span></span>

<span data-ttu-id="de8f7-112">`Set-PSDebug -Strict` включает в себя режим для глобальной области.</span><span class="sxs-lookup"><span data-stu-id="de8f7-112">`Set-PSDebug -Strict` cmdlet turns on strict mode for the global scope.</span></span> <span data-ttu-id="de8f7-113">`Set-StrictMode` влияет только на текущую область и ее дочерние области.</span><span class="sxs-lookup"><span data-stu-id="de8f7-113">`Set-StrictMode` affects only the current scope and its child scopes.</span></span> <span data-ttu-id="de8f7-114">Таким образом, его можно использовать в скрипте или функции для переопределения параметра, унаследованного от глобальной области.</span><span class="sxs-lookup"><span data-stu-id="de8f7-114">Therefore, you can use it in a script or function to override the setting inherited from the global scope.</span></span>

<span data-ttu-id="de8f7-115">Если `Set-StrictMode` параметр имеет значение OFF, PowerShell имеет следующие характеристики:</span><span class="sxs-lookup"><span data-stu-id="de8f7-115">When `Set-StrictMode` is off, PowerShell has the following behaviors:</span></span>

- <span data-ttu-id="de8f7-116">Предполагается, что неинициализированные переменные имеют значение 0 (ноль) или `$Null` , в зависимости от типа.</span><span class="sxs-lookup"><span data-stu-id="de8f7-116">Uninitialized variables are assumed to have a value of 0 (zero) or `$Null`, depending on type</span></span>
- <span data-ttu-id="de8f7-117">Возвращают ссылки на несуществующие свойства `$Null`</span><span class="sxs-lookup"><span data-stu-id="de8f7-117">References to non-existent properties return `$Null`</span></span>
- <span data-ttu-id="de8f7-118">Результаты неправильного синтаксиса функции зависят от условий возникновения ошибок</span><span class="sxs-lookup"><span data-stu-id="de8f7-118">Results of improper function syntax vary with the error conditions</span></span>
- <span data-ttu-id="de8f7-119">Попытка получить значение с помощью недопустимого индекса в массиве возвращает `$Null`</span><span class="sxs-lookup"><span data-stu-id="de8f7-119">Attempting to retrieve a value using an invalid index in an array returns `$Null`</span></span>

## <span data-ttu-id="de8f7-120">Примеры</span><span class="sxs-lookup"><span data-stu-id="de8f7-120">EXAMPLES</span></span>

### <span data-ttu-id="de8f7-121">Пример 1. Включение режима "в режиме" для версии 1,0</span><span class="sxs-lookup"><span data-stu-id="de8f7-121">Example 1: Turn on strict mode as version 1.0</span></span>

```powershell
# Strict mode is off by default.
$a -gt 5
```

```Output
False
```

```powershell
Set-StrictMode -Version 1.0
$a -gt 5
```

```Output
InvalidOperation: The variable '$a' cannot be retrieved because it has not been set.
```

<span data-ttu-id="de8f7-122">Если в режиме ограниченного режима задана версия 1,0, пытается ссылаться на переменные, которые не были инициализированы ошибкой.</span><span class="sxs-lookup"><span data-stu-id="de8f7-122">With strict mode set to version 1.0, attempts to reference variables that are not initialized fail.</span></span>

### <span data-ttu-id="de8f7-123">Пример 2. Включение режима "в режиме" для версии 2,0</span><span class="sxs-lookup"><span data-stu-id="de8f7-123">Example 2: Turn on strict mode as version 2.0</span></span>

```powershell
# Strict mode is off by default.
function add ($a, $b) {
    '$a = ' + $a
    '$b = ' + $b
    '$a+$b = ' + ($a + $b)
}
add 3 4
```

```Output
$a = 3
$b = 4
$a+$b = 7
```

```powershell
add(3,4)
```

```Output
$a = 3 4
$b =
$a+$b = 3 4
```

```powershell
Set-StrictMode -Version 2.0
add(3,4)
```

```Output
InvalidOperation: The function or command was called as if it were a method. Parameters should be separated by spaces. For information about parameters, see the about_Parameters Help topic.
```

```powershell
Set-StrictMode -Off
$string = "This is a string."
$null -eq $string.Month
```

```Output
True
```

```powershell
Set-StrictMode -Version 2.0
$string = "This is a string."
$null -eq $string.Month
```

```Output
PropertyNotFoundException: The property 'Month' cannot be found on this object. Verify that the property exists.
```

<span data-ttu-id="de8f7-124">Эта команда включает строгий режим и задает его версию 2.0.</span><span class="sxs-lookup"><span data-stu-id="de8f7-124">This command turns strict mode on and sets it to version 2.0.</span></span> <span data-ttu-id="de8f7-125">В результате PowerShell возвращает ошибку, если используется синтаксис метода, который использует круглые скобки и запятые для вызова функции или ссылки на неинициализированные переменные или несуществующие свойства.</span><span class="sxs-lookup"><span data-stu-id="de8f7-125">As a result, PowerShell returns an error if you use method syntax, which uses parentheses and commas, for a function call or reference uninitialized variables or non-existent properties.</span></span>

<span data-ttu-id="de8f7-126">Пример выходных данных приведен для строгого режима версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="de8f7-126">The sample output shows the effect of version 2.0 strict mode.</span></span>

<span data-ttu-id="de8f7-127">Если строгий режим версии 2.0 не используется, значение "(3,4)" интерпретируется как один объект массива, к которому ничего не добавляется.</span><span class="sxs-lookup"><span data-stu-id="de8f7-127">Without version 2.0 strict mode, the "(3,4)" value is interpreted as a single array object to which nothing is added.</span></span> <span data-ttu-id="de8f7-128">С помощью режима в режиме версии 2,0 он правильно интерпретируется как ошибочный синтаксис для отправки двух значений.</span><span class="sxs-lookup"><span data-stu-id="de8f7-128">By using version 2.0 strict mode, it is correctly interpreted as faulty syntax for submitting two values.</span></span>

<span data-ttu-id="de8f7-129">Без версии 2,0 ссылка на несуществующее свойство **Month** строки возвращает только `$Null` .</span><span class="sxs-lookup"><span data-stu-id="de8f7-129">Without version 2.0, the reference to the non-existent **Month** property of a string returns only `$Null`.</span></span> <span data-ttu-id="de8f7-130">С помощью версии 2,0 она правильно интерпретируется как ошибка ссылки.</span><span class="sxs-lookup"><span data-stu-id="de8f7-130">By using version 2.0, it is interpreted correctly as a reference error.</span></span>

### <span data-ttu-id="de8f7-131">Пример 3. Включение режима "в режиме" для версии 3,0</span><span class="sxs-lookup"><span data-stu-id="de8f7-131">Example 3: Turn on strict mode as version 3.0</span></span>

<span data-ttu-id="de8f7-132">Если задан режим " **выкл**.", то результатом недопустимости или выхода из индексов границ будет возвращено значение null.</span><span class="sxs-lookup"><span data-stu-id="de8f7-132">With strict mode set to **Off**, invalid or out of bounds indexes result return null values.</span></span>

```powershell
# Strict mode is off by default.
$a = @(1)
$null -eq $a[2]
$null -eq $a['abc']
```

```Output
True
True
```

```powershell
Set-StrictMode -Version 3
$a = @(1)
$null -eq $a[2]
$null -eq $a['abc']
```

```Output
OperationStopped: Index was outside the bounds of the array.

InvalidArgument: Cannot convert value "abc" to type "System.Int32". Error: "Input string was not in a correct format."
```

<span data-ttu-id="de8f7-133">Если в режиме строгих версий задано значение версии 3 или выше, индексы недопустим или out вне границ приводят к ошибкам.</span><span class="sxs-lookup"><span data-stu-id="de8f7-133">With strict mode set to version 3 or higher, invalid or out of bounds indexes result in errors.</span></span>

## <span data-ttu-id="de8f7-134">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="de8f7-134">PARAMETERS</span></span>

### <span data-ttu-id="de8f7-135">-Выкл.</span><span class="sxs-lookup"><span data-stu-id="de8f7-135">-Off</span></span>

<span data-ttu-id="de8f7-136">Указывает, что этот командлет выключает режим "ограничено" для текущей области и всех дочерних областей.</span><span class="sxs-lookup"><span data-stu-id="de8f7-136">Indicates that this cmdlet turns strict mode off for the current scope and all child scopes.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Off
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="de8f7-137">-Version</span><span class="sxs-lookup"><span data-stu-id="de8f7-137">-Version</span></span>

<span data-ttu-id="de8f7-138">Определяет условия, которые приводят к ошибке в строгом режиме.</span><span class="sxs-lookup"><span data-stu-id="de8f7-138">Specifies the conditions that cause an error in strict mode.</span></span> <span data-ttu-id="de8f7-139">Этот параметр принимает любой допустимый номер версии PowerShell.</span><span class="sxs-lookup"><span data-stu-id="de8f7-139">This parameter accepts any valid PowerShell version number.</span></span> <span data-ttu-id="de8f7-140">Любое число выше 3 обрабатывается как **Последнее**.</span><span class="sxs-lookup"><span data-stu-id="de8f7-140">Any number higher than 3 is treated as **Latest**.</span></span>

<span data-ttu-id="de8f7-141">Действующие значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="de8f7-141">The effective values for this parameter are:</span></span>

- <span data-ttu-id="de8f7-142">1.0</span><span class="sxs-lookup"><span data-stu-id="de8f7-142">1.0</span></span>
  - <span data-ttu-id="de8f7-143">Запрещает ссылки на неинициализированные переменные, за исключением неинициализированных переменных в строках.</span><span class="sxs-lookup"><span data-stu-id="de8f7-143">Prohibits references to uninitialized variables, except for uninitialized variables in strings.</span></span>
- <span data-ttu-id="de8f7-144">2.0</span><span class="sxs-lookup"><span data-stu-id="de8f7-144">2.0</span></span>
  - <span data-ttu-id="de8f7-145">Запрещает ссылки на неинициализированные переменные.</span><span class="sxs-lookup"><span data-stu-id="de8f7-145">Prohibits references to uninitialized variables.</span></span> <span data-ttu-id="de8f7-146">Сюда входят неинициализированные переменные в строках.</span><span class="sxs-lookup"><span data-stu-id="de8f7-146">This includes uninitialized variables in strings.</span></span>
  - <span data-ttu-id="de8f7-147">Запрещает ссылки на несуществующие свойства объекта.</span><span class="sxs-lookup"><span data-stu-id="de8f7-147">Prohibits references to non-existent properties of an object.</span></span>
  - <span data-ttu-id="de8f7-148">Запрещает вызовы функций, которые используют синтаксис для вызова методов.</span><span class="sxs-lookup"><span data-stu-id="de8f7-148">Prohibits function calls that use the syntax for calling methods.</span></span>
- <span data-ttu-id="de8f7-149">3.0</span><span class="sxs-lookup"><span data-stu-id="de8f7-149">3.0</span></span>
  - <span data-ttu-id="de8f7-150">Запрещает ссылки на неинициализированные переменные.</span><span class="sxs-lookup"><span data-stu-id="de8f7-150">Prohibits references to uninitialized variables.</span></span> <span data-ttu-id="de8f7-151">Сюда входят неинициализированные переменные в строках.</span><span class="sxs-lookup"><span data-stu-id="de8f7-151">This includes uninitialized variables in strings.</span></span>
  - <span data-ttu-id="de8f7-152">Запрещает ссылки на несуществующие свойства объекта.</span><span class="sxs-lookup"><span data-stu-id="de8f7-152">Prohibits references to non-existent properties of an object.</span></span>
  - <span data-ttu-id="de8f7-153">Запрещает вызовы функций, которые используют синтаксис для вызова методов.</span><span class="sxs-lookup"><span data-stu-id="de8f7-153">Prohibits function calls that use the syntax for calling methods.</span></span>
  - <span data-ttu-id="de8f7-154">Запрет вне границ или неразрешимые индексы массива.</span><span class="sxs-lookup"><span data-stu-id="de8f7-154">Prohibit out of bounds or unresolvable array indexes.</span></span>
- <span data-ttu-id="de8f7-155">Последняя версия</span><span class="sxs-lookup"><span data-stu-id="de8f7-155">Latest</span></span>
  - <span data-ttu-id="de8f7-156">Выбирается последняя доступная версия.</span><span class="sxs-lookup"><span data-stu-id="de8f7-156">Selects the latest version available.</span></span> <span data-ttu-id="de8f7-157">Самая последняя версия — наиболее доступная.</span><span class="sxs-lookup"><span data-stu-id="de8f7-157">The latest version is the most strict.</span></span> <span data-ttu-id="de8f7-158">Используйте это значение, чтобы убедиться, что скрипты используют наиболее доступную версию, даже если новые версии добавлены в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="de8f7-158">Use this value to make sure that scripts use the strictest available version, even when new versions are added to PowerShell.</span></span>

> [!CAUTION]
> <span data-ttu-id="de8f7-159">Использование последней **версии** в  скриптах.</span><span class="sxs-lookup"><span data-stu-id="de8f7-159">Using a **Version** of **Latest** in scripts.</span></span> <span data-ttu-id="de8f7-160">Значение **последней** может измениться в новых выпусках PowerShell.</span><span class="sxs-lookup"><span data-stu-id="de8f7-160">The meaning of **Latest** can change in new releases of PowerShell.</span></span> <span data-ttu-id="de8f7-161">Таким образом, сценарий, написанный для более ранней версии PowerShell, который использует, `Set-StrictMode -Version Latest` имеет более ограниченные правила при запуске в более новой версии PowerShell.</span><span class="sxs-lookup"><span data-stu-id="de8f7-161">Therefore, a script written for an older version of PowerShell that uses `Set-StrictMode -Version Latest` is subject to more restrictive rules when run in a newer version of PowerShell.</span></span>

```yaml
Type: System.Version
Parameter Sets: Version
Aliases: v

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="de8f7-162">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="de8f7-162">CommonParameters</span></span>

<span data-ttu-id="de8f7-163">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="de8f7-163">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="de8f7-164">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="de8f7-164">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="de8f7-165">Входные данные</span><span class="sxs-lookup"><span data-stu-id="de8f7-165">INPUTS</span></span>

### <span data-ttu-id="de8f7-166">None</span><span class="sxs-lookup"><span data-stu-id="de8f7-166">None</span></span>

<span data-ttu-id="de8f7-167">В этот командлет нельзя передать входные данные.</span><span class="sxs-lookup"><span data-stu-id="de8f7-167">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="de8f7-168">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="de8f7-168">OUTPUTS</span></span>

### <span data-ttu-id="de8f7-169">None</span><span class="sxs-lookup"><span data-stu-id="de8f7-169">None</span></span>

<span data-ttu-id="de8f7-170">Этот командлет не возвращает никакие выходные данные.</span><span class="sxs-lookup"><span data-stu-id="de8f7-170">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="de8f7-171">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="de8f7-171">NOTES</span></span>

<span data-ttu-id="de8f7-172">`Set-StrictMode` действует только в области, в которой он задан, и в его дочерних областях.</span><span class="sxs-lookup"><span data-stu-id="de8f7-172">`Set-StrictMode` is effective only in the scope in which it is set and in its child scopes.</span></span> <span data-ttu-id="de8f7-173">Дополнительные сведения об областях в PowerShell см. в разделе [about_Scopes](about/about_Scopes.md).</span><span class="sxs-lookup"><span data-stu-id="de8f7-173">For more information about scopes in PowerShell, see [about_Scopes](about/about_Scopes.md).</span></span>

## <span data-ttu-id="de8f7-174">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="de8f7-174">RELATED LINKS</span></span>

[<span data-ttu-id="de8f7-175">Set-PSDebug</span><span class="sxs-lookup"><span data-stu-id="de8f7-175">Set-PSDebug</span></span>](Set-PSDebug.md)
