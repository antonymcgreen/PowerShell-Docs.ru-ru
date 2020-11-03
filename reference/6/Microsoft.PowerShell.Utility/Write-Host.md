---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 09/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/write-host?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-Host
ms.openlocfilehash: f0b7542d551fa0dbbdec186980dcdb7ac600b60c
ms.sourcegitcommit: 758e6dbb428295698d4852b3e19f5d03deade037
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "93230633"
---
# <span data-ttu-id="5b954-103">Write-Host</span><span class="sxs-lookup"><span data-stu-id="5b954-103">Write-Host</span></span>

## <span data-ttu-id="5b954-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="5b954-104">SYNOPSIS</span></span>

<span data-ttu-id="5b954-105">Записывает пользовательские выходные данные в узел.</span><span class="sxs-lookup"><span data-stu-id="5b954-105">Writes customized output to a host.</span></span>

## <span data-ttu-id="5b954-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5b954-106">SYNTAX</span></span>

```
Write-Host [[-Object] <Object>] [-NoNewline] [-Separator <Object>] [-ForegroundColor <ConsoleColor>]
 [-BackgroundColor <ConsoleColor>] [<CommonParameters>]
```

## <span data-ttu-id="5b954-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5b954-107">DESCRIPTION</span></span>

<span data-ttu-id="5b954-108">`Write-Host`Основным предназначением командлета является создание для (узла) вывода только для просмотра, например при выводе запроса на ввод в сочетании с [чтением-узлом](Read-Host.md).</span><span class="sxs-lookup"><span data-stu-id="5b954-108">The `Write-Host` cmdlet's primary purpose is to produce for-(host)-display-only output, such as printing colored text like when prompting the user for input in conjunction with [Read-Host](Read-Host.md).</span></span>
<span data-ttu-id="5b954-109">`Write-Host` использует метод [ToString ()](/dotnet/api/system.object.tostring) для записи выходных данных.</span><span class="sxs-lookup"><span data-stu-id="5b954-109">`Write-Host` uses the [ToString()](/dotnet/api/system.object.tostring) method to write the output.</span></span> <span data-ttu-id="5b954-110">Напротив, для вывода данных в конвейер используйте [Write-Output](Write-Output.md) или неявные выходные данные.</span><span class="sxs-lookup"><span data-stu-id="5b954-110">By contrast, to output data to the pipeline, use [Write-Output](Write-Output.md) or implicit output.</span></span>

<span data-ttu-id="5b954-111">Можно указать цвет текста с помощью `ForegroundColor` параметра, а цвет фона можно указать с помощью `BackgroundColor` параметра.</span><span class="sxs-lookup"><span data-stu-id="5b954-111">You can specify the color of text by using the `ForegroundColor` parameter, and you can specify the background color by using the `BackgroundColor` parameter.</span></span> <span data-ttu-id="5b954-112">Параметр Separator позволяет указать строку, которая будет использоваться для разделения отображаемых объектов.</span><span class="sxs-lookup"><span data-stu-id="5b954-112">The Separator parameter lets you specify a string to use to separate displayed objects.</span></span> <span data-ttu-id="5b954-113">Конкретный результат зависит от программы, в которой размещается PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5b954-113">The particular result depends on the program that is hosting PowerShell.</span></span>

> [!NOTE]
> <span data-ttu-id="5b954-114">Начиная с Windows PowerShell 5,0, `Write-Host` — это оболочка для этого, которая `Write-Information` позволяет использовать `Write-Host` для отправки выходных данных в информационный поток.</span><span class="sxs-lookup"><span data-stu-id="5b954-114">Starting in Windows PowerShell 5.0, `Write-Host` is a wrapper for `Write-Information` This allows you to use `Write-Host` to emit output to the information stream.</span></span> <span data-ttu-id="5b954-115">Это позволяет **записывать** или **подавить** данные, написанные с помощью, сохраняя `Write-Host` обратную совместимость.</span><span class="sxs-lookup"><span data-stu-id="5b954-115">This enables the **capture** or **suppression** of data written using `Write-Host` while preserving backwards compatibility.</span></span>
>
> <span data-ttu-id="5b954-116">`$InformationPreference`Привилегированная переменная и `InformationAction` общий параметр не влияют на `Write-Host` сообщения.</span><span class="sxs-lookup"><span data-stu-id="5b954-116">The `$InformationPreference` preference variable and `InformationAction` common parameter do not affect `Write-Host` messages.</span></span> <span data-ttu-id="5b954-117">Исключением из этого правила является `-InformationAction Ignore` , которое фактически подавляет `Write-Host` вывод.</span><span class="sxs-lookup"><span data-stu-id="5b954-117">The exception to this rule is `-InformationAction Ignore`, which effectively suppresses `Write-Host` output.</span></span> <span data-ttu-id="5b954-118">(см. "Пример 5")</span><span class="sxs-lookup"><span data-stu-id="5b954-118">(see "Example 5")</span></span>

## <span data-ttu-id="5b954-119">Примеры</span><span class="sxs-lookup"><span data-stu-id="5b954-119">EXAMPLES</span></span>

### <span data-ttu-id="5b954-120">Пример 1. запись в консоль без добавления новой строки</span><span class="sxs-lookup"><span data-stu-id="5b954-120">Example 1: Write to the console without adding a new line</span></span>

```powershell
Write-Host "no newline test " -NoNewline
Write-Host "second string"
```

```output
no newline test second string
```

<span data-ttu-id="5b954-121">Эта команда отображает строку "без теста для новой строки" с `NoNewline` параметром.</span><span class="sxs-lookup"><span data-stu-id="5b954-121">This command displays the string 'no newline test' with the `NoNewline` parameter.</span></span>

<span data-ttu-id="5b954-122">Записывается вторая строка, но она завершается на той же строке, что и первая из-за отсутствия строки, разделяющей строку.</span><span class="sxs-lookup"><span data-stu-id="5b954-122">A second string is written, but it ends up on the same line as the first due to the absence of a newline separating the strings.</span></span>

### <span data-ttu-id="5b954-123">Пример 2. запись в консоль и добавление разделителя</span><span class="sxs-lookup"><span data-stu-id="5b954-123">Example 2: Write to the console and include a separator</span></span>

```powershell
Write-Host (2,4,6,8,10,12) -Separator ", +2= "
```

```output
2, +2= 4, +2= 6, +2= 8, +2= 10, +2= 12
```

Эта команда отображает четные числа от двух до двенадцати. <span data-ttu-id="5b954-125">Параметр **разделителя** используется для добавления строки `, +2= ` (запятая, пробел,,, `+` `2` `=` , пробел).</span><span class="sxs-lookup"><span data-stu-id="5b954-125">The **Separator** parameter is used to add the string `, +2= ` (comma, space, `+`, `2`, `=`, space).</span></span>

### <span data-ttu-id="5b954-126">Пример 3. запись с другими цветами текста и фона</span><span class="sxs-lookup"><span data-stu-id="5b954-126">Example 3: Write with different text and background colors</span></span>

```powershell
Write-Host (2,4,6,8,10,12) -Separator ", -> " -ForegroundColor DarkGreen -BackgroundColor White
```

```output
2, -> 4, -> 6, -> 8, -> 10, -> 12
```

<span data-ttu-id="5b954-127">Эта команда отображает четные числа от двух до двенадцати.</span><span class="sxs-lookup"><span data-stu-id="5b954-127">This command displays the even numbers from two through twelve.</span></span> <span data-ttu-id="5b954-128">Он использует `ForegroundColor` параметр для вывода темно-зеленого текста, а `BackgroundColor` параметр — для показа белого фона.</span><span class="sxs-lookup"><span data-stu-id="5b954-128">It uses the `ForegroundColor` parameter to output dark green text and the `BackgroundColor` parameter to display a white background.</span></span>

### <span data-ttu-id="5b954-129">Пример 4. запись с различными цветами текста и фона</span><span class="sxs-lookup"><span data-stu-id="5b954-129">Example 4: Write with different text and background colors</span></span>

```powershell
Write-Host "Red on white text." -ForegroundColor red -BackgroundColor white
```

```output
Red on white text.
```

<span data-ttu-id="5b954-130">Эта команда выводит строку Red on white text.</span><span class="sxs-lookup"><span data-stu-id="5b954-130">This command displays the string "Red on white text."</span></span> <span data-ttu-id="5b954-131">Текст имеет красный цвет, как определено `ForegroundColor` параметром.</span><span class="sxs-lookup"><span data-stu-id="5b954-131">The text is red, as defined by the `ForegroundColor` parameter.</span></span> <span data-ttu-id="5b954-132">Фон является белым, как определено `BackgroundColor` параметром.</span><span class="sxs-lookup"><span data-stu-id="5b954-132">The background is white, as defined by the `BackgroundColor` parameter.</span></span>

### <span data-ttu-id="5b954-133">Пример 5. Отключение вывода от Write-Host</span><span class="sxs-lookup"><span data-stu-id="5b954-133">Example 5: Suppress output from Write-Host</span></span>

```powershell
# The following two statements can be used to effectively suppress output from Write-Host
Write-Host "I won't print" -InformationAction Ignore
Write-Host "I won't print" 6>$null
```

```output

```

<span data-ttu-id="5b954-134">Эти команды эффективно подавляют вывод `Write-Host` командлета.</span><span class="sxs-lookup"><span data-stu-id="5b954-134">These commands effectively suppress output of the `Write-Host` cmdlet.</span></span> <span data-ttu-id="5b954-135">В первом из них используется `InformationAction` параметр со `Ignore` значением для подавления вывода в информационный поток.</span><span class="sxs-lookup"><span data-stu-id="5b954-135">The first one uses the `InformationAction` parameter with the `Ignore` Value to suppress output to the information stream.</span></span>
<span data-ttu-id="5b954-136">Во втором примере поток информации команды переправляется в `$null` переменную и, таким образом, подавляется.</span><span class="sxs-lookup"><span data-stu-id="5b954-136">The second example redirects the information stream of the command to the `$null` variable and thereby suppresses it.</span></span>

## <span data-ttu-id="5b954-137">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="5b954-137">PARAMETERS</span></span>

### <span data-ttu-id="5b954-138">-BackgroundColor</span><span class="sxs-lookup"><span data-stu-id="5b954-138">-BackgroundColor</span></span>

<span data-ttu-id="5b954-139">Определяет цвет фона.</span><span class="sxs-lookup"><span data-stu-id="5b954-139">Specifies the background color.</span></span> <span data-ttu-id="5b954-140">Значение по умолчанию отсутствует.</span><span class="sxs-lookup"><span data-stu-id="5b954-140">There is no default.</span></span> <span data-ttu-id="5b954-141">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="5b954-141">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="5b954-142">Черный</span><span class="sxs-lookup"><span data-stu-id="5b954-142">Black</span></span>
- <span data-ttu-id="5b954-143">даркблуе</span><span class="sxs-lookup"><span data-stu-id="5b954-143">DarkBlue</span></span>
- <span data-ttu-id="5b954-144">даркгрин</span><span class="sxs-lookup"><span data-stu-id="5b954-144">DarkGreen</span></span>
- <span data-ttu-id="5b954-145">даркциан</span><span class="sxs-lookup"><span data-stu-id="5b954-145">DarkCyan</span></span>
- <span data-ttu-id="5b954-146">даркред</span><span class="sxs-lookup"><span data-stu-id="5b954-146">DarkRed</span></span>
- <span data-ttu-id="5b954-147">даркмажента</span><span class="sxs-lookup"><span data-stu-id="5b954-147">DarkMagenta</span></span>
- <span data-ttu-id="5b954-148">даркеллов</span><span class="sxs-lookup"><span data-stu-id="5b954-148">DarkYellow</span></span>
- <span data-ttu-id="5b954-149">Серый</span><span class="sxs-lookup"><span data-stu-id="5b954-149">Gray</span></span>
- <span data-ttu-id="5b954-150">даркграй</span><span class="sxs-lookup"><span data-stu-id="5b954-150">DarkGray</span></span>
- <span data-ttu-id="5b954-151">Синий</span><span class="sxs-lookup"><span data-stu-id="5b954-151">Blue</span></span>
- <span data-ttu-id="5b954-152">Зеленый</span><span class="sxs-lookup"><span data-stu-id="5b954-152">Green</span></span>
- <span data-ttu-id="5b954-153">Цвет</span><span class="sxs-lookup"><span data-stu-id="5b954-153">Cyan</span></span>
- <span data-ttu-id="5b954-154">Красный</span><span class="sxs-lookup"><span data-stu-id="5b954-154">Red</span></span>
- <span data-ttu-id="5b954-155">Пурпурный</span><span class="sxs-lookup"><span data-stu-id="5b954-155">Magenta</span></span>
- <span data-ttu-id="5b954-156">Желтый</span><span class="sxs-lookup"><span data-stu-id="5b954-156">Yellow</span></span>
- <span data-ttu-id="5b954-157">White</span><span class="sxs-lookup"><span data-stu-id="5b954-157">White</span></span>

```yaml
Type: System.ConsoleColor
Parameter Sets: (All)
Aliases:
Accepted values: Black, DarkBlue, DarkGreen, DarkCyan, DarkRed, DarkMagenta, DarkYellow, Gray, DarkGray, Blue, Green, Cyan, Red, Magenta, Yellow, White

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5b954-158">-ForegroundColor</span><span class="sxs-lookup"><span data-stu-id="5b954-158">-ForegroundColor</span></span>

<span data-ttu-id="5b954-159">Определяет цвет текста.</span><span class="sxs-lookup"><span data-stu-id="5b954-159">Specifies the text color.</span></span> <span data-ttu-id="5b954-160">Значение по умолчанию отсутствует.</span><span class="sxs-lookup"><span data-stu-id="5b954-160">There is no default.</span></span> <span data-ttu-id="5b954-161">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="5b954-161">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="5b954-162">Черный</span><span class="sxs-lookup"><span data-stu-id="5b954-162">Black</span></span>
- <span data-ttu-id="5b954-163">даркблуе</span><span class="sxs-lookup"><span data-stu-id="5b954-163">DarkBlue</span></span>
- <span data-ttu-id="5b954-164">даркгрин</span><span class="sxs-lookup"><span data-stu-id="5b954-164">DarkGreen</span></span>
- <span data-ttu-id="5b954-165">даркциан</span><span class="sxs-lookup"><span data-stu-id="5b954-165">DarkCyan</span></span>
- <span data-ttu-id="5b954-166">даркред</span><span class="sxs-lookup"><span data-stu-id="5b954-166">DarkRed</span></span>
- <span data-ttu-id="5b954-167">даркмажента</span><span class="sxs-lookup"><span data-stu-id="5b954-167">DarkMagenta</span></span>
- <span data-ttu-id="5b954-168">даркеллов</span><span class="sxs-lookup"><span data-stu-id="5b954-168">DarkYellow</span></span>
- <span data-ttu-id="5b954-169">Серый</span><span class="sxs-lookup"><span data-stu-id="5b954-169">Gray</span></span>
- <span data-ttu-id="5b954-170">даркграй</span><span class="sxs-lookup"><span data-stu-id="5b954-170">DarkGray</span></span>
- <span data-ttu-id="5b954-171">Синий</span><span class="sxs-lookup"><span data-stu-id="5b954-171">Blue</span></span>
- <span data-ttu-id="5b954-172">Зеленый</span><span class="sxs-lookup"><span data-stu-id="5b954-172">Green</span></span>
- <span data-ttu-id="5b954-173">Цвет</span><span class="sxs-lookup"><span data-stu-id="5b954-173">Cyan</span></span>
- <span data-ttu-id="5b954-174">Красный</span><span class="sxs-lookup"><span data-stu-id="5b954-174">Red</span></span>
- <span data-ttu-id="5b954-175">Пурпурный</span><span class="sxs-lookup"><span data-stu-id="5b954-175">Magenta</span></span>
- <span data-ttu-id="5b954-176">Желтый</span><span class="sxs-lookup"><span data-stu-id="5b954-176">Yellow</span></span>
- <span data-ttu-id="5b954-177">White</span><span class="sxs-lookup"><span data-stu-id="5b954-177">White</span></span>

```yaml
Type: System.ConsoleColor
Parameter Sets: (All)
Aliases:
Accepted values: Black, DarkBlue, DarkGreen, DarkCyan, DarkRed, DarkMagenta, DarkYellow, Gray, DarkGray, Blue, Green, Cyan, Red, Magenta, Yellow, White

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5b954-178">-Новая строка</span><span class="sxs-lookup"><span data-stu-id="5b954-178">-NoNewline</span></span>

<span data-ttu-id="5b954-179">Строковые представления входных объектов сцепляются для формирования выходных данных.</span><span class="sxs-lookup"><span data-stu-id="5b954-179">The string representations of the input objects are concatenated to form the output.</span></span> <span data-ttu-id="5b954-180">Между выходными строками не вставляются пробелы и символы новой строки.</span><span class="sxs-lookup"><span data-stu-id="5b954-180">No spaces or newlines are inserted between the output strings.</span></span> <span data-ttu-id="5b954-181">После последней выходной строки не добавляется новая строка.</span><span class="sxs-lookup"><span data-stu-id="5b954-181">No newline is added after the last output string.</span></span>

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

### <span data-ttu-id="5b954-182">-Object</span><span class="sxs-lookup"><span data-stu-id="5b954-182">-Object</span></span>

<span data-ttu-id="5b954-183">Объекты, отображаемые на узле.</span><span class="sxs-lookup"><span data-stu-id="5b954-183">Objects to display in the host.</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases: Msg, Message

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="5b954-184">-Separator</span><span class="sxs-lookup"><span data-stu-id="5b954-184">-Separator</span></span>

<span data-ttu-id="5b954-185">Задает разделительную строку для вставки между объектами, отображаемыми узлом.</span><span class="sxs-lookup"><span data-stu-id="5b954-185">Specifies a separator string to insert between objects displayed by the host.</span></span>

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

### <span data-ttu-id="5b954-186">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="5b954-186">CommonParameters</span></span>
<span data-ttu-id="5b954-187">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="5b954-187">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="5b954-188">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="5b954-188">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="5b954-189">Входные данные</span><span class="sxs-lookup"><span data-stu-id="5b954-189">INPUTS</span></span>

### <span data-ttu-id="5b954-190">System.Object</span><span class="sxs-lookup"><span data-stu-id="5b954-190">System.Object</span></span>

<span data-ttu-id="5b954-191">Объекты, которые необходимо записать в хост, можно передавать по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="5b954-191">You can pipe objects to be written to the host.</span></span>

## <span data-ttu-id="5b954-192">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="5b954-192">OUTPUTS</span></span>

### <span data-ttu-id="5b954-193">Нет</span><span class="sxs-lookup"><span data-stu-id="5b954-193">None</span></span>

<span data-ttu-id="5b954-194">`Write-Host` отправляет объекты на узел.</span><span class="sxs-lookup"><span data-stu-id="5b954-194">`Write-Host` sends the objects to the host.</span></span> <span data-ttu-id="5b954-195">Он не возвращает никакие объекты.</span><span class="sxs-lookup"><span data-stu-id="5b954-195">It does not return any objects.</span></span> <span data-ttu-id="5b954-196">Однако узел отображает объекты, которые `Write-Host` отправляются в него.</span><span class="sxs-lookup"><span data-stu-id="5b954-196">However, the host displays the objects that `Write-Host` sends to it.</span></span>

## <span data-ttu-id="5b954-197">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="5b954-197">NOTES</span></span>

- <span data-ttu-id="5b954-198">При записи коллекции на узел элементы коллекции выводятся на той же строке, разделенной одним пробелом.</span><span class="sxs-lookup"><span data-stu-id="5b954-198">When writing a collection to the host, elements of the collection are printed on the same line separated by a single space.</span></span> <span data-ttu-id="5b954-199">Это можно переопределить с помощью параметра **разделителя** .</span><span class="sxs-lookup"><span data-stu-id="5b954-199">This can be overridden with the **Separator** parameter.</span></span>

- <span data-ttu-id="5b954-200">Типы данных, отличные от примитивов, такие как объекты со свойствами, могут вызвать непредвиденные результаты и не предоставить осмысленные выходные данные.</span><span class="sxs-lookup"><span data-stu-id="5b954-200">Non-primitive data types such as objects with properties can cause unexpected results and not provide meaningful output.</span></span> <span data-ttu-id="5b954-201">Например, `Write-Host @{a = 1; b = 2}` выполнит печать `System.Collections.DictionaryEntry System.Collections.DictionaryEntry` на узле.</span><span class="sxs-lookup"><span data-stu-id="5b954-201">For example, `Write-Host @{a = 1; b = 2}` will print `System.Collections.DictionaryEntry System.Collections.DictionaryEntry` to the host.</span></span>

## <span data-ttu-id="5b954-202">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="5b954-202">RELATED LINKS</span></span>

[<span data-ttu-id="5b954-203">Clear-Host;</span><span class="sxs-lookup"><span data-stu-id="5b954-203">Clear-Host</span></span>](../Microsoft.PowerShell.Core/Clear-Host.md)

[<span data-ttu-id="5b954-204">Out-Host</span><span class="sxs-lookup"><span data-stu-id="5b954-204">Out-Host</span></span>](../Microsoft.PowerShell.Core/Out-Host.md)

[<span data-ttu-id="5b954-205">Write-Debug</span><span class="sxs-lookup"><span data-stu-id="5b954-205">Write-Debug</span></span>](Write-Debug.md)

[<span data-ttu-id="5b954-206">Ошибка записи</span><span class="sxs-lookup"><span data-stu-id="5b954-206">Write-Error</span></span>](Write-Error.md)

[<span data-ttu-id="5b954-207">Write-Output</span><span class="sxs-lookup"><span data-stu-id="5b954-207">Write-Output</span></span>](Write-Output.md)

[<span data-ttu-id="5b954-208">Write-Progress</span><span class="sxs-lookup"><span data-stu-id="5b954-208">Write-Progress</span></span>](Write-Progress.md)

[<span data-ttu-id="5b954-209">Write-Verbose</span><span class="sxs-lookup"><span data-stu-id="5b954-209">Write-Verbose</span></span>](Write-Verbose.md)

[<span data-ttu-id="5b954-210">Write-Warning</span><span class="sxs-lookup"><span data-stu-id="5b954-210">Write-Warning</span></span>](Write-Warning.md)
