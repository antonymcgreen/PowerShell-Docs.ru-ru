---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 07/21/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/remove-variable?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Variable
ms.openlocfilehash: 6b9d351b5092d96d7698a28d3de63a493d566c6d
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600193"
---
# <span data-ttu-id="0b1b5-102">Remove-Variable</span><span class="sxs-lookup"><span data-stu-id="0b1b5-102">Remove-Variable</span></span>

## <span data-ttu-id="0b1b5-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="0b1b5-103">SYNOPSIS</span></span>
<span data-ttu-id="0b1b5-104">Удаляет переменную и ее значение.</span><span class="sxs-lookup"><span data-stu-id="0b1b5-104">Deletes a variable and its value.</span></span>

## <span data-ttu-id="0b1b5-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0b1b5-105">SYNTAX</span></span>

```
Remove-Variable [-Name] <String[]> [-Include <String[]>] [-Exclude <String[]>] [-Force] [-Scope <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="0b1b5-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0b1b5-106">DESCRIPTION</span></span>

<span data-ttu-id="0b1b5-107">`Remove-Variable`Командлет удаляет переменную и ее значение из области, в которой она определена, например в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="0b1b5-107">The `Remove-Variable` cmdlet deletes a variable and its value from the scope in which it is defined, such as the current session.</span></span> <span data-ttu-id="0b1b5-108">Этот командлет невозможно использовать для удаления переменных, задающихся как константы или принадлежащих системе.</span><span class="sxs-lookup"><span data-stu-id="0b1b5-108">You cannot use this cmdlet to delete variables that are set as constants or those that are owned by the system.</span></span>

## <span data-ttu-id="0b1b5-109">Примеры</span><span class="sxs-lookup"><span data-stu-id="0b1b5-109">EXAMPLES</span></span>

### <span data-ttu-id="0b1b5-110">Пример 1. Удаление переменной</span><span class="sxs-lookup"><span data-stu-id="0b1b5-110">Example 1: Remove a variable</span></span>

```powershell
Remove-Variable Smp
```

<span data-ttu-id="0b1b5-111">Эта команда удаляет `$Smp` переменную.</span><span class="sxs-lookup"><span data-stu-id="0b1b5-111">This command deletes the `$Smp` variable.</span></span>

## <span data-ttu-id="0b1b5-112">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0b1b5-112">PARAMETERS</span></span>

### <span data-ttu-id="0b1b5-113">-Exclude</span><span class="sxs-lookup"><span data-stu-id="0b1b5-113">-Exclude</span></span>

<span data-ttu-id="0b1b5-114">Указывает массив элементов, который не пропускается этим командлетом из операции.</span><span class="sxs-lookup"><span data-stu-id="0b1b5-114">Specifies an array of items that this cmdlet omits from the operation.</span></span> <span data-ttu-id="0b1b5-115">Значение этого параметра определяет параметр **Name** .</span><span class="sxs-lookup"><span data-stu-id="0b1b5-115">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="0b1b5-116">Введите часть имени или шаблон, например "s\*".</span><span class="sxs-lookup"><span data-stu-id="0b1b5-116">Enter a name element or pattern, such as "s\*".</span></span> <span data-ttu-id="0b1b5-117">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="0b1b5-117">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="0b1b5-118">-Force</span><span class="sxs-lookup"><span data-stu-id="0b1b5-118">-Force</span></span>

<span data-ttu-id="0b1b5-119">Указывает, что командлет удаляет переменную, даже если она доступна только для чтения.</span><span class="sxs-lookup"><span data-stu-id="0b1b5-119">Indicates that the cmdlet removes a variable even if it is read-only.</span></span> <span data-ttu-id="0b1b5-120">Даже при использовании параметра **Force** командлет не может удалить константу.</span><span class="sxs-lookup"><span data-stu-id="0b1b5-120">Even using the **Force** parameter, the cmdlet cannot remove a constant.</span></span>

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

### <span data-ttu-id="0b1b5-121">-Include</span><span class="sxs-lookup"><span data-stu-id="0b1b5-121">-Include</span></span>

<span data-ttu-id="0b1b5-122">Указывает массив элементов, которые этот командлет удаляет в операции.</span><span class="sxs-lookup"><span data-stu-id="0b1b5-122">Specifies an array of items that this cmdlet deletes in the operation.</span></span> <span data-ttu-id="0b1b5-123">Значение этого параметра определяет параметр **Name** .</span><span class="sxs-lookup"><span data-stu-id="0b1b5-123">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="0b1b5-124">Введите часть имени или шаблон, например "s\*".</span><span class="sxs-lookup"><span data-stu-id="0b1b5-124">Enter a name element or pattern, such as s\*.</span></span> <span data-ttu-id="0b1b5-125">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="0b1b5-125">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="0b1b5-126">-Name</span><span class="sxs-lookup"><span data-stu-id="0b1b5-126">-Name</span></span>

<span data-ttu-id="0b1b5-127">Указывает имя удаляемой переменной.</span><span class="sxs-lookup"><span data-stu-id="0b1b5-127">Specifies the name of the variable to be removed.</span></span> <span data-ttu-id="0b1b5-128">Имя параметра (**Name**) является необязательным.</span><span class="sxs-lookup"><span data-stu-id="0b1b5-128">The parameter name (**Name**) is optional.</span></span>
<span data-ttu-id="0b1b5-129">Разрешены подстановочные знаки</span><span class="sxs-lookup"><span data-stu-id="0b1b5-129">Wildcards are permitted</span></span>

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

### <span data-ttu-id="0b1b5-130">-Scope</span><span class="sxs-lookup"><span data-stu-id="0b1b5-130">-Scope</span></span>

<span data-ttu-id="0b1b5-131">Возвращает только те переменные, которые относятся к указанной области.</span><span class="sxs-lookup"><span data-stu-id="0b1b5-131">Gets only the variables in the specified scope.</span></span> <span data-ttu-id="0b1b5-132">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="0b1b5-132">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="0b1b5-133">Глобальный</span><span class="sxs-lookup"><span data-stu-id="0b1b5-133">Global</span></span>
- <span data-ttu-id="0b1b5-134">Локальная</span><span class="sxs-lookup"><span data-stu-id="0b1b5-134">Local</span></span>
- <span data-ttu-id="0b1b5-135">Скрипт</span><span class="sxs-lookup"><span data-stu-id="0b1b5-135">Script</span></span>
- <span data-ttu-id="0b1b5-136">Номер относительно текущей области (от 0 до количества областей, где 0 — это текущая область, а 1 — ее родительская область).</span><span class="sxs-lookup"><span data-stu-id="0b1b5-136">A number relative to the current scope (0 through the number of scopes, where 0 is the current scope and 1 is its parent)</span></span>

<span data-ttu-id="0b1b5-137">По умолчанию используется значение Local.</span><span class="sxs-lookup"><span data-stu-id="0b1b5-137">Local is the default.</span></span> <span data-ttu-id="0b1b5-138">Дополнительные сведения см. в разделе [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span><span class="sxs-lookup"><span data-stu-id="0b1b5-138">For more information, see [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span></span>

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

### <span data-ttu-id="0b1b5-139">-Confirm</span><span class="sxs-lookup"><span data-stu-id="0b1b5-139">-Confirm</span></span>

<span data-ttu-id="0b1b5-140">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="0b1b5-140">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="0b1b5-141">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="0b1b5-141">-WhatIf</span></span>

<span data-ttu-id="0b1b5-142">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="0b1b5-142">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="0b1b5-143">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="0b1b5-143">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="0b1b5-144">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="0b1b5-144">CommonParameters</span></span>

<span data-ttu-id="0b1b5-145">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="0b1b5-145">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0b1b5-146">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="0b1b5-146">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0b1b5-147">Входные данные</span><span class="sxs-lookup"><span data-stu-id="0b1b5-147">INPUTS</span></span>

### <span data-ttu-id="0b1b5-148">System. Management. Automation. PSVariable</span><span class="sxs-lookup"><span data-stu-id="0b1b5-148">System.Management.Automation.PSVariable</span></span>

<span data-ttu-id="0b1b5-149">Объект переменной можно передать в `Remove-Variable` .</span><span class="sxs-lookup"><span data-stu-id="0b1b5-149">You can pipe a variable object to `Remove-Variable`.</span></span>

## <span data-ttu-id="0b1b5-150">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="0b1b5-150">OUTPUTS</span></span>

### <span data-ttu-id="0b1b5-151">None</span><span class="sxs-lookup"><span data-stu-id="0b1b5-151">None</span></span>

<span data-ttu-id="0b1b5-152">Этот командлет не возвращает никакие выходные данные.</span><span class="sxs-lookup"><span data-stu-id="0b1b5-152">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="0b1b5-153">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="0b1b5-153">NOTES</span></span>

- <span data-ttu-id="0b1b5-154">Изменения затрагивают только текущую область, например сеанс.</span><span class="sxs-lookup"><span data-stu-id="0b1b5-154">Changes affect only the current scope, such as a session.</span></span> <span data-ttu-id="0b1b5-155">Чтобы удалить переменную из всех сеансов, добавьте `Remove-Variable` команду в профиль PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0b1b5-155">To delete a variable from all sessions, add a `Remove-Variable` command to your PowerShell profile.</span></span>

- <span data-ttu-id="0b1b5-156">Также можно ссылаться `Remove-Variable` по встроенному псевдониму `rv` .</span><span class="sxs-lookup"><span data-stu-id="0b1b5-156">You can also refer to `Remove-Variable` by its built-in alias, `rv`.</span></span> <span data-ttu-id="0b1b5-157">Дополнительные сведения см. в разделе [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="0b1b5-157">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>

## <span data-ttu-id="0b1b5-158">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="0b1b5-158">RELATED LINKS</span></span>

[<span data-ttu-id="0b1b5-159">Clear-Variable</span><span class="sxs-lookup"><span data-stu-id="0b1b5-159">Clear-Variable</span></span>](Clear-Variable.md)

[<span data-ttu-id="0b1b5-160">Get-Variable</span><span class="sxs-lookup"><span data-stu-id="0b1b5-160">Get-Variable</span></span>](Get-Variable.md)

[<span data-ttu-id="0b1b5-161">New-Variable</span><span class="sxs-lookup"><span data-stu-id="0b1b5-161">New-Variable</span></span>](New-Variable.md)

[<span data-ttu-id="0b1b5-162">Set-Variable</span><span class="sxs-lookup"><span data-stu-id="0b1b5-162">Set-Variable</span></span>](Set-Variable.md)
