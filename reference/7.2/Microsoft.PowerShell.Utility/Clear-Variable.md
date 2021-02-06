---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/clear-variable?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-Variable
ms.openlocfilehash: 0381b48097f75d3195a82a67225cd8d6759e7433
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602285"
---
# <span data-ttu-id="d19b7-102">Clear-Variable</span><span class="sxs-lookup"><span data-stu-id="d19b7-102">Clear-Variable</span></span>

## <span data-ttu-id="d19b7-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="d19b7-103">SYNOPSIS</span></span>
<span data-ttu-id="d19b7-104">Удаляет значение переменной.</span><span class="sxs-lookup"><span data-stu-id="d19b7-104">Deletes the value of a variable.</span></span>

## <span data-ttu-id="d19b7-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d19b7-105">SYNTAX</span></span>

```
Clear-Variable [-Name] <String[]> [-Include <String[]>] [-Exclude <String[]>] [-Force] [-PassThru]
 [-Scope <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="d19b7-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d19b7-106">DESCRIPTION</span></span>

<span data-ttu-id="d19b7-107">Командлет **clear-variable** удаляет данные, хранящиеся в переменной, но не удаляет переменную.</span><span class="sxs-lookup"><span data-stu-id="d19b7-107">The **Clear-Variable** cmdlet deletes the data stored in a variable, but it does not delete the variable.</span></span>
<span data-ttu-id="d19b7-108">В результате переменная получает значение NULL (пустое).</span><span class="sxs-lookup"><span data-stu-id="d19b7-108">As a result, the value of the variable is NULL (empty).</span></span>
<span data-ttu-id="d19b7-109">Если переменная имеет указанный тип данных или объект, этот командлет сохраняет тип объекта, хранящегося в переменной.</span><span class="sxs-lookup"><span data-stu-id="d19b7-109">If the variable has a specified data or object type, this cmdlet preserves the type of the object stored in the variable.</span></span>

## <span data-ttu-id="d19b7-110">Примеры</span><span class="sxs-lookup"><span data-stu-id="d19b7-110">EXAMPLES</span></span>

### <span data-ttu-id="d19b7-111">Пример 1. Удаление значений глобальных переменных, начинающихся со строки поиска</span><span class="sxs-lookup"><span data-stu-id="d19b7-111">Example 1: Remove the value of global variables that begin with a search string</span></span>

```
PS C:\> Clear-Variable my* -Scope Global
```

<span data-ttu-id="d19b7-112">Эта команда удаляет значения глобальных переменных, имена которых начинаются с My.</span><span class="sxs-lookup"><span data-stu-id="d19b7-112">This command removes the value of global variables that have names that begin with my.</span></span>

### <span data-ttu-id="d19b7-113">Пример 2. Очистка переменной в дочерней области, но не родительской области</span><span class="sxs-lookup"><span data-stu-id="d19b7-113">Example 2: Clear a variable in a child scope but not the parent scope</span></span>

```
PS C:\> $a=3
PS C:\> &{ Clear-Variable a }
PS C:\> $a
3
```

<span data-ttu-id="d19b7-114">Эти команды показывают, что при очистке переменной в дочерней области значение в родительской области не удаляется.</span><span class="sxs-lookup"><span data-stu-id="d19b7-114">These commands demonstrate that clearing a variable in a child scope does not clear the value in the parent scope.</span></span>
<span data-ttu-id="d19b7-115">Первая команда задает значение переменной $A равным 3.</span><span class="sxs-lookup"><span data-stu-id="d19b7-115">The first command sets the value of the variable $A to 3.</span></span>
<span data-ttu-id="d19b7-116">Вторая команда использует оператор Invoke (&) для выполнения команды **clear-variable** в новой области.</span><span class="sxs-lookup"><span data-stu-id="d19b7-116">The second command uses the invoke operator (&) to run the **Clear-Variable** command in a new scope.</span></span>
<span data-ttu-id="d19b7-117">В результате в дочерней области переменная очищается (хотя она и не существовала), а в локальной — нет.</span><span class="sxs-lookup"><span data-stu-id="d19b7-117">The variable is cleared in the child scope (although it did not exist), but it is not cleared in the local scope.</span></span>
<span data-ttu-id="d19b7-118">Третья команда, которая получает значение $A, показывает, что значение 3 не затрагивается.</span><span class="sxs-lookup"><span data-stu-id="d19b7-118">The third command, which gets the value of $A, shows that the value 3 is unaffected.</span></span>

### <span data-ttu-id="d19b7-119">Пример 3. Удаление значения указанной переменной</span><span class="sxs-lookup"><span data-stu-id="d19b7-119">Example 3: Delete the value of the specified variable</span></span>

```
PS C:\> Clear-Variable -Name "Processes"
```

<span data-ttu-id="d19b7-120">Эта команда удаляет значение переменной с именем Processes.</span><span class="sxs-lookup"><span data-stu-id="d19b7-120">This command deletes the value of the variable named Processes.</span></span>
<span data-ttu-id="d19b7-121">После того как командлет завершит операцию, переменная с именем Processes по-прежнему существует, но имеет значение null.</span><span class="sxs-lookup"><span data-stu-id="d19b7-121">After the cmdlet completes the operation, the variable named Processes still exists, but the value is null.</span></span>

## <span data-ttu-id="d19b7-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d19b7-122">PARAMETERS</span></span>

### <span data-ttu-id="d19b7-123">-Exclude</span><span class="sxs-lookup"><span data-stu-id="d19b7-123">-Exclude</span></span>

<span data-ttu-id="d19b7-124">Указывает массив элементов, пропущенных этим командлетом в операции.</span><span class="sxs-lookup"><span data-stu-id="d19b7-124">Specifies an array of items that this cmdlet omits in the operation.</span></span>
<span data-ttu-id="d19b7-125">Значение этого параметра определяет параметр *Name* .</span><span class="sxs-lookup"><span data-stu-id="d19b7-125">The value of this parameter qualifies the *Name* parameter.</span></span>
<span data-ttu-id="d19b7-126">Введите часть имени или шаблон, например "s\*".</span><span class="sxs-lookup"><span data-stu-id="d19b7-126">Enter a name element or pattern, such as "s\*".</span></span>
<span data-ttu-id="d19b7-127">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="d19b7-127">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="d19b7-128">-Force</span><span class="sxs-lookup"><span data-stu-id="d19b7-128">-Force</span></span>

<span data-ttu-id="d19b7-129">Позволяет командлету очистить переменную, даже если она доступна только для чтения.</span><span class="sxs-lookup"><span data-stu-id="d19b7-129">Allows the cmdlet to clear a variable even if it is read-only.</span></span>
<span data-ttu-id="d19b7-130">Даже при использовании параметра Force командлет не может очистить константу.</span><span class="sxs-lookup"><span data-stu-id="d19b7-130">Even using the Force parameter, the cmdlet cannot clear constants.</span></span>

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

### <span data-ttu-id="d19b7-131">-Include</span><span class="sxs-lookup"><span data-stu-id="d19b7-131">-Include</span></span>

<span data-ttu-id="d19b7-132">Задает массив элементов, включаемых этим командлетом в операцию.</span><span class="sxs-lookup"><span data-stu-id="d19b7-132">Specifies an array of items that this cmdlet includes in the operation.</span></span>
<span data-ttu-id="d19b7-133">Значение этого параметра определяет параметр *Name* .</span><span class="sxs-lookup"><span data-stu-id="d19b7-133">The value of this parameter qualifies the *Name* parameter.</span></span>
<span data-ttu-id="d19b7-134">Введите часть имени или шаблон, например "s\*".</span><span class="sxs-lookup"><span data-stu-id="d19b7-134">Enter a name element or pattern, such as "s\*".</span></span>
<span data-ttu-id="d19b7-135">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="d19b7-135">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="d19b7-136">-Name</span><span class="sxs-lookup"><span data-stu-id="d19b7-136">-Name</span></span>

<span data-ttu-id="d19b7-137">Указывает имя переменной, которую нужно очистить.</span><span class="sxs-lookup"><span data-stu-id="d19b7-137">Specifies the name of the variable to be cleared.</span></span>
<span data-ttu-id="d19b7-138">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="d19b7-138">Wildcards are permitted.</span></span>
<span data-ttu-id="d19b7-139">Этот параметр обязателен, но его имя (Name) можно не указывать.</span><span class="sxs-lookup"><span data-stu-id="d19b7-139">This parameter is required, but the parameter name ("Name") is optional.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="d19b7-140">-PassThru</span><span class="sxs-lookup"><span data-stu-id="d19b7-140">-PassThru</span></span>

<span data-ttu-id="d19b7-141">Возвращает объект, представляющий элемент, с которым вы работаете.</span><span class="sxs-lookup"><span data-stu-id="d19b7-141">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="d19b7-142">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="d19b7-142">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="d19b7-143">-Scope</span><span class="sxs-lookup"><span data-stu-id="d19b7-143">-Scope</span></span>

<span data-ttu-id="d19b7-144">Задает область действия псевдонима.</span><span class="sxs-lookup"><span data-stu-id="d19b7-144">Specifies the scope in which this alias is valid.</span></span>

<span data-ttu-id="d19b7-145">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="d19b7-145">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="d19b7-146">Глобальный</span><span class="sxs-lookup"><span data-stu-id="d19b7-146">Global</span></span>
- <span data-ttu-id="d19b7-147">Локальная</span><span class="sxs-lookup"><span data-stu-id="d19b7-147">Local</span></span>
- <span data-ttu-id="d19b7-148">Скрипт</span><span class="sxs-lookup"><span data-stu-id="d19b7-148">Script</span></span>

<span data-ttu-id="d19b7-149">Можно также использовать число относительно текущей области (от 0 до количества областей, где 0 — текущая область, а 1 — ее родителя).</span><span class="sxs-lookup"><span data-stu-id="d19b7-149">You can also use a number relative to the current scope (0 through the number of scopes, where 0 is the current scope and 1 is its parent).</span></span>
<span data-ttu-id="d19b7-150">По умолчанию используется значение Local.</span><span class="sxs-lookup"><span data-stu-id="d19b7-150">Local is the default.</span></span>
<span data-ttu-id="d19b7-151">Дополнительные сведения см. в разделе about_Scopes.</span><span class="sxs-lookup"><span data-stu-id="d19b7-151">For more information, see about_Scopes.</span></span>

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

### <span data-ttu-id="d19b7-152">-Confirm</span><span class="sxs-lookup"><span data-stu-id="d19b7-152">-Confirm</span></span>

<span data-ttu-id="d19b7-153">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="d19b7-153">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d19b7-154">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="d19b7-154">-WhatIf</span></span>

<span data-ttu-id="d19b7-155">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="d19b7-155">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="d19b7-156">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="d19b7-156">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d19b7-157">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="d19b7-157">CommonParameters</span></span>

<span data-ttu-id="d19b7-158">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="d19b7-158">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d19b7-159">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="d19b7-159">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d19b7-160">Входные данные</span><span class="sxs-lookup"><span data-stu-id="d19b7-160">INPUTS</span></span>

### <span data-ttu-id="d19b7-161">None</span><span class="sxs-lookup"><span data-stu-id="d19b7-161">None</span></span>

<span data-ttu-id="d19b7-162">Нельзя передать объекты в этот командлет с помощью конвейера.</span><span class="sxs-lookup"><span data-stu-id="d19b7-162">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="d19b7-163">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="d19b7-163">OUTPUTS</span></span>

### <span data-ttu-id="d19b7-164">None или System. Management. Automation. PSVariable</span><span class="sxs-lookup"><span data-stu-id="d19b7-164">None or System.Management.Automation.PSVariable</span></span>

<span data-ttu-id="d19b7-165">При использовании параметра *PassThru* этот командлет создает объект **System. Management. Automation. PSVariable** , представляющий переменную, которая была сброшена.</span><span class="sxs-lookup"><span data-stu-id="d19b7-165">When you use the *PassThru* parameter, this cmdlet generates a **System.Management.Automation.PSVariable** object representing the cleared variable.</span></span>
<span data-ttu-id="d19b7-166">В противном случае командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="d19b7-166">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="d19b7-167">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="d19b7-167">NOTES</span></span>

* <span data-ttu-id="d19b7-168">Чтобы удалить переменную вместе со значением, используйте командлеты Remove-Variable или Remove-Item.</span><span class="sxs-lookup"><span data-stu-id="d19b7-168">To delete a variable, along with its value, use Remove-Variable or Remove-Item.</span></span>

  <span data-ttu-id="d19b7-169">Этот командлет не удаляет значения переменных, которые установлены как константы или принадлежат системе, даже если используется параметр *Force* .</span><span class="sxs-lookup"><span data-stu-id="d19b7-169">This cmdlet does not delete the values of variables that are set as constants or owned by the system, even if you use the *Force* parameter.</span></span>

  <span data-ttu-id="d19b7-170">Если очищаемой переменной не существует, этот командлет не выполняет никаких действий.</span><span class="sxs-lookup"><span data-stu-id="d19b7-170">If the variable that you are clearing does not exist, the cmdlet has no effect.</span></span>
<span data-ttu-id="d19b7-171">Он не создает переменную со значением NULL.</span><span class="sxs-lookup"><span data-stu-id="d19b7-171">It does not create a variable with a null value.</span></span>

  <span data-ttu-id="d19b7-172">Можно также ссылаться на **clear-variable** по встроенному псевдониму CLV.</span><span class="sxs-lookup"><span data-stu-id="d19b7-172">You can also refer to **Clear-Variable** by its built-in alias, clv.</span></span>
<span data-ttu-id="d19b7-173">Подробнее см. в разделе "about_Aliases".</span><span class="sxs-lookup"><span data-stu-id="d19b7-173">For more information, see about_Aliases.</span></span>

*

## <span data-ttu-id="d19b7-174">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="d19b7-174">RELATED LINKS</span></span>

[<span data-ttu-id="d19b7-175">Get-Variable</span><span class="sxs-lookup"><span data-stu-id="d19b7-175">Get-Variable</span></span>](Get-Variable.md)

[<span data-ttu-id="d19b7-176">New-Variable</span><span class="sxs-lookup"><span data-stu-id="d19b7-176">New-Variable</span></span>](New-Variable.md)

[<span data-ttu-id="d19b7-177">Remove-Variable</span><span class="sxs-lookup"><span data-stu-id="d19b7-177">Remove-Variable</span></span>](Remove-Variable.md)

[<span data-ttu-id="d19b7-178">Set-Variable</span><span class="sxs-lookup"><span data-stu-id="d19b7-178">Set-Variable</span></span>](Set-Variable.md)

