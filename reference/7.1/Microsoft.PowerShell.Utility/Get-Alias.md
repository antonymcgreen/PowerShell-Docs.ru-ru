---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-alias?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Alias
ms.openlocfilehash: e0a08a4ee6f00702f765bc359a20bf9e30b9b1c5
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227218"
---
# <span data-ttu-id="016fe-103">Get-Alias</span><span class="sxs-lookup"><span data-stu-id="016fe-103">Get-Alias</span></span>

## <span data-ttu-id="016fe-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="016fe-104">SYNOPSIS</span></span>
<span data-ttu-id="016fe-105">Получает псевдонимы, действительные в ходе текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="016fe-105">Gets the aliases for the current session.</span></span>

## <span data-ttu-id="016fe-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="016fe-106">SYNTAX</span></span>

### <span data-ttu-id="016fe-107">Default (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="016fe-107">Default (Default)</span></span>

```
Get-Alias [[-Name] <String[]>] [-Exclude <String[]>] [-Scope <String>] [<CommonParameters>]
```

### <span data-ttu-id="016fe-108">Определение</span><span class="sxs-lookup"><span data-stu-id="016fe-108">Definition</span></span>

```
Get-Alias [-Exclude <String[]>] [-Scope <String>] [-Definition <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="016fe-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="016fe-109">DESCRIPTION</span></span>

<span data-ttu-id="016fe-110">Командлет **Get-Alias** получает псевдонимы в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="016fe-110">The **Get-Alias** cmdlet gets the aliases in the current session.</span></span>
<span data-ttu-id="016fe-111">Сюда входят встроенные псевдонимы, псевдонимы, которые вы установили или импортировали, и псевдонимы, добавленные в профиль PowerShell.</span><span class="sxs-lookup"><span data-stu-id="016fe-111">This includes built-in aliases, aliases that you have set or imported, and aliases that you have added to your PowerShell profile.</span></span>

<span data-ttu-id="016fe-112">По умолчанию командлет **Get-Alias** принимает псевдоним и возвращает имя команды.</span><span class="sxs-lookup"><span data-stu-id="016fe-112">By default, **Get-Alias** takes an alias and returns the command name.</span></span>
<span data-ttu-id="016fe-113">При использовании параметра *определения* командлет **Get-Alias** принимает имя команды и возвращает его псевдонимы.</span><span class="sxs-lookup"><span data-stu-id="016fe-113">When you use the *Definition* parameter, **Get-Alias** takes a command name and returns its aliases.</span></span>

<span data-ttu-id="016fe-114">Начиная с Windows PowerShell 3,0, **Get-Alias** отображает имена псевдонимов без дефисов в `<alias> -> <definition>` формате, чтобы упростить поиск нужных сведений.</span><span class="sxs-lookup"><span data-stu-id="016fe-114">Beginning in Windows PowerShell 3.0, **Get-Alias** displays non-hyphenated alias names in an `<alias> -> <definition>` format to make it even easier to find the information that you need.</span></span>

## <span data-ttu-id="016fe-115">Примеры</span><span class="sxs-lookup"><span data-stu-id="016fe-115">EXAMPLES</span></span>

### <span data-ttu-id="016fe-116">Пример 1. Получение всех псевдонимов в текущем сеансе</span><span class="sxs-lookup"><span data-stu-id="016fe-116">Example 1: Get all aliases in the current session</span></span>

```
PS C:\> Get-Alias

CommandType     Name
-----------     ----
Alias           % -> ForEach-Object
Alias           ? -> Where-Object
Alias           ac -> Add-Content
Alias           asnp -> Add-PSSnapin
Alias           cat -> Get-Content
Alias           cd -> Set-Location
Alias           chdir -> Set-Location
Alias           clc -> Clear-Content
Alias           clear -> Clear-Host
Alias           clhy -> Clear-History
...
```

<span data-ttu-id="016fe-117">Эта команда получает все псевдонимы в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="016fe-117">This command gets all aliases in the current session.</span></span>

<span data-ttu-id="016fe-118">В выходных данных показан `<alias> -> <definition>` Формат, представленный в Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="016fe-118">The output shows the `<alias> -> <definition>` format that was introduced in Windows PowerShell 3.0.</span></span>
<span data-ttu-id="016fe-119">Этот формат используется только для псевдонимов, не содержащих дефисы, поскольку вместо названий командлетов и функций предпочтительнее использовать псевдонимы с дефисами.</span><span class="sxs-lookup"><span data-stu-id="016fe-119">This format is used only for aliases that do not include hyphens, because aliases with hyphens are typically preferred names for cmdlets and functions, rather than nicknames.</span></span>

### <span data-ttu-id="016fe-120">Пример 2. Получение псевдонимов по имени</span><span class="sxs-lookup"><span data-stu-id="016fe-120">Example 2: Get aliases by name</span></span>

```powershell
Get-Alias -Name gp*, sp* -Exclude *ps
```

<span data-ttu-id="016fe-121">Эта команда возвращает все псевдонимы, которые начинаются с GP или SP, за исключением псевдонимов, которые заканчиваются на PS.</span><span class="sxs-lookup"><span data-stu-id="016fe-121">This command gets all aliases that begin with gp or sp, except for aliases that end with ps.</span></span>

### <span data-ttu-id="016fe-122">Пример 3. Получение псевдонимов для командлета</span><span class="sxs-lookup"><span data-stu-id="016fe-122">Example 3: Get aliases for a cmdlet</span></span>

```powershell
Get-Alias -Definition Get-ChildItem
```

<span data-ttu-id="016fe-123">Эта команда получает псевдонимы для командлета Get-ChildItem.</span><span class="sxs-lookup"><span data-stu-id="016fe-123">This command gets the aliases for the Get-ChildItem cmdlet.</span></span>

<span data-ttu-id="016fe-124">По умолчанию командлет **Get-Alias** получает имя элемента, если известно его псевдоним.</span><span class="sxs-lookup"><span data-stu-id="016fe-124">By default, the **Get-Alias** cmdlet gets the item name when you know the alias.</span></span>
<span data-ttu-id="016fe-125">Параметр *определения* получает псевдоним, если известно имя элемента.</span><span class="sxs-lookup"><span data-stu-id="016fe-125">The *Definition* parameter gets the alias when you know the item name.</span></span>

### <span data-ttu-id="016fe-126">Пример 4. Получение псевдонимов по свойству</span><span class="sxs-lookup"><span data-stu-id="016fe-126">Example 4: Get aliases by property</span></span>

```powershell
Get-Alias | Where-Object {$_.Options -Match "ReadOnly"}
```

<span data-ttu-id="016fe-127">Эта команда получает все псевдонимы, в которых свойство Options имеет значение ReadOnly.</span><span class="sxs-lookup"><span data-stu-id="016fe-127">This command gets all aliases in which the value of the Options property is ReadOnly.</span></span>
<span data-ttu-id="016fe-128">Эта команда позволяет быстро найти псевдонимы, встроенные в PowerShell, так как они имеют параметр ReadOnly.</span><span class="sxs-lookup"><span data-stu-id="016fe-128">This command provides a quick way to find the aliases that are built into PowerShell, because they have the ReadOnly option.</span></span>

<span data-ttu-id="016fe-129">Параметры — это только одно свойство объектов AliasInfo, которое получает **Get-Alias** .</span><span class="sxs-lookup"><span data-stu-id="016fe-129">Options is just one property of the AliasInfo objects that **Get-Alias** gets.</span></span>
<span data-ttu-id="016fe-130">Чтобы найти все свойства и методы объектов AliasInfo, введите команду `Get-Alias | get-member`.</span><span class="sxs-lookup"><span data-stu-id="016fe-130">To find all properties and methods of AliasInfo objects, type `Get-Alias | get-member`.</span></span>

### <span data-ttu-id="016fe-131">Пример 5. Получение псевдонимов по имени и фильтрование по первой букве</span><span class="sxs-lookup"><span data-stu-id="016fe-131">Example 5: Get aliases by name and filter by beginning letter</span></span>

```powershell
Get-Alias -Definition "*-PSSession" -Exclude e* -Scope Global
```

<span data-ttu-id="016fe-132">Этот пример получает псевдонимы команд, имена которых заканчиваются на "-PSSession", кроме команд, начинающихся на букву "e".</span><span class="sxs-lookup"><span data-stu-id="016fe-132">This example gets aliases for commands that have names that end in "-PSSession", except for those that begin with "e".</span></span>

<span data-ttu-id="016fe-133">Команда использует параметр *Scope* для применения команды в глобальной области.</span><span class="sxs-lookup"><span data-stu-id="016fe-133">The command uses the *Scope* parameter to apply the command in the global scope.</span></span>
<span data-ttu-id="016fe-134">Эта функция пригодится в скриптах, где необходимо получить псевдонимы, действительные в сеансе.</span><span class="sxs-lookup"><span data-stu-id="016fe-134">This is useful in scripts when you want to get the aliases in the session.</span></span>

## <span data-ttu-id="016fe-135">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="016fe-135">PARAMETERS</span></span>

### <span data-ttu-id="016fe-136">-Definition</span><span class="sxs-lookup"><span data-stu-id="016fe-136">-Definition</span></span>

<span data-ttu-id="016fe-137">Получает псевдонимы для заданного элемента.</span><span class="sxs-lookup"><span data-stu-id="016fe-137">Gets the aliases for the specified item.</span></span>
<span data-ttu-id="016fe-138">Введите имя командлета, функции, скрипта, файла или исполняемого файла.</span><span class="sxs-lookup"><span data-stu-id="016fe-138">Enter the name of a cmdlet, function, script, file, or executable file.</span></span>

<span data-ttu-id="016fe-139">Этот параметр называется *определением* , так как он ищет имя элемента в свойстве Definition объекта псевдонима.</span><span class="sxs-lookup"><span data-stu-id="016fe-139">This parameter is called *Definition* , because it searches for the item name in the Definition property of the alias object.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Definition
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="016fe-140">-Exclude</span><span class="sxs-lookup"><span data-stu-id="016fe-140">-Exclude</span></span>

<span data-ttu-id="016fe-141">Исключает указанные элементы.</span><span class="sxs-lookup"><span data-stu-id="016fe-141">Omits the specified items.</span></span>
<span data-ttu-id="016fe-142">Значение этого параметра определяет значение параметров Name и Definition.</span><span class="sxs-lookup"><span data-stu-id="016fe-142">The value of this parameter qualifies the Name and Definition parameters.</span></span>
<span data-ttu-id="016fe-143">Введите имя, определение или шаблон, например, "s \*".</span><span class="sxs-lookup"><span data-stu-id="016fe-143">Enter a name, a definition, or a pattern, such as "s\*".</span></span>
<span data-ttu-id="016fe-144">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="016fe-144">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="016fe-145">-Name</span><span class="sxs-lookup"><span data-stu-id="016fe-145">-Name</span></span>

<span data-ttu-id="016fe-146">Задает получаемые этим командлетом псевдонимы.</span><span class="sxs-lookup"><span data-stu-id="016fe-146">Specifies the aliases that this cmdlet gets.</span></span>
<span data-ttu-id="016fe-147">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="016fe-147">Wildcards are permitted.</span></span>
<span data-ttu-id="016fe-148">По умолчанию `Get-Alias` получает все псевдонимы, определенные для текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="016fe-148">By default, `Get-Alias` retrieves all aliases defined for the current session.</span></span>
<span data-ttu-id="016fe-149">**Имя параметра является** необязательным.</span><span class="sxs-lookup"><span data-stu-id="016fe-149">The parameter name **Name** is optional.</span></span>
<span data-ttu-id="016fe-150">Имена псевдонимов можно также передавать в `Get-Alias` .</span><span class="sxs-lookup"><span data-stu-id="016fe-150">You can also pipe alias names to `Get-Alias`.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Default
Aliases:

Required: False
Position: 0
Default value: All aliases
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="016fe-151">-Scope</span><span class="sxs-lookup"><span data-stu-id="016fe-151">-Scope</span></span>

<span data-ttu-id="016fe-152">Задает область, псевдонимы для которой получает этот командлет.</span><span class="sxs-lookup"><span data-stu-id="016fe-152">Specifies the scope for which this cmdlet gets aliases.</span></span>
<span data-ttu-id="016fe-153">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="016fe-153">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="016fe-154">Глобальный</span><span class="sxs-lookup"><span data-stu-id="016fe-154">Global</span></span>
- <span data-ttu-id="016fe-155">Локальная</span><span class="sxs-lookup"><span data-stu-id="016fe-155">Local</span></span>
- <span data-ttu-id="016fe-156">Сценарий</span><span class="sxs-lookup"><span data-stu-id="016fe-156">Script</span></span>
- <span data-ttu-id="016fe-157">Номер относительно текущей области (от 0 до количества областей, где 0 — это текущая область, а 1 — ее родительская область).</span><span class="sxs-lookup"><span data-stu-id="016fe-157">A number relative to the current scope (0 through the number of scopes, where 0 is the current scope and 1 is its parent)</span></span>

<span data-ttu-id="016fe-158">По умолчанию используется значение Local.</span><span class="sxs-lookup"><span data-stu-id="016fe-158">Local is the default.</span></span>
<span data-ttu-id="016fe-159">Дополнительные сведения см. в разделе about_Scopes.</span><span class="sxs-lookup"><span data-stu-id="016fe-159">For more information, see about_Scopes.</span></span>

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

### <span data-ttu-id="016fe-160">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="016fe-160">CommonParameters</span></span>

<span data-ttu-id="016fe-161">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="016fe-161">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="016fe-162">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="016fe-162">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="016fe-163">Входные данные</span><span class="sxs-lookup"><span data-stu-id="016fe-163">INPUTS</span></span>

### <span data-ttu-id="016fe-164">System.String</span><span class="sxs-lookup"><span data-stu-id="016fe-164">System.String</span></span>

<span data-ttu-id="016fe-165">Имена псевдонимов можно передавать в командлет **Get-Alias**.</span><span class="sxs-lookup"><span data-stu-id="016fe-165">You can pipe alias names to **Get-Alias**.</span></span>

## <span data-ttu-id="016fe-166">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="016fe-166">OUTPUTS</span></span>

### <span data-ttu-id="016fe-167">System.Management.Automation.AliasInfo</span><span class="sxs-lookup"><span data-stu-id="016fe-167">System.Management.Automation.AliasInfo</span></span>

<span data-ttu-id="016fe-168">Командлет **Get-Alias** возвращает объект, представляющий каждый псевдоним.</span><span class="sxs-lookup"><span data-stu-id="016fe-168">**Get-Alias** returns an object that represents each alias.</span></span>
<span data-ttu-id="016fe-169">Командлет **Get-Alias** возвращает один и тот же объект для каждого псевдонима, но PowerShell использует формат на основе стрелок для вывода имен псевдонимов, отличных от дефисов.</span><span class="sxs-lookup"><span data-stu-id="016fe-169">**Get-Alias** returns the same object for every alias, but PowerShell uses an arrow-based format to display the names of non-hyphenated aliases.</span></span>

## <span data-ttu-id="016fe-170">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="016fe-170">NOTES</span></span>

- <span data-ttu-id="016fe-171">Для создания нового псевдонима используйте командлет Set-Alias или New-Alias.</span><span class="sxs-lookup"><span data-stu-id="016fe-171">To create a new alias, use Set-Alias or New-Alias.</span></span> <span data-ttu-id="016fe-172">Для удаления псевдонима используйте командлет Remove-Item.</span><span class="sxs-lookup"><span data-stu-id="016fe-172">To delete an alias, use Remove-Item.</span></span>
- <span data-ttu-id="016fe-173">Формат имени псевдонима со стрелками не используется для псевдонимов, содержащих дефис.</span><span class="sxs-lookup"><span data-stu-id="016fe-173">The arrow-based alias name format is not used for aliases that include a hyphen.</span></span> <span data-ttu-id="016fe-174">Для замены названий командлетов и функций такие псевдонимы более предпочтительны, чем обычные псевдонимы и сокращения.</span><span class="sxs-lookup"><span data-stu-id="016fe-174">These are likely to be preferred substitute names for cmdlets and functions, instead of typical abbreviations or nicknames.</span></span>

## <span data-ttu-id="016fe-175">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="016fe-175">RELATED LINKS</span></span>

[<span data-ttu-id="016fe-176">Export-Alias</span><span class="sxs-lookup"><span data-stu-id="016fe-176">Export-Alias</span></span>](Export-Alias.md)

[<span data-ttu-id="016fe-177">Import-Alias</span><span class="sxs-lookup"><span data-stu-id="016fe-177">Import-Alias</span></span>](Import-Alias.md)

[<span data-ttu-id="016fe-178">New-Alias</span><span class="sxs-lookup"><span data-stu-id="016fe-178">New-Alias</span></span>](New-Alias.md)

[<span data-ttu-id="016fe-179">Set-Alias</span><span class="sxs-lookup"><span data-stu-id="016fe-179">Set-Alias</span></span>](Set-Alias.md)

[<span data-ttu-id="016fe-180">Alias Provider</span><span class="sxs-lookup"><span data-stu-id="016fe-180">Alias Provider</span></span>](../Microsoft.PowerShell.Core/About/about_Alias_Provider.md)

[<span data-ttu-id="016fe-181">about_Aliases</span><span class="sxs-lookup"><span data-stu-id="016fe-181">about_Aliases</span></span>](../Microsoft.PowerShell.Core/About/about_Aliases.md)

