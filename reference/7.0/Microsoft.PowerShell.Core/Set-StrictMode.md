---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 04/09/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/set-strictmode?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-StrictMode
ms.openlocfilehash: ef80c2c63855bffcd23f51474009b241f8f4b3ba
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93225597"
---
# <span data-ttu-id="4af74-103">Set-StrictMode</span><span class="sxs-lookup"><span data-stu-id="4af74-103">Set-StrictMode</span></span>

## <span data-ttu-id="4af74-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="4af74-104">SYNOPSIS</span></span>
<span data-ttu-id="4af74-105">Устанавливает и применяет правила кодирования в выражениях, сценариях и блоках сценариев.</span><span class="sxs-lookup"><span data-stu-id="4af74-105">Establishes and enforces coding rules in expressions, scripts, and script blocks.</span></span>

## <span data-ttu-id="4af74-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4af74-106">SYNTAX</span></span>

### <span data-ttu-id="4af74-107">Версия (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="4af74-107">Version (Default)</span></span>

```
Set-StrictMode -Version <Version> [<CommonParameters>]
```

### <span data-ttu-id="4af74-108">Выключено</span><span class="sxs-lookup"><span data-stu-id="4af74-108">Off</span></span>

```
Set-StrictMode [-Off] [<CommonParameters>]
```

## <span data-ttu-id="4af74-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="4af74-109">DESCRIPTION</span></span>

<span data-ttu-id="4af74-110">`Set-StrictMode`Командлет настраивает в режиме ограниченного режима для текущей области и всех дочерних областей, включает и выключает ее.</span><span class="sxs-lookup"><span data-stu-id="4af74-110">The `Set-StrictMode` cmdlet configures strict mode for the current scope and all child scopes, and turns it on and off.</span></span> <span data-ttu-id="4af74-111">Если режим строгого режима включен, PowerShell создает завершающую ошибку, если содержимое выражения, скрипта или блока скрипта нарушает основные рекомендации по написанию кода.</span><span class="sxs-lookup"><span data-stu-id="4af74-111">When strict mode is on, PowerShell generates a terminating error when the content of an expression, script, or script block violates basic best-practice coding rules.</span></span>

<span data-ttu-id="4af74-112">Используйте параметр **Version** , чтобы определить, какие правила кодирования применяются.</span><span class="sxs-lookup"><span data-stu-id="4af74-112">Use the **Version** parameter to determine which coding rules are enforced.</span></span>

<span data-ttu-id="4af74-113">`Set-PSDebug -Strict` включает в себя режим для глобальной области.</span><span class="sxs-lookup"><span data-stu-id="4af74-113">`Set-PSDebug -Strict` cmdlet turns on strict mode for the global scope.</span></span> <span data-ttu-id="4af74-114">`Set-StrictMode` влияет только на текущую область и ее дочерние области.</span><span class="sxs-lookup"><span data-stu-id="4af74-114">`Set-StrictMode` affects only the current scope and its child scopes.</span></span> <span data-ttu-id="4af74-115">Таким образом, его можно использовать в скрипте или функции для переопределения параметра, унаследованного от глобальной области.</span><span class="sxs-lookup"><span data-stu-id="4af74-115">Therefore, you can use it in a script or function to override the setting inherited from the global scope.</span></span>

<span data-ttu-id="4af74-116">Если `Set-StrictMode` параметр имеет значение OFF, PowerShell имеет следующие характеристики:</span><span class="sxs-lookup"><span data-stu-id="4af74-116">When `Set-StrictMode` is off, PowerShell has the following behaviors:</span></span>

- <span data-ttu-id="4af74-117">Предполагается, что неинициализированные переменные имеют значение 0 (ноль) или `$Null` , в зависимости от типа.</span><span class="sxs-lookup"><span data-stu-id="4af74-117">Uninitialized variables are assumed to have a value of 0 (zero) or `$Null`, depending on type</span></span>
- <span data-ttu-id="4af74-118">Возвращают ссылки на несуществующие свойства `$Null`</span><span class="sxs-lookup"><span data-stu-id="4af74-118">References to non-existent properties return `$Null`</span></span>
- <span data-ttu-id="4af74-119">Результаты неправильного синтаксиса функции зависят от условий возникновения ошибок</span><span class="sxs-lookup"><span data-stu-id="4af74-119">Results of improper function syntax vary with the error conditions</span></span>
- <span data-ttu-id="4af74-120">Попытка получить значение с помощью недопустимого индекса в массиве возвращает `$Null`</span><span class="sxs-lookup"><span data-stu-id="4af74-120">Attempting to retrieve a value using an invalid index in an array returns `$Null`</span></span>

## <span data-ttu-id="4af74-121">Примеры</span><span class="sxs-lookup"><span data-stu-id="4af74-121">EXAMPLES</span></span>

### <span data-ttu-id="4af74-122">Пример 1. Включение режима "в режиме" для версии 1,0</span><span class="sxs-lookup"><span data-stu-id="4af74-122">Example 1: Turn on strict mode as version 1.0</span></span>

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
The variable $a cannot be retrieved because it has not been set yet.

At line:1 char:3
+ $a <<<<  -gt 5
+ CategoryInfo          : InvalidOperation: (a:Token) [], RuntimeException
+ FullyQualifiedErrorId : VariableIsUndefined
```

<span data-ttu-id="4af74-123">Если в режиме ограниченного режима задана версия 1,0, пытается ссылаться на переменные, которые не были инициализированы ошибкой.</span><span class="sxs-lookup"><span data-stu-id="4af74-123">With strict mode set to version 1.0, attempts to reference variables that are not initialized fail.</span></span>

### <span data-ttu-id="4af74-124">Пример 2. Включение режима "в режиме" для версии 2,0</span><span class="sxs-lookup"><span data-stu-id="4af74-124">Example 2: Turn on strict mode as version 2.0</span></span>

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
The function or command was called like a method. Parameters should be separated by spaces,
as described in 'Get-Help about_Parameter.'
At line:1 char:4
+ add <<<< (3,4)
+ CategoryInfo          : InvalidOperation: (:) [], RuntimeException
+ FullyQualifiedErrorId : StrictModeFunctionCallWithParens
```

```powershell
Set-StrictMode -Off
$string = "This is a string."
$string.Month -eq $null
```

```Output
True
```

```powershell
Set-StrictMode -Version 2.0
$string = "This is a string."
$string.Month -eq $null
```

```Output
Property 'Month' cannot be found on this object; make sure it exists.
At line:1 char:9
+ $string. <<<< month
+ CategoryInfo          : InvalidOperation: (.:OperatorToken) [], RuntimeException
+ FullyQualifiedErrorId : PropertyNotFoundStrict
```

<span data-ttu-id="4af74-125">Эта команда включает строгий режим и задает его версию 2.0.</span><span class="sxs-lookup"><span data-stu-id="4af74-125">This command turns strict mode on and sets it to version 2.0.</span></span> <span data-ttu-id="4af74-126">В результате PowerShell возвращает ошибку, если используется синтаксис метода, который использует круглые скобки и запятые для вызова функции или ссылки на неинициализированные переменные или несуществующие свойства.</span><span class="sxs-lookup"><span data-stu-id="4af74-126">As a result, PowerShell returns an error if you use method syntax, which uses parentheses and commas, for a function call or reference uninitialized variables or non-existent properties.</span></span>

<span data-ttu-id="4af74-127">Пример выходных данных приведен для строгого режима версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="4af74-127">The sample output shows the effect of version 2.0 strict mode.</span></span>

<span data-ttu-id="4af74-128">Если строгий режим версии 2.0 не используется, значение "(3,4)" интерпретируется как один объект массива, к которому ничего не добавляется.</span><span class="sxs-lookup"><span data-stu-id="4af74-128">Without version 2.0 strict mode, the "(3,4)" value is interpreted as a single array object to which nothing is added.</span></span> <span data-ttu-id="4af74-129">С помощью режима в режиме версии 2,0 он правильно интерпретируется как ошибочный синтаксис для отправки двух значений.</span><span class="sxs-lookup"><span data-stu-id="4af74-129">By using version 2.0 strict mode, it is correctly interpreted as faulty syntax for submitting two values.</span></span>

<span data-ttu-id="4af74-130">Без версии 2,0 ссылка на несуществующее свойство **Month** строки возвращает только `$Null` .</span><span class="sxs-lookup"><span data-stu-id="4af74-130">Without version 2.0, the reference to the non-existent **Month** property of a string returns only `$Null`.</span></span> <span data-ttu-id="4af74-131">С помощью версии 2,0 она правильно интерпретируется как ошибка ссылки.</span><span class="sxs-lookup"><span data-stu-id="4af74-131">By using version 2.0, it is interpreted correctly as a reference error.</span></span>

### <span data-ttu-id="4af74-132">Пример 3. Включение режима "в режиме" для версии 3,0</span><span class="sxs-lookup"><span data-stu-id="4af74-132">Example 3: Turn on strict mode as version 3.0</span></span>

<span data-ttu-id="4af74-133">Если задан режим " **выкл**.", то результатом недопустимости или выхода из индексов границ будет возвращено значение null.</span><span class="sxs-lookup"><span data-stu-id="4af74-133">With strict mode set to **Off** , invalid or out of bounds indexes result return null values.</span></span>

```powershell
# Strict mode is off by default.
$a = @(1)
$a[2] -eq $null
$a['abc'] -eq $null
```

```Output
True
True
```

```powershell
Set-StrictMode -Version 3
$a = @(1)
$a[2] -eq $null
$a['abc'] -eq $null
```

```Output
Index was outside the bounds of the array.
At line:1 char:1
+ $a[2] -eq $null
+ ~~~~~~~~~~~~~~~
    + CategoryInfo          : OperationStopped: (:) [], IndexOutOfRangeException
    + FullyQualifiedErrorId : System.IndexOutOfRangeException

Cannot convert value "abc" to type "System.Int32". Error: "Input string was not in a correct format."
At line:1 char:1
+ $a['abc'] -eq $null
+ ~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidArgument: (:) [], RuntimeException
    + FullyQualifiedErrorId : InvalidCastFromStringToInteger
```

<span data-ttu-id="4af74-134">Если в режиме строгих версий задано значение версии 3 или выше, индексы недопустим или out вне границ приводят к ошибкам.</span><span class="sxs-lookup"><span data-stu-id="4af74-134">With strict mode set to version 3 or higher, invalid or out of bounds indexes result in errors.</span></span>

## <span data-ttu-id="4af74-135">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4af74-135">PARAMETERS</span></span>

### <span data-ttu-id="4af74-136">-Выкл.</span><span class="sxs-lookup"><span data-stu-id="4af74-136">-Off</span></span>

<span data-ttu-id="4af74-137">Указывает, что этот командлет выключает режим "ограничено" для текущей области и всех дочерних областей.</span><span class="sxs-lookup"><span data-stu-id="4af74-137">Indicates that this cmdlet turns strict mode off for the current scope and all child scopes.</span></span>

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

### <span data-ttu-id="4af74-138">-Version</span><span class="sxs-lookup"><span data-stu-id="4af74-138">-Version</span></span>

<span data-ttu-id="4af74-139">Определяет условия, которые приводят к ошибке в строгом режиме.</span><span class="sxs-lookup"><span data-stu-id="4af74-139">Specifies the conditions that cause an error in strict mode.</span></span> <span data-ttu-id="4af74-140">Этот параметр принимает любой допустимый номер версии PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4af74-140">This parameter accepts any valid PowerShell version number.</span></span> <span data-ttu-id="4af74-141">Любое число выше 3 обрабатывается как **Последнее**.</span><span class="sxs-lookup"><span data-stu-id="4af74-141">Any number higher than 3 is treated as **Latest**.</span></span>

<span data-ttu-id="4af74-142">Действующие значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="4af74-142">The effective values for this parameter are:</span></span>

- <span data-ttu-id="4af74-143">1.0</span><span class="sxs-lookup"><span data-stu-id="4af74-143">1.0</span></span>
  - <span data-ttu-id="4af74-144">Запрещает ссылки на неинициализированные переменные, за исключением неинициализированных переменных в строках.</span><span class="sxs-lookup"><span data-stu-id="4af74-144">Prohibits references to uninitialized variables, except for uninitialized variables in strings.</span></span>
- <span data-ttu-id="4af74-145">2.0</span><span class="sxs-lookup"><span data-stu-id="4af74-145">2.0</span></span>
  - <span data-ttu-id="4af74-146">Запрещает ссылки на неинициализированные переменные.</span><span class="sxs-lookup"><span data-stu-id="4af74-146">Prohibits references to uninitialized variables.</span></span> <span data-ttu-id="4af74-147">Сюда входят неинициализированные переменные в строках.</span><span class="sxs-lookup"><span data-stu-id="4af74-147">This includes uninitialized variables in strings.</span></span>
  - <span data-ttu-id="4af74-148">Запрещает ссылки на несуществующие свойства объекта.</span><span class="sxs-lookup"><span data-stu-id="4af74-148">Prohibits references to non-existent properties of an object.</span></span>
  - <span data-ttu-id="4af74-149">Запрещает вызовы функций, которые используют синтаксис для вызова методов.</span><span class="sxs-lookup"><span data-stu-id="4af74-149">Prohibits function calls that use the syntax for calling methods.</span></span>
- <span data-ttu-id="4af74-150">3.0</span><span class="sxs-lookup"><span data-stu-id="4af74-150">3.0</span></span>
  - <span data-ttu-id="4af74-151">Запрещает ссылки на неинициализированные переменные.</span><span class="sxs-lookup"><span data-stu-id="4af74-151">Prohibits references to uninitialized variables.</span></span> <span data-ttu-id="4af74-152">Сюда входят неинициализированные переменные в строках.</span><span class="sxs-lookup"><span data-stu-id="4af74-152">This includes uninitialized variables in strings.</span></span>
  - <span data-ttu-id="4af74-153">Запрещает ссылки на несуществующие свойства объекта.</span><span class="sxs-lookup"><span data-stu-id="4af74-153">Prohibits references to non-existent properties of an object.</span></span>
  - <span data-ttu-id="4af74-154">Запрещает вызовы функций, которые используют синтаксис для вызова методов.</span><span class="sxs-lookup"><span data-stu-id="4af74-154">Prohibits function calls that use the syntax for calling methods.</span></span>
  - <span data-ttu-id="4af74-155">Запрет вне границ или неразрешимые индексы массива.</span><span class="sxs-lookup"><span data-stu-id="4af74-155">Prohibit out of bounds or unresolvable array indexes.</span></span>
- <span data-ttu-id="4af74-156">Последняя версия</span><span class="sxs-lookup"><span data-stu-id="4af74-156">Latest</span></span>
  - <span data-ttu-id="4af74-157">Выбирается последняя доступная версия.</span><span class="sxs-lookup"><span data-stu-id="4af74-157">Selects the latest version available.</span></span> <span data-ttu-id="4af74-158">Самая последняя версия — наиболее доступная.</span><span class="sxs-lookup"><span data-stu-id="4af74-158">The latest version is the most strict.</span></span> <span data-ttu-id="4af74-159">Используйте это значение, чтобы убедиться, что скрипты используют наиболее доступную версию, даже если новые версии добавлены в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4af74-159">Use this value to make sure that scripts use the strictest available version, even when new versions are added to PowerShell.</span></span>

> [!CAUTION]
> <span data-ttu-id="4af74-160">Использование последней **версии** в **Latest** скриптах.</span><span class="sxs-lookup"><span data-stu-id="4af74-160">Using a **Version** of **Latest** in scripts.</span></span> <span data-ttu-id="4af74-161">Значение **последней** может измениться в новых выпусках PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4af74-161">The meaning of **Latest** can change in new releases of PowerShell.</span></span> <span data-ttu-id="4af74-162">Таким образом, сценарий, написанный для более ранней версии PowerShell, который использует, `Set-StrictMode -Version Latest` имеет более ограниченные правила при запуске в более новой версии PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4af74-162">Therefore, a script written for an older version of PowerShell that uses `Set-StrictMode -Version Latest` is subject to more restrictive rules when run in a newer version of PowerShell.</span></span>

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

### <span data-ttu-id="4af74-163">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="4af74-163">CommonParameters</span></span>

<span data-ttu-id="4af74-164">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="4af74-164">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4af74-165">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="4af74-165">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4af74-166">Входные данные</span><span class="sxs-lookup"><span data-stu-id="4af74-166">INPUTS</span></span>

### <span data-ttu-id="4af74-167">Нет</span><span class="sxs-lookup"><span data-stu-id="4af74-167">None</span></span>

<span data-ttu-id="4af74-168">В этот командлет нельзя передать входные данные.</span><span class="sxs-lookup"><span data-stu-id="4af74-168">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="4af74-169">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="4af74-169">OUTPUTS</span></span>

### <span data-ttu-id="4af74-170">Нет</span><span class="sxs-lookup"><span data-stu-id="4af74-170">None</span></span>

<span data-ttu-id="4af74-171">Этот командлет не возвращает никакие выходные данные.</span><span class="sxs-lookup"><span data-stu-id="4af74-171">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="4af74-172">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="4af74-172">NOTES</span></span>

<span data-ttu-id="4af74-173">`Set-StrictMode` действует только в области, в которой он задан, и в его дочерних областях.</span><span class="sxs-lookup"><span data-stu-id="4af74-173">`Set-StrictMode` is effective only in the scope in which it is set and in its child scopes.</span></span> <span data-ttu-id="4af74-174">Дополнительные сведения об областях в PowerShell см. в разделе [about_Scopes](about/about_Scopes.md).</span><span class="sxs-lookup"><span data-stu-id="4af74-174">For more information about scopes in PowerShell, see [about_Scopes](about/about_Scopes.md).</span></span>

## <span data-ttu-id="4af74-175">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="4af74-175">RELATED LINKS</span></span>

[<span data-ttu-id="4af74-176">Set-PSDebug</span><span class="sxs-lookup"><span data-stu-id="4af74-176">Set-PSDebug</span></span>](Set-PSDebug.md)
