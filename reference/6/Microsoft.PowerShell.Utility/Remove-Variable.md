---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 07/21/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/remove-variable?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Variable
ms.openlocfilehash: 2e0e9388c592cb83dd7609fed663ae220e380750
ms.sourcegitcommit: 84fcc90bd018ab76ac4e964d53e7c9c2b5a7b6c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "93230110"
---
# <span data-ttu-id="bd1da-103">Remove-Variable</span><span class="sxs-lookup"><span data-stu-id="bd1da-103">Remove-Variable</span></span>

## <span data-ttu-id="bd1da-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="bd1da-104">SYNOPSIS</span></span>
<span data-ttu-id="bd1da-105">Удаляет переменную и ее значение.</span><span class="sxs-lookup"><span data-stu-id="bd1da-105">Deletes a variable and its value.</span></span>

## <span data-ttu-id="bd1da-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="bd1da-106">SYNTAX</span></span>

```
Remove-Variable [-Name] <String[]> [-Include <String[]>] [-Exclude <String[]>] [-Force] [-Scope <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="bd1da-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="bd1da-107">DESCRIPTION</span></span>

<span data-ttu-id="bd1da-108">`Remove-Variable`Командлет удаляет переменную и ее значение из области, в которой она определена, например в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="bd1da-108">The `Remove-Variable` cmdlet deletes a variable and its value from the scope in which it is defined, such as the current session.</span></span> <span data-ttu-id="bd1da-109">Этот командлет невозможно использовать для удаления переменных, задающихся как константы или принадлежащих системе.</span><span class="sxs-lookup"><span data-stu-id="bd1da-109">You cannot use this cmdlet to delete variables that are set as constants or those that are owned by the system.</span></span>

## <span data-ttu-id="bd1da-110">Примеры</span><span class="sxs-lookup"><span data-stu-id="bd1da-110">EXAMPLES</span></span>

### <span data-ttu-id="bd1da-111">Пример 1. Удаление переменной</span><span class="sxs-lookup"><span data-stu-id="bd1da-111">Example 1: Remove a variable</span></span>

```powershell
Remove-Variable Smp
```

<span data-ttu-id="bd1da-112">Эта команда удаляет `$Smp` переменную.</span><span class="sxs-lookup"><span data-stu-id="bd1da-112">This command deletes the `$Smp` variable.</span></span>

## <span data-ttu-id="bd1da-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="bd1da-113">PARAMETERS</span></span>

### <span data-ttu-id="bd1da-114">-Exclude</span><span class="sxs-lookup"><span data-stu-id="bd1da-114">-Exclude</span></span>

<span data-ttu-id="bd1da-115">Указывает массив элементов, который не пропускается этим командлетом из операции.</span><span class="sxs-lookup"><span data-stu-id="bd1da-115">Specifies an array of items that this cmdlet omits from the operation.</span></span> <span data-ttu-id="bd1da-116">Значение этого параметра определяет параметр **Name** .</span><span class="sxs-lookup"><span data-stu-id="bd1da-116">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="bd1da-117">Введите часть имени или шаблон, например "s\*".</span><span class="sxs-lookup"><span data-stu-id="bd1da-117">Enter a name element or pattern, such as "s\*".</span></span> <span data-ttu-id="bd1da-118">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="bd1da-118">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="bd1da-119">-Force</span><span class="sxs-lookup"><span data-stu-id="bd1da-119">-Force</span></span>

<span data-ttu-id="bd1da-120">Указывает, что командлет удаляет переменную, даже если она доступна только для чтения.</span><span class="sxs-lookup"><span data-stu-id="bd1da-120">Indicates that the cmdlet removes a variable even if it is read-only.</span></span> <span data-ttu-id="bd1da-121">Даже при использовании параметра **Force** командлет не может удалить константу.</span><span class="sxs-lookup"><span data-stu-id="bd1da-121">Even using the **Force** parameter, the cmdlet cannot remove a constant.</span></span>

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

### <span data-ttu-id="bd1da-122">-Include</span><span class="sxs-lookup"><span data-stu-id="bd1da-122">-Include</span></span>

<span data-ttu-id="bd1da-123">Указывает массив элементов, которые этот командлет удаляет в операции.</span><span class="sxs-lookup"><span data-stu-id="bd1da-123">Specifies an array of items that this cmdlet deletes in the operation.</span></span> <span data-ttu-id="bd1da-124">Значение этого параметра определяет параметр **Name** .</span><span class="sxs-lookup"><span data-stu-id="bd1da-124">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="bd1da-125">Введите часть имени или шаблон, например "s\*".</span><span class="sxs-lookup"><span data-stu-id="bd1da-125">Enter a name element or pattern, such as s\*.</span></span> <span data-ttu-id="bd1da-126">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="bd1da-126">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="bd1da-127">-Name</span><span class="sxs-lookup"><span data-stu-id="bd1da-127">-Name</span></span>

<span data-ttu-id="bd1da-128">Указывает имя удаляемой переменной.</span><span class="sxs-lookup"><span data-stu-id="bd1da-128">Specifies the name of the variable to be removed.</span></span> <span data-ttu-id="bd1da-129">Имя параметра ( **Name** ) является необязательным.</span><span class="sxs-lookup"><span data-stu-id="bd1da-129">The parameter name ( **Name** ) is optional.</span></span>
<span data-ttu-id="bd1da-130">Разрешены подстановочные знаки</span><span class="sxs-lookup"><span data-stu-id="bd1da-130">Wildcards are permitted</span></span>

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

### <span data-ttu-id="bd1da-131">-Scope</span><span class="sxs-lookup"><span data-stu-id="bd1da-131">-Scope</span></span>

<span data-ttu-id="bd1da-132">Возвращает только те переменные, которые относятся к указанной области.</span><span class="sxs-lookup"><span data-stu-id="bd1da-132">Gets only the variables in the specified scope.</span></span> <span data-ttu-id="bd1da-133">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="bd1da-133">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="bd1da-134">Глобальный</span><span class="sxs-lookup"><span data-stu-id="bd1da-134">Global</span></span>
- <span data-ttu-id="bd1da-135">Локальная</span><span class="sxs-lookup"><span data-stu-id="bd1da-135">Local</span></span>
- <span data-ttu-id="bd1da-136">Сценарий</span><span class="sxs-lookup"><span data-stu-id="bd1da-136">Script</span></span>
- <span data-ttu-id="bd1da-137">Номер относительно текущей области (от 0 до количества областей, где 0 — это текущая область, а 1 — ее родительская область).</span><span class="sxs-lookup"><span data-stu-id="bd1da-137">A number relative to the current scope (0 through the number of scopes, where 0 is the current scope and 1 is its parent)</span></span>

<span data-ttu-id="bd1da-138">По умолчанию используется значение Local.</span><span class="sxs-lookup"><span data-stu-id="bd1da-138">Local is the default.</span></span> <span data-ttu-id="bd1da-139">Дополнительные сведения см. в разделе [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span><span class="sxs-lookup"><span data-stu-id="bd1da-139">For more information, see [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span></span>

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

### <span data-ttu-id="bd1da-140">-Confirm</span><span class="sxs-lookup"><span data-stu-id="bd1da-140">-Confirm</span></span>

<span data-ttu-id="bd1da-141">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="bd1da-141">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="bd1da-142">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="bd1da-142">-WhatIf</span></span>

<span data-ttu-id="bd1da-143">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="bd1da-143">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="bd1da-144">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="bd1da-144">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="bd1da-145">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="bd1da-145">CommonParameters</span></span>

<span data-ttu-id="bd1da-146">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="bd1da-146">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="bd1da-147">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="bd1da-147">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="bd1da-148">Входные данные</span><span class="sxs-lookup"><span data-stu-id="bd1da-148">INPUTS</span></span>

### <span data-ttu-id="bd1da-149">System. Management. Automation. PSVariable</span><span class="sxs-lookup"><span data-stu-id="bd1da-149">System.Management.Automation.PSVariable</span></span>

<span data-ttu-id="bd1da-150">Объект переменной можно передать в `Remove-Variable` .</span><span class="sxs-lookup"><span data-stu-id="bd1da-150">You can pipe a variable object to `Remove-Variable`.</span></span>

## <span data-ttu-id="bd1da-151">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="bd1da-151">OUTPUTS</span></span>

### <span data-ttu-id="bd1da-152">Нет</span><span class="sxs-lookup"><span data-stu-id="bd1da-152">None</span></span>

<span data-ttu-id="bd1da-153">Этот командлет не возвращает никакие выходные данные.</span><span class="sxs-lookup"><span data-stu-id="bd1da-153">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="bd1da-154">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="bd1da-154">NOTES</span></span>

- <span data-ttu-id="bd1da-155">Изменения затрагивают только текущую область, например сеанс.</span><span class="sxs-lookup"><span data-stu-id="bd1da-155">Changes affect only the current scope, such as a session.</span></span> <span data-ttu-id="bd1da-156">Чтобы удалить переменную из всех сеансов, добавьте `Remove-Variable` команду в профиль PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bd1da-156">To delete a variable from all sessions, add a `Remove-Variable` command to your PowerShell profile.</span></span>

- <span data-ttu-id="bd1da-157">Также можно ссылаться `Remove-Variable` по встроенному псевдониму `rv` .</span><span class="sxs-lookup"><span data-stu-id="bd1da-157">You can also refer to `Remove-Variable` by its built-in alias, `rv`.</span></span> <span data-ttu-id="bd1da-158">Дополнительные сведения см. в разделе [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="bd1da-158">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>

## <span data-ttu-id="bd1da-159">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="bd1da-159">RELATED LINKS</span></span>

[<span data-ttu-id="bd1da-160">Clear-Variable</span><span class="sxs-lookup"><span data-stu-id="bd1da-160">Clear-Variable</span></span>](Clear-Variable.md)

[<span data-ttu-id="bd1da-161">Get-Variable</span><span class="sxs-lookup"><span data-stu-id="bd1da-161">Get-Variable</span></span>](Get-Variable.md)

[<span data-ttu-id="bd1da-162">New-Variable</span><span class="sxs-lookup"><span data-stu-id="bd1da-162">New-Variable</span></span>](New-Variable.md)

[<span data-ttu-id="bd1da-163">Set-Variable</span><span class="sxs-lookup"><span data-stu-id="bd1da-163">Set-Variable</span></span>](Set-Variable.md)
