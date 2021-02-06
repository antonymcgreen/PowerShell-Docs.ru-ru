---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-alias?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Alias
ms.openlocfilehash: 7b6f639d1c5685e341260c056a1dd0a17fe9f46d
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599622"
---
# <span data-ttu-id="30094-102">Get-Alias</span><span class="sxs-lookup"><span data-stu-id="30094-102">Get-Alias</span></span>

## <span data-ttu-id="30094-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="30094-103">SYNOPSIS</span></span>
<span data-ttu-id="30094-104">Получает псевдонимы, действительные в ходе текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="30094-104">Gets the aliases for the current session.</span></span>

## <span data-ttu-id="30094-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="30094-105">SYNTAX</span></span>

### <span data-ttu-id="30094-106">Default (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="30094-106">Default (Default)</span></span>

```
Get-Alias [[-Name] <String[]>] [-Exclude <String[]>] [-Scope <String>] [<CommonParameters>]
```

### <span data-ttu-id="30094-107">Определение</span><span class="sxs-lookup"><span data-stu-id="30094-107">Definition</span></span>

```
Get-Alias [-Exclude <String[]>] [-Scope <String>] [-Definition <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="30094-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="30094-108">DESCRIPTION</span></span>

<span data-ttu-id="30094-109">Командлет **Get-Alias** получает псевдонимы в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="30094-109">The **Get-Alias** cmdlet gets the aliases in the current session.</span></span>
<span data-ttu-id="30094-110">Сюда входят встроенные псевдонимы, псевдонимы, которые вы установили или импортировали, и псевдонимы, добавленные в профиль PowerShell.</span><span class="sxs-lookup"><span data-stu-id="30094-110">This includes built-in aliases, aliases that you have set or imported, and aliases that you have added to your PowerShell profile.</span></span>

<span data-ttu-id="30094-111">По умолчанию командлет **Get-Alias** принимает псевдоним и возвращает имя команды.</span><span class="sxs-lookup"><span data-stu-id="30094-111">By default, **Get-Alias** takes an alias and returns the command name.</span></span>
<span data-ttu-id="30094-112">При использовании параметра *определения* командлет **Get-Alias** принимает имя команды и возвращает его псевдонимы.</span><span class="sxs-lookup"><span data-stu-id="30094-112">When you use the *Definition* parameter, **Get-Alias** takes a command name and returns its aliases.</span></span>

<span data-ttu-id="30094-113">Начиная с Windows PowerShell 3,0, **Get-Alias** отображает имена псевдонимов без дефисов в `<alias> -> <definition>` формате, чтобы упростить поиск нужных сведений.</span><span class="sxs-lookup"><span data-stu-id="30094-113">Beginning in Windows PowerShell 3.0, **Get-Alias** displays non-hyphenated alias names in an `<alias> -> <definition>` format to make it even easier to find the information that you need.</span></span>

## <span data-ttu-id="30094-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="30094-114">EXAMPLES</span></span>

### <span data-ttu-id="30094-115">Пример 1. Получение всех псевдонимов в текущем сеансе</span><span class="sxs-lookup"><span data-stu-id="30094-115">Example 1: Get all aliases in the current session</span></span>

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

<span data-ttu-id="30094-116">Эта команда получает все псевдонимы в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="30094-116">This command gets all aliases in the current session.</span></span>

<span data-ttu-id="30094-117">В выходных данных показан `<alias> -> <definition>` Формат, представленный в Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="30094-117">The output shows the `<alias> -> <definition>` format that was introduced in Windows PowerShell 3.0.</span></span>
<span data-ttu-id="30094-118">Этот формат используется только для псевдонимов, не содержащих дефисы, поскольку вместо названий командлетов и функций предпочтительнее использовать псевдонимы с дефисами.</span><span class="sxs-lookup"><span data-stu-id="30094-118">This format is used only for aliases that do not include hyphens, because aliases with hyphens are typically preferred names for cmdlets and functions, rather than nicknames.</span></span>

### <span data-ttu-id="30094-119">Пример 2. Получение псевдонимов по имени</span><span class="sxs-lookup"><span data-stu-id="30094-119">Example 2: Get aliases by name</span></span>

```powershell
Get-Alias -Name gp*, sp* -Exclude *ps
```

<span data-ttu-id="30094-120">Эта команда возвращает все псевдонимы, которые начинаются с GP или SP, за исключением псевдонимов, которые заканчиваются на PS.</span><span class="sxs-lookup"><span data-stu-id="30094-120">This command gets all aliases that begin with gp or sp, except for aliases that end with ps.</span></span>

### <span data-ttu-id="30094-121">Пример 3. Получение псевдонимов для командлета</span><span class="sxs-lookup"><span data-stu-id="30094-121">Example 3: Get aliases for a cmdlet</span></span>

```powershell
Get-Alias -Definition Get-ChildItem
```

<span data-ttu-id="30094-122">Эта команда получает псевдонимы для командлета Get-ChildItem.</span><span class="sxs-lookup"><span data-stu-id="30094-122">This command gets the aliases for the Get-ChildItem cmdlet.</span></span>

<span data-ttu-id="30094-123">По умолчанию командлет **Get-Alias** получает имя элемента, если известно его псевдоним.</span><span class="sxs-lookup"><span data-stu-id="30094-123">By default, the **Get-Alias** cmdlet gets the item name when you know the alias.</span></span>
<span data-ttu-id="30094-124">Параметр *определения* получает псевдоним, если известно имя элемента.</span><span class="sxs-lookup"><span data-stu-id="30094-124">The *Definition* parameter gets the alias when you know the item name.</span></span>

### <span data-ttu-id="30094-125">Пример 4. Получение псевдонимов по свойству</span><span class="sxs-lookup"><span data-stu-id="30094-125">Example 4: Get aliases by property</span></span>

```powershell
Get-Alias | Where-Object {$_.Options -Match "ReadOnly"}
```

<span data-ttu-id="30094-126">Эта команда получает все псевдонимы, в которых свойство Options имеет значение ReadOnly.</span><span class="sxs-lookup"><span data-stu-id="30094-126">This command gets all aliases in which the value of the Options property is ReadOnly.</span></span>
<span data-ttu-id="30094-127">Эта команда позволяет быстро найти псевдонимы, встроенные в PowerShell, так как они имеют параметр ReadOnly.</span><span class="sxs-lookup"><span data-stu-id="30094-127">This command provides a quick way to find the aliases that are built into PowerShell, because they have the ReadOnly option.</span></span>

<span data-ttu-id="30094-128">Параметры — это только одно свойство объектов AliasInfo, которое получает **Get-Alias** .</span><span class="sxs-lookup"><span data-stu-id="30094-128">Options is just one property of the AliasInfo objects that **Get-Alias** gets.</span></span>
<span data-ttu-id="30094-129">Чтобы найти все свойства и методы объектов AliasInfo, введите команду `Get-Alias | get-member`.</span><span class="sxs-lookup"><span data-stu-id="30094-129">To find all properties and methods of AliasInfo objects, type `Get-Alias | get-member`.</span></span>

### <span data-ttu-id="30094-130">Пример 5. Получение псевдонимов по имени и фильтрование по первой букве</span><span class="sxs-lookup"><span data-stu-id="30094-130">Example 5: Get aliases by name and filter by beginning letter</span></span>

```powershell
Get-Alias -Definition "*-PSSession" -Exclude e* -Scope Global
```

<span data-ttu-id="30094-131">Этот пример получает псевдонимы команд, имена которых заканчиваются на "-PSSession", кроме команд, начинающихся на букву "e".</span><span class="sxs-lookup"><span data-stu-id="30094-131">This example gets aliases for commands that have names that end in "-PSSession", except for those that begin with "e".</span></span>

<span data-ttu-id="30094-132">Команда использует параметр *Scope* для применения команды в глобальной области.</span><span class="sxs-lookup"><span data-stu-id="30094-132">The command uses the *Scope* parameter to apply the command in the global scope.</span></span>
<span data-ttu-id="30094-133">Эта функция пригодится в скриптах, где необходимо получить псевдонимы, действительные в сеансе.</span><span class="sxs-lookup"><span data-stu-id="30094-133">This is useful in scripts when you want to get the aliases in the session.</span></span>

## <span data-ttu-id="30094-134">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="30094-134">PARAMETERS</span></span>

### <span data-ttu-id="30094-135">-Definition</span><span class="sxs-lookup"><span data-stu-id="30094-135">-Definition</span></span>

<span data-ttu-id="30094-136">Получает псевдонимы для заданного элемента.</span><span class="sxs-lookup"><span data-stu-id="30094-136">Gets the aliases for the specified item.</span></span>
<span data-ttu-id="30094-137">Введите имя командлета, функции, скрипта, файла или исполняемого файла.</span><span class="sxs-lookup"><span data-stu-id="30094-137">Enter the name of a cmdlet, function, script, file, or executable file.</span></span>

<span data-ttu-id="30094-138">Этот параметр называется *определением*, так как он ищет имя элемента в свойстве Definition объекта псевдонима.</span><span class="sxs-lookup"><span data-stu-id="30094-138">This parameter is called *Definition*, because it searches for the item name in the Definition property of the alias object.</span></span>

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

### <span data-ttu-id="30094-139">-Exclude</span><span class="sxs-lookup"><span data-stu-id="30094-139">-Exclude</span></span>

<span data-ttu-id="30094-140">Исключает указанные элементы.</span><span class="sxs-lookup"><span data-stu-id="30094-140">Omits the specified items.</span></span>
<span data-ttu-id="30094-141">Значение этого параметра определяет значение параметров Name и Definition.</span><span class="sxs-lookup"><span data-stu-id="30094-141">The value of this parameter qualifies the Name and Definition parameters.</span></span>
<span data-ttu-id="30094-142">Введите имя, определение или шаблон, например, "s \*".</span><span class="sxs-lookup"><span data-stu-id="30094-142">Enter a name, a definition, or a pattern, such as "s\*".</span></span>
<span data-ttu-id="30094-143">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="30094-143">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="30094-144">-Name</span><span class="sxs-lookup"><span data-stu-id="30094-144">-Name</span></span>

<span data-ttu-id="30094-145">Задает получаемые этим командлетом псевдонимы.</span><span class="sxs-lookup"><span data-stu-id="30094-145">Specifies the aliases that this cmdlet gets.</span></span>
<span data-ttu-id="30094-146">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="30094-146">Wildcards are permitted.</span></span>
<span data-ttu-id="30094-147">По умолчанию `Get-Alias` получает все псевдонимы, определенные для текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="30094-147">By default, `Get-Alias` retrieves all aliases defined for the current session.</span></span>
<span data-ttu-id="30094-148">**Имя параметра является** необязательным.</span><span class="sxs-lookup"><span data-stu-id="30094-148">The parameter name **Name** is optional.</span></span>
<span data-ttu-id="30094-149">Имена псевдонимов можно также передавать в `Get-Alias` .</span><span class="sxs-lookup"><span data-stu-id="30094-149">You can also pipe alias names to `Get-Alias`.</span></span>

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

### <span data-ttu-id="30094-150">-Scope</span><span class="sxs-lookup"><span data-stu-id="30094-150">-Scope</span></span>

<span data-ttu-id="30094-151">Задает область, псевдонимы для которой получает этот командлет.</span><span class="sxs-lookup"><span data-stu-id="30094-151">Specifies the scope for which this cmdlet gets aliases.</span></span>
<span data-ttu-id="30094-152">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="30094-152">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="30094-153">Глобальный</span><span class="sxs-lookup"><span data-stu-id="30094-153">Global</span></span>
- <span data-ttu-id="30094-154">Локальная</span><span class="sxs-lookup"><span data-stu-id="30094-154">Local</span></span>
- <span data-ttu-id="30094-155">Скрипт</span><span class="sxs-lookup"><span data-stu-id="30094-155">Script</span></span>
- <span data-ttu-id="30094-156">Номер относительно текущей области (от 0 до количества областей, где 0 — это текущая область, а 1 — ее родительская область).</span><span class="sxs-lookup"><span data-stu-id="30094-156">A number relative to the current scope (0 through the number of scopes, where 0 is the current scope and 1 is its parent)</span></span>

<span data-ttu-id="30094-157">По умолчанию используется значение Local.</span><span class="sxs-lookup"><span data-stu-id="30094-157">Local is the default.</span></span>
<span data-ttu-id="30094-158">Дополнительные сведения см. в разделе about_Scopes.</span><span class="sxs-lookup"><span data-stu-id="30094-158">For more information, see about_Scopes.</span></span>

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

### <span data-ttu-id="30094-159">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="30094-159">CommonParameters</span></span>

<span data-ttu-id="30094-160">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="30094-160">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="30094-161">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="30094-161">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="30094-162">Входные данные</span><span class="sxs-lookup"><span data-stu-id="30094-162">INPUTS</span></span>

### <span data-ttu-id="30094-163">System.String</span><span class="sxs-lookup"><span data-stu-id="30094-163">System.String</span></span>

<span data-ttu-id="30094-164">Имена псевдонимов можно передавать в командлет **Get-Alias**.</span><span class="sxs-lookup"><span data-stu-id="30094-164">You can pipe alias names to **Get-Alias**.</span></span>

## <span data-ttu-id="30094-165">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="30094-165">OUTPUTS</span></span>

### <span data-ttu-id="30094-166">System.Management.Automation.AliasInfo</span><span class="sxs-lookup"><span data-stu-id="30094-166">System.Management.Automation.AliasInfo</span></span>

<span data-ttu-id="30094-167">Командлет **Get-Alias** возвращает объект, представляющий каждый псевдоним.</span><span class="sxs-lookup"><span data-stu-id="30094-167">**Get-Alias** returns an object that represents each alias.</span></span>
<span data-ttu-id="30094-168">Командлет **Get-Alias** возвращает один и тот же объект для каждого псевдонима, но PowerShell использует формат на основе стрелок для вывода имен псевдонимов, отличных от дефисов.</span><span class="sxs-lookup"><span data-stu-id="30094-168">**Get-Alias** returns the same object for every alias, but PowerShell uses an arrow-based format to display the names of non-hyphenated aliases.</span></span>

## <span data-ttu-id="30094-169">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="30094-169">NOTES</span></span>

- <span data-ttu-id="30094-170">Для создания нового псевдонима используйте командлет Set-Alias или New-Alias.</span><span class="sxs-lookup"><span data-stu-id="30094-170">To create a new alias, use Set-Alias or New-Alias.</span></span> <span data-ttu-id="30094-171">Для удаления псевдонима используйте командлет Remove-Item.</span><span class="sxs-lookup"><span data-stu-id="30094-171">To delete an alias, use Remove-Item.</span></span>
- <span data-ttu-id="30094-172">Формат имени псевдонима со стрелками не используется для псевдонимов, содержащих дефис.</span><span class="sxs-lookup"><span data-stu-id="30094-172">The arrow-based alias name format is not used for aliases that include a hyphen.</span></span> <span data-ttu-id="30094-173">Для замены названий командлетов и функций такие псевдонимы более предпочтительны, чем обычные псевдонимы и сокращения.</span><span class="sxs-lookup"><span data-stu-id="30094-173">These are likely to be preferred substitute names for cmdlets and functions, instead of typical abbreviations or nicknames.</span></span>

## <span data-ttu-id="30094-174">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="30094-174">RELATED LINKS</span></span>

[<span data-ttu-id="30094-175">Export-Alias</span><span class="sxs-lookup"><span data-stu-id="30094-175">Export-Alias</span></span>](Export-Alias.md)

[<span data-ttu-id="30094-176">Import-Alias</span><span class="sxs-lookup"><span data-stu-id="30094-176">Import-Alias</span></span>](Import-Alias.md)

[<span data-ttu-id="30094-177">New-Alias</span><span class="sxs-lookup"><span data-stu-id="30094-177">New-Alias</span></span>](New-Alias.md)

[<span data-ttu-id="30094-178">Set-Alias</span><span class="sxs-lookup"><span data-stu-id="30094-178">Set-Alias</span></span>](Set-Alias.md)

[<span data-ttu-id="30094-179">Alias Provider</span><span class="sxs-lookup"><span data-stu-id="30094-179">Alias Provider</span></span>](../Microsoft.PowerShell.Core/About/about_Alias_Provider.md)

[<span data-ttu-id="30094-180">about_Aliases</span><span class="sxs-lookup"><span data-stu-id="30094-180">about_Aliases</span></span>](../Microsoft.PowerShell.Core/About/about_Aliases.md)

