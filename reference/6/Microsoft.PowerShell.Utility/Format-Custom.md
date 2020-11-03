---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/format-custom?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Format-Custom
ms.openlocfilehash: 28914b86c86d5c16f09c81a5dc70ed1e05123b3e
ms.sourcegitcommit: 9a6b6714ded4edb5119f1b82a253608018ea6b98
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/10/2020
ms.locfileid: "93230290"
---
# <span data-ttu-id="40040-103">Format-Custom</span><span class="sxs-lookup"><span data-stu-id="40040-103">Format-Custom</span></span>

## <span data-ttu-id="40040-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="40040-104">SYNOPSIS</span></span>
<span data-ttu-id="40040-105">Использует пользовательское представление для форматирования выходных данных.</span><span class="sxs-lookup"><span data-stu-id="40040-105">Uses a customized view to format the output.</span></span>

## <span data-ttu-id="40040-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="40040-106">SYNTAX</span></span>

```
Format-Custom [[-Property] <Object[]>] [-Depth <Int32>] [-GroupBy <Object>] [-View <String>]
 [-ShowError] [-DisplayError] [-Force] [-Expand <String>] [-InputObject <PSObject>]
 [<CommonParameters>]
```

## <span data-ttu-id="40040-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="40040-107">DESCRIPTION</span></span>

<span data-ttu-id="40040-108">`Format-Custom`Командлет форматирует выходные данные команды, как определено в альтернативном представлении.</span><span class="sxs-lookup"><span data-stu-id="40040-108">The `Format-Custom` cmdlet formats the output of a command as defined in an alternate view.</span></span>
<span data-ttu-id="40040-109">`Format-Custom` предназначен для отображения представлений, которые не просто являются таблицами или просто списками.</span><span class="sxs-lookup"><span data-stu-id="40040-109">`Format-Custom` is designed to display views that are not just tables or just lists.</span></span> <span data-ttu-id="40040-110">Можно использовать представления, определенные в PowerShell, или создать собственные представления в новом `format.ps1xml` файле и `Update-FormatData` добавить их в PowerShell с помощью командлета.</span><span class="sxs-lookup"><span data-stu-id="40040-110">You can use the views defined in PowerShell, or you can create your own views in a new `format.ps1xml` file and use the `Update-FormatData` cmdlet to add them to PowerShell.</span></span>

## <span data-ttu-id="40040-111">Примеры</span><span class="sxs-lookup"><span data-stu-id="40040-111">EXAMPLES</span></span>

### <span data-ttu-id="40040-112">Пример 1. Форматирование выходных данных с помощью пользовательского представления</span><span class="sxs-lookup"><span data-stu-id="40040-112">Example 1: Format output with a custom view</span></span>

```powershell
Get-Command Start-Transcript | Format-Custom -View MyView
```

<span data-ttu-id="40040-113">Эта команда форматирует сведения о `Start-Transcript` командлете в формате, определенном представлением MyView, настраиваемым представлением, созданным пользователем.</span><span class="sxs-lookup"><span data-stu-id="40040-113">This command formats information about the `Start-Transcript` cmdlet in the format defined by the MyView view, a custom view created by the user.</span></span> <span data-ttu-id="40040-114">Чтобы успешно выполнить эту команду, необходимо сначала создать новый файл PS1XML, определить представление **MyView** , а затем использовать `Update-FormatData` команду, чтобы добавить файл ps1xml в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="40040-114">To run this command successfully, you must first create a new PS1XML file, define the **MyView** view, and then use the `Update-FormatData` command to add the PS1XML file to PowerShell.</span></span>

### <span data-ttu-id="40040-115">Пример 2. Форматирование выходных данных с помощью представления по умолчанию</span><span class="sxs-lookup"><span data-stu-id="40040-115">Example 2: Format output with the default view</span></span>

```powershell
Get-Process Winlogon | Format-Custom
```

<span data-ttu-id="40040-116">Эта команда форматирует сведения о процессе **Winlogon** в альтернативном настраиваемом представлении.</span><span class="sxs-lookup"><span data-stu-id="40040-116">This command formats information about the **Winlogon** process in an alternate customized view.</span></span>
<span data-ttu-id="40040-117">Поскольку команда не использует параметр **View** , `Format-Custom` использует пользовательское представление по умолчанию для форматирования данных.</span><span class="sxs-lookup"><span data-stu-id="40040-117">Because the command does not use the **View** parameter, `Format-Custom` uses a default custom view to format the data.</span></span>

### <span data-ttu-id="40040-118">Пример 3. Устранение ошибок формата</span><span class="sxs-lookup"><span data-stu-id="40040-118">Example 3: Troubleshooting format errors</span></span>

<span data-ttu-id="40040-119">В следующих примерах показаны результаты добавления параметров **DisplayError** или **ShowError** в выражение.</span><span class="sxs-lookup"><span data-stu-id="40040-119">The following examples show of the results of adding the **DisplayError** or **ShowError** parameters with an expression.</span></span>

```powershell
PC /> Get-Date | Format-Custom DayOfWeek,{ $_ / $null } -DisplayError

class DateTime
{
  DayOfWeek = Friday
   $_ / $null  = #ERR
}


PC /> Get-Date | Format-Custom DayOfWeek,{ $_ / $null } -ShowError

class DateTime
{
  DayOfWeek = Friday
   $_ / $null  =
}

Failed to evaluate expression " $_ / $null ".
+ CategoryInfo          : InvalidArgument: (12/21/2018 8:01:04 AM:PSObject) [], RuntimeException
+ FullyQualifiedErrorId : PSPropertyExpressionError
```

## <span data-ttu-id="40040-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="40040-120">PARAMETERS</span></span>

### <span data-ttu-id="40040-121">-Depth</span><span class="sxs-lookup"><span data-stu-id="40040-121">-Depth</span></span>

<span data-ttu-id="40040-122">Задает количество столбцов в отображаемых данных.</span><span class="sxs-lookup"><span data-stu-id="40040-122">Specifies the number of columns in the display.</span></span>

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

### <span data-ttu-id="40040-123">-DisplayError</span><span class="sxs-lookup"><span data-stu-id="40040-123">-DisplayError</span></span>

<span data-ttu-id="40040-124">Отображает сообщения об ошибках в командной строке.</span><span class="sxs-lookup"><span data-stu-id="40040-124">Displays errors at the command line.</span></span> <span data-ttu-id="40040-125">Этот параметр редко используется, но его можно использовать в качестве вспомогательного средства отладки при форматировании выражений в `Format-Custom` команде, и выражения не работают.</span><span class="sxs-lookup"><span data-stu-id="40040-125">This parameter is rarely used, but can be used as a debugging aid when you are formatting expressions in a `Format-Custom` command, and the expressions do not appear to be working.</span></span>

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

### <span data-ttu-id="40040-126">-Expand</span><span class="sxs-lookup"><span data-stu-id="40040-126">-Expand</span></span>

<span data-ttu-id="40040-127">Форматирует объект коллекции, а также объекты, содержащиеся в коллекции.</span><span class="sxs-lookup"><span data-stu-id="40040-127">Formats the collection object, as well as the objects in the collection.</span></span> <span data-ttu-id="40040-128">Этот параметр предназначен для форматирования объектов, поддерживающих интерфейс **System. Collections. ICollection** .</span><span class="sxs-lookup"><span data-stu-id="40040-128">This parameter is designed to format objects that support the **System.Collections.ICollection** interface.</span></span> <span data-ttu-id="40040-129">Значение по умолчанию — **енумонли** .</span><span class="sxs-lookup"><span data-stu-id="40040-129">The default value is **EnumOnly** .</span></span>

<span data-ttu-id="40040-130">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="40040-130">Valid values are:</span></span>

- <span data-ttu-id="40040-131">EnumOnly — отображаются свойства объектов в коллекции.</span><span class="sxs-lookup"><span data-stu-id="40040-131">EnumOnly: Displays the properties of the objects in the collection.</span></span>
- <span data-ttu-id="40040-132">CoreOnly — отображаются свойства объекта коллекции.</span><span class="sxs-lookup"><span data-stu-id="40040-132">CoreOnly: Displays the properties of the collection object.</span></span>
- <span data-ttu-id="40040-133">Оба: отображает свойства объекта коллекции и объекты в коллекции.</span><span class="sxs-lookup"><span data-stu-id="40040-133">Both: Displays the properties of the collection object and the objects in the collection.</span></span>

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

### <span data-ttu-id="40040-134">-Force</span><span class="sxs-lookup"><span data-stu-id="40040-134">-Force</span></span>

<span data-ttu-id="40040-135">Заставляет командлет отображать полные сведения об ошибках.</span><span class="sxs-lookup"><span data-stu-id="40040-135">Directs the cmdlet to display all of the error information.</span></span> <span data-ttu-id="40040-136">Используйте с параметрами **DisplayError** или **ShowError** .</span><span class="sxs-lookup"><span data-stu-id="40040-136">Use with the **DisplayError** or **ShowError** parameters.</span></span> <span data-ttu-id="40040-137">По умолчанию при записи объекта ошибки в поток ошибок или поток отображения отображаются только некоторые сведения об ошибке.</span><span class="sxs-lookup"><span data-stu-id="40040-137">By default, when an error object is written to the error or display streams, only some of the error information is displayed.</span></span>

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

### <span data-ttu-id="40040-138">-GroupBy</span><span class="sxs-lookup"><span data-stu-id="40040-138">-GroupBy</span></span>

<span data-ttu-id="40040-139">Форматирует вывод в группы на основе общего свойства или значения.</span><span class="sxs-lookup"><span data-stu-id="40040-139">Formats the output in groups based on a shared property or value.</span></span> <span data-ttu-id="40040-140">Введите выражение или свойство вывода.</span><span class="sxs-lookup"><span data-stu-id="40040-140">Enter an expression or a property of the output.</span></span>

<span data-ttu-id="40040-141">Значением параметра **GroupBy** может быть новое вычисляемое свойство.</span><span class="sxs-lookup"><span data-stu-id="40040-141">The value of the **GroupBy** parameter can be a new calculated property.</span></span> <span data-ttu-id="40040-142">Вычисляемое свойство может быть блоком скрипта или хэш-таблицей.</span><span class="sxs-lookup"><span data-stu-id="40040-142">The calculated property can be a script block or a hash table.</span></span> <span data-ttu-id="40040-143">Допустимые пары "ключ-значение":</span><span class="sxs-lookup"><span data-stu-id="40040-143">Valid key-value pairs are:</span></span>

- <span data-ttu-id="40040-144">Имя (или метка) — `<string>`</span><span class="sxs-lookup"><span data-stu-id="40040-144">Name (or Label) - `<string>`</span></span>
- <span data-ttu-id="40040-145">Выражение — `<string>` или `<script block>`</span><span class="sxs-lookup"><span data-stu-id="40040-145">Expression - `<string>` or `<script block>`</span></span>
- <span data-ttu-id="40040-146">FormatString `<string>`</span><span class="sxs-lookup"><span data-stu-id="40040-146">FormatString - `<string>`</span></span>

<span data-ttu-id="40040-147">Дополнительные сведения см. в разделе [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span><span class="sxs-lookup"><span data-stu-id="40040-147">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

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

### <span data-ttu-id="40040-148">-InputObject</span><span class="sxs-lookup"><span data-stu-id="40040-148">-InputObject</span></span>

<span data-ttu-id="40040-149">Задает объекты, подлежащие форматированию.</span><span class="sxs-lookup"><span data-stu-id="40040-149">Specifies the objects to be formatted.</span></span> <span data-ttu-id="40040-150">Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты.</span><span class="sxs-lookup"><span data-stu-id="40040-150">Enter a variable that contains the objects or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="40040-151">-Property</span><span class="sxs-lookup"><span data-stu-id="40040-151">-Property</span></span>

<span data-ttu-id="40040-152">Задает свойства объекта, которые будут включены в вывод, и порядок их вывода.</span><span class="sxs-lookup"><span data-stu-id="40040-152">Specifies the object properties that appear in the display and the order in which they appear.</span></span>
<span data-ttu-id="40040-153">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="40040-153">Wildcards are permitted.</span></span>

<span data-ttu-id="40040-154">Если этот параметр не указан, свойства включаются в вывод в зависимости от отображаемого объекта.</span><span class="sxs-lookup"><span data-stu-id="40040-154">If you omit this parameter, the properties that appear in the display depend on the object being displayed.</span></span> <span data-ttu-id="40040-155">**Свойство** имени параметра является необязательным.</span><span class="sxs-lookup"><span data-stu-id="40040-155">The parameter name **Property** is optional.</span></span> <span data-ttu-id="40040-156">Нельзя использовать **Свойства** и параметры **представления** в одной команде.</span><span class="sxs-lookup"><span data-stu-id="40040-156">You cannot use the **Property** and **View** parameters in the same command.</span></span>

<span data-ttu-id="40040-157">Значением параметра **Property** может быть новое вычисляемое свойство.</span><span class="sxs-lookup"><span data-stu-id="40040-157">The value of the **Property** parameter can be a new calculated property.</span></span> <span data-ttu-id="40040-158">Вычисляемое свойство может быть блоком скрипта или хэш-таблицей.</span><span class="sxs-lookup"><span data-stu-id="40040-158">The calculated property can be a script block or a hash table.</span></span> <span data-ttu-id="40040-159">Допустимые пары "ключ-значение":</span><span class="sxs-lookup"><span data-stu-id="40040-159">Valid key-value pairs are:</span></span>

- <span data-ttu-id="40040-160">Выражение — `<string>` или `<script block>`</span><span class="sxs-lookup"><span data-stu-id="40040-160">Expression - `<string>` or `<script block>`</span></span>
- <span data-ttu-id="40040-161">Длина `<int32>`</span><span class="sxs-lookup"><span data-stu-id="40040-161">Depth - `<int32>`</span></span>

<span data-ttu-id="40040-162">Дополнительные сведения см. в разделе [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span><span class="sxs-lookup"><span data-stu-id="40040-162">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="40040-163">-ShowError</span><span class="sxs-lookup"><span data-stu-id="40040-163">-ShowError</span></span>

<span data-ttu-id="40040-164">Отправляет ошибки по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="40040-164">Sends errors through the pipeline.</span></span> <span data-ttu-id="40040-165">Этот параметр редко используется, но его можно использовать в качестве вспомогательного средства отладки при форматировании выражений в `Format-Custom` команде, и выражения не работают.</span><span class="sxs-lookup"><span data-stu-id="40040-165">This parameter is rarely used, but can be used as a debugging aid when you are formatting expressions in a `Format-Custom` command, and the expressions do not appear to be working.</span></span>

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

### <span data-ttu-id="40040-166">-View</span><span class="sxs-lookup"><span data-stu-id="40040-166">-View</span></span>

<span data-ttu-id="40040-167">Указывает имя альтернативного формата или представления.</span><span class="sxs-lookup"><span data-stu-id="40040-167">Specifies the name of an alternate format or view.</span></span> <span data-ttu-id="40040-168">Если опустить этот параметр, `Format-Custom` использует настраиваемое представление по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="40040-168">If you omit this parameter, `Format-Custom` uses a default custom view.</span></span> <span data-ttu-id="40040-169">Нельзя использовать **Свойства** и параметры **представления** в одной команде.</span><span class="sxs-lookup"><span data-stu-id="40040-169">You cannot use the **Property** and **View** parameters in the same command.</span></span>

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

### <span data-ttu-id="40040-170">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="40040-170">CommonParameters</span></span>

<span data-ttu-id="40040-171">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="40040-171">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="40040-172">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="40040-172">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="40040-173">Входные данные</span><span class="sxs-lookup"><span data-stu-id="40040-173">INPUTS</span></span>

### <span data-ttu-id="40040-174">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="40040-174">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="40040-175">Любой объект можно передать по конвейеру в `Format-Custom` .</span><span class="sxs-lookup"><span data-stu-id="40040-175">You can pipe any object to `Format-Custom`.</span></span>

## <span data-ttu-id="40040-176">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="40040-176">OUTPUTS</span></span>

### <span data-ttu-id="40040-177">Microsoft.PowerShell.Commands.Internal.Format</span><span class="sxs-lookup"><span data-stu-id="40040-177">Microsoft.PowerShell.Commands.Internal.Format</span></span>

<span data-ttu-id="40040-178">`Format-Custom` Возвращает объекты формата, представляющие отображение.</span><span class="sxs-lookup"><span data-stu-id="40040-178">`Format-Custom` returns the format objects that represent the display.</span></span>

## <span data-ttu-id="40040-179">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="40040-179">NOTES</span></span>

<span data-ttu-id="40040-180">`Format-Custom` предназначен для отображения представлений, которые не просто являются таблицами или просто списками.</span><span class="sxs-lookup"><span data-stu-id="40040-180">`Format-Custom` is designed to display views that are not just tables or just lists.</span></span> <span data-ttu-id="40040-181">Чтобы отобразить альтернативное табличное представление, используйте `Format-Table` .</span><span class="sxs-lookup"><span data-stu-id="40040-181">To display an alternate table view, use `Format-Table`.</span></span> <span data-ttu-id="40040-182">Чтобы отобразить альтернативное представление списка, используйте `Format-List` .</span><span class="sxs-lookup"><span data-stu-id="40040-182">To display an alternate list view, use `Format-List`.</span></span>

<span data-ttu-id="40040-183">Также можно ссылаться `Format-Custom` по встроенному псевдониму `fc` .</span><span class="sxs-lookup"><span data-stu-id="40040-183">You can also refer to `Format-Custom` by its built-in alias, `fc`.</span></span> <span data-ttu-id="40040-184">Дополнительные сведения см. в разделе [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="40040-184">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>

<span data-ttu-id="40040-185">Параметр **GroupBy** предполагает, что объекты сортируются.</span><span class="sxs-lookup"><span data-stu-id="40040-185">The **GroupBy** parameter assumes that the objects are sorted.</span></span> <span data-ttu-id="40040-186">Перед использованием `Format-Custom` для группирования объектов используйте `Sort-Object` для сортировки.</span><span class="sxs-lookup"><span data-stu-id="40040-186">Before using `Format-Custom` to group the objects, use `Sort-Object` to sort them.</span></span>

## <span data-ttu-id="40040-187">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="40040-187">RELATED LINKS</span></span>

[<span data-ttu-id="40040-188">about_Calculated_Properties</span><span class="sxs-lookup"><span data-stu-id="40040-188">about_Calculated_Properties</span></span>](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[<span data-ttu-id="40040-189">Format-Hex</span><span class="sxs-lookup"><span data-stu-id="40040-189">Format-Hex</span></span>](Format-Hex.md)

[<span data-ttu-id="40040-190">Format-List</span><span class="sxs-lookup"><span data-stu-id="40040-190">Format-List</span></span>](Format-List.md)

[<span data-ttu-id="40040-191">Format-Table</span><span class="sxs-lookup"><span data-stu-id="40040-191">Format-Table</span></span>](Format-Table.md)

[<span data-ttu-id="40040-192">Format-Wide</span><span class="sxs-lookup"><span data-stu-id="40040-192">Format-Wide</span></span>](Format-Wide.md)

[<span data-ttu-id="40040-193">Get-Process</span><span class="sxs-lookup"><span data-stu-id="40040-193">Get-Process</span></span>](../Microsoft.PowerShell.Management/Get-Process.md)
