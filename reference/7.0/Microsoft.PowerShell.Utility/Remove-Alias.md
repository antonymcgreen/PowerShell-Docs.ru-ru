---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/24/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/remove-alias?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Alias
ms.openlocfilehash: 6f98a910e43b87793ac4f2af8ffb069d3e5d47ba
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93225809"
---
# <span data-ttu-id="e254c-103">Remove-Alias</span><span class="sxs-lookup"><span data-stu-id="e254c-103">Remove-Alias</span></span>

## <span data-ttu-id="e254c-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="e254c-104">SYNOPSIS</span></span>
<span data-ttu-id="e254c-105">Удаление псевдонима из текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="e254c-105">Remove an alias from the current session.</span></span>

## <span data-ttu-id="e254c-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e254c-106">SYNTAX</span></span>

### <span data-ttu-id="e254c-107">Default (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="e254c-107">Default (Default)</span></span>

```
Remove-Alias [-Name] <String[]> [-Scope <String>] [-Force] [<CommonParameters>]
```

## <span data-ttu-id="e254c-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e254c-108">DESCRIPTION</span></span>

<span data-ttu-id="e254c-109">`Remove-Alias`Командлет удаляет псевдоним из текущего сеанса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e254c-109">The `Remove-Alias` cmdlet removes an alias from the current PowerShell session.</span></span> <span data-ttu-id="e254c-110">Чтобы удалить псевдоним с свойством **Option** , имеющим значение **ReadOnly** , используйте параметр **Force** .</span><span class="sxs-lookup"><span data-stu-id="e254c-110">To remove an alias with the **Option** property set to **ReadOnly** , use the **Force** parameter.</span></span>

<span data-ttu-id="e254c-111">`Remove-Alias`Командлет был представлен в PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="e254c-111">The `Remove-Alias` cmdlet was introduced in PowerShell 6.0.</span></span>

## <span data-ttu-id="e254c-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="e254c-112">EXAMPLES</span></span>

### <span data-ttu-id="e254c-113">Пример 1. Удаление псевдонима</span><span class="sxs-lookup"><span data-stu-id="e254c-113">Example 1 - Remove an alias</span></span>

<span data-ttu-id="e254c-114">В этом примере удаляется псевдоним с именем `del` , который представляет `Remove-Item` командлет.</span><span class="sxs-lookup"><span data-stu-id="e254c-114">This example removes an alias named `del` that represents the `Remove-Item` cmdlet.</span></span>

```powershell
Remove-Alias -Name del
```

### <span data-ttu-id="e254c-115">Пример 2. Удаление всех псевдонимов, не являющихся константами</span><span class="sxs-lookup"><span data-stu-id="e254c-115">Example 2 - Remove all non-Constant aliases</span></span>

<span data-ttu-id="e254c-116">В этом примере удаляются все псевдонимы из текущего сеанса PowerShell, за исключением псевдонимов со свойством **Options** , для которых установлено значение **Constant** .</span><span class="sxs-lookup"><span data-stu-id="e254c-116">This example removes all aliases from the current PowerShell session, except for aliases with the **Options** property set to **Constant** .</span></span> <span data-ttu-id="e254c-117">После выполнения команды псевдонимы будут доступны в других сеансах PowerShell или в новых сеансах PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e254c-117">After the command is run, the aliases are available in other PowerShell sessions or new PowerShell sessions.</span></span>

```powershell
Get-Alias | Where-Object { $_.Options -NE "Constant" } | Remove-Alias -Force
```

<span data-ttu-id="e254c-118">`Get-Alias` Получает все псевдонимы в сеансе PowerShell и отправляет объекты по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="e254c-118">`Get-Alias` gets all the aliases in the PowerShell session and sends the objects down the pipeline.</span></span>
<span data-ttu-id="e254c-119">`Where-Object` использует блок скрипта, а свойство Variables ( `$_` ) и **Options** представляет текущий объект конвейера.</span><span class="sxs-lookup"><span data-stu-id="e254c-119">`Where-Object` uses a script block, and the automatic variable (`$_`) and **Options** property represent the current pipeline object.</span></span> <span data-ttu-id="e254c-120">Параметр **Ne** (не равно) выбирает объекты, для которых **не задано значение "** **константа** ".</span><span class="sxs-lookup"><span data-stu-id="e254c-120">The parameter **NE** (not equal), selects objects that don't have an **Options** value set to **Constant** .</span></span> <span data-ttu-id="e254c-121">`Remove-Alias` использует параметр **Force** для удаления псевдонимов, в том числе псевдонимов только для чтения, из сеанса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e254c-121">`Remove-Alias` uses the **Force** parameter to remove aliases, including read-only aliases, from the PowerShell session.</span></span>

## <span data-ttu-id="e254c-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e254c-122">PARAMETERS</span></span>

### <span data-ttu-id="e254c-123">-Force</span><span class="sxs-lookup"><span data-stu-id="e254c-123">-Force</span></span>

<span data-ttu-id="e254c-124">Указывает, что командлет удаляет псевдоним, включая псевдонимы со свойством **Option** , имеющим значение **ReadOnly** .</span><span class="sxs-lookup"><span data-stu-id="e254c-124">Indicates that the cmdlet removes an alias, including aliases with the **Option** property set to **ReadOnly** .</span></span> <span data-ttu-id="e254c-125">Параметр **Force** не может удалить псевдоним с свойством **параметра** , имеющим значение **Constant** .</span><span class="sxs-lookup"><span data-stu-id="e254c-125">The **Force** parameter can't remove an alias with an **Option** property set to **Constant** .</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e254c-126">-Name</span><span class="sxs-lookup"><span data-stu-id="e254c-126">-Name</span></span>

<span data-ttu-id="e254c-127">Указывает имя удаляемого псевдонима.</span><span class="sxs-lookup"><span data-stu-id="e254c-127">Specifies the name of the alias to remove.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="e254c-128">-Scope</span><span class="sxs-lookup"><span data-stu-id="e254c-128">-Scope</span></span>

<span data-ttu-id="e254c-129">Затрагивает только псевдонимы в указанной области.</span><span class="sxs-lookup"><span data-stu-id="e254c-129">Affects only the aliases in the specified scope.</span></span> <span data-ttu-id="e254c-130">Область по умолчанию — **Local** .</span><span class="sxs-lookup"><span data-stu-id="e254c-130">The default scope is **Local** .</span></span> <span data-ttu-id="e254c-131">Дополнительные сведения см. в разделе [about_Scopes](../microsoft.powershell.core/about/about_scopes.md).</span><span class="sxs-lookup"><span data-stu-id="e254c-131">For more information, see [about_Scopes](../microsoft.powershell.core/about/about_scopes.md).</span></span>

<span data-ttu-id="e254c-132">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="e254c-132">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="e254c-133">Глобальный</span><span class="sxs-lookup"><span data-stu-id="e254c-133">Global</span></span>
- <span data-ttu-id="e254c-134">Локальная</span><span class="sxs-lookup"><span data-stu-id="e254c-134">Local</span></span>
- <span data-ttu-id="e254c-135">Сценарий</span><span class="sxs-lookup"><span data-stu-id="e254c-135">Script</span></span>
- <span data-ttu-id="e254c-136">Номер относительно текущей области (от 0 до количества областей, где 0 — это текущая область, а 1 — ее родительская область).</span><span class="sxs-lookup"><span data-stu-id="e254c-136">A number relative to the current scope (0 through the number of scopes, where 0 is the current scope and 1 is its parent)</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Local
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e254c-137">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="e254c-137">CommonParameters</span></span>

<span data-ttu-id="e254c-138">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="e254c-138">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e254c-139">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="e254c-139">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e254c-140">Входные данные</span><span class="sxs-lookup"><span data-stu-id="e254c-140">INPUTS</span></span>

### <span data-ttu-id="e254c-141">System.String[]</span><span class="sxs-lookup"><span data-stu-id="e254c-141">System.String[]</span></span>

<span data-ttu-id="e254c-142">Объект псевдонима можно передать в командлет **Remove-Alias** .</span><span class="sxs-lookup"><span data-stu-id="e254c-142">You can pipe an alias object to **Remove-Alias** .</span></span>

## <span data-ttu-id="e254c-143">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="e254c-143">OUTPUTS</span></span>

### <span data-ttu-id="e254c-144">Нет</span><span class="sxs-lookup"><span data-stu-id="e254c-144">None</span></span>

<span data-ttu-id="e254c-145">Этот командлет не возвращает никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="e254c-145">This cmdlet doesn't return any output.</span></span>

## <span data-ttu-id="e254c-146">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="e254c-146">NOTES</span></span>

<span data-ttu-id="e254c-147">Изменения влияют только на текущую область.</span><span class="sxs-lookup"><span data-stu-id="e254c-147">Changes only affect the current scope.</span></span> <span data-ttu-id="e254c-148">Чтобы удалить псевдоним из всех сеансов, добавьте команду **Remove-Alias** в профиль PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e254c-148">To remove an alias from all sessions, add a **Remove-Alias** command to your PowerShell profile.</span></span>

<span data-ttu-id="e254c-149">Дополнительные сведения см. в разделе [about_Aliases](../microsoft.powershell.core/about/about_aliases.md).</span><span class="sxs-lookup"><span data-stu-id="e254c-149">For more information, see [about_Aliases](../microsoft.powershell.core/about/about_aliases.md).</span></span>

## <span data-ttu-id="e254c-150">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="e254c-150">RELATED LINKS</span></span>

[<span data-ttu-id="e254c-151">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="e254c-151">about_Automatic_Variables</span></span>](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md)

[<span data-ttu-id="e254c-152">Export-Alias</span><span class="sxs-lookup"><span data-stu-id="e254c-152">Export-Alias</span></span>](Export-Alias.md)

[<span data-ttu-id="e254c-153">Get-Alias</span><span class="sxs-lookup"><span data-stu-id="e254c-153">Get-Alias</span></span>](Get-Alias.md)

[<span data-ttu-id="e254c-154">Import-Alias</span><span class="sxs-lookup"><span data-stu-id="e254c-154">Import-Alias</span></span>](Import-Alias.md)

[<span data-ttu-id="e254c-155">New-Alias</span><span class="sxs-lookup"><span data-stu-id="e254c-155">New-Alias</span></span>](New-Alias.md)

[<span data-ttu-id="e254c-156">Set-Alias</span><span class="sxs-lookup"><span data-stu-id="e254c-156">Set-Alias</span></span>](Set-Alias.md)

[<span data-ttu-id="e254c-157">Where-Object</span><span class="sxs-lookup"><span data-stu-id="e254c-157">Where-Object</span></span>](../Microsoft.PowerShell.Core/Where-Object.md)
