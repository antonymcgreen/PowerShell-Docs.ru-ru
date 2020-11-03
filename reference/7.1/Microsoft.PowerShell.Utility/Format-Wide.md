---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/format-wide?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Format-Wide
ms.openlocfilehash: eed3ba1982792cc5675b7343525e1182f9e6a420
ms.sourcegitcommit: 9a6b6714ded4edb5119f1b82a253608018ea6b98
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/10/2020
ms.locfileid: "93230393"
---
# <span data-ttu-id="945a3-103">Format-Wide</span><span class="sxs-lookup"><span data-stu-id="945a3-103">Format-Wide</span></span>

## <span data-ttu-id="945a3-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="945a3-104">SYNOPSIS</span></span>
<span data-ttu-id="945a3-105">Форматирует объекты в виде широкой таблицы, в которой отображается только одно свойство каждого объекта.</span><span class="sxs-lookup"><span data-stu-id="945a3-105">Formats objects as a wide table that displays only one property of each object.</span></span>

## <span data-ttu-id="945a3-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="945a3-106">SYNTAX</span></span>

```
Format-Wide [[-Property] <Object>] [-AutoSize] [-Column <int>] [-GroupBy <Object>] [-View <string>]
  [-ShowError] [-DisplayError] [-Force] [-Expand <string>] [-InputObject <psobject>]
  [<CommonParameters>]
```

## <span data-ttu-id="945a3-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="945a3-107">DESCRIPTION</span></span>

<span data-ttu-id="945a3-108">`Format-Wide`Командлет форматирует объекты в виде широкой таблицы, в которой отображается только одно свойство каждого объекта.</span><span class="sxs-lookup"><span data-stu-id="945a3-108">The `Format-Wide` cmdlet formats objects as a wide table that displays only one property of each object.</span></span> <span data-ttu-id="945a3-109">Для определения отображаемого свойства можно использовать параметр **Property** .</span><span class="sxs-lookup"><span data-stu-id="945a3-109">You can use the **Property** parameter to determine which property is displayed.</span></span>

## <span data-ttu-id="945a3-110">Примеры</span><span class="sxs-lookup"><span data-stu-id="945a3-110">EXAMPLES</span></span>

### <span data-ttu-id="945a3-111">Пример 1. форматирование имен файлов в текущем каталоге</span><span class="sxs-lookup"><span data-stu-id="945a3-111">Example 1: Format names of files in the current directory</span></span>

<span data-ttu-id="945a3-112">Эта команда отображает имена файлов в текущем каталоге в трех столбцах на весь экран.</span><span class="sxs-lookup"><span data-stu-id="945a3-112">This command displays the names of files in the current directory in three columns across the screen.</span></span>

```powershell
Get-ChildItem | Format-Wide -Column 3
```

<span data-ttu-id="945a3-113">Командлет Get-ChildItem получает объекты, представляющие каждый файл в каталоге.</span><span class="sxs-lookup"><span data-stu-id="945a3-113">The Get-ChildItem cmdlet gets objects representing each file in the directory.</span></span> <span data-ttu-id="945a3-114">Оператор конвейера (|) передает объекты файлов через конвейер в `Format-Wide` , который форматирует их для вывода.</span><span class="sxs-lookup"><span data-stu-id="945a3-114">The pipeline operator (|) passes the file objects through the pipeline to `Format-Wide`, which formats them for output.</span></span> <span data-ttu-id="945a3-115">Параметр **Column** указывает количество столбцов.</span><span class="sxs-lookup"><span data-stu-id="945a3-115">The **Column** parameter specifies the number of columns.</span></span>

### <span data-ttu-id="945a3-116">Пример 2. форматирование имен разделов реестра</span><span class="sxs-lookup"><span data-stu-id="945a3-116">Example 2: Format names of registry keys</span></span>

<span data-ttu-id="945a3-117">Эта команда выводит на экран имена разделов реестров в разделе HKEY_CURRENT_USER\Software\Microsoft.</span><span class="sxs-lookup"><span data-stu-id="945a3-117">This command displays the names of registry keys in the HKEY_CURRENT_USER\Software\Microsoft key.</span></span>

```powershell
Get-ChildItem HKCU:\software\microsoft | Format-Wide -Property pschildname -AutoSize
```

<span data-ttu-id="945a3-118">Командлет Get-ChildItem получает объекты, представляющие разделы.</span><span class="sxs-lookup"><span data-stu-id="945a3-118">The Get-ChildItem cmdlet gets objects representing the keys.</span></span> <span data-ttu-id="945a3-119">Путь указывается в разделе HKCU:, на одном из дисков, предоставляемых поставщиком реестра PowerShell, за которым следует путь к ключу.</span><span class="sxs-lookup"><span data-stu-id="945a3-119">The path is specified as HKCU:, one of the drives exposed by the PowerShell Registry provider, followed by the key path.</span></span> <span data-ttu-id="945a3-120">Оператор конвейера (|) передает объекты раздела реестра по конвейеру в `Format-Wide` , который форматирует их для вывода.</span><span class="sxs-lookup"><span data-stu-id="945a3-120">The pipeline operator (|) passes the registry key objects through the pipeline to `Format-Wide`, which formats them for output.</span></span> <span data-ttu-id="945a3-121">Параметр **Property** задает имя свойства, а параметр **AutoSize** корректирует столбцы для удобства чтения.</span><span class="sxs-lookup"><span data-stu-id="945a3-121">The **Property** parameter specifies the name of the property, and the **AutoSize** parameter adjusts the columns for readability.</span></span>

### <span data-ttu-id="945a3-122">Пример 3. Устранение ошибок формата</span><span class="sxs-lookup"><span data-stu-id="945a3-122">Example 3: Troubleshooting format errors</span></span>

<span data-ttu-id="945a3-123">В следующих примерах показаны результаты добавления параметров **DisplayError** или **ShowError** в выражение.</span><span class="sxs-lookup"><span data-stu-id="945a3-123">The following examples show of the results of adding the **DisplayError** or **ShowError** parameters with an expression.</span></span>

```powershell
PS /> Get-Date | Format-Wide { $_ / $null } -DisplayError


#ERR

PS /> Get-Date | Format-Wide { $_ / $null } -ShowError


Failed to evaluate expression " $_ / $null ".
+ CategoryInfo          : InvalidArgument: (12/21/2018 8:18:01 AM:PSObject) [], RuntimeException
+ FullyQualifiedErrorId : PSPropertyExpressionError
```

## <span data-ttu-id="945a3-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="945a3-124">PARAMETERS</span></span>

### <span data-ttu-id="945a3-125">-AutoSize</span><span class="sxs-lookup"><span data-stu-id="945a3-125">-AutoSize</span></span>

<span data-ttu-id="945a3-126">Корректирует размер столбца и количество столбцов в зависимости от ширины данных.</span><span class="sxs-lookup"><span data-stu-id="945a3-126">Adjusts the column size and number of columns based on the width of the data.</span></span> <span data-ttu-id="945a3-127">По умолчанию размер и количество столбцов определяются представлением.</span><span class="sxs-lookup"><span data-stu-id="945a3-127">By default, the column size and number are determined by the view.</span></span> <span data-ttu-id="945a3-128">Нельзя использовать параметры **AutoSize** и **Column** в одной команде.</span><span class="sxs-lookup"><span data-stu-id="945a3-128">You cannot use the **AutoSize** and **Column** parameters in the same command.</span></span>

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

### <span data-ttu-id="945a3-129">-Column</span><span class="sxs-lookup"><span data-stu-id="945a3-129">-Column</span></span>

<span data-ttu-id="945a3-130">Задает количество столбцов в отображаемых данных.</span><span class="sxs-lookup"><span data-stu-id="945a3-130">Specifies the number of columns in the display.</span></span> <span data-ttu-id="945a3-131">Нельзя использовать параметры **AutoSize** и **Column** в одной команде.</span><span class="sxs-lookup"><span data-stu-id="945a3-131">You cannot use the **AutoSize** and **Column** parameters in the same command.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="945a3-132">-DisplayError</span><span class="sxs-lookup"><span data-stu-id="945a3-132">-DisplayError</span></span>

<span data-ttu-id="945a3-133">Отображает сообщения об ошибках в командной строке.</span><span class="sxs-lookup"><span data-stu-id="945a3-133">Displays errors at the command line.</span></span> <span data-ttu-id="945a3-134">Этот параметр редко используется, но его можно использовать в качестве вспомогательного средства отладки при форматировании выражений в `Format-Wide` команде, и выражения не работают.</span><span class="sxs-lookup"><span data-stu-id="945a3-134">This parameter is rarely used, but can be used as a debugging aid when you are formatting expressions in a `Format-Wide` command, and the expressions do not appear to be working.</span></span>

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

### <span data-ttu-id="945a3-135">-Expand</span><span class="sxs-lookup"><span data-stu-id="945a3-135">-Expand</span></span>

<span data-ttu-id="945a3-136">Форматирует объект коллекции, а также объекты, содержащиеся в коллекции.</span><span class="sxs-lookup"><span data-stu-id="945a3-136">Formats the collection object, as well as the objects in the collection.</span></span> <span data-ttu-id="945a3-137">Этот параметр служит для форматирования объектов, поддерживающих интерфейс ICollection (System.Collections).</span><span class="sxs-lookup"><span data-stu-id="945a3-137">This parameter is designed to format objects that support the ICollection (System.Collections) interface.</span></span> <span data-ttu-id="945a3-138">Значение по умолчанию — **енумонли** .</span><span class="sxs-lookup"><span data-stu-id="945a3-138">The default value is **EnumOnly** .</span></span>

<span data-ttu-id="945a3-139">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="945a3-139">Valid values are:</span></span>

- <span data-ttu-id="945a3-140">EnumOnly — отображаются свойства объектов в коллекции.</span><span class="sxs-lookup"><span data-stu-id="945a3-140">EnumOnly: Displays the properties of the objects in the collection.</span></span>
- <span data-ttu-id="945a3-141">CoreOnly — отображаются свойства объекта коллекции.</span><span class="sxs-lookup"><span data-stu-id="945a3-141">CoreOnly: Displays the properties of the collection object.</span></span>
- <span data-ttu-id="945a3-142">Both — отображаются свойства объекта коллекции и свойства объектов, содержащихся в коллекции.</span><span class="sxs-lookup"><span data-stu-id="945a3-142">Both: Displays the properties of the collection object and the properties of objects in the collection.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: CoreOnly, EnumOnly, Both

Required: False
Position: Named
Default value: EnumOnly
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="945a3-143">-Force</span><span class="sxs-lookup"><span data-stu-id="945a3-143">-Force</span></span>

<span data-ttu-id="945a3-144">Указывает, что этот командлет переопределяет ограничения, препятствующие выполнению команды, так что изменения не нарушают безопасность.</span><span class="sxs-lookup"><span data-stu-id="945a3-144">Indicates that this cmdlet overrides restrictions that prevent the command from succeeding, just so the changes do not compromise security.</span></span> <span data-ttu-id="945a3-145">Например, параметр **Force** позволяет переопределить атрибут «только для чтения» или создать дополнительные каталоги в пути, не меняя разрешения на доступ к файлу.</span><span class="sxs-lookup"><span data-stu-id="945a3-145">For example, **Force** will override the read-only attribute or create directories to complete a file path, but it will not attempt to change file permissions.</span></span>

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

### <span data-ttu-id="945a3-146">-GroupBy</span><span class="sxs-lookup"><span data-stu-id="945a3-146">-GroupBy</span></span>

<span data-ttu-id="945a3-147">Форматирует вывод в группы на основе общего свойства или значения.</span><span class="sxs-lookup"><span data-stu-id="945a3-147">Formats the output in groups based on a shared property or value.</span></span> <span data-ttu-id="945a3-148">Введите выражение или свойство вывода.</span><span class="sxs-lookup"><span data-stu-id="945a3-148">Enter an expression or a property of the output.</span></span>

<span data-ttu-id="945a3-149">Значением параметра **GroupBy** может быть новое вычисляемое свойство.</span><span class="sxs-lookup"><span data-stu-id="945a3-149">The value of the **GroupBy** parameter can be a new calculated property.</span></span> <span data-ttu-id="945a3-150">Вычисляемое свойство может быть блоком скрипта или хэш-таблицей.</span><span class="sxs-lookup"><span data-stu-id="945a3-150">The calculated property can be a script block or a hash table.</span></span> <span data-ttu-id="945a3-151">Допустимые пары "ключ-значение":</span><span class="sxs-lookup"><span data-stu-id="945a3-151">Valid key-value pairs are:</span></span>

- <span data-ttu-id="945a3-152">Имя (или метка) — `<string>`</span><span class="sxs-lookup"><span data-stu-id="945a3-152">Name (or Label) - `<string>`</span></span>
- <span data-ttu-id="945a3-153">Выражение — `<string>` или `<script block>`</span><span class="sxs-lookup"><span data-stu-id="945a3-153">Expression - `<string>` or `<script block>`</span></span>
- <span data-ttu-id="945a3-154">FormatString `<string>`</span><span class="sxs-lookup"><span data-stu-id="945a3-154">FormatString - `<string>`</span></span>

<span data-ttu-id="945a3-155">Дополнительные сведения см. в разделе [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span><span class="sxs-lookup"><span data-stu-id="945a3-155">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="945a3-156">-InputObject</span><span class="sxs-lookup"><span data-stu-id="945a3-156">-InputObject</span></span>

<span data-ttu-id="945a3-157">Задает объекты для форматирования.</span><span class="sxs-lookup"><span data-stu-id="945a3-157">Specifies the objects to format.</span></span> <span data-ttu-id="945a3-158">Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты.</span><span class="sxs-lookup"><span data-stu-id="945a3-158">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="945a3-159">-Property</span><span class="sxs-lookup"><span data-stu-id="945a3-159">-Property</span></span>

<span data-ttu-id="945a3-160">Задает свойства объекта, которые будут включены в вывод, и порядок их вывода.</span><span class="sxs-lookup"><span data-stu-id="945a3-160">Specifies the object properties that appear in the display and the order in which they appear.</span></span>
<span data-ttu-id="945a3-161">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="945a3-161">Wildcards are permitted.</span></span>

<span data-ttu-id="945a3-162">Если этот параметр не указан, свойства включаются в вывод в зависимости от отображаемого объекта.</span><span class="sxs-lookup"><span data-stu-id="945a3-162">If you omit this parameter, the properties that appear in the display depend on the object being displayed.</span></span> <span data-ttu-id="945a3-163">Имя параметра "свойство" является необязательным.</span><span class="sxs-lookup"><span data-stu-id="945a3-163">The parameter name "Property" is optional.</span></span> <span data-ttu-id="945a3-164">Нельзя использовать **Свойства** и параметры **представления** в одной команде.</span><span class="sxs-lookup"><span data-stu-id="945a3-164">You cannot use the **Property** and **View** parameters in the same command.</span></span>

<span data-ttu-id="945a3-165">Значением параметра **Property** может быть новое вычисляемое свойство.</span><span class="sxs-lookup"><span data-stu-id="945a3-165">The value of the **Property** parameter can be a new calculated property.</span></span> <span data-ttu-id="945a3-166">Вычисляемое свойство может быть блоком скрипта или хэш-таблицей.</span><span class="sxs-lookup"><span data-stu-id="945a3-166">The calculated property can be a script block or a hash table.</span></span> <span data-ttu-id="945a3-167">Допустимые пары "ключ-значение":</span><span class="sxs-lookup"><span data-stu-id="945a3-167">Valid key-value pairs are:</span></span>

- <span data-ttu-id="945a3-168">Выражение — `<string>` или `<script block>`</span><span class="sxs-lookup"><span data-stu-id="945a3-168">Expression - `<string>` or `<script block>`</span></span>
- <span data-ttu-id="945a3-169">FormatString `<string>`</span><span class="sxs-lookup"><span data-stu-id="945a3-169">FormatString - `<string>`</span></span>

<span data-ttu-id="945a3-170">Дополнительные сведения см. в разделе [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span><span class="sxs-lookup"><span data-stu-id="945a3-170">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="945a3-171">-ShowError</span><span class="sxs-lookup"><span data-stu-id="945a3-171">-ShowError</span></span>

<span data-ttu-id="945a3-172">Отправляет ошибки по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="945a3-172">Sends errors through the pipeline.</span></span> <span data-ttu-id="945a3-173">Этот параметр редко используется, но его можно использовать в качестве вспомогательного средства отладки при форматировании выражений в `Format-Wide` команде, и выражения не работают.</span><span class="sxs-lookup"><span data-stu-id="945a3-173">This parameter is rarely used, but can be used as a debugging aid when you are formatting expressions in a `Format-Wide` command, and the expressions do not appear to be working.</span></span>

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

### <span data-ttu-id="945a3-174">-View</span><span class="sxs-lookup"><span data-stu-id="945a3-174">-View</span></span>

<span data-ttu-id="945a3-175">Указывает имя альтернативного формата таблицы или представления.</span><span class="sxs-lookup"><span data-stu-id="945a3-175">Specifies the name of an alternate table format or view.</span></span> <span data-ttu-id="945a3-176">Нельзя использовать **Свойства** и параметры **представления** в одной команде.</span><span class="sxs-lookup"><span data-stu-id="945a3-176">You cannot use the **Property** and **View** parameters in the same command.</span></span>

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

### <span data-ttu-id="945a3-177">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="945a3-177">CommonParameters</span></span>

<span data-ttu-id="945a3-178">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="945a3-178">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="945a3-179">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="945a3-179">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="945a3-180">Входные данные</span><span class="sxs-lookup"><span data-stu-id="945a3-180">INPUTS</span></span>

### <span data-ttu-id="945a3-181">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="945a3-181">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="945a3-182">Любой объект можно передать по конвейеру в `Format-Wide` .</span><span class="sxs-lookup"><span data-stu-id="945a3-182">You can pipe any object to `Format-Wide`.</span></span>

## <span data-ttu-id="945a3-183">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="945a3-183">OUTPUTS</span></span>

### <span data-ttu-id="945a3-184">Microsoft.PowerShell.Commands.Internal.Format</span><span class="sxs-lookup"><span data-stu-id="945a3-184">Microsoft.PowerShell.Commands.Internal.Format</span></span>

<span data-ttu-id="945a3-185">`Format-Wide` Возвращает объекты форматирования, представляющие таблицу.</span><span class="sxs-lookup"><span data-stu-id="945a3-185">`Format-Wide` returns format objects that represent the table.</span></span>

## <span data-ttu-id="945a3-186">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="945a3-186">NOTES</span></span>

<span data-ttu-id="945a3-187">Также можно ссылаться `Format-Wide` по встроенному псевдониму `fw` .</span><span class="sxs-lookup"><span data-stu-id="945a3-187">You can also refer to `Format-Wide` by its built-in alias, `fw`.</span></span> <span data-ttu-id="945a3-188">Дополнительные сведения см. в разделе [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="945a3-188">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>

<span data-ttu-id="945a3-189">Параметр **GroupBy** предполагает, что объекты сортируются.</span><span class="sxs-lookup"><span data-stu-id="945a3-189">The **GroupBy** parameter assumes that the objects are sorted.</span></span> <span data-ttu-id="945a3-190">Используйте `Sort-Object` перед использованием `Format-Custom` для группирования объектов.</span><span class="sxs-lookup"><span data-stu-id="945a3-190">Use `Sort-Object` before using `Format-Custom` to group the objects.</span></span>

<span data-ttu-id="945a3-191">Параметр **View** позволяет указать альтернативный формат для таблицы.</span><span class="sxs-lookup"><span data-stu-id="945a3-191">The **View** parameter lets you specify an alternate format for the table.</span></span> <span data-ttu-id="945a3-192">Вы можете использовать представления, определенные в `*.format.PS1XML` файлах в каталоге PowerShell, или создать собственные представления в новых файлах ps1xml и использовать `Update-FormatData` командлет для их включения в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="945a3-192">You can use the views defined in the `*.format.PS1XML` files in the PowerShell directory or you can create your own views in new PS1XML files and use the `Update-FormatData` cmdlet to include them in PowerShell.</span></span>

<span data-ttu-id="945a3-193">Альтернативное представление для параметра **представления** должно использовать формат таблицы. в противном случае команда завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="945a3-193">The alternate view for the **View** parameter must use table format; if it does not, the command fails.</span></span> <span data-ttu-id="945a3-194">Если альтернативное представление является списком, используйте `Format-List` .</span><span class="sxs-lookup"><span data-stu-id="945a3-194">If the alternate view is a list, use `Format-List`.</span></span> <span data-ttu-id="945a3-195">Если альтернативное представление не является ни списком, ни таблицей, используйте командлет Format-Custom.</span><span class="sxs-lookup"><span data-stu-id="945a3-195">If the alternate view is neither a list nor a table, use Format-Custom.</span></span>

## <span data-ttu-id="945a3-196">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="945a3-196">RELATED LINKS</span></span>

[<span data-ttu-id="945a3-197">about_Calculated_Properties</span><span class="sxs-lookup"><span data-stu-id="945a3-197">about_Calculated_Properties</span></span>](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[<span data-ttu-id="945a3-198">Format-Custom</span><span class="sxs-lookup"><span data-stu-id="945a3-198">Format-Custom</span></span>](Format-Custom.md)

[<span data-ttu-id="945a3-199">Format-Hex</span><span class="sxs-lookup"><span data-stu-id="945a3-199">Format-Hex</span></span>](Format-Hex.md)

[<span data-ttu-id="945a3-200">Format-List</span><span class="sxs-lookup"><span data-stu-id="945a3-200">Format-List</span></span>](Format-List.md)

[<span data-ttu-id="945a3-201">Format-Table</span><span class="sxs-lookup"><span data-stu-id="945a3-201">Format-Table</span></span>](Format-Table.md)
