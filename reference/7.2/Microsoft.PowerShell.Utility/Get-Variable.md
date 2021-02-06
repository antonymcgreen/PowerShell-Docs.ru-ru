---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 05/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-variable?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Variable
ms.openlocfilehash: 6cd7a4611f6118ed1f0846d9c11a8fe8edc69ef0
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599798"
---
# <span data-ttu-id="e2d4c-102">Get-Variable</span><span class="sxs-lookup"><span data-stu-id="e2d4c-102">Get-Variable</span></span>

## <span data-ttu-id="e2d4c-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="e2d4c-103">SYNOPSIS</span></span>
<span data-ttu-id="e2d4c-104">Получает переменные в текущей консоли.</span><span class="sxs-lookup"><span data-stu-id="e2d4c-104">Gets the variables in the current console.</span></span>

## <span data-ttu-id="e2d4c-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e2d4c-105">SYNTAX</span></span>

```
Get-Variable [[-Name] <String[]>] [-ValueOnly] [-Include <String[]>] [-Exclude <String[]>] [-Scope <String>]
 [<CommonParameters>]
```

## <span data-ttu-id="e2d4c-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e2d4c-106">DESCRIPTION</span></span>

<span data-ttu-id="e2d4c-107">`Get-Variable`Командлет получает переменные PowerShell в текущей консоли.</span><span class="sxs-lookup"><span data-stu-id="e2d4c-107">The `Get-Variable` cmdlet gets the PowerShell variables in the current console.</span></span>
<span data-ttu-id="e2d4c-108">Вы можете получить только значения переменных, указав параметр **ValueOnly**, и отфильтровать полученные переменные по имени.</span><span class="sxs-lookup"><span data-stu-id="e2d4c-108">You can retrieve just the values of the variables by specifying the **ValueOnly** parameter, and you can filter the variables returned by name.</span></span>

## <span data-ttu-id="e2d4c-109">Примеры</span><span class="sxs-lookup"><span data-stu-id="e2d4c-109">EXAMPLES</span></span>

### <span data-ttu-id="e2d4c-110">Пример 1. получение переменных по буквам</span><span class="sxs-lookup"><span data-stu-id="e2d4c-110">Example 1: Get variables by letter</span></span>

<span data-ttu-id="e2d4c-111">Эта команда получает переменные с именами, начинающимися с буквы m.</span><span class="sxs-lookup"><span data-stu-id="e2d4c-111">This command gets variables with names that begin with the letter m.</span></span>
<span data-ttu-id="e2d4c-112">Она также возвращает значения переменных.</span><span class="sxs-lookup"><span data-stu-id="e2d4c-112">The command also gets the value of the variables.</span></span>

```powershell
Get-Variable m*
```

### <span data-ttu-id="e2d4c-113">Пример 2. Получение значений переменных по буквам</span><span class="sxs-lookup"><span data-stu-id="e2d4c-113">Example 2: Get variable values by letter</span></span>

<span data-ttu-id="e2d4c-114">Эта команда возвращает только значения переменных, имена которых начинаются с m.</span><span class="sxs-lookup"><span data-stu-id="e2d4c-114">This command gets only the values of the variables that have names that begin with m.</span></span>

```powershell
Get-Variable m* -ValueOnly
```

### <span data-ttu-id="e2d4c-115">Пример 3. получение переменных по двум буквам</span><span class="sxs-lookup"><span data-stu-id="e2d4c-115">Example 3: Get variables by two letters</span></span>

<span data-ttu-id="e2d4c-116">Эта команда возвращает сведения о переменных, которые начинаются с буквы M или буквы P.</span><span class="sxs-lookup"><span data-stu-id="e2d4c-116">This command gets information about the variables that begin with either the letter M or the letter P.</span></span>

```powershell
Get-Variable -Include M*,P*
```

### <span data-ttu-id="e2d4c-117">Пример 4. получение переменных по области</span><span class="sxs-lookup"><span data-stu-id="e2d4c-117">Example 4: Get variables by scope</span></span>

<span data-ttu-id="e2d4c-118">Первая команда возвращает только те переменные, которые определены в локальной области.</span><span class="sxs-lookup"><span data-stu-id="e2d4c-118">The first command gets only the variables that are defined in the local scope.</span></span>
<span data-ttu-id="e2d4c-119">Оно эквивалентно `Get-Variable -Scope Local` и может быть сокращено до `gv -s 0` .</span><span class="sxs-lookup"><span data-stu-id="e2d4c-119">It is equivalent to `Get-Variable -Scope Local` and can be abbreviated as `gv -s 0`.</span></span>

<span data-ttu-id="e2d4c-120">Вторая команда использует `Compare-Object` командлет для поиска переменных, определенных в родительской области (область 1), но видимых только в локальной области (область 0).</span><span class="sxs-lookup"><span data-stu-id="e2d4c-120">The second command uses the `Compare-Object` cmdlet to find the variables that are defined in the parent scope (Scope 1) but are visible only in the local scope (Scope 0).</span></span>

```powershell
Get-Variable -Scope 0
Compare-Object (Get-Variable -Scope 0) (Get-Variable -Scope 1)
```

## <span data-ttu-id="e2d4c-121">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e2d4c-121">PARAMETERS</span></span>

### <span data-ttu-id="e2d4c-122">-Exclude</span><span class="sxs-lookup"><span data-stu-id="e2d4c-122">-Exclude</span></span>

<span data-ttu-id="e2d4c-123">Указывает массив элементов, которые этот командлет исключает из операции.</span><span class="sxs-lookup"><span data-stu-id="e2d4c-123">Specifies an array of items that this cmdlet excludes from the operation.</span></span>
<span data-ttu-id="e2d4c-124">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="e2d4c-124">Wildcards are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="e2d4c-125">-Include</span><span class="sxs-lookup"><span data-stu-id="e2d4c-125">-Include</span></span>

<span data-ttu-id="e2d4c-126">Указывает массив элементов, на основании которых будет действовать командлет, исключая все остальные.</span><span class="sxs-lookup"><span data-stu-id="e2d4c-126">Specifies an array of items upon which the cmdlet will act, excluding all others.</span></span>
<span data-ttu-id="e2d4c-127">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="e2d4c-127">Wildcards are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="e2d4c-128">-Name</span><span class="sxs-lookup"><span data-stu-id="e2d4c-128">-Name</span></span>

<span data-ttu-id="e2d4c-129">Указывает имя переменной.</span><span class="sxs-lookup"><span data-stu-id="e2d4c-129">Specifies the name of the variable.</span></span>
<span data-ttu-id="e2d4c-130">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="e2d4c-130">Wildcards are permitted.</span></span>
<span data-ttu-id="e2d4c-131">Можно также передать имя переменной по конвейеру в `Get-Variable` .</span><span class="sxs-lookup"><span data-stu-id="e2d4c-131">You can also pipe a variable name to `Get-Variable`.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="e2d4c-132">-Scope</span><span class="sxs-lookup"><span data-stu-id="e2d4c-132">-Scope</span></span>

<span data-ttu-id="e2d4c-133">Задает переменные в области. Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="e2d4c-133">Specifies the variables in the scope.The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="e2d4c-134">**Глобальный**</span><span class="sxs-lookup"><span data-stu-id="e2d4c-134">**Global**</span></span>
- <span data-ttu-id="e2d4c-135">**Локальное**</span><span class="sxs-lookup"><span data-stu-id="e2d4c-135">**Local**</span></span>
- <span data-ttu-id="e2d4c-136">**Скрипт**</span><span class="sxs-lookup"><span data-stu-id="e2d4c-136">**Script**</span></span>
- <span data-ttu-id="e2d4c-137">Номер относительно текущей области (от 0 до количества областей, где 0 — это текущая область, а 1 — ее родительская область).</span><span class="sxs-lookup"><span data-stu-id="e2d4c-137">A number relative to the current scope (0 through the number of scopes, where 0 is the current scope and 1 is its parent)</span></span>

<span data-ttu-id="e2d4c-138">По умолчанию используется **Local** .</span><span class="sxs-lookup"><span data-stu-id="e2d4c-138">**Local** is the default.</span></span>
<span data-ttu-id="e2d4c-139">Дополнительные сведения см. в разделе [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span><span class="sxs-lookup"><span data-stu-id="e2d4c-139">For more information, see [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e2d4c-140">-Валуеонли</span><span class="sxs-lookup"><span data-stu-id="e2d4c-140">-ValueOnly</span></span>

<span data-ttu-id="e2d4c-141">Указывает, что этот командлет возвращает только значение переменной.</span><span class="sxs-lookup"><span data-stu-id="e2d4c-141">Indicates that this cmdlet gets only the value of the variable.</span></span>

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

### <span data-ttu-id="e2d4c-142">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="e2d4c-142">CommonParameters</span></span>

<span data-ttu-id="e2d4c-143">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="e2d4c-143">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e2d4c-144">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="e2d4c-144">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="e2d4c-145">Входные данные</span><span class="sxs-lookup"><span data-stu-id="e2d4c-145">INPUTS</span></span>

### <span data-ttu-id="e2d4c-146">System.String</span><span class="sxs-lookup"><span data-stu-id="e2d4c-146">System.String</span></span>

<span data-ttu-id="e2d4c-147">Строку, содержащую имя переменной, можно передать в `Get-Variable` .</span><span class="sxs-lookup"><span data-stu-id="e2d4c-147">You can pipe a string that contains the variable name to `Get-Variable`.</span></span>

## <span data-ttu-id="e2d4c-148">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="e2d4c-148">OUTPUTS</span></span>

### <span data-ttu-id="e2d4c-149">System. Management. Automation. PSVariable</span><span class="sxs-lookup"><span data-stu-id="e2d4c-149">System.Management.Automation.PSVariable</span></span>

<span data-ttu-id="e2d4c-150">Этот командлет возвращает объект **System. Management. аутоматионпсвариабле** для каждой переменной, которую она получает.</span><span class="sxs-lookup"><span data-stu-id="e2d4c-150">This cmdlet returns a **System.Management.AutomationPSVariable** object for each variable that it gets.</span></span> <span data-ttu-id="e2d4c-151">Тип объекта зависит от переменной.</span><span class="sxs-lookup"><span data-stu-id="e2d4c-151">The object type depends on the variable.</span></span>

### <span data-ttu-id="e2d4c-152">System. Object []</span><span class="sxs-lookup"><span data-stu-id="e2d4c-152">System.Object[]</span></span>

<span data-ttu-id="e2d4c-153">При указании параметра **валуеонли** , если значение указанной переменной является коллекцией, `Get-Variable` возвращает `[System.Object[]]` .</span><span class="sxs-lookup"><span data-stu-id="e2d4c-153">When you specify the **ValueOnly** parameter, if the specified variable's value is a collection, `Get-Variable` returns a `[System.Object[]]`.</span></span> <span data-ttu-id="e2d4c-154">Это поведение предотвращает обработку значений переменных в обычной операции конвейера по одной за раз.</span><span class="sxs-lookup"><span data-stu-id="e2d4c-154">This behavior prevents normal pipeline operation from processing the variable's values one at a time.</span></span> <span data-ttu-id="e2d4c-155">Обходной путь для принудительного перечисления коллекций заключается в заключении `Get-Variable` команды в круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="e2d4c-155">A workaround to force collection enumeration is to enclose the `Get-Variable` command in parenthesis.</span></span>

## <span data-ttu-id="e2d4c-156">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="e2d4c-156">NOTES</span></span>

- <span data-ttu-id="e2d4c-157">Этот командлет не управляет переменными среды.</span><span class="sxs-lookup"><span data-stu-id="e2d4c-157">This cmdlet does not manage environment variables.</span></span> <span data-ttu-id="e2d4c-158">Для управления этими переменными можно использовать поставщика переменных среды.</span><span class="sxs-lookup"><span data-stu-id="e2d4c-158">To manage environment variables, you can use the environment variable provider.</span></span>

## <span data-ttu-id="e2d4c-159">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="e2d4c-159">RELATED LINKS</span></span>

[<span data-ttu-id="e2d4c-160">Clear-Variable</span><span class="sxs-lookup"><span data-stu-id="e2d4c-160">Clear-Variable</span></span>](Clear-Variable.md)

[<span data-ttu-id="e2d4c-161">New-Variable</span><span class="sxs-lookup"><span data-stu-id="e2d4c-161">New-Variable</span></span>](New-Variable.md)

[<span data-ttu-id="e2d4c-162">Remove-Variable</span><span class="sxs-lookup"><span data-stu-id="e2d4c-162">Remove-Variable</span></span>](Remove-Variable.md)

[<span data-ttu-id="e2d4c-163">Set-Variable</span><span class="sxs-lookup"><span data-stu-id="e2d4c-163">Set-Variable</span></span>](Set-Variable.md)

