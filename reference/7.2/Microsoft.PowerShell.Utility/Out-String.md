---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 01/20/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/out-string?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Out-String
ms.openlocfilehash: 59e5b728604ce37f27b56ebe62e1a22d6af8a966
ms.sourcegitcommit: 94d597c4fb38793bc49ca7610e2c9973b1e577c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/21/2021
ms.locfileid: "99604651"
---
# <span data-ttu-id="b14ed-102">Out-String</span><span class="sxs-lookup"><span data-stu-id="b14ed-102">Out-String</span></span>

## <span data-ttu-id="b14ed-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="b14ed-103">Synopsis</span></span>
<span data-ttu-id="b14ed-104">Выводит входные объекты в виде строк.</span><span class="sxs-lookup"><span data-stu-id="b14ed-104">Outputs input objects as a strings.</span></span>

## <span data-ttu-id="b14ed-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b14ed-105">Syntax</span></span>

### <span data-ttu-id="b14ed-106">Ноневлинеформаттинг (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="b14ed-106">NoNewLineFormatting (Default)</span></span>

```
Out-String [-Width <Int32>] [-NoNewline] [-InputObject <PSObject>] [<CommonParameters>]
```

### <span data-ttu-id="b14ed-107">стреамформаттинг</span><span class="sxs-lookup"><span data-stu-id="b14ed-107">StreamFormatting</span></span>

```
Out-String [-Stream] [-Width <Int32>] [-InputObject <PSObject>] [<CommonParameters>]
```

## <span data-ttu-id="b14ed-108">Описание</span><span class="sxs-lookup"><span data-stu-id="b14ed-108">Description</span></span>

<span data-ttu-id="b14ed-109">`Out-String`Командлет преобразует входные объекты в строки.</span><span class="sxs-lookup"><span data-stu-id="b14ed-109">The `Out-String` cmdlet converts input objects into strings.</span></span> <span data-ttu-id="b14ed-110">По умолчанию `Out-String` накапливает строки и возвращает их в виде одной строки, но можно использовать параметр **Stream** , чтобы направить `Out-String` Возврат по одной строке за раз или создать массив строк.</span><span class="sxs-lookup"><span data-stu-id="b14ed-110">By default, `Out-String` accumulates the strings and returns them as a single string, but you can use the **Stream** parameter to direct `Out-String` to return one line at a time or create and array of strings.</span></span> <span data-ttu-id="b14ed-111">Этот командлет позволяет управлять строковым выводом и выполнять в нем поиск, как при работе с традиционными оболочками, если использовать объектов неудобно.</span><span class="sxs-lookup"><span data-stu-id="b14ed-111">This cmdlet lets you search and manipulate string output as you would in traditional shells when object manipulation is less convenient.</span></span>

## <span data-ttu-id="b14ed-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="b14ed-112">Examples</span></span>

### <span data-ttu-id="b14ed-113">Пример 1. Получение текущего языка и региональных параметров и преобразование данных в строки</span><span class="sxs-lookup"><span data-stu-id="b14ed-113">Example 1: Get the current culture and convert the data to strings</span></span>

<span data-ttu-id="b14ed-114">Этот пример возвращает региональные параметры текущего пользователя и преобразует данные объекта в строки.</span><span class="sxs-lookup"><span data-stu-id="b14ed-114">This example gets the regional settings for the current user and converts the object data to strings.</span></span>

```powershell
$C = Get-Culture | Select-Object -Property *
Out-String -InputObject $C -Width 100
```

```Output
Parent                         : en
LCID                           : 1033
KeyboardLayoutId               : 1033
Name                           : en-US
IetfLanguageTag                : en-US
DisplayName                    : English (United States)
NativeName                     : English (United States)
EnglishName                    : English (United States)
TwoLetterISOLanguageName       : en
ThreeLetterISOLanguageName     : eng
ThreeLetterWindowsLanguageName : ENU
CompareInfo                    : CompareInfo - en-US
TextInfo                       : TextInfo - en-US
IsNeutralCulture               : False
CultureTypes                   : SpecificCultures, InstalledWin32Cultures, FrameworkCultures
NumberFormat                   : System.Globalization.NumberFormatInfo
DateTimeFormat                 : System.Globalization.DateTimeFormatInfo
Calendar                       : System.Globalization.GregorianCalendar
OptionalCalendars              : {System.Globalization.GregorianCalendar,
                                 System.Globalization.GregorianCalendar}
UseUserOverride                : True
IsReadOnly                     : False
```

<span data-ttu-id="b14ed-115">`$C`Переменная хранит **Selected.SysTEM. Объект Globalization. CultureInfo** .</span><span class="sxs-lookup"><span data-stu-id="b14ed-115">The `$C` variable stores a **Selected.System.Globalization.CultureInfo** object.</span></span> <span data-ttu-id="b14ed-116">Объект является результатом `Get-Culture` отправки выходных данных в конвейер `Select-Object` .</span><span class="sxs-lookup"><span data-stu-id="b14ed-116">The object is the result of `Get-Culture` sending output down the pipeline to `Select-Object`.</span></span> <span data-ttu-id="b14ed-117">Параметр **Property** использует `*` подстановочный знак звездочки (), чтобы указать все свойства, содержащиеся в объекте.</span><span class="sxs-lookup"><span data-stu-id="b14ed-117">The **Property** parameter uses an asterisk (`*`) wildcard to specify all properties are contained in the object.</span></span>

<span data-ttu-id="b14ed-118">`Out-String` использует параметр **InputObject** для указания объекта **CultureInfo** , хранящегося в `$C` переменной.</span><span class="sxs-lookup"><span data-stu-id="b14ed-118">`Out-String` uses the **InputObject** parameter to specify the **CultureInfo** object stored in the `$C` variable.</span></span> <span data-ttu-id="b14ed-119">Объекты в `$C` преобразуются в строку.</span><span class="sxs-lookup"><span data-stu-id="b14ed-119">The objects in `$C` are converted to a string.</span></span>

> [!NOTE]
> <span data-ttu-id="b14ed-120">Чтобы просмотреть `Out-String` массив, сохраните выходные данные в переменную и используйте индекс массива для просмотра элементов.</span><span class="sxs-lookup"><span data-stu-id="b14ed-120">To view the `Out-String` array, store the output to a variable and use an array index to view the elements.</span></span> <span data-ttu-id="b14ed-121">Дополнительные сведения об индексе массива см. в разделе [about_Arrays](../microsoft.powershell.core/about/about_arrays.md).</span><span class="sxs-lookup"><span data-stu-id="b14ed-121">For more information about the array index, see [about_Arrays](../microsoft.powershell.core/about/about_arrays.md).</span></span>
>
> `$str = Out-String -InputObject $C -Width 100`

### <span data-ttu-id="b14ed-122">Пример 2. Работа с объектами</span><span class="sxs-lookup"><span data-stu-id="b14ed-122">Example 2: Working with objects</span></span>

<span data-ttu-id="b14ed-123">В этом примере показано различие между работой с объектами и работой со строками.</span><span class="sxs-lookup"><span data-stu-id="b14ed-123">This example demonstrates the difference between working with objects and working with strings.</span></span> <span data-ttu-id="b14ed-124">Команда отображает псевдоним, который содержит текст **gcm**, псевдоним для `Get-Command` .</span><span class="sxs-lookup"><span data-stu-id="b14ed-124">The command displays an alias that includes the text **gcm**, the alias for `Get-Command`.</span></span>

```powershell
Get-Alias | Out-String -Stream | Select-String -Pattern "gcm"
```

```Output
Alias           gcm -> Get-Command
```

<span data-ttu-id="b14ed-125">`Get-Alias` Возвращает объекты **System. Management. Automation. AliasInfo** , по одному для каждого псевдонима, и отправляет объекты по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="b14ed-125">`Get-Alias` gets the **System.Management.Automation.AliasInfo** objects, one for each alias, and sends the objects down the pipeline.</span></span> <span data-ttu-id="b14ed-126">`Out-String` использует параметр **Stream** для преобразования каждого объекта в строку, вместо того чтобы объединить все объекты в одну строку.</span><span class="sxs-lookup"><span data-stu-id="b14ed-126">`Out-String` uses the **Stream** parameter to convert each object to a string rather concatenating all the objects into a single string.</span></span> <span data-ttu-id="b14ed-127">Объекты **System. String** отправляются в конвейер и `Select-String` используют параметр **pattern** для поиска совпадений для текста **gcm**.</span><span class="sxs-lookup"><span data-stu-id="b14ed-127">The **System.String** objects are sent down the pipeline and `Select-String` uses the **Pattern** parameter to find matches for the text **gcm**.</span></span>

> [!NOTE]
> <span data-ttu-id="b14ed-128">Если опустить параметр **Stream** , команда выводит все псевдонимы, так как `Select-String` находит текст **gcm** в одной строке, которая `Out-String` возвращает.</span><span class="sxs-lookup"><span data-stu-id="b14ed-128">If you omit the **Stream** parameter, the command displays all the aliases because `Select-String` finds the text **gcm** in the single string that `Out-String` returns.</span></span>

### <span data-ttu-id="b14ed-129">Пример 3. Использование параметра Width для предотвращения усечения.</span><span class="sxs-lookup"><span data-stu-id="b14ed-129">Example 3: Use the Width parameter to prevent truncation.</span></span>

<span data-ttu-id="b14ed-130">Хотя большинство выходных данных из `Out-String` переносится на следующую строку, существуют сценарии, в которых выходные данные усекаются системой форматирования перед передачей в `Out-String` .</span><span class="sxs-lookup"><span data-stu-id="b14ed-130">While most output from `Out-String` is wrapped to the next line, there are scenarios where the output is truncated by the formatting system before being passed to `Out-String`.</span></span> <span data-ttu-id="b14ed-131">Можно избежать усечения с помощью параметра **Width** .</span><span class="sxs-lookup"><span data-stu-id="b14ed-131">You can avoid truncation using the **Width** parameter.</span></span>

```powershell
PS> @{TestKey = ('x' * 200)} | Out-String
Name                           Value
----                           -----
TestKey                        xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx...

PS> @{TestKey = ('x' * 200)} | Out-String -Width 250

Name                           Value
----                           -----
TestKey                        xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
```

## <span data-ttu-id="b14ed-132">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b14ed-132">PARAMETERS</span></span>

### <span data-ttu-id="b14ed-133">-InputObject</span><span class="sxs-lookup"><span data-stu-id="b14ed-133">-InputObject</span></span>

<span data-ttu-id="b14ed-134">Указывает объекты для записи в строку.</span><span class="sxs-lookup"><span data-stu-id="b14ed-134">Specifies the objects to be written to a string.</span></span> <span data-ttu-id="b14ed-135">Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты.</span><span class="sxs-lookup"><span data-stu-id="b14ed-135">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="b14ed-136">-Новая строка</span><span class="sxs-lookup"><span data-stu-id="b14ed-136">-NoNewline</span></span>

<span data-ttu-id="b14ed-137">Удаляет все символы новой строки из выходных данных, созданных модулем форматирования PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b14ed-137">Removes all newlines from output generated by the PowerShell formatter.</span></span> <span data-ttu-id="b14ed-138">Символы новой строки, которые являются частью строковых объектов, сохраняются.</span><span class="sxs-lookup"><span data-stu-id="b14ed-138">Newlines that are part of the string objects are preserved.</span></span>

<span data-ttu-id="b14ed-139">Этот параметр появился в PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="b14ed-139">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NoNewLineFormatting
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b14ed-140">-Stream</span><span class="sxs-lookup"><span data-stu-id="b14ed-140">-Stream</span></span>

<span data-ttu-id="b14ed-141">По умолчанию `Out-String` выводит одну строку, отформатированную как можно увидеть в консоли, включая любые пустые заголовки или завершающие строки.</span><span class="sxs-lookup"><span data-stu-id="b14ed-141">By default, `Out-String` outputs a single string formatted as you would see it in the console including any blank headers or trailing newlines.</span></span> <span data-ttu-id="b14ed-142">Параметр **Stream** позволяет `Out-String` выводить каждую строку по одному.</span><span class="sxs-lookup"><span data-stu-id="b14ed-142">The **Stream** parameter enables `Out-String` to output each line one by one.</span></span> <span data-ttu-id="b14ed-143">Единственным исключением являются многострочные строки.</span><span class="sxs-lookup"><span data-stu-id="b14ed-143">The only exception to this are multiline strings.</span></span> <span data-ttu-id="b14ed-144">В этом случае `Out-String` будет по-прежнему выводить строку в виде одной многострочной строки.</span><span class="sxs-lookup"><span data-stu-id="b14ed-144">In that case, `Out-String` will still output the string as a single, multiline string.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: StreamFormatting
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b14ed-145">-Width</span><span class="sxs-lookup"><span data-stu-id="b14ed-145">-Width</span></span>

<span data-ttu-id="b14ed-146">Указывает количество символов в каждой строке выходных данных.</span><span class="sxs-lookup"><span data-stu-id="b14ed-146">Specifies the number of characters in each line of output.</span></span> <span data-ttu-id="b14ed-147">Все дополнительные символы упаковываются в следующую строку или усекаются в зависимости от используемого командлета модуля форматирования.</span><span class="sxs-lookup"><span data-stu-id="b14ed-147">Any additional characters are wrapped to the next line or truncated depending on the formatter cmdlet used.</span></span> <span data-ttu-id="b14ed-148">Параметр **Width** применяется только к отформатированным объектам.</span><span class="sxs-lookup"><span data-stu-id="b14ed-148">The **Width** parameter applies only to objects that are being formatted.</span></span> <span data-ttu-id="b14ed-149">Если данный параметр не указан, ширина определяется характеристиками основного приложения.</span><span class="sxs-lookup"><span data-stu-id="b14ed-149">If you omit this parameter, the width is determined by the characteristics of the host program.</span></span> <span data-ttu-id="b14ed-150">В окнах терминала (консоли) в качестве значения по умолчанию используется текущая ширина окна.</span><span class="sxs-lookup"><span data-stu-id="b14ed-150">In terminal (console) windows, the current window width is used as the default value.</span></span> <span data-ttu-id="b14ed-151">В окнах консоли PowerShell по умолчанию устанавливается ширина 80 символов при установке.</span><span class="sxs-lookup"><span data-stu-id="b14ed-151">PowerShell console windows default to a width of 80 characters on installation.</span></span>

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

### <span data-ttu-id="b14ed-152">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="b14ed-152">CommonParameters</span></span>

<span data-ttu-id="b14ed-153">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b14ed-153">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b14ed-154">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="b14ed-154">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b14ed-155">Входные данные</span><span class="sxs-lookup"><span data-stu-id="b14ed-155">INPUTS</span></span>

### <span data-ttu-id="b14ed-156">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="b14ed-156">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="b14ed-157">Объекты можно отправить по конвейеру в `Out-String` .</span><span class="sxs-lookup"><span data-stu-id="b14ed-157">You can send objects down the pipeline to `Out-String`.</span></span>

## <span data-ttu-id="b14ed-158">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="b14ed-158">OUTPUTS</span></span>

### <span data-ttu-id="b14ed-159">System.String</span><span class="sxs-lookup"><span data-stu-id="b14ed-159">System.String</span></span>

<span data-ttu-id="b14ed-160">`Out-String` Возвращает строку, которая создается из входного объекта.</span><span class="sxs-lookup"><span data-stu-id="b14ed-160">`Out-String` returns the string that it creates from the input object.</span></span>

## <span data-ttu-id="b14ed-161">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="b14ed-161">NOTES</span></span>

<span data-ttu-id="b14ed-162">Командлеты, содержащие `Out` команду, не отформатируют объекты.</span><span class="sxs-lookup"><span data-stu-id="b14ed-162">The cmdlets that contain the `Out` verb don't format objects.</span></span> <span data-ttu-id="b14ed-163">`Out`Командлеты отправляют объекты в модуль форматирования для указанного отображаемого назначения.</span><span class="sxs-lookup"><span data-stu-id="b14ed-163">The `Out` cmdlets send objects to the formatter for the specified display destination.</span></span>

## <span data-ttu-id="b14ed-164">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="b14ed-164">RELATED LINKS</span></span>

[<span data-ttu-id="b14ed-165">about_Formatting</span><span class="sxs-lookup"><span data-stu-id="b14ed-165">about_Formatting</span></span>](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md)

[<span data-ttu-id="b14ed-166">Out-Default;</span><span class="sxs-lookup"><span data-stu-id="b14ed-166">Out-Default</span></span>](../Microsoft.PowerShell.Core/Out-Default.md)

[<span data-ttu-id="b14ed-167">Out-File</span><span class="sxs-lookup"><span data-stu-id="b14ed-167">Out-File</span></span>](Out-File.md)

[<span data-ttu-id="b14ed-168">Out-Host</span><span class="sxs-lookup"><span data-stu-id="b14ed-168">Out-Host</span></span>](../Microsoft.PowerShell.Core/Out-Host.md)

[<span data-ttu-id="b14ed-169">Out-Null</span><span class="sxs-lookup"><span data-stu-id="b14ed-169">Out-Null</span></span>](../Microsoft.PowerShell.Core/Out-Null.md)

[<span data-ttu-id="b14ed-170">Out-GridView</span><span class="sxs-lookup"><span data-stu-id="b14ed-170">Out-GridView</span></span>](Out-GridView.md)

[<span data-ttu-id="b14ed-171">Out-Printer</span><span class="sxs-lookup"><span data-stu-id="b14ed-171">Out-Printer</span></span>](Out-Printer.md)
