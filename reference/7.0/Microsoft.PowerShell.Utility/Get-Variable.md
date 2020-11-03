---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 5/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-variable?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Variable
ms.openlocfilehash: 128bdd997e006723a69997e1419efd2f012e97f6
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93226390"
---
# <span data-ttu-id="bd1f5-103">Get-Variable</span><span class="sxs-lookup"><span data-stu-id="bd1f5-103">Get-Variable</span></span>

## <span data-ttu-id="bd1f5-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="bd1f5-104">SYNOPSIS</span></span>
<span data-ttu-id="bd1f5-105">Получает переменные в текущей консоли.</span><span class="sxs-lookup"><span data-stu-id="bd1f5-105">Gets the variables in the current console.</span></span>

## <span data-ttu-id="bd1f5-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="bd1f5-106">SYNTAX</span></span>

```
Get-Variable [[-Name] <String[]>] [-ValueOnly] [-Include <String[]>] [-Exclude <String[]>] [-Scope <String>]
 [<CommonParameters>]
```

## <span data-ttu-id="bd1f5-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="bd1f5-107">DESCRIPTION</span></span>

<span data-ttu-id="bd1f5-108">`Get-Variable`Командлет получает переменные PowerShell в текущей консоли.</span><span class="sxs-lookup"><span data-stu-id="bd1f5-108">The `Get-Variable` cmdlet gets the PowerShell variables in the current console.</span></span>
<span data-ttu-id="bd1f5-109">Вы можете получить только значения переменных, указав параметр **ValueOnly** , и отфильтровать полученные переменные по имени.</span><span class="sxs-lookup"><span data-stu-id="bd1f5-109">You can retrieve just the values of the variables by specifying the **ValueOnly** parameter, and you can filter the variables returned by name.</span></span>

## <span data-ttu-id="bd1f5-110">Примеры</span><span class="sxs-lookup"><span data-stu-id="bd1f5-110">EXAMPLES</span></span>

### <span data-ttu-id="bd1f5-111">Пример 1. получение переменных по буквам</span><span class="sxs-lookup"><span data-stu-id="bd1f5-111">Example 1: Get variables by letter</span></span>

<span data-ttu-id="bd1f5-112">Эта команда получает переменные с именами, начинающимися с буквы m.</span><span class="sxs-lookup"><span data-stu-id="bd1f5-112">This command gets variables with names that begin with the letter m.</span></span>
<span data-ttu-id="bd1f5-113">Она также возвращает значения переменных.</span><span class="sxs-lookup"><span data-stu-id="bd1f5-113">The command also gets the value of the variables.</span></span>

```powershell
Get-Variable m*
```

### <span data-ttu-id="bd1f5-114">Пример 2. Получение значений переменных по буквам</span><span class="sxs-lookup"><span data-stu-id="bd1f5-114">Example 2: Get variable values by letter</span></span>

<span data-ttu-id="bd1f5-115">Эта команда возвращает только значения переменных, имена которых начинаются с m.</span><span class="sxs-lookup"><span data-stu-id="bd1f5-115">This command gets only the values of the variables that have names that begin with m.</span></span>

```powershell
Get-Variable m* -ValueOnly
```

### <span data-ttu-id="bd1f5-116">Пример 3. получение переменных по двум буквам</span><span class="sxs-lookup"><span data-stu-id="bd1f5-116">Example 3: Get variables by two letters</span></span>

<span data-ttu-id="bd1f5-117">Эта команда возвращает сведения о переменных, которые начинаются с буквы M или буквы P.</span><span class="sxs-lookup"><span data-stu-id="bd1f5-117">This command gets information about the variables that begin with either the letter M or the letter P.</span></span>

```powershell
Get-Variable -Include M*,P*
```

### <span data-ttu-id="bd1f5-118">Пример 4. получение переменных по области</span><span class="sxs-lookup"><span data-stu-id="bd1f5-118">Example 4: Get variables by scope</span></span>

<span data-ttu-id="bd1f5-119">Первая команда возвращает только те переменные, которые определены в локальной области.</span><span class="sxs-lookup"><span data-stu-id="bd1f5-119">The first command gets only the variables that are defined in the local scope.</span></span>
<span data-ttu-id="bd1f5-120">Оно эквивалентно `Get-Variable -Scope Local` и может быть сокращено до `gv -s 0` .</span><span class="sxs-lookup"><span data-stu-id="bd1f5-120">It is equivalent to `Get-Variable -Scope Local` and can be abbreviated as `gv -s 0`.</span></span>

<span data-ttu-id="bd1f5-121">Вторая команда использует `Compare-Object` командлет для поиска переменных, определенных в родительской области (область 1), но видимых только в локальной области (область 0).</span><span class="sxs-lookup"><span data-stu-id="bd1f5-121">The second command uses the `Compare-Object` cmdlet to find the variables that are defined in the parent scope (Scope 1) but are visible only in the local scope (Scope 0).</span></span>

```powershell
Get-Variable -Scope 0
Compare-Object (Get-Variable -Scope 0) (Get-Variable -Scope 1)
```

## <span data-ttu-id="bd1f5-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="bd1f5-122">PARAMETERS</span></span>

### <span data-ttu-id="bd1f5-123">-Exclude</span><span class="sxs-lookup"><span data-stu-id="bd1f5-123">-Exclude</span></span>

<span data-ttu-id="bd1f5-124">Указывает массив элементов, которые этот командлет исключает из операции.</span><span class="sxs-lookup"><span data-stu-id="bd1f5-124">Specifies an array of items that this cmdlet excludes from the operation.</span></span>
<span data-ttu-id="bd1f5-125">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="bd1f5-125">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="bd1f5-126">-Include</span><span class="sxs-lookup"><span data-stu-id="bd1f5-126">-Include</span></span>

<span data-ttu-id="bd1f5-127">Указывает массив элементов, на основании которых будет действовать командлет, исключая все остальные.</span><span class="sxs-lookup"><span data-stu-id="bd1f5-127">Specifies an array of items upon which the cmdlet will act, excluding all others.</span></span>
<span data-ttu-id="bd1f5-128">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="bd1f5-128">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="bd1f5-129">-Name</span><span class="sxs-lookup"><span data-stu-id="bd1f5-129">-Name</span></span>

<span data-ttu-id="bd1f5-130">Указывает имя переменной.</span><span class="sxs-lookup"><span data-stu-id="bd1f5-130">Specifies the name of the variable.</span></span>
<span data-ttu-id="bd1f5-131">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="bd1f5-131">Wildcards are permitted.</span></span>
<span data-ttu-id="bd1f5-132">Можно также передать имя переменной по конвейеру в `Get-Variable` .</span><span class="sxs-lookup"><span data-stu-id="bd1f5-132">You can also pipe a variable name to `Get-Variable`.</span></span>

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

### <span data-ttu-id="bd1f5-133">-Scope</span><span class="sxs-lookup"><span data-stu-id="bd1f5-133">-Scope</span></span>

<span data-ttu-id="bd1f5-134">Задает переменные в области. Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="bd1f5-134">Specifies the variables in the scope.The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="bd1f5-135">**Глобальный**</span><span class="sxs-lookup"><span data-stu-id="bd1f5-135">**Global**</span></span>
- <span data-ttu-id="bd1f5-136">**Локальное**</span><span class="sxs-lookup"><span data-stu-id="bd1f5-136">**Local**</span></span>
- <span data-ttu-id="bd1f5-137">**Сценарий**</span><span class="sxs-lookup"><span data-stu-id="bd1f5-137">**Script**</span></span>
- <span data-ttu-id="bd1f5-138">Номер относительно текущей области (от 0 до количества областей, где 0 — это текущая область, а 1 — ее родительская область).</span><span class="sxs-lookup"><span data-stu-id="bd1f5-138">A number relative to the current scope (0 through the number of scopes, where 0 is the current scope and 1 is its parent)</span></span>

<span data-ttu-id="bd1f5-139">По умолчанию используется **Local** .</span><span class="sxs-lookup"><span data-stu-id="bd1f5-139">**Local** is the default.</span></span>
<span data-ttu-id="bd1f5-140">Дополнительные сведения см. в разделе [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span><span class="sxs-lookup"><span data-stu-id="bd1f5-140">For more information, see [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span></span>

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

### <span data-ttu-id="bd1f5-141">-Валуеонли</span><span class="sxs-lookup"><span data-stu-id="bd1f5-141">-ValueOnly</span></span>

<span data-ttu-id="bd1f5-142">Указывает, что этот командлет возвращает только значение переменной.</span><span class="sxs-lookup"><span data-stu-id="bd1f5-142">Indicates that this cmdlet gets only the value of the variable.</span></span>

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

### <span data-ttu-id="bd1f5-143">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="bd1f5-143">CommonParameters</span></span>

<span data-ttu-id="bd1f5-144">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="bd1f5-144">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="bd1f5-145">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="bd1f5-145">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="bd1f5-146">Входные данные</span><span class="sxs-lookup"><span data-stu-id="bd1f5-146">INPUTS</span></span>

### <span data-ttu-id="bd1f5-147">System.String</span><span class="sxs-lookup"><span data-stu-id="bd1f5-147">System.String</span></span>

<span data-ttu-id="bd1f5-148">Строку, содержащую имя переменной, можно передать в `Get-Variable` .</span><span class="sxs-lookup"><span data-stu-id="bd1f5-148">You can pipe a string that contains the variable name to `Get-Variable`.</span></span>

## <span data-ttu-id="bd1f5-149">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="bd1f5-149">OUTPUTS</span></span>

### <span data-ttu-id="bd1f5-150">System. Management. Automation. PSVariable</span><span class="sxs-lookup"><span data-stu-id="bd1f5-150">System.Management.Automation.PSVariable</span></span>

<span data-ttu-id="bd1f5-151">Этот командлет возвращает объект **System. Management. аутоматионпсвариабле** для каждой переменной, которую она получает.</span><span class="sxs-lookup"><span data-stu-id="bd1f5-151">This cmdlet returns a **System.Management.AutomationPSVariable** object for each variable that it gets.</span></span> <span data-ttu-id="bd1f5-152">Тип объекта зависит от переменной.</span><span class="sxs-lookup"><span data-stu-id="bd1f5-152">The object type depends on the variable.</span></span>

### <span data-ttu-id="bd1f5-153">System. Object []</span><span class="sxs-lookup"><span data-stu-id="bd1f5-153">System.Object[]</span></span>

<span data-ttu-id="bd1f5-154">При указании параметра **валуеонли** , если значение указанной переменной является коллекцией, `Get-Variable` возвращает `[System.Object[]]` .</span><span class="sxs-lookup"><span data-stu-id="bd1f5-154">When you specify the **ValueOnly** parameter, if the specified variable's value is a collection, `Get-Variable` returns a `[System.Object[]]`.</span></span> <span data-ttu-id="bd1f5-155">Это поведение предотвращает обработку значений переменных в обычной операции конвейера по одной за раз.</span><span class="sxs-lookup"><span data-stu-id="bd1f5-155">This behavior prevents normal pipeline operation from processing the variable's values one at a time.</span></span> <span data-ttu-id="bd1f5-156">Обходной путь для принудительного перечисления коллекций заключается в заключении `Get-Variable` команды в круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="bd1f5-156">A workaround to force collection enumeration is to enclose the `Get-Variable` command in parenthesis.</span></span>

## <span data-ttu-id="bd1f5-157">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="bd1f5-157">NOTES</span></span>

- <span data-ttu-id="bd1f5-158">Этот командлет не управляет переменными среды.</span><span class="sxs-lookup"><span data-stu-id="bd1f5-158">This cmdlet does not manage environment variables.</span></span> <span data-ttu-id="bd1f5-159">Для управления этими переменными можно использовать поставщика переменных среды.</span><span class="sxs-lookup"><span data-stu-id="bd1f5-159">To manage environment variables, you can use the environment variable provider.</span></span>

## <span data-ttu-id="bd1f5-160">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="bd1f5-160">RELATED LINKS</span></span>

[<span data-ttu-id="bd1f5-161">Clear-Variable</span><span class="sxs-lookup"><span data-stu-id="bd1f5-161">Clear-Variable</span></span>](Clear-Variable.md)

[<span data-ttu-id="bd1f5-162">New-Variable</span><span class="sxs-lookup"><span data-stu-id="bd1f5-162">New-Variable</span></span>](New-Variable.md)

[<span data-ttu-id="bd1f5-163">Remove-Variable</span><span class="sxs-lookup"><span data-stu-id="bd1f5-163">Remove-Variable</span></span>](Remove-Variable.md)

[<span data-ttu-id="bd1f5-164">Set-Variable</span><span class="sxs-lookup"><span data-stu-id="bd1f5-164">Set-Variable</span></span>](Set-Variable.md)
