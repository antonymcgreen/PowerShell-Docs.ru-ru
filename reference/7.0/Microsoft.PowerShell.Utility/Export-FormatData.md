---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/export-formatdata?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-FormatData
ms.openlocfilehash: d89d80b296d8800d65c5acfae37434e9b3f3bce9
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93226186"
---
# <span data-ttu-id="29b43-103">Export-FormatData</span><span class="sxs-lookup"><span data-stu-id="29b43-103">Export-FormatData</span></span>

## <span data-ttu-id="29b43-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="29b43-104">SYNOPSIS</span></span>
<span data-ttu-id="29b43-105">Сохраняет данные форматирования текущего сеанса в файле форматирования.</span><span class="sxs-lookup"><span data-stu-id="29b43-105">Saves formatting data from the current session in a formatting file.</span></span>

## <span data-ttu-id="29b43-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="29b43-106">SYNTAX</span></span>

### <span data-ttu-id="29b43-107">ByPath (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="29b43-107">ByPath (Default)</span></span>

```
Export-FormatData -InputObject <ExtendedTypeDefinition[]> -Path <String> [-Force] [-NoClobber]
 [-IncludeScriptBlock] [<CommonParameters>]
```

### <span data-ttu-id="29b43-108">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="29b43-108">ByLiteralPath</span></span>

```
Export-FormatData -InputObject <ExtendedTypeDefinition[]> -LiteralPath <String> [-Force] [-NoClobber]
 [-IncludeScriptBlock] [<CommonParameters>]
```

## <span data-ttu-id="29b43-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="29b43-109">DESCRIPTION</span></span>

<span data-ttu-id="29b43-110">`Export-FormatData`Командлет создает файлы форматирования PowerShell (format.ps1XML) из объектов форматирования в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="29b43-110">The `Export-FormatData` cmdlet creates PowerShell formatting files (format.ps1xml) from the formatting objects in the current session.</span></span> <span data-ttu-id="29b43-111">Он принимает объекты **екстендедтипедефинитион** , которые `Get-FormatData` возвращают и сохраняет их в файле в формате XML.</span><span class="sxs-lookup"><span data-stu-id="29b43-111">It takes the **ExtendedTypeDefinition** objects that `Get-FormatData` returns and saves them in a file in XML format.</span></span>

<span data-ttu-id="29b43-112">PowerShell использует данные в файлах форматирования (format.ps1XML), чтобы создать отображение по умолчанию Microsoft .NET объектов платформы в сеансе.</span><span class="sxs-lookup"><span data-stu-id="29b43-112">PowerShell uses the data in formatting files (format.ps1xml) to generate the default display of Microsoft .NET Framework objects in the session.</span></span> <span data-ttu-id="29b43-113">Вы можете просматривать и изменять файлы форматирования и использовать командлет Update-FormatData для добавления данных форматирования в сеанс.</span><span class="sxs-lookup"><span data-stu-id="29b43-113">You can view and edit the formatting files and use the Update-FormatData cmdlet to add the formatting data to a session.</span></span>

<span data-ttu-id="29b43-114">Дополнительные сведения о файлах форматирования в PowerShell см. в разделе [about_Format.ps1XML](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md).</span><span class="sxs-lookup"><span data-stu-id="29b43-114">For more information about formatting files in PowerShell, see [about_Format.ps1xml](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md).</span></span>

## <span data-ttu-id="29b43-115">Примеры</span><span class="sxs-lookup"><span data-stu-id="29b43-115">EXAMPLES</span></span>

### <span data-ttu-id="29b43-116">Пример 1. экспорт данных в формате сеанса</span><span class="sxs-lookup"><span data-stu-id="29b43-116">Example 1: Export session format data</span></span>

```powershell
Get-FormatData -TypeName "*" -PowerShellVersion 5.1 | Export-FormatData -Path "allformat.ps1xml" -IncludeScriptBlock
```

<span data-ttu-id="29b43-117">Эта команда экспортирует все данные форматирования из сеанса в файл AllFormat.ps1xml.</span><span class="sxs-lookup"><span data-stu-id="29b43-117">This command exports all of the format data in the session to the AllFormat.ps1xml file.</span></span>

<span data-ttu-id="29b43-118">Команда использует `Get-FormatData` командлет для получения данных формата в сеансе.</span><span class="sxs-lookup"><span data-stu-id="29b43-118">The command uses the `Get-FormatData` cmdlet to get the format data in the session.</span></span> <span data-ttu-id="29b43-119">Значение `*` (ALL) для параметра **TypeName** указывает командлету получить все данные в сеансе.</span><span class="sxs-lookup"><span data-stu-id="29b43-119">A value of `*` (all) for the **TypeName** parameter directs the cmdlet to get all of the data in the session.</span></span>

<span data-ttu-id="29b43-120">Команда использует оператор конвейера ( `|` ) для отправки данных формата из `Get-FormatData` команды в `Export-FormatData` командлет, который экспортирует данные формата в файл AllFormat.ps1.</span><span class="sxs-lookup"><span data-stu-id="29b43-120">The command uses a pipeline operator (`|`) to send the format data from the `Get-FormatData` command to the `Export-FormatData` cmdlet, which exports the format data to the AllFormat.ps1 file.</span></span>

<span data-ttu-id="29b43-121">`Export-FormatData`Команда использует параметр **IncludeScriptBlock** для включения блоков скрипта в формат данных в файле.</span><span class="sxs-lookup"><span data-stu-id="29b43-121">The `Export-FormatData` command uses the **IncludeScriptBlock** parameter to include script blocks in the format data in the file.</span></span>

### <span data-ttu-id="29b43-122">Пример 2. экспорт данных формата для типа</span><span class="sxs-lookup"><span data-stu-id="29b43-122">Example 2: Export format data for a type</span></span>

```powershell
$F = Get-FormatData -TypeName "helpinfoshort" -PowerShellVersion 5.1
Export-FormatData -InputObject $F -Path "c:\test\help.format.ps1xml" -IncludeScriptBlock
```

<span data-ttu-id="29b43-123">Эти команды экспортируют данные формата для типа **HelpInfoShort** в XML-файл Help.format.ps1.</span><span class="sxs-lookup"><span data-stu-id="29b43-123">These commands export the format data for the **HelpInfoShort** type to the Help.format.ps1xml file.</span></span>

<span data-ttu-id="29b43-124">Первая команда использует `Get-FormatData` командлет для получения данных формата для типа **HelpInfoShort** и сохраняет его в `$F` переменной.</span><span class="sxs-lookup"><span data-stu-id="29b43-124">The first command uses the `Get-FormatData` cmdlet to get the format data for the **HelpInfoShort** type, and it saves it in the `$F` variable.</span></span>

<span data-ttu-id="29b43-125">Вторая команда использует параметр **InputObject** `Export-FormatData` командлета для ввода данных формата, сохраненных в `$F` переменной.</span><span class="sxs-lookup"><span data-stu-id="29b43-125">The second command uses the **InputObject** parameter of the `Export-FormatData` cmdlet to enter the format data saved in the `$F` variable.</span></span> <span data-ttu-id="29b43-126">Он также использует параметр **IncludeScriptBlock** для включения в выходные данные блоков сценариев.</span><span class="sxs-lookup"><span data-stu-id="29b43-126">It also uses the **IncludeScriptBlock** parameter to include script blocks in the output.</span></span>

### <span data-ttu-id="29b43-127">Пример 3. экспорт данных формата без блока сценария</span><span class="sxs-lookup"><span data-stu-id="29b43-127">Example 3: Export format data without a script block</span></span>

```powershell
Get-FormatData -TypeName "System.Diagnostics.Process" -PowerShellVersion 5.1 | Export-FormatData -Path process.format.ps1xml
Update-FormatData -PrependPath ".\process.format.ps1xml"
Get-Process p*
```

```Output
Handles  NPM(K)  PM(K)  WS(K) VM(M)   CPU(s)    Id ProcessName
-------  ------  -----  ----- -----   ------    -- -----------
323                                       5600 powershell
336                                       3900 powershell_ise
138                                       4076 PresentationFontCache
```

<span data-ttu-id="29b43-128">В этом примере показан результат пропуска параметра **IncludeScriptBlock** из `Export-FormatData` команды.</span><span class="sxs-lookup"><span data-stu-id="29b43-128">This example shows the effect of omitting the **IncludeScriptBlock** parameter from an `Export-FormatData` command.</span></span>

<span data-ttu-id="29b43-129">Первая команда использует `Get-FormatData` командлет для получения данных формата для объекта **System. Diagnostics. Process** , возвращаемого командлетом Get-Process.</span><span class="sxs-lookup"><span data-stu-id="29b43-129">The first command uses the `Get-FormatData` cmdlet to get the format data for the **System.Diagnostics.Process** object that the Get-Process cmdlet returns.</span></span> <span data-ttu-id="29b43-130">Команда использует оператор конвейера ( `|` ) для отправки данных форматирования в `Export-FormatData` командлет, который экспортирует его в Process.format.ps1XML-файл в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="29b43-130">The command uses a pipeline operator (`|`) to send the formatting data to the `Export-FormatData` cmdlet, which exports it to the Process.format.ps1xml file in the current directory.</span></span>

<span data-ttu-id="29b43-131">В этом случае `Export-FormatData` команда не использует параметр **IncludeScriptBlock** .</span><span class="sxs-lookup"><span data-stu-id="29b43-131">In this case, the `Export-FormatData` command does not use the **IncludeScriptBlock** parameter.</span></span>

<span data-ttu-id="29b43-132">Вторая команда использует `Update-FormatData` командлет для добавления Process.format.ps1XML-файла в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="29b43-132">The second command uses the `Update-FormatData` cmdlet to add the Process.format.ps1xml file to the current session.</span></span> <span data-ttu-id="29b43-133">Команда использует параметр **препендпас** , чтобы убедиться, что данные форматирования для объектов обработки в Process.format.ps1XML-файле найдены перед стандартными данными форматирования для объектов обработки.</span><span class="sxs-lookup"><span data-stu-id="29b43-133">The command uses the **PrependPath** parameter to ensure that the formatting data for process objects in the Process.format.ps1xml file is found before the standard formatting data for process objects.</span></span>

<span data-ttu-id="29b43-134">Третья команда демонстрирует последствия этого изменения.</span><span class="sxs-lookup"><span data-stu-id="29b43-134">The third command shows the effects of this change.</span></span> <span data-ttu-id="29b43-135">Команда использует `Get-Process` командлет для получения процессов, имена которых начинаются с P. Выходные данные показывают, что значения свойств, вычисляемые с помощью блоков скриптов, отсутствуют на экране.</span><span class="sxs-lookup"><span data-stu-id="29b43-135">The command uses the `Get-Process` cmdlet to get processes that have names that begin with P. The output shows that property values that are calculated by using script blocks are missing from the display.</span></span>

## <span data-ttu-id="29b43-136">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="29b43-136">PARAMETERS</span></span>

### <span data-ttu-id="29b43-137">-Force</span><span class="sxs-lookup"><span data-stu-id="29b43-137">-Force</span></span>

<span data-ttu-id="29b43-138">Принудительное выполнение команды без запроса на подтверждение пользователем.</span><span class="sxs-lookup"><span data-stu-id="29b43-138">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="29b43-139">-IncludeScriptBlock</span><span class="sxs-lookup"><span data-stu-id="29b43-139">-IncludeScriptBlock</span></span>

<span data-ttu-id="29b43-140">Указывает, экспортируются ли блоки скриптов в данных формата.</span><span class="sxs-lookup"><span data-stu-id="29b43-140">Indicates whether script blocks in the format data are exported.</span></span>

<span data-ttu-id="29b43-141">Так как блоки сценариев содержат код и могут использоваться во вредоносных целях, по умолчанию они не экспортируются.</span><span class="sxs-lookup"><span data-stu-id="29b43-141">Because script blocks contain code and can be used maliciously, they are not exported by default.</span></span>

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

### <span data-ttu-id="29b43-142">-InputObject</span><span class="sxs-lookup"><span data-stu-id="29b43-142">-InputObject</span></span>

<span data-ttu-id="29b43-143">Указывает объекты данных форматирования для экспорта.</span><span class="sxs-lookup"><span data-stu-id="29b43-143">Specifies the format data objects to be exported.</span></span> <span data-ttu-id="29b43-144">Введите переменную, которая содержит объекты, или команду, которая получает объекты, например `Get-FormatData` команду.</span><span class="sxs-lookup"><span data-stu-id="29b43-144">Enter a variable that contains the objects or a command that gets the objects, such as a `Get-FormatData` command.</span></span> <span data-ttu-id="29b43-145">Можно также передать объекты по конвейеру из `Get-FormatData` в `Export-FormatData` .</span><span class="sxs-lookup"><span data-stu-id="29b43-145">You can also pipe the objects from `Get-FormatData` to `Export-FormatData`.</span></span>

```yaml
Type: System.Management.Automation.ExtendedTypeDefinition[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="29b43-146">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="29b43-146">-LiteralPath</span></span>

<span data-ttu-id="29b43-147">Задает расположение выходного файла.</span><span class="sxs-lookup"><span data-stu-id="29b43-147">Specifies a location for the output file.</span></span> <span data-ttu-id="29b43-148">В отличие от параметра **Path** , значение **LiteralPath** используется именно так, как оно введено.</span><span class="sxs-lookup"><span data-stu-id="29b43-148">Unlike the **Path** parameter, the value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="29b43-149">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="29b43-149">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="29b43-150">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="29b43-150">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="29b43-151">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="29b43-151">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: ByLiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="29b43-152">-NoClobber</span><span class="sxs-lookup"><span data-stu-id="29b43-152">-NoClobber</span></span>

<span data-ttu-id="29b43-153">Указывает, что командлет не перезаписывает существующие файлы.</span><span class="sxs-lookup"><span data-stu-id="29b43-153">Indicates that the cmdlet does not overwrite existing files.</span></span> <span data-ttu-id="29b43-154">По умолчанию `Export-FormatData` перезаписывает файлы без предупреждения, если только файл не имеет атрибута только для чтения.</span><span class="sxs-lookup"><span data-stu-id="29b43-154">By default, `Export-FormatData` overwrites files without warning unless the file has the read-only attribute.</span></span>

<span data-ttu-id="29b43-155">Чтобы направлять `Export-FormatData` Перезапись файлов только для чтения, используйте параметр **Force** .</span><span class="sxs-lookup"><span data-stu-id="29b43-155">To direct `Export-FormatData` to overwrite read-only files, use the **Force** parameter.</span></span>

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

### <span data-ttu-id="29b43-156">-Path</span><span class="sxs-lookup"><span data-stu-id="29b43-156">-Path</span></span>

<span data-ttu-id="29b43-157">Задает расположение выходного файла.</span><span class="sxs-lookup"><span data-stu-id="29b43-157">Specifies a location for the output file.</span></span>
<span data-ttu-id="29b43-158">Введите путь (необязательно) и имя файла с расширением format.ps1xml.</span><span class="sxs-lookup"><span data-stu-id="29b43-158">Enter a path (optional) and file name with a format.ps1xml file name extension.</span></span>
<span data-ttu-id="29b43-159">Если опустить путь, `Export-FormatData` создает файл в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="29b43-159">If you omit the path, `Export-FormatData` creates the file in the current directory.</span></span>

<span data-ttu-id="29b43-160">Если используется расширение имени файла, отличное от. ps1xml, `Update-FormatData` командлет не сможет распознать файл.</span><span class="sxs-lookup"><span data-stu-id="29b43-160">If you use a file name extension other than .ps1xml, the `Update-FormatData` cmdlet will not recognize the file.</span></span>

<span data-ttu-id="29b43-161">При указании существующего файла `Export-FormatData` перезаписывает файл без предупреждения, если только файл не имеет атрибута только для чтения.</span><span class="sxs-lookup"><span data-stu-id="29b43-161">If you specify an existing file, `Export-FormatData` overwrites the file without warning, unless the file has the read-only attribute.</span></span> <span data-ttu-id="29b43-162">Чтобы перезаписать файл, доступный только для чтения, используйте параметр **Force** .</span><span class="sxs-lookup"><span data-stu-id="29b43-162">To overwrite a read-only file, use the **Force** parameter.</span></span> <span data-ttu-id="29b43-163">Чтобы предотвратить перезапись файлов, используйте параметр **NoClobber** .</span><span class="sxs-lookup"><span data-stu-id="29b43-163">To prevent files from being overwritten, use the **NoClobber** parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: ByPath
Aliases: FilePath

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="29b43-164">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="29b43-164">CommonParameters</span></span>

<span data-ttu-id="29b43-165">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="29b43-165">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="29b43-166">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="29b43-166">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="29b43-167">Входные данные</span><span class="sxs-lookup"><span data-stu-id="29b43-167">INPUTS</span></span>

### <span data-ttu-id="29b43-168">System. Management. Automation. Екстендедтипедефинитион</span><span class="sxs-lookup"><span data-stu-id="29b43-168">System.Management.Automation.ExtendedTypeDefinition</span></span>

<span data-ttu-id="29b43-169">Вы можете передать объекты **екстендедтипедефинитион** из `Get-FormatData` в `Export-FormatData` .</span><span class="sxs-lookup"><span data-stu-id="29b43-169">You can pipe **ExtendedTypeDefinition** objects from `Get-FormatData` to `Export-FormatData`.</span></span>

## <span data-ttu-id="29b43-170">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="29b43-170">OUTPUTS</span></span>

### <span data-ttu-id="29b43-171">Нет</span><span class="sxs-lookup"><span data-stu-id="29b43-171">None</span></span>

<span data-ttu-id="29b43-172">`Export-FormatData` не возвращает никаких объектов.</span><span class="sxs-lookup"><span data-stu-id="29b43-172">`Export-FormatData` does not return any objects.</span></span>
<span data-ttu-id="29b43-173">Он создает файл и сохраняет его по указанному пути.</span><span class="sxs-lookup"><span data-stu-id="29b43-173">It generates a file and saves it in the specified path.</span></span>

## <span data-ttu-id="29b43-174">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="29b43-174">NOTES</span></span>

- <span data-ttu-id="29b43-175">Для использования любого файла форматирования, включая экспортированный, политика выполнения сеанса должна разрешать запуск сценариев и файлов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="29b43-175">To use any formatting file, including an exported formatting file, the execution policy for the session must allow scripts and configuration files to run.</span></span> <span data-ttu-id="29b43-176">Подробнее см. в разделе [about_Execution_Policies](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md).</span><span class="sxs-lookup"><span data-stu-id="29b43-176">For more information, see [about_Execution_Policies](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md).</span></span>

## <span data-ttu-id="29b43-177">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="29b43-177">RELATED LINKS</span></span>

[<span data-ttu-id="29b43-178">Get-FormatData;</span><span class="sxs-lookup"><span data-stu-id="29b43-178">Get-FormatData</span></span>](Get-FormatData.md)

[<span data-ttu-id="29b43-179">Update-FormatData</span><span class="sxs-lookup"><span data-stu-id="29b43-179">Update-FormatData</span></span>](Update-FormatData.md)
