---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/clear-variable?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-Variable
ms.openlocfilehash: c696fb0f9d95548d80e772809c6f83e86f1581f6
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227742"
---
# <span data-ttu-id="8df82-103">Clear-Variable</span><span class="sxs-lookup"><span data-stu-id="8df82-103">Clear-Variable</span></span>

## <span data-ttu-id="8df82-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="8df82-104">SYNOPSIS</span></span>
<span data-ttu-id="8df82-105">Удаляет значение переменной.</span><span class="sxs-lookup"><span data-stu-id="8df82-105">Deletes the value of a variable.</span></span>

## <span data-ttu-id="8df82-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8df82-106">SYNTAX</span></span>

```
Clear-Variable [-Name] <String[]> [-Include <String[]>] [-Exclude <String[]>] [-Force] [-PassThru]
 [-Scope <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="8df82-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="8df82-107">DESCRIPTION</span></span>

<span data-ttu-id="8df82-108">Командлет **clear-variable** удаляет данные, хранящиеся в переменной, но не удаляет переменную.</span><span class="sxs-lookup"><span data-stu-id="8df82-108">The **Clear-Variable** cmdlet deletes the data stored in a variable, but it does not delete the variable.</span></span>
<span data-ttu-id="8df82-109">В результате переменная получает значение NULL (пустое).</span><span class="sxs-lookup"><span data-stu-id="8df82-109">As a result, the value of the variable is NULL (empty).</span></span>
<span data-ttu-id="8df82-110">Если переменная имеет указанный тип данных или объект, этот командлет сохраняет тип объекта, хранящегося в переменной.</span><span class="sxs-lookup"><span data-stu-id="8df82-110">If the variable has a specified data or object type, this cmdlet preserves the type of the object stored in the variable.</span></span>

## <span data-ttu-id="8df82-111">Примеры</span><span class="sxs-lookup"><span data-stu-id="8df82-111">EXAMPLES</span></span>

### <span data-ttu-id="8df82-112">Пример 1. Удаление значений глобальных переменных, начинающихся со строки поиска</span><span class="sxs-lookup"><span data-stu-id="8df82-112">Example 1: Remove the value of global variables that begin with a search string</span></span>

```
PS C:\> Clear-Variable my* -Scope Global
```

<span data-ttu-id="8df82-113">Эта команда удаляет значения глобальных переменных, имена которых начинаются с My.</span><span class="sxs-lookup"><span data-stu-id="8df82-113">This command removes the value of global variables that have names that begin with my.</span></span>

### <span data-ttu-id="8df82-114">Пример 2. Очистка переменной в дочерней области, но не родительской области</span><span class="sxs-lookup"><span data-stu-id="8df82-114">Example 2: Clear a variable in a child scope but not the parent scope</span></span>

```
PS C:\> $a=3
PS C:\> &{ Clear-Variable a }
PS C:\> $a
3
```

<span data-ttu-id="8df82-115">Эти команды показывают, что при очистке переменной в дочерней области значение в родительской области не удаляется.</span><span class="sxs-lookup"><span data-stu-id="8df82-115">These commands demonstrate that clearing a variable in a child scope does not clear the value in the parent scope.</span></span>
<span data-ttu-id="8df82-116">Первая команда задает значение переменной $A равным 3.</span><span class="sxs-lookup"><span data-stu-id="8df82-116">The first command sets the value of the variable $A to 3.</span></span>
<span data-ttu-id="8df82-117">Вторая команда использует оператор Invoke (&) для выполнения команды **clear-variable** в новой области.</span><span class="sxs-lookup"><span data-stu-id="8df82-117">The second command uses the invoke operator (&) to run the **Clear-Variable** command in a new scope.</span></span>
<span data-ttu-id="8df82-118">В результате в дочерней области переменная очищается (хотя она и не существовала), а в локальной — нет.</span><span class="sxs-lookup"><span data-stu-id="8df82-118">The variable is cleared in the child scope (although it did not exist), but it is not cleared in the local scope.</span></span>
<span data-ttu-id="8df82-119">Третья команда, которая получает значение $A, показывает, что значение 3 не затрагивается.</span><span class="sxs-lookup"><span data-stu-id="8df82-119">The third command, which gets the value of $A, shows that the value 3 is unaffected.</span></span>

### <span data-ttu-id="8df82-120">Пример 3. Удаление значения указанной переменной</span><span class="sxs-lookup"><span data-stu-id="8df82-120">Example 3: Delete the value of the specified variable</span></span>

```
PS C:\> Clear-Variable -Name "Processes"
```

<span data-ttu-id="8df82-121">Эта команда удаляет значение переменной с именем Processes.</span><span class="sxs-lookup"><span data-stu-id="8df82-121">This command deletes the value of the variable named Processes.</span></span>
<span data-ttu-id="8df82-122">После того как командлет завершит операцию, переменная с именем Processes по-прежнему существует, но имеет значение null.</span><span class="sxs-lookup"><span data-stu-id="8df82-122">After the cmdlet completes the operation, the variable named Processes still exists, but the value is null.</span></span>

## <span data-ttu-id="8df82-123">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8df82-123">PARAMETERS</span></span>

### <span data-ttu-id="8df82-124">-Exclude</span><span class="sxs-lookup"><span data-stu-id="8df82-124">-Exclude</span></span>

<span data-ttu-id="8df82-125">Указывает массив элементов, пропущенных этим командлетом в операции.</span><span class="sxs-lookup"><span data-stu-id="8df82-125">Specifies an array of items that this cmdlet omits in the operation.</span></span>
<span data-ttu-id="8df82-126">Значение этого параметра определяет параметр *Name* .</span><span class="sxs-lookup"><span data-stu-id="8df82-126">The value of this parameter qualifies the *Name* parameter.</span></span>
<span data-ttu-id="8df82-127">Введите часть имени или шаблон, например "s\*".</span><span class="sxs-lookup"><span data-stu-id="8df82-127">Enter a name element or pattern, such as "s\*".</span></span>
<span data-ttu-id="8df82-128">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="8df82-128">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="8df82-129">-Force</span><span class="sxs-lookup"><span data-stu-id="8df82-129">-Force</span></span>

<span data-ttu-id="8df82-130">Позволяет командлету очистить переменную, даже если она доступна только для чтения.</span><span class="sxs-lookup"><span data-stu-id="8df82-130">Allows the cmdlet to clear a variable even if it is read-only.</span></span>
<span data-ttu-id="8df82-131">Даже при использовании параметра Force командлет не может очистить константу.</span><span class="sxs-lookup"><span data-stu-id="8df82-131">Even using the Force parameter, the cmdlet cannot clear constants.</span></span>

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

### <span data-ttu-id="8df82-132">-Include</span><span class="sxs-lookup"><span data-stu-id="8df82-132">-Include</span></span>

<span data-ttu-id="8df82-133">Задает массив элементов, включаемых этим командлетом в операцию.</span><span class="sxs-lookup"><span data-stu-id="8df82-133">Specifies an array of items that this cmdlet includes in the operation.</span></span>
<span data-ttu-id="8df82-134">Значение этого параметра определяет параметр *Name* .</span><span class="sxs-lookup"><span data-stu-id="8df82-134">The value of this parameter qualifies the *Name* parameter.</span></span>
<span data-ttu-id="8df82-135">Введите часть имени или шаблон, например "s\*".</span><span class="sxs-lookup"><span data-stu-id="8df82-135">Enter a name element or pattern, such as "s\*".</span></span>
<span data-ttu-id="8df82-136">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="8df82-136">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="8df82-137">-Name</span><span class="sxs-lookup"><span data-stu-id="8df82-137">-Name</span></span>

<span data-ttu-id="8df82-138">Указывает имя переменной, которую нужно очистить.</span><span class="sxs-lookup"><span data-stu-id="8df82-138">Specifies the name of the variable to be cleared.</span></span>
<span data-ttu-id="8df82-139">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="8df82-139">Wildcards are permitted.</span></span>
<span data-ttu-id="8df82-140">Этот параметр обязателен, но его имя (Name) можно не указывать.</span><span class="sxs-lookup"><span data-stu-id="8df82-140">This parameter is required, but the parameter name ("Name") is optional.</span></span>

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

### <span data-ttu-id="8df82-141">-PassThru</span><span class="sxs-lookup"><span data-stu-id="8df82-141">-PassThru</span></span>

<span data-ttu-id="8df82-142">Возвращает объект, представляющий элемент, с которым вы работаете.</span><span class="sxs-lookup"><span data-stu-id="8df82-142">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="8df82-143">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="8df82-143">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="8df82-144">-Scope</span><span class="sxs-lookup"><span data-stu-id="8df82-144">-Scope</span></span>

<span data-ttu-id="8df82-145">Задает область действия псевдонима.</span><span class="sxs-lookup"><span data-stu-id="8df82-145">Specifies the scope in which this alias is valid.</span></span>

<span data-ttu-id="8df82-146">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="8df82-146">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="8df82-147">Глобальный</span><span class="sxs-lookup"><span data-stu-id="8df82-147">Global</span></span>
- <span data-ttu-id="8df82-148">Локальная</span><span class="sxs-lookup"><span data-stu-id="8df82-148">Local</span></span>
- <span data-ttu-id="8df82-149">Сценарий</span><span class="sxs-lookup"><span data-stu-id="8df82-149">Script</span></span>

<span data-ttu-id="8df82-150">Можно также использовать число относительно текущей области (от 0 до количества областей, где 0 — текущая область, а 1 — ее родителя).</span><span class="sxs-lookup"><span data-stu-id="8df82-150">You can also use a number relative to the current scope (0 through the number of scopes, where 0 is the current scope and 1 is its parent).</span></span>
<span data-ttu-id="8df82-151">По умолчанию используется значение Local.</span><span class="sxs-lookup"><span data-stu-id="8df82-151">Local is the default.</span></span>
<span data-ttu-id="8df82-152">Дополнительные сведения см. в разделе about_Scopes.</span><span class="sxs-lookup"><span data-stu-id="8df82-152">For more information, see about_Scopes.</span></span>

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

### <span data-ttu-id="8df82-153">-Confirm</span><span class="sxs-lookup"><span data-stu-id="8df82-153">-Confirm</span></span>

<span data-ttu-id="8df82-154">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="8df82-154">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="8df82-155">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="8df82-155">-WhatIf</span></span>

<span data-ttu-id="8df82-156">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="8df82-156">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="8df82-157">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="8df82-157">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="8df82-158">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="8df82-158">CommonParameters</span></span>

<span data-ttu-id="8df82-159">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="8df82-159">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="8df82-160">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="8df82-160">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="8df82-161">Входные данные</span><span class="sxs-lookup"><span data-stu-id="8df82-161">INPUTS</span></span>

### <span data-ttu-id="8df82-162">Нет</span><span class="sxs-lookup"><span data-stu-id="8df82-162">None</span></span>

<span data-ttu-id="8df82-163">Нельзя передать объекты в этот командлет с помощью конвейера.</span><span class="sxs-lookup"><span data-stu-id="8df82-163">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="8df82-164">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="8df82-164">OUTPUTS</span></span>

### <span data-ttu-id="8df82-165">None или System. Management. Automation. PSVariable</span><span class="sxs-lookup"><span data-stu-id="8df82-165">None or System.Management.Automation.PSVariable</span></span>

<span data-ttu-id="8df82-166">При использовании параметра *PassThru* этот командлет создает объект **System. Management. Automation. PSVariable** , представляющий переменную, которая была сброшена.</span><span class="sxs-lookup"><span data-stu-id="8df82-166">When you use the *PassThru* parameter, this cmdlet generates a **System.Management.Automation.PSVariable** object representing the cleared variable.</span></span>
<span data-ttu-id="8df82-167">В противном случае командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="8df82-167">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="8df82-168">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="8df82-168">NOTES</span></span>

* <span data-ttu-id="8df82-169">Чтобы удалить переменную вместе со значением, используйте командлеты Remove-Variable или Remove-Item.</span><span class="sxs-lookup"><span data-stu-id="8df82-169">To delete a variable, along with its value, use Remove-Variable or Remove-Item.</span></span>

  <span data-ttu-id="8df82-170">Этот командлет не удаляет значения переменных, которые установлены как константы или принадлежат системе, даже если используется параметр *Force* .</span><span class="sxs-lookup"><span data-stu-id="8df82-170">This cmdlet does not delete the values of variables that are set as constants or owned by the system, even if you use the *Force* parameter.</span></span>

  <span data-ttu-id="8df82-171">Если очищаемой переменной не существует, этот командлет не выполняет никаких действий.</span><span class="sxs-lookup"><span data-stu-id="8df82-171">If the variable that you are clearing does not exist, the cmdlet has no effect.</span></span>
<span data-ttu-id="8df82-172">Он не создает переменную со значением NULL.</span><span class="sxs-lookup"><span data-stu-id="8df82-172">It does not create a variable with a null value.</span></span>

  <span data-ttu-id="8df82-173">Можно также ссылаться на **clear-variable** по встроенному псевдониму CLV.</span><span class="sxs-lookup"><span data-stu-id="8df82-173">You can also refer to **Clear-Variable** by its built-in alias, clv.</span></span>
<span data-ttu-id="8df82-174">Подробнее см. в разделе "about_Aliases".</span><span class="sxs-lookup"><span data-stu-id="8df82-174">For more information, see about_Aliases.</span></span>

*

## <span data-ttu-id="8df82-175">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="8df82-175">RELATED LINKS</span></span>

[<span data-ttu-id="8df82-176">Get-Variable</span><span class="sxs-lookup"><span data-stu-id="8df82-176">Get-Variable</span></span>](Get-Variable.md)

[<span data-ttu-id="8df82-177">New-Variable</span><span class="sxs-lookup"><span data-stu-id="8df82-177">New-Variable</span></span>](New-Variable.md)

[<span data-ttu-id="8df82-178">Remove-Variable</span><span class="sxs-lookup"><span data-stu-id="8df82-178">Remove-Variable</span></span>](Remove-Variable.md)

[<span data-ttu-id="8df82-179">Set-Variable</span><span class="sxs-lookup"><span data-stu-id="8df82-179">Set-Variable</span></span>](Set-Variable.md)
