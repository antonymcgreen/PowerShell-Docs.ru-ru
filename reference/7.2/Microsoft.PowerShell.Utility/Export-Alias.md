---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/export-alias?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-Alias
ms.openlocfilehash: 9da204513ed4a17eb8dc20481b878a4a783534f6
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601881"
---
# <span data-ttu-id="b3357-102">Export-Alias</span><span class="sxs-lookup"><span data-stu-id="b3357-102">Export-Alias</span></span>

## <span data-ttu-id="b3357-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="b3357-103">SYNOPSIS</span></span>
<span data-ttu-id="b3357-104">Экспортирует сведения об определенных на текущий момент псевдонимах в файл.</span><span class="sxs-lookup"><span data-stu-id="b3357-104">Exports information about currently defined aliases to a file.</span></span>

## <span data-ttu-id="b3357-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b3357-105">SYNTAX</span></span>

### <span data-ttu-id="b3357-106">ByPath (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="b3357-106">ByPath (Default)</span></span>

```
Export-Alias [-Path] <String> [[-Name] <String[]>] [-PassThru] [-As <ExportAliasFormat>] [-Append] [-Force]
 [-NoClobber] [-Description <String>] [-Scope <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="b3357-107">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="b3357-107">ByLiteralPath</span></span>

```
Export-Alias -LiteralPath <String> [[-Name] <String[]>] [-PassThru] [-As <ExportAliasFormat>] [-Append]
 [-Force] [-NoClobber] [-Description <String>] [-Scope <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="b3357-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b3357-108">DESCRIPTION</span></span>

<span data-ttu-id="b3357-109">`Export-Alias`Командлет экспортирует псевдонимы в текущем сеансе в файл.</span><span class="sxs-lookup"><span data-stu-id="b3357-109">The `Export-Alias` cmdlet exports the aliases in the current session to a file.</span></span>
<span data-ttu-id="b3357-110">Если файл вывода не существует, командлет его создаст.</span><span class="sxs-lookup"><span data-stu-id="b3357-110">If the output file does not exist, the cmdlet will create it.</span></span>

<span data-ttu-id="b3357-111">`Export-Alias` может экспортировать псевдонимы в определенной области или во всех областях, они могут создавать данные в формате CSV или в виде серии Set-Alias команд, которые можно добавить в сеанс или в профиль PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b3357-111">`Export-Alias` can export the aliases in a particular scope or all scopes, it can generate the data in CSV format or as a series of Set-Alias commands that you can add to a session or to a PowerShell profile.</span></span>

## <span data-ttu-id="b3357-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="b3357-112">EXAMPLES</span></span>

### <span data-ttu-id="b3357-113">Пример 1. экспорт псевдонима</span><span class="sxs-lookup"><span data-stu-id="b3357-113">Example 1: Export an alias</span></span>

```powershell
Export-Alias -Path "alias.csv"
```

<span data-ttu-id="b3357-114">Эта команда экспортирует текущие сведения о псевдонимах в файл Alias.csv, находящийся в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="b3357-114">This command exports current alias information to a file named Alias.csv in the current directory.</span></span>

### <span data-ttu-id="b3357-115">Пример 2. экспорт псевдонима, если файл экспорта уже не существует</span><span class="sxs-lookup"><span data-stu-id="b3357-115">Example 2: Export an alias unless the export file already exists</span></span>

```powershell
Export-Alias -Path "alias.csv" -NoClobber
```

<span data-ttu-id="b3357-116">Эта команда экспортирует псевдонимы текущего сеанса в файл Alias.csv.</span><span class="sxs-lookup"><span data-stu-id="b3357-116">This command exports the aliases in the current session to an Alias.csv file.</span></span>

<span data-ttu-id="b3357-117">Так как указан параметр **NoClobber** , команда завершится ошибкой, если файл Alias.csv уже существует в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="b3357-117">Because the **NoClobber** parameter is specified, the command will fail if an Alias.csv file already exists in the current directory.</span></span>

### <span data-ttu-id="b3357-118">Пример 3. Добавление псевдонимов в файл</span><span class="sxs-lookup"><span data-stu-id="b3357-118">Example 3: Append aliases to a file</span></span>

```powershell
Export-Alias -Path "alias.csv" -Append -Description "Appended Aliases" -Force
```

<span data-ttu-id="b3357-119">Эта команда добавляет псевдонимы текущего сеанса в файл Alias.csv.</span><span class="sxs-lookup"><span data-stu-id="b3357-119">This command appends the aliases in the current session to the Alias.csv file.</span></span>

<span data-ttu-id="b3357-120">Команда использует параметр **Description** для добавления описания к комментариям в верхней части файла.</span><span class="sxs-lookup"><span data-stu-id="b3357-120">The command uses the **Description** parameter to add a description to the comments at the top of the file.</span></span>

<span data-ttu-id="b3357-121">Команда также использует параметр **Force** для перезаписи существующих файлов Alias.csv, даже если они имеют атрибут «только для чтения».</span><span class="sxs-lookup"><span data-stu-id="b3357-121">The command also uses the **Force** parameter to overwrite any existing Alias.csv files, even if they have the read-only attribute.</span></span>

### <span data-ttu-id="b3357-122">Пример 4. экспорт псевдонимов в качестве скрипта</span><span class="sxs-lookup"><span data-stu-id="b3357-122">Example 4: Export aliases as a script</span></span>

```powershell
Export-Alias -Path "alias.ps1" -As Script
Add-Content -Path $Profile -Value (Get-Content alias.ps1)
$S = New-PSSession -ComputerName Server01
Invoke-Command -Session $S -FilePath .\alias.ps1
```

<span data-ttu-id="b3357-123">В этом примере показано, как использовать формат файла скрипта, который `Export-Alias` создает.</span><span class="sxs-lookup"><span data-stu-id="b3357-123">This example shows how to use the script file format that `Export-Alias` generates.</span></span>

<span data-ttu-id="b3357-124">Первая команда экспортирует псевдонимы текущего сеанса в файл Alias.ps1.</span><span class="sxs-lookup"><span data-stu-id="b3357-124">The first command exports the aliases in the session to the Alias.ps1 file.</span></span>
<span data-ttu-id="b3357-125">Для создания файла, содержащего команду Set-Alias для каждого псевдонима, используется параметр **as** со значением скрипта.</span><span class="sxs-lookup"><span data-stu-id="b3357-125">It uses the **As** parameter with a value of Script to generate a file that contains a Set-Alias command for each alias.</span></span>

<span data-ttu-id="b3357-126">Вторая команда добавляет псевдонимы из файла Alias.ps1 к профилю CurrentUser-CurrentHost.</span><span class="sxs-lookup"><span data-stu-id="b3357-126">The second command adds the aliases in the Alias.ps1 file to the CurrentUser-CurrentHost profile.</span></span>
<span data-ttu-id="b3357-127">Путь к профилю сохраняется в `$Profile` переменной.</span><span class="sxs-lookup"><span data-stu-id="b3357-127">The path to the profile is saved in the `$Profile` variable.</span></span>
<span data-ttu-id="b3357-128">Команда использует `Get-Content` командлет для получения псевдонимов из файла Alias.ps1 и `Add-Content` командлета, чтобы добавить их в профиль.</span><span class="sxs-lookup"><span data-stu-id="b3357-128">The command uses the `Get-Content` cmdlet to get the aliases from the Alias.ps1 file and the `Add-Content` cmdlet to add them to the profile.</span></span>
<span data-ttu-id="b3357-129">Дополнительные сведения см. в разделе about_Profiles.</span><span class="sxs-lookup"><span data-stu-id="b3357-129">For more information, see about_Profiles.</span></span>

<span data-ttu-id="b3357-130">Третья и четвертая команды добавляют псевдонимы в файл Alias.ps1 в удаленный сеанс на компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="b3357-130">The third and fourth commands add the aliases in the Alias.ps1 file to a remote session on the Server01 computer.</span></span>
<span data-ttu-id="b3357-131">Третья команда использует `New-PSSession` командлет для создания сеанса.</span><span class="sxs-lookup"><span data-stu-id="b3357-131">The third command uses the `New-PSSession` cmdlet to create the session.</span></span>
<span data-ttu-id="b3357-132">Четвертая команда использует параметр **FilePath** `Invoke-Command` командлета для запуска файла Alias.ps1 в новом сеансе.</span><span class="sxs-lookup"><span data-stu-id="b3357-132">The fourth command uses the **FilePath** parameter of the `Invoke-Command` cmdlet to run the Alias.ps1 file in the new session.</span></span>

## <span data-ttu-id="b3357-133">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b3357-133">PARAMETERS</span></span>

### <span data-ttu-id="b3357-134">— Добавление</span><span class="sxs-lookup"><span data-stu-id="b3357-134">-Append</span></span>

<span data-ttu-id="b3357-135">Указывает, что этот командлет добавляет выходные данные в указанный файл вместо перезаписи существующего содержимого этого файла.</span><span class="sxs-lookup"><span data-stu-id="b3357-135">Indicates that this cmdlet appends the output to the specified file, rather than overwriting the existing contents of that file.</span></span>

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

### <span data-ttu-id="b3357-136">— Как</span><span class="sxs-lookup"><span data-stu-id="b3357-136">-As</span></span>

<span data-ttu-id="b3357-137">Задает формат выходных данных.</span><span class="sxs-lookup"><span data-stu-id="b3357-137">Specifies the output format.</span></span>
<span data-ttu-id="b3357-138">По умолчанию используется формат CSV.</span><span class="sxs-lookup"><span data-stu-id="b3357-138">CSV is the default.</span></span>
<span data-ttu-id="b3357-139">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="b3357-139">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="b3357-140">CSV.</span><span class="sxs-lookup"><span data-stu-id="b3357-140">CSV.</span></span>
<span data-ttu-id="b3357-141">формат значений, разделенных запятыми (CSV).</span><span class="sxs-lookup"><span data-stu-id="b3357-141">Comma-separated value (CSV) format.</span></span>
- <span data-ttu-id="b3357-142">Скрипт.</span><span class="sxs-lookup"><span data-stu-id="b3357-142">Script.</span></span>
<span data-ttu-id="b3357-143">Создает `Set-Alias` команду для каждого экспортированного псевдонима.</span><span class="sxs-lookup"><span data-stu-id="b3357-143">Creates a `Set-Alias` command for each exported alias.</span></span>
<span data-ttu-id="b3357-144">Если выходной файл имеет расширение PS1, его можно запускать в качестве скрипта для добавления псевдонимов к любому сеансу.</span><span class="sxs-lookup"><span data-stu-id="b3357-144">If you name the output file with a .ps1 file name extension, you can run it as a script to add the aliases to any session.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.ExportAliasFormat
Parameter Sets: (All)
Aliases:
Accepted values: Csv, Script

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b3357-145">-Description</span><span class="sxs-lookup"><span data-stu-id="b3357-145">-Description</span></span>

<span data-ttu-id="b3357-146">Задает описание экспортируемого файла.</span><span class="sxs-lookup"><span data-stu-id="b3357-146">Specifies the description of the exported file.</span></span>
<span data-ttu-id="b3357-147">Описание добавляется в виде комментария в начало файла после заголовка.</span><span class="sxs-lookup"><span data-stu-id="b3357-147">The description appears as a comment at the top of the file, following the header information.</span></span>

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

### <span data-ttu-id="b3357-148">-Force</span><span class="sxs-lookup"><span data-stu-id="b3357-148">-Force</span></span>

<span data-ttu-id="b3357-149">Принудительное выполнение команды без запроса на подтверждение пользователем.</span><span class="sxs-lookup"><span data-stu-id="b3357-149">Forces the command to run without asking for user confirmation.</span></span>

<span data-ttu-id="b3357-150">Перезаписывает выходной файл, даже если для него установлен атрибут «только для чтения».</span><span class="sxs-lookup"><span data-stu-id="b3357-150">Overwrites the output file, even if the read-only attribute is set on the file.</span></span>

<span data-ttu-id="b3357-151">По умолчанию `Export-Alias` перезаписывает файлы без предупреждения, если только атрибут "только для чтения" или "скрытый" не задан, либо в команде используется параметр **NoClobber** .</span><span class="sxs-lookup"><span data-stu-id="b3357-151">By default, `Export-Alias` overwrites files without warning, unless the read-only or hidden attribute is set or the **NoClobber** parameter is used in the command.</span></span>
<span data-ttu-id="b3357-152">Параметр **NoClobber** имеет приоритет над параметром **Force** , если оба используются в команде.</span><span class="sxs-lookup"><span data-stu-id="b3357-152">The **NoClobber** parameter takes precedence over the **Force** parameter when both are used in a command.</span></span>

<span data-ttu-id="b3357-153">Параметр **Force** не может принудительно `Export-Alias` перезаписать файлы с атрибутом Hidden.</span><span class="sxs-lookup"><span data-stu-id="b3357-153">The **Force** parameter cannot force `Export-Alias` to overwrite files with the hidden attribute.</span></span>

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

### <span data-ttu-id="b3357-154">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="b3357-154">-LiteralPath</span></span>

<span data-ttu-id="b3357-155">Указывает путь к выходному файлу.</span><span class="sxs-lookup"><span data-stu-id="b3357-155">Specifies the path to the output file.</span></span>
<span data-ttu-id="b3357-156">В отличие от параметра **Path**, значение параметра **LiteralPath** используется в точности так, как вводится.</span><span class="sxs-lookup"><span data-stu-id="b3357-156">Unlike **Path**, the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span>
<span data-ttu-id="b3357-157">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="b3357-157">No characters are interpreted as wildcards.</span></span>
<span data-ttu-id="b3357-158">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="b3357-158">If the path includes escape characters, enclose it in single quotation marks.</span></span>
<span data-ttu-id="b3357-159">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="b3357-159">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: ByLiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b3357-160">-Name</span><span class="sxs-lookup"><span data-stu-id="b3357-160">-Name</span></span>

<span data-ttu-id="b3357-161">Задает имена в виде массива псевдонимов для экспорта.</span><span class="sxs-lookup"><span data-stu-id="b3357-161">Specifies the names as an array of the aliases to export.</span></span>
<span data-ttu-id="b3357-162">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="b3357-162">Wildcards are permitted.</span></span>

<span data-ttu-id="b3357-163">По умолчанию `Export-Alias` экспортирует все псевдонимы в сеансе или области.</span><span class="sxs-lookup"><span data-stu-id="b3357-163">By default, `Export-Alias` exports all aliases in the session or scope.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="b3357-164">-NoClobber</span><span class="sxs-lookup"><span data-stu-id="b3357-164">-NoClobber</span></span>

<span data-ttu-id="b3357-165">Указывает, что этот командлет не позволяет `Export-Alias` перезаписывать какие-либо файлы, даже если в команде используется параметр **Force** .</span><span class="sxs-lookup"><span data-stu-id="b3357-165">Indicates that this cmdlet prevents `Export-Alias` from overwriting any files, even if the **Force** parameter is used in the command.</span></span>

<span data-ttu-id="b3357-166">Если параметр **NoClobber** опущен, `Export-Alias` будет перезаписан существующий файл без предупреждения, если только для этого файла не задан атрибут «только для чтения».</span><span class="sxs-lookup"><span data-stu-id="b3357-166">If the **NoClobber** parameter is omitted, `Export-Alias` will overwrite an existing file without warning, unless the read-only attribute is set on the file.</span></span>
<span data-ttu-id="b3357-167">*NoClobber* имеет приоритет над параметром **Force** , который позволяет `Export-Alias` перезаписывать файл с атрибутом только для чтения.</span><span class="sxs-lookup"><span data-stu-id="b3357-167">*NoClobber* takes precedence over the **Force** parameter, which permits `Export-Alias` to overwrite a file with the read-only attribute.</span></span>

<span data-ttu-id="b3357-168">*NoClobber* не запрещает параметру **append** добавлять содержимое в существующий файл.</span><span class="sxs-lookup"><span data-stu-id="b3357-168">*NoClobber* does not prevent the **Append** parameter from adding content to an existing file.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: NoOverwrite

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b3357-169">-PassThru</span><span class="sxs-lookup"><span data-stu-id="b3357-169">-PassThru</span></span>

<span data-ttu-id="b3357-170">Возвращает объект, представляющий элемент, с которым вы работаете.</span><span class="sxs-lookup"><span data-stu-id="b3357-170">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="b3357-171">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="b3357-171">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="b3357-172">-Path</span><span class="sxs-lookup"><span data-stu-id="b3357-172">-Path</span></span>

<span data-ttu-id="b3357-173">Указывает путь к выходному файлу.</span><span class="sxs-lookup"><span data-stu-id="b3357-173">Specifies the path to the output file.</span></span>
<span data-ttu-id="b3357-174">Знаки подстановки использовать можно, но итоговое значение пути должно указывать только на одно имя файла.</span><span class="sxs-lookup"><span data-stu-id="b3357-174">Wildcards are permitted, but the resulting path value must resolve to a single file name.</span></span>

```yaml
Type: System.String
Parameter Sets: ByPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="b3357-175">-Scope</span><span class="sxs-lookup"><span data-stu-id="b3357-175">-Scope</span></span>

<span data-ttu-id="b3357-176">Задает область, из которой должны быть экспортированы псевдонимы.</span><span class="sxs-lookup"><span data-stu-id="b3357-176">Specifies the scope from which the aliases should be exported.</span></span>
<span data-ttu-id="b3357-177">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="b3357-177">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="b3357-178">Глобальный</span><span class="sxs-lookup"><span data-stu-id="b3357-178">Global</span></span>
- <span data-ttu-id="b3357-179">Локальная</span><span class="sxs-lookup"><span data-stu-id="b3357-179">Local</span></span>
- <span data-ttu-id="b3357-180">Скрипт</span><span class="sxs-lookup"><span data-stu-id="b3357-180">Script</span></span>
- <span data-ttu-id="b3357-181">Число относительно текущей области (от 0 до количества областей, где 0 является текущей областью, а 1 — ее родителем)</span><span class="sxs-lookup"><span data-stu-id="b3357-181">A number relative to the current scope (0 through the number of scopes where 0 is the current scope and 1 is its parent)</span></span>

<span data-ttu-id="b3357-182">По умолчанию используется значение Local.</span><span class="sxs-lookup"><span data-stu-id="b3357-182">The default value is Local.</span></span>
<span data-ttu-id="b3357-183">Дополнительные сведения см. в разделе about_Scopes.</span><span class="sxs-lookup"><span data-stu-id="b3357-183">For more information, see about_Scopes.</span></span>

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

### <span data-ttu-id="b3357-184">-Confirm</span><span class="sxs-lookup"><span data-stu-id="b3357-184">-Confirm</span></span>

<span data-ttu-id="b3357-185">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="b3357-185">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="b3357-186">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="b3357-186">-WhatIf</span></span>

<span data-ttu-id="b3357-187">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="b3357-187">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="b3357-188">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="b3357-188">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="b3357-189">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="b3357-189">CommonParameters</span></span>

<span data-ttu-id="b3357-190">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b3357-190">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b3357-191">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="b3357-191">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b3357-192">Входные данные</span><span class="sxs-lookup"><span data-stu-id="b3357-192">INPUTS</span></span>

### <span data-ttu-id="b3357-193">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="b3357-193">None.</span></span>

<span data-ttu-id="b3357-194">Нельзя передать объекты в этот командлет с помощью конвейера.</span><span class="sxs-lookup"><span data-stu-id="b3357-194">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="b3357-195">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="b3357-195">OUTPUTS</span></span>

### <span data-ttu-id="b3357-196">None или System. Management. Automation. AliasInfo</span><span class="sxs-lookup"><span data-stu-id="b3357-196">None or System.Management.Automation.AliasInfo</span></span>

<span data-ttu-id="b3357-197">При использовании параметра **PassThru** `Export-Alias` возвращает объект **System. Management. Automation. AliasInfo** , представляющий псевдоним.</span><span class="sxs-lookup"><span data-stu-id="b3357-197">When you use the **Passthru** parameter, `Export-Alias` returns a **System.Management.Automation.AliasInfo** object that represents the alias.</span></span>
<span data-ttu-id="b3357-198">В противном случае командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="b3357-198">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="b3357-199">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="b3357-199">NOTES</span></span>

* <span data-ttu-id="b3357-200">Командлет Export-Alias можно применять только для экспорта в файл.</span><span class="sxs-lookup"><span data-stu-id="b3357-200">You can only Export-Aliases to a file.</span></span>

## <span data-ttu-id="b3357-201">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="b3357-201">RELATED LINKS</span></span>

[<span data-ttu-id="b3357-202">Get-Alias</span><span class="sxs-lookup"><span data-stu-id="b3357-202">Get-Alias</span></span>](Get-Alias.md)

[<span data-ttu-id="b3357-203">Import-Alias</span><span class="sxs-lookup"><span data-stu-id="b3357-203">Import-Alias</span></span>](Import-Alias.md)

[<span data-ttu-id="b3357-204">New-Alias</span><span class="sxs-lookup"><span data-stu-id="b3357-204">New-Alias</span></span>](New-Alias.md)

[<span data-ttu-id="b3357-205">Set-Alias</span><span class="sxs-lookup"><span data-stu-id="b3357-205">Set-Alias</span></span>](Set-Alias.md)

