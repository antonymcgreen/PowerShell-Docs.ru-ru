---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/format-custom?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Format-Custom
ms.openlocfilehash: ff4b2dda3f12fa34fc518c6a180f3213ba873d90
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601879"
---
# <span data-ttu-id="b9741-102">Format-Custom</span><span class="sxs-lookup"><span data-stu-id="b9741-102">Format-Custom</span></span>

## <span data-ttu-id="b9741-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="b9741-103">SYNOPSIS</span></span>
<span data-ttu-id="b9741-104">Использует пользовательское представление для форматирования выходных данных.</span><span class="sxs-lookup"><span data-stu-id="b9741-104">Uses a customized view to format the output.</span></span>

## <span data-ttu-id="b9741-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b9741-105">SYNTAX</span></span>

```
Format-Custom [[-Property] <Object[]>] [-Depth <Int32>] [-GroupBy <Object>] [-View <String>]
 [-ShowError] [-DisplayError] [-Force] [-Expand <String>] [-InputObject <PSObject>]
 [<CommonParameters>]
```

## <span data-ttu-id="b9741-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b9741-106">DESCRIPTION</span></span>

<span data-ttu-id="b9741-107">`Format-Custom`Командлет форматирует выходные данные команды, как определено в альтернативном представлении.</span><span class="sxs-lookup"><span data-stu-id="b9741-107">The `Format-Custom` cmdlet formats the output of a command as defined in an alternate view.</span></span>
<span data-ttu-id="b9741-108">`Format-Custom` предназначен для отображения представлений, которые не просто являются таблицами или просто списками.</span><span class="sxs-lookup"><span data-stu-id="b9741-108">`Format-Custom` is designed to display views that are not just tables or just lists.</span></span> <span data-ttu-id="b9741-109">Можно использовать представления, определенные в PowerShell, или создать собственные представления в новом `format.ps1xml` файле и `Update-FormatData` добавить их в PowerShell с помощью командлета.</span><span class="sxs-lookup"><span data-stu-id="b9741-109">You can use the views defined in PowerShell, or you can create your own views in a new `format.ps1xml` file and use the `Update-FormatData` cmdlet to add them to PowerShell.</span></span>

## <span data-ttu-id="b9741-110">Примеры</span><span class="sxs-lookup"><span data-stu-id="b9741-110">EXAMPLES</span></span>

### <span data-ttu-id="b9741-111">Пример 1. Форматирование выходных данных с помощью пользовательского представления</span><span class="sxs-lookup"><span data-stu-id="b9741-111">Example 1: Format output with a custom view</span></span>

```powershell
Get-Command Start-Transcript | Format-Custom -View MyView
```

<span data-ttu-id="b9741-112">Эта команда форматирует сведения о `Start-Transcript` командлете в формате, определенном представлением MyView, настраиваемым представлением, созданным пользователем.</span><span class="sxs-lookup"><span data-stu-id="b9741-112">This command formats information about the `Start-Transcript` cmdlet in the format defined by the MyView view, a custom view created by the user.</span></span> <span data-ttu-id="b9741-113">Чтобы успешно выполнить эту команду, необходимо сначала создать новый файл PS1XML, определить представление **MyView** , а затем использовать `Update-FormatData` команду, чтобы добавить файл ps1xml в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b9741-113">To run this command successfully, you must first create a new PS1XML file, define the **MyView** view, and then use the `Update-FormatData` command to add the PS1XML file to PowerShell.</span></span>

### <span data-ttu-id="b9741-114">Пример 2. Форматирование выходных данных с помощью представления по умолчанию</span><span class="sxs-lookup"><span data-stu-id="b9741-114">Example 2: Format output with the default view</span></span>

```powershell
Get-Process Winlogon | Format-Custom
```

<span data-ttu-id="b9741-115">Эта команда форматирует сведения о процессе **Winlogon** в альтернативном настраиваемом представлении.</span><span class="sxs-lookup"><span data-stu-id="b9741-115">This command formats information about the **Winlogon** process in an alternate customized view.</span></span>
<span data-ttu-id="b9741-116">Поскольку команда не использует параметр **View** , `Format-Custom` использует пользовательское представление по умолчанию для форматирования данных.</span><span class="sxs-lookup"><span data-stu-id="b9741-116">Because the command does not use the **View** parameter, `Format-Custom` uses a default custom view to format the data.</span></span>

### <span data-ttu-id="b9741-117">Пример 3. Устранение ошибок формата</span><span class="sxs-lookup"><span data-stu-id="b9741-117">Example 3: Troubleshooting format errors</span></span>

<span data-ttu-id="b9741-118">В следующих примерах показаны результаты добавления параметров **DisplayError** или **ShowError** в выражение.</span><span class="sxs-lookup"><span data-stu-id="b9741-118">The following examples show of the results of adding the **DisplayError** or **ShowError** parameters with an expression.</span></span>

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

## <span data-ttu-id="b9741-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b9741-119">PARAMETERS</span></span>

### <span data-ttu-id="b9741-120">-Depth</span><span class="sxs-lookup"><span data-stu-id="b9741-120">-Depth</span></span>

<span data-ttu-id="b9741-121">Задает количество столбцов в отображаемых данных.</span><span class="sxs-lookup"><span data-stu-id="b9741-121">Specifies the number of columns in the display.</span></span>

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

### <span data-ttu-id="b9741-122">-DisplayError</span><span class="sxs-lookup"><span data-stu-id="b9741-122">-DisplayError</span></span>

<span data-ttu-id="b9741-123">Отображает сообщения об ошибках в командной строке.</span><span class="sxs-lookup"><span data-stu-id="b9741-123">Displays errors at the command line.</span></span> <span data-ttu-id="b9741-124">Этот параметр редко используется, но его можно использовать в качестве вспомогательного средства отладки при форматировании выражений в `Format-Custom` команде, и выражения не работают.</span><span class="sxs-lookup"><span data-stu-id="b9741-124">This parameter is rarely used, but can be used as a debugging aid when you are formatting expressions in a `Format-Custom` command, and the expressions do not appear to be working.</span></span>

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

### <span data-ttu-id="b9741-125">-Expand</span><span class="sxs-lookup"><span data-stu-id="b9741-125">-Expand</span></span>

<span data-ttu-id="b9741-126">Форматирует объект коллекции, а также объекты, содержащиеся в коллекции.</span><span class="sxs-lookup"><span data-stu-id="b9741-126">Formats the collection object, as well as the objects in the collection.</span></span> <span data-ttu-id="b9741-127">Этот параметр предназначен для форматирования объектов, поддерживающих интерфейс **System. Collections. ICollection** .</span><span class="sxs-lookup"><span data-stu-id="b9741-127">This parameter is designed to format objects that support the **System.Collections.ICollection** interface.</span></span> <span data-ttu-id="b9741-128">Значение по умолчанию — **енумонли**.</span><span class="sxs-lookup"><span data-stu-id="b9741-128">The default value is **EnumOnly**.</span></span>

<span data-ttu-id="b9741-129">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="b9741-129">Valid values are:</span></span>

- <span data-ttu-id="b9741-130">EnumOnly — отображаются свойства объектов в коллекции.</span><span class="sxs-lookup"><span data-stu-id="b9741-130">EnumOnly: Displays the properties of the objects in the collection.</span></span>
- <span data-ttu-id="b9741-131">CoreOnly — отображаются свойства объекта коллекции.</span><span class="sxs-lookup"><span data-stu-id="b9741-131">CoreOnly: Displays the properties of the collection object.</span></span>
- <span data-ttu-id="b9741-132">Оба: отображает свойства объекта коллекции и объекты в коллекции.</span><span class="sxs-lookup"><span data-stu-id="b9741-132">Both: Displays the properties of the collection object and the objects in the collection.</span></span>

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

### <span data-ttu-id="b9741-133">-Force</span><span class="sxs-lookup"><span data-stu-id="b9741-133">-Force</span></span>

<span data-ttu-id="b9741-134">Заставляет командлет отображать полные сведения об ошибках.</span><span class="sxs-lookup"><span data-stu-id="b9741-134">Directs the cmdlet to display all of the error information.</span></span> <span data-ttu-id="b9741-135">Используйте с параметрами **DisplayError** или **ShowError** .</span><span class="sxs-lookup"><span data-stu-id="b9741-135">Use with the **DisplayError** or **ShowError** parameters.</span></span> <span data-ttu-id="b9741-136">По умолчанию при записи объекта ошибки в поток ошибок или поток отображения отображаются только некоторые сведения об ошибке.</span><span class="sxs-lookup"><span data-stu-id="b9741-136">By default, when an error object is written to the error or display streams, only some of the error information is displayed.</span></span>

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

### <span data-ttu-id="b9741-137">-GroupBy</span><span class="sxs-lookup"><span data-stu-id="b9741-137">-GroupBy</span></span>

<span data-ttu-id="b9741-138">Форматирует вывод в группы на основе общего свойства или значения.</span><span class="sxs-lookup"><span data-stu-id="b9741-138">Formats the output in groups based on a shared property or value.</span></span> <span data-ttu-id="b9741-139">Введите выражение или свойство вывода.</span><span class="sxs-lookup"><span data-stu-id="b9741-139">Enter an expression or a property of the output.</span></span>

<span data-ttu-id="b9741-140">Значением параметра **GroupBy** может быть новое вычисляемое свойство.</span><span class="sxs-lookup"><span data-stu-id="b9741-140">The value of the **GroupBy** parameter can be a new calculated property.</span></span> <span data-ttu-id="b9741-141">Вычисляемое свойство может быть блоком скрипта или хэш-таблицей.</span><span class="sxs-lookup"><span data-stu-id="b9741-141">The calculated property can be a script block or a hash table.</span></span> <span data-ttu-id="b9741-142">Допустимые пары "ключ-значение":</span><span class="sxs-lookup"><span data-stu-id="b9741-142">Valid key-value pairs are:</span></span>

- <span data-ttu-id="b9741-143">Имя (или метка) — `<string>`</span><span class="sxs-lookup"><span data-stu-id="b9741-143">Name (or Label) - `<string>`</span></span>
- <span data-ttu-id="b9741-144">Выражение — `<string>` или `<script block>`</span><span class="sxs-lookup"><span data-stu-id="b9741-144">Expression - `<string>` or `<script block>`</span></span>
- <span data-ttu-id="b9741-145">FormatString `<string>`</span><span class="sxs-lookup"><span data-stu-id="b9741-145">FormatString - `<string>`</span></span>

<span data-ttu-id="b9741-146">Дополнительные сведения см. в разделе [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span><span class="sxs-lookup"><span data-stu-id="b9741-146">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

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

### <span data-ttu-id="b9741-147">-InputObject</span><span class="sxs-lookup"><span data-stu-id="b9741-147">-InputObject</span></span>

<span data-ttu-id="b9741-148">Задает объекты, подлежащие форматированию.</span><span class="sxs-lookup"><span data-stu-id="b9741-148">Specifies the objects to be formatted.</span></span> <span data-ttu-id="b9741-149">Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты.</span><span class="sxs-lookup"><span data-stu-id="b9741-149">Enter a variable that contains the objects or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="b9741-150">-Property</span><span class="sxs-lookup"><span data-stu-id="b9741-150">-Property</span></span>

<span data-ttu-id="b9741-151">Задает свойства объекта, которые будут включены в вывод, и порядок их вывода.</span><span class="sxs-lookup"><span data-stu-id="b9741-151">Specifies the object properties that appear in the display and the order in which they appear.</span></span>
<span data-ttu-id="b9741-152">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="b9741-152">Wildcards are permitted.</span></span>

<span data-ttu-id="b9741-153">Если этот параметр не указан, свойства включаются в вывод в зависимости от отображаемого объекта.</span><span class="sxs-lookup"><span data-stu-id="b9741-153">If you omit this parameter, the properties that appear in the display depend on the object being displayed.</span></span> <span data-ttu-id="b9741-154">**Свойство** имени параметра является необязательным.</span><span class="sxs-lookup"><span data-stu-id="b9741-154">The parameter name **Property** is optional.</span></span> <span data-ttu-id="b9741-155">Нельзя использовать **Свойства** и параметры **представления** в одной команде.</span><span class="sxs-lookup"><span data-stu-id="b9741-155">You cannot use the **Property** and **View** parameters in the same command.</span></span>

<span data-ttu-id="b9741-156">Значением параметра **Property** может быть новое вычисляемое свойство.</span><span class="sxs-lookup"><span data-stu-id="b9741-156">The value of the **Property** parameter can be a new calculated property.</span></span> <span data-ttu-id="b9741-157">Вычисляемое свойство может быть блоком скрипта или хэш-таблицей.</span><span class="sxs-lookup"><span data-stu-id="b9741-157">The calculated property can be a script block or a hash table.</span></span> <span data-ttu-id="b9741-158">Допустимые пары "ключ-значение":</span><span class="sxs-lookup"><span data-stu-id="b9741-158">Valid key-value pairs are:</span></span>

- <span data-ttu-id="b9741-159">Выражение — `<string>` или `<script block>`</span><span class="sxs-lookup"><span data-stu-id="b9741-159">Expression - `<string>` or `<script block>`</span></span>
- <span data-ttu-id="b9741-160">Длина `<int32>`</span><span class="sxs-lookup"><span data-stu-id="b9741-160">Depth - `<int32>`</span></span>

<span data-ttu-id="b9741-161">Дополнительные сведения см. в разделе [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span><span class="sxs-lookup"><span data-stu-id="b9741-161">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

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

### <span data-ttu-id="b9741-162">-ShowError</span><span class="sxs-lookup"><span data-stu-id="b9741-162">-ShowError</span></span>

<span data-ttu-id="b9741-163">Отправляет ошибки по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="b9741-163">Sends errors through the pipeline.</span></span> <span data-ttu-id="b9741-164">Этот параметр редко используется, но его можно использовать в качестве вспомогательного средства отладки при форматировании выражений в `Format-Custom` команде, и выражения не работают.</span><span class="sxs-lookup"><span data-stu-id="b9741-164">This parameter is rarely used, but can be used as a debugging aid when you are formatting expressions in a `Format-Custom` command, and the expressions do not appear to be working.</span></span>

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

### <span data-ttu-id="b9741-165">-View</span><span class="sxs-lookup"><span data-stu-id="b9741-165">-View</span></span>

<span data-ttu-id="b9741-166">Указывает имя альтернативного формата или представления.</span><span class="sxs-lookup"><span data-stu-id="b9741-166">Specifies the name of an alternate format or view.</span></span> <span data-ttu-id="b9741-167">Если опустить этот параметр, `Format-Custom` использует настраиваемое представление по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b9741-167">If you omit this parameter, `Format-Custom` uses a default custom view.</span></span> <span data-ttu-id="b9741-168">Нельзя использовать **Свойства** и параметры **представления** в одной команде.</span><span class="sxs-lookup"><span data-stu-id="b9741-168">You cannot use the **Property** and **View** parameters in the same command.</span></span>

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

### <span data-ttu-id="b9741-169">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="b9741-169">CommonParameters</span></span>

<span data-ttu-id="b9741-170">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b9741-170">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b9741-171">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="b9741-171">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b9741-172">Входные данные</span><span class="sxs-lookup"><span data-stu-id="b9741-172">INPUTS</span></span>

### <span data-ttu-id="b9741-173">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="b9741-173">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="b9741-174">Любой объект можно передать по конвейеру в `Format-Custom` .</span><span class="sxs-lookup"><span data-stu-id="b9741-174">You can pipe any object to `Format-Custom`.</span></span>

## <span data-ttu-id="b9741-175">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="b9741-175">OUTPUTS</span></span>

### <span data-ttu-id="b9741-176">Microsoft.PowerShell.Commands.Internal.Format</span><span class="sxs-lookup"><span data-stu-id="b9741-176">Microsoft.PowerShell.Commands.Internal.Format</span></span>

<span data-ttu-id="b9741-177">`Format-Custom` Возвращает объекты формата, представляющие отображение.</span><span class="sxs-lookup"><span data-stu-id="b9741-177">`Format-Custom` returns the format objects that represent the display.</span></span>

## <span data-ttu-id="b9741-178">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="b9741-178">NOTES</span></span>

<span data-ttu-id="b9741-179">`Format-Custom` предназначен для отображения представлений, которые не просто являются таблицами или просто списками.</span><span class="sxs-lookup"><span data-stu-id="b9741-179">`Format-Custom` is designed to display views that are not just tables or just lists.</span></span> <span data-ttu-id="b9741-180">Чтобы отобразить альтернативное табличное представление, используйте `Format-Table` .</span><span class="sxs-lookup"><span data-stu-id="b9741-180">To display an alternate table view, use `Format-Table`.</span></span> <span data-ttu-id="b9741-181">Чтобы отобразить альтернативное представление списка, используйте `Format-List` .</span><span class="sxs-lookup"><span data-stu-id="b9741-181">To display an alternate list view, use `Format-List`.</span></span>

<span data-ttu-id="b9741-182">Также можно ссылаться `Format-Custom` по встроенному псевдониму `fc` .</span><span class="sxs-lookup"><span data-stu-id="b9741-182">You can also refer to `Format-Custom` by its built-in alias, `fc`.</span></span> <span data-ttu-id="b9741-183">Дополнительные сведения см. в разделе [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="b9741-183">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>

<span data-ttu-id="b9741-184">Параметр **GroupBy** предполагает, что объекты сортируются.</span><span class="sxs-lookup"><span data-stu-id="b9741-184">The **GroupBy** parameter assumes that the objects are sorted.</span></span> <span data-ttu-id="b9741-185">Перед использованием `Format-Custom` для группирования объектов используйте `Sort-Object` для сортировки.</span><span class="sxs-lookup"><span data-stu-id="b9741-185">Before using `Format-Custom` to group the objects, use `Sort-Object` to sort them.</span></span>

## <span data-ttu-id="b9741-186">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="b9741-186">RELATED LINKS</span></span>

[<span data-ttu-id="b9741-187">about_Calculated_Properties</span><span class="sxs-lookup"><span data-stu-id="b9741-187">about_Calculated_Properties</span></span>](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[<span data-ttu-id="b9741-188">Format-Hex</span><span class="sxs-lookup"><span data-stu-id="b9741-188">Format-Hex</span></span>](Format-Hex.md)

[<span data-ttu-id="b9741-189">Format-List</span><span class="sxs-lookup"><span data-stu-id="b9741-189">Format-List</span></span>](Format-List.md)

[<span data-ttu-id="b9741-190">Format-Table</span><span class="sxs-lookup"><span data-stu-id="b9741-190">Format-Table</span></span>](Format-Table.md)

[<span data-ttu-id="b9741-191">Format-Wide</span><span class="sxs-lookup"><span data-stu-id="b9741-191">Format-Wide</span></span>](Format-Wide.md)

[<span data-ttu-id="b9741-192">Get-Process</span><span class="sxs-lookup"><span data-stu-id="b9741-192">Get-Process</span></span>](../Microsoft.PowerShell.Management/Get-Process.md)
