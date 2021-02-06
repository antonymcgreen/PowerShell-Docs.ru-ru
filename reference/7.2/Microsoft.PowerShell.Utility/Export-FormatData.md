---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/export-formatdata?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-FormatData
ms.openlocfilehash: d42b108d469ed8989628a6c0b4214af4afc0db00
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599379"
---
# <span data-ttu-id="b90cf-102">Export-FormatData</span><span class="sxs-lookup"><span data-stu-id="b90cf-102">Export-FormatData</span></span>

## <span data-ttu-id="b90cf-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="b90cf-103">SYNOPSIS</span></span>
<span data-ttu-id="b90cf-104">Сохраняет данные форматирования текущего сеанса в файле форматирования.</span><span class="sxs-lookup"><span data-stu-id="b90cf-104">Saves formatting data from the current session in a formatting file.</span></span>

## <span data-ttu-id="b90cf-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b90cf-105">SYNTAX</span></span>

### <span data-ttu-id="b90cf-106">ByPath (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="b90cf-106">ByPath (Default)</span></span>

```
Export-FormatData -InputObject <ExtendedTypeDefinition[]> -Path <String> [-Force] [-NoClobber]
 [-IncludeScriptBlock] [<CommonParameters>]
```

### <span data-ttu-id="b90cf-107">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="b90cf-107">ByLiteralPath</span></span>

```
Export-FormatData -InputObject <ExtendedTypeDefinition[]> -LiteralPath <String> [-Force] [-NoClobber]
 [-IncludeScriptBlock] [<CommonParameters>]
```

## <span data-ttu-id="b90cf-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b90cf-108">DESCRIPTION</span></span>

<span data-ttu-id="b90cf-109">`Export-FormatData`Командлет создает файлы форматирования PowerShell (format.ps1XML) из объектов форматирования в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="b90cf-109">The `Export-FormatData` cmdlet creates PowerShell formatting files (format.ps1xml) from the formatting objects in the current session.</span></span> <span data-ttu-id="b90cf-110">Он принимает объекты **екстендедтипедефинитион** , которые `Get-FormatData` возвращают и сохраняет их в файле в формате XML.</span><span class="sxs-lookup"><span data-stu-id="b90cf-110">It takes the **ExtendedTypeDefinition** objects that `Get-FormatData` returns and saves them in a file in XML format.</span></span>

<span data-ttu-id="b90cf-111">PowerShell использует данные в файлах форматирования (format.ps1XML), чтобы создать отображение по умолчанию Microsoft .NET объектов платформы в сеансе.</span><span class="sxs-lookup"><span data-stu-id="b90cf-111">PowerShell uses the data in formatting files (format.ps1xml) to generate the default display of Microsoft .NET Framework objects in the session.</span></span> <span data-ttu-id="b90cf-112">Вы можете просматривать и изменять файлы форматирования и использовать командлет Update-FormatData для добавления данных форматирования в сеанс.</span><span class="sxs-lookup"><span data-stu-id="b90cf-112">You can view and edit the formatting files and use the Update-FormatData cmdlet to add the formatting data to a session.</span></span>

<span data-ttu-id="b90cf-113">Дополнительные сведения о файлах форматирования в PowerShell см. в разделе [about_Format.ps1XML](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md).</span><span class="sxs-lookup"><span data-stu-id="b90cf-113">For more information about formatting files in PowerShell, see [about_Format.ps1xml](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md).</span></span>

## <span data-ttu-id="b90cf-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="b90cf-114">EXAMPLES</span></span>

### <span data-ttu-id="b90cf-115">Пример 1. экспорт данных в формате сеанса</span><span class="sxs-lookup"><span data-stu-id="b90cf-115">Example 1: Export session format data</span></span>

```powershell
Get-FormatData -TypeName "*" | Export-FormatData -Path "allformat.ps1xml" -IncludeScriptBlock
```

<span data-ttu-id="b90cf-116">Эта команда экспортирует все данные форматирования из сеанса в файл AllFormat.ps1xml.</span><span class="sxs-lookup"><span data-stu-id="b90cf-116">This command exports all of the format data in the session to the AllFormat.ps1xml file.</span></span>

<span data-ttu-id="b90cf-117">Команда использует `Get-FormatData` командлет для получения данных формата в сеансе.</span><span class="sxs-lookup"><span data-stu-id="b90cf-117">The command uses the `Get-FormatData` cmdlet to get the format data in the session.</span></span> <span data-ttu-id="b90cf-118">Значение `*` (ALL) для параметра **TypeName** указывает командлету получить все данные в сеансе.</span><span class="sxs-lookup"><span data-stu-id="b90cf-118">A value of `*` (all) for the **TypeName** parameter directs the cmdlet to get all of the data in the session.</span></span>

<span data-ttu-id="b90cf-119">Команда использует оператор конвейера ( `|` ) для отправки данных формата из `Get-FormatData` команды в `Export-FormatData` командлет, который экспортирует данные формата в файл AllFormat.ps1.</span><span class="sxs-lookup"><span data-stu-id="b90cf-119">The command uses a pipeline operator (`|`) to send the format data from the `Get-FormatData` command to the `Export-FormatData` cmdlet, which exports the format data to the AllFormat.ps1 file.</span></span>

<span data-ttu-id="b90cf-120">`Export-FormatData`Команда использует параметр **IncludeScriptBlock** для включения блоков скрипта в формат данных в файле.</span><span class="sxs-lookup"><span data-stu-id="b90cf-120">The `Export-FormatData` command uses the **IncludeScriptBlock** parameter to include script blocks in the format data in the file.</span></span>

### <span data-ttu-id="b90cf-121">Пример 2. экспорт данных формата для типа</span><span class="sxs-lookup"><span data-stu-id="b90cf-121">Example 2: Export format data for a type</span></span>

```powershell
$F = Get-FormatData -TypeName "helpinfoshort"
Export-FormatData -InputObject $F -Path "c:\test\help.format.ps1xml" -IncludeScriptBlock
```

<span data-ttu-id="b90cf-122">Эти команды экспортируют данные формата для типа **HelpInfoShort** в XML-файл Help.format.ps1.</span><span class="sxs-lookup"><span data-stu-id="b90cf-122">These commands export the format data for the **HelpInfoShort** type to the Help.format.ps1xml file.</span></span>

<span data-ttu-id="b90cf-123">Первая команда использует `Get-FormatData` командлет для получения данных формата для типа **HelpInfoShort** и сохраняет его в `$F` переменной.</span><span class="sxs-lookup"><span data-stu-id="b90cf-123">The first command uses the `Get-FormatData` cmdlet to get the format data for the **HelpInfoShort** type, and it saves it in the `$F` variable.</span></span>

<span data-ttu-id="b90cf-124">Вторая команда использует параметр **InputObject** `Export-FormatData` командлета для ввода данных формата, сохраненных в `$F` переменной.</span><span class="sxs-lookup"><span data-stu-id="b90cf-124">The second command uses the **InputObject** parameter of the `Export-FormatData` cmdlet to enter the format data saved in the `$F` variable.</span></span> <span data-ttu-id="b90cf-125">Он также использует параметр **IncludeScriptBlock** для включения в выходные данные блоков сценариев.</span><span class="sxs-lookup"><span data-stu-id="b90cf-125">It also uses the **IncludeScriptBlock** parameter to include script blocks in the output.</span></span>

### <span data-ttu-id="b90cf-126">Пример 3. экспорт данных формата без блока сценария</span><span class="sxs-lookup"><span data-stu-id="b90cf-126">Example 3: Export format data without a script block</span></span>

```powershell
Get-FormatData -TypeName "System.Diagnostics.Process" | Export-FormatData -Path process.format.ps1xml
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

<span data-ttu-id="b90cf-127">В этом примере показан результат пропуска параметра **IncludeScriptBlock** из `Export-FormatData` команды.</span><span class="sxs-lookup"><span data-stu-id="b90cf-127">This example shows the effect of omitting the **IncludeScriptBlock** parameter from an `Export-FormatData` command.</span></span>

<span data-ttu-id="b90cf-128">Первая команда использует `Get-FormatData` командлет для получения данных формата для объекта **System. Diagnostics. Process** , возвращаемого командлетом Get-Process.</span><span class="sxs-lookup"><span data-stu-id="b90cf-128">The first command uses the `Get-FormatData` cmdlet to get the format data for the **System.Diagnostics.Process** object that the Get-Process cmdlet returns.</span></span> <span data-ttu-id="b90cf-129">Команда использует оператор конвейера ( `|` ) для отправки данных форматирования в `Export-FormatData` командлет, который экспортирует его в Process.format.ps1XML-файл в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="b90cf-129">The command uses a pipeline operator (`|`) to send the formatting data to the `Export-FormatData` cmdlet, which exports it to the Process.format.ps1xml file in the current directory.</span></span>

<span data-ttu-id="b90cf-130">В этом случае `Export-FormatData` команда не использует параметр **IncludeScriptBlock** .</span><span class="sxs-lookup"><span data-stu-id="b90cf-130">In this case, the `Export-FormatData` command does not use the **IncludeScriptBlock** parameter.</span></span>

<span data-ttu-id="b90cf-131">Вторая команда использует `Update-FormatData` командлет для добавления Process.format.ps1XML-файла в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="b90cf-131">The second command uses the `Update-FormatData` cmdlet to add the Process.format.ps1xml file to the current session.</span></span> <span data-ttu-id="b90cf-132">Команда использует параметр **препендпас** , чтобы убедиться, что данные форматирования для объектов обработки в Process.format.ps1XML-файле найдены перед стандартными данными форматирования для объектов обработки.</span><span class="sxs-lookup"><span data-stu-id="b90cf-132">The command uses the **PrependPath** parameter to ensure that the formatting data for process objects in the Process.format.ps1xml file is found before the standard formatting data for process objects.</span></span>

<span data-ttu-id="b90cf-133">Третья команда демонстрирует последствия этого изменения.</span><span class="sxs-lookup"><span data-stu-id="b90cf-133">The third command shows the effects of this change.</span></span> <span data-ttu-id="b90cf-134">Команда использует `Get-Process` командлет для получения процессов, имена которых начинаются с P. Выходные данные показывают, что значения свойств, вычисляемые с помощью блоков скриптов, отсутствуют на экране.</span><span class="sxs-lookup"><span data-stu-id="b90cf-134">The command uses the `Get-Process` cmdlet to get processes that have names that begin with P. The output shows that property values that are calculated by using script blocks are missing from the display.</span></span>

## <span data-ttu-id="b90cf-135">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b90cf-135">PARAMETERS</span></span>

### <span data-ttu-id="b90cf-136">-Force</span><span class="sxs-lookup"><span data-stu-id="b90cf-136">-Force</span></span>

<span data-ttu-id="b90cf-137">Принудительное выполнение команды без запроса на подтверждение пользователем.</span><span class="sxs-lookup"><span data-stu-id="b90cf-137">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="b90cf-138">-IncludeScriptBlock</span><span class="sxs-lookup"><span data-stu-id="b90cf-138">-IncludeScriptBlock</span></span>

<span data-ttu-id="b90cf-139">Указывает, экспортируются ли блоки скриптов в данных формата.</span><span class="sxs-lookup"><span data-stu-id="b90cf-139">Indicates whether script blocks in the format data are exported.</span></span>

<span data-ttu-id="b90cf-140">Так как блоки сценариев содержат код и могут использоваться во вредоносных целях, по умолчанию они не экспортируются.</span><span class="sxs-lookup"><span data-stu-id="b90cf-140">Because script blocks contain code and can be used maliciously, they are not exported by default.</span></span>

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

### <span data-ttu-id="b90cf-141">-InputObject</span><span class="sxs-lookup"><span data-stu-id="b90cf-141">-InputObject</span></span>

<span data-ttu-id="b90cf-142">Указывает объекты данных форматирования для экспорта.</span><span class="sxs-lookup"><span data-stu-id="b90cf-142">Specifies the format data objects to be exported.</span></span> <span data-ttu-id="b90cf-143">Введите переменную, которая содержит объекты, или команду, которая получает объекты, например `Get-FormatData` команду.</span><span class="sxs-lookup"><span data-stu-id="b90cf-143">Enter a variable that contains the objects or a command that gets the objects, such as a `Get-FormatData` command.</span></span> <span data-ttu-id="b90cf-144">Можно также передать объекты по конвейеру из `Get-FormatData` в `Export-FormatData` .</span><span class="sxs-lookup"><span data-stu-id="b90cf-144">You can also pipe the objects from `Get-FormatData` to `Export-FormatData`.</span></span>

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

### <span data-ttu-id="b90cf-145">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="b90cf-145">-LiteralPath</span></span>

<span data-ttu-id="b90cf-146">Задает расположение выходного файла.</span><span class="sxs-lookup"><span data-stu-id="b90cf-146">Specifies a location for the output file.</span></span> <span data-ttu-id="b90cf-147">В отличие от параметра **Path**, значение **LiteralPath** используется именно так, как оно введено.</span><span class="sxs-lookup"><span data-stu-id="b90cf-147">Unlike the **Path** parameter, the value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="b90cf-148">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="b90cf-148">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="b90cf-149">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="b90cf-149">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="b90cf-150">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="b90cf-150">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="b90cf-151">-NoClobber</span><span class="sxs-lookup"><span data-stu-id="b90cf-151">-NoClobber</span></span>

<span data-ttu-id="b90cf-152">Указывает, что командлет не перезаписывает существующие файлы.</span><span class="sxs-lookup"><span data-stu-id="b90cf-152">Indicates that the cmdlet does not overwrite existing files.</span></span> <span data-ttu-id="b90cf-153">По умолчанию `Export-FormatData` перезаписывает файлы без предупреждения, если только файл не имеет атрибута только для чтения.</span><span class="sxs-lookup"><span data-stu-id="b90cf-153">By default, `Export-FormatData` overwrites files without warning unless the file has the read-only attribute.</span></span>

<span data-ttu-id="b90cf-154">Чтобы направлять `Export-FormatData` Перезапись файлов только для чтения, используйте параметр **Force** .</span><span class="sxs-lookup"><span data-stu-id="b90cf-154">To direct `Export-FormatData` to overwrite read-only files, use the **Force** parameter.</span></span>

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

### <span data-ttu-id="b90cf-155">-Path</span><span class="sxs-lookup"><span data-stu-id="b90cf-155">-Path</span></span>

<span data-ttu-id="b90cf-156">Задает расположение выходного файла.</span><span class="sxs-lookup"><span data-stu-id="b90cf-156">Specifies a location for the output file.</span></span>
<span data-ttu-id="b90cf-157">Введите путь (необязательно) и имя файла с расширением format.ps1xml.</span><span class="sxs-lookup"><span data-stu-id="b90cf-157">Enter a path (optional) and file name with a format.ps1xml file name extension.</span></span>
<span data-ttu-id="b90cf-158">Если опустить путь, `Export-FormatData` создает файл в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="b90cf-158">If you omit the path, `Export-FormatData` creates the file in the current directory.</span></span>

<span data-ttu-id="b90cf-159">Если используется расширение имени файла, отличное от. ps1xml, `Update-FormatData` командлет не сможет распознать файл.</span><span class="sxs-lookup"><span data-stu-id="b90cf-159">If you use a file name extension other than .ps1xml, the `Update-FormatData` cmdlet will not recognize the file.</span></span>

<span data-ttu-id="b90cf-160">При указании существующего файла `Export-FormatData` перезаписывает файл без предупреждения, если только файл не имеет атрибута только для чтения.</span><span class="sxs-lookup"><span data-stu-id="b90cf-160">If you specify an existing file, `Export-FormatData` overwrites the file without warning, unless the file has the read-only attribute.</span></span> <span data-ttu-id="b90cf-161">Чтобы перезаписать файл, доступный только для чтения, используйте параметр **Force** .</span><span class="sxs-lookup"><span data-stu-id="b90cf-161">To overwrite a read-only file, use the **Force** parameter.</span></span> <span data-ttu-id="b90cf-162">Чтобы предотвратить перезапись файлов, используйте параметр **NoClobber** .</span><span class="sxs-lookup"><span data-stu-id="b90cf-162">To prevent files from being overwritten, use the **NoClobber** parameter.</span></span>

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

### <span data-ttu-id="b90cf-163">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="b90cf-163">CommonParameters</span></span>

<span data-ttu-id="b90cf-164">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b90cf-164">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b90cf-165">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="b90cf-165">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b90cf-166">Входные данные</span><span class="sxs-lookup"><span data-stu-id="b90cf-166">INPUTS</span></span>

### <span data-ttu-id="b90cf-167">System. Management. Automation. Екстендедтипедефинитион</span><span class="sxs-lookup"><span data-stu-id="b90cf-167">System.Management.Automation.ExtendedTypeDefinition</span></span>

<span data-ttu-id="b90cf-168">Вы можете передать объекты **екстендедтипедефинитион** из `Get-FormatData` в `Export-FormatData` .</span><span class="sxs-lookup"><span data-stu-id="b90cf-168">You can pipe **ExtendedTypeDefinition** objects from `Get-FormatData` to `Export-FormatData`.</span></span>

## <span data-ttu-id="b90cf-169">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="b90cf-169">OUTPUTS</span></span>

### <span data-ttu-id="b90cf-170">None</span><span class="sxs-lookup"><span data-stu-id="b90cf-170">None</span></span>

<span data-ttu-id="b90cf-171">`Export-FormatData` не возвращает никаких объектов.</span><span class="sxs-lookup"><span data-stu-id="b90cf-171">`Export-FormatData` does not return any objects.</span></span>
<span data-ttu-id="b90cf-172">Он создает файл и сохраняет его по указанному пути.</span><span class="sxs-lookup"><span data-stu-id="b90cf-172">It generates a file and saves it in the specified path.</span></span>

## <span data-ttu-id="b90cf-173">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="b90cf-173">NOTES</span></span>

- <span data-ttu-id="b90cf-174">Для использования любого файла форматирования, включая экспортированный, политика выполнения сеанса должна разрешать запуск сценариев и файлов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="b90cf-174">To use any formatting file, including an exported formatting file, the execution policy for the session must allow scripts and configuration files to run.</span></span> <span data-ttu-id="b90cf-175">Подробнее см. в разделе [about_Execution_Policies](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md).</span><span class="sxs-lookup"><span data-stu-id="b90cf-175">For more information, see [about_Execution_Policies](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md).</span></span>

## <span data-ttu-id="b90cf-176">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="b90cf-176">RELATED LINKS</span></span>

[<span data-ttu-id="b90cf-177">Get-FormatData;</span><span class="sxs-lookup"><span data-stu-id="b90cf-177">Get-FormatData</span></span>](Get-FormatData.md)

[<span data-ttu-id="b90cf-178">Update-FormatData</span><span class="sxs-lookup"><span data-stu-id="b90cf-178">Update-FormatData</span></span>](Update-FormatData.md)
