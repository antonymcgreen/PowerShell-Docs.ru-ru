---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 09/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/write-host?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-Host
ms.openlocfilehash: 01d045a6254b40161462bf36976fdbf57f205705
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601598"
---
# <span data-ttu-id="2506f-102">Write-Host</span><span class="sxs-lookup"><span data-stu-id="2506f-102">Write-Host</span></span>

## <span data-ttu-id="2506f-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="2506f-103">SYNOPSIS</span></span>

<span data-ttu-id="2506f-104">Записывает пользовательские выходные данные в узел.</span><span class="sxs-lookup"><span data-stu-id="2506f-104">Writes customized output to a host.</span></span>

## <span data-ttu-id="2506f-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2506f-105">SYNTAX</span></span>

```
Write-Host [[-Object] <Object>] [-NoNewline] [-Separator <Object>] [-ForegroundColor <ConsoleColor>]
 [-BackgroundColor <ConsoleColor>] [<CommonParameters>]
```

## <span data-ttu-id="2506f-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2506f-106">DESCRIPTION</span></span>

<span data-ttu-id="2506f-107">`Write-Host`Основным предназначением командлета является создание для (узла) вывода только для просмотра, например при выводе запроса на ввод в сочетании с [чтением-узлом](Read-Host.md).</span><span class="sxs-lookup"><span data-stu-id="2506f-107">The `Write-Host` cmdlet's primary purpose is to produce for-(host)-display-only output, such as printing colored text like when prompting the user for input in conjunction with [Read-Host](Read-Host.md).</span></span>
<span data-ttu-id="2506f-108">`Write-Host` использует метод [ToString ()](/dotnet/api/system.object.tostring) для записи выходных данных.</span><span class="sxs-lookup"><span data-stu-id="2506f-108">`Write-Host` uses the [ToString()](/dotnet/api/system.object.tostring) method to write the output.</span></span> <span data-ttu-id="2506f-109">Напротив, для вывода данных в конвейер используйте [Write-Output](Write-Output.md) или неявные выходные данные.</span><span class="sxs-lookup"><span data-stu-id="2506f-109">By contrast, to output data to the pipeline, use [Write-Output](Write-Output.md) or implicit output.</span></span>

<span data-ttu-id="2506f-110">Можно указать цвет текста с помощью `ForegroundColor` параметра, а цвет фона можно указать с помощью `BackgroundColor` параметра.</span><span class="sxs-lookup"><span data-stu-id="2506f-110">You can specify the color of text by using the `ForegroundColor` parameter, and you can specify the background color by using the `BackgroundColor` parameter.</span></span> <span data-ttu-id="2506f-111">Параметр Separator позволяет указать строку, которая будет использоваться для разделения отображаемых объектов.</span><span class="sxs-lookup"><span data-stu-id="2506f-111">The Separator parameter lets you specify a string to use to separate displayed objects.</span></span> <span data-ttu-id="2506f-112">Конкретный результат зависит от программы, в которой размещается PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2506f-112">The particular result depends on the program that is hosting PowerShell.</span></span>

> [!NOTE]
> <span data-ttu-id="2506f-113">Начиная с Windows PowerShell 5,0, `Write-Host` — это оболочка для этого, которая `Write-Information` позволяет использовать `Write-Host` для отправки выходных данных в информационный поток.</span><span class="sxs-lookup"><span data-stu-id="2506f-113">Starting in Windows PowerShell 5.0, `Write-Host` is a wrapper for `Write-Information` This allows you to use `Write-Host` to emit output to the information stream.</span></span> <span data-ttu-id="2506f-114">Это позволяет **записывать** или **подавить** данные, написанные с помощью, сохраняя `Write-Host` обратную совместимость.</span><span class="sxs-lookup"><span data-stu-id="2506f-114">This enables the **capture** or **suppression** of data written using `Write-Host` while preserving backwards compatibility.</span></span>
>
> <span data-ttu-id="2506f-115">`$InformationPreference`Привилегированная переменная и `InformationAction` общий параметр не влияют на `Write-Host` сообщения.</span><span class="sxs-lookup"><span data-stu-id="2506f-115">The `$InformationPreference` preference variable and `InformationAction` common parameter do not affect `Write-Host` messages.</span></span> <span data-ttu-id="2506f-116">Исключением из этого правила является `-InformationAction Ignore` , которое фактически подавляет `Write-Host` вывод.</span><span class="sxs-lookup"><span data-stu-id="2506f-116">The exception to this rule is `-InformationAction Ignore`, which effectively suppresses `Write-Host` output.</span></span> <span data-ttu-id="2506f-117">(см. "Пример 5")</span><span class="sxs-lookup"><span data-stu-id="2506f-117">(see "Example 5")</span></span>

## <span data-ttu-id="2506f-118">Примеры</span><span class="sxs-lookup"><span data-stu-id="2506f-118">EXAMPLES</span></span>

### <span data-ttu-id="2506f-119">Пример 1. запись в консоль без добавления новой строки</span><span class="sxs-lookup"><span data-stu-id="2506f-119">Example 1: Write to the console without adding a new line</span></span>

```powershell
Write-Host "no newline test " -NoNewline
Write-Host "second string"
```

```output
no newline test second string
```

<span data-ttu-id="2506f-120">Эта команда отображает строку "без теста для новой строки" с `NoNewline` параметром.</span><span class="sxs-lookup"><span data-stu-id="2506f-120">This command displays the string 'no newline test' with the `NoNewline` parameter.</span></span>

<span data-ttu-id="2506f-121">Записывается вторая строка, но она завершается на той же строке, что и первая из-за отсутствия строки, разделяющей строку.</span><span class="sxs-lookup"><span data-stu-id="2506f-121">A second string is written, but it ends up on the same line as the first due to the absence of a newline separating the strings.</span></span>

### <span data-ttu-id="2506f-122">Пример 2. запись в консоль и добавление разделителя</span><span class="sxs-lookup"><span data-stu-id="2506f-122">Example 2: Write to the console and include a separator</span></span>

```powershell
Write-Host (2,4,6,8,10,12) -Separator ", +2= "
```

```output
2, +2= 4, +2= 6, +2= 8, +2= 10, +2= 12
```

Эта команда отображает четные числа от двух до двенадцати. <span data-ttu-id="2506f-124">Параметр **разделителя** используется для добавления строки `, +2= ` (запятая, пробел,,, `+` `2` `=` , пробел).</span><span class="sxs-lookup"><span data-stu-id="2506f-124">The **Separator** parameter is used to add the string `, +2= ` (comma, space, `+`, `2`, `=`, space).</span></span>

### <span data-ttu-id="2506f-125">Пример 3. запись с другими цветами текста и фона</span><span class="sxs-lookup"><span data-stu-id="2506f-125">Example 3: Write with different text and background colors</span></span>

```powershell
Write-Host (2,4,6,8,10,12) -Separator ", -> " -ForegroundColor DarkGreen -BackgroundColor White
```

```output
2, -> 4, -> 6, -> 8, -> 10, -> 12
```

<span data-ttu-id="2506f-126">Эта команда отображает четные числа от двух до двенадцати.</span><span class="sxs-lookup"><span data-stu-id="2506f-126">This command displays the even numbers from two through twelve.</span></span> <span data-ttu-id="2506f-127">Он использует `ForegroundColor` параметр для вывода темно-зеленого текста, а `BackgroundColor` параметр — для показа белого фона.</span><span class="sxs-lookup"><span data-stu-id="2506f-127">It uses the `ForegroundColor` parameter to output dark green text and the `BackgroundColor` parameter to display a white background.</span></span>

### <span data-ttu-id="2506f-128">Пример 4. запись с различными цветами текста и фона</span><span class="sxs-lookup"><span data-stu-id="2506f-128">Example 4: Write with different text and background colors</span></span>

```powershell
Write-Host "Red on white text." -ForegroundColor red -BackgroundColor white
```

```output
Red on white text.
```

<span data-ttu-id="2506f-129">Эта команда выводит строку Red on white text.</span><span class="sxs-lookup"><span data-stu-id="2506f-129">This command displays the string "Red on white text."</span></span> <span data-ttu-id="2506f-130">Текст имеет красный цвет, как определено `ForegroundColor` параметром.</span><span class="sxs-lookup"><span data-stu-id="2506f-130">The text is red, as defined by the `ForegroundColor` parameter.</span></span> <span data-ttu-id="2506f-131">Фон является белым, как определено `BackgroundColor` параметром.</span><span class="sxs-lookup"><span data-stu-id="2506f-131">The background is white, as defined by the `BackgroundColor` parameter.</span></span>

### <span data-ttu-id="2506f-132">Пример 5. Отключение вывода от Write-Host</span><span class="sxs-lookup"><span data-stu-id="2506f-132">Example 5: Suppress output from Write-Host</span></span>

```powershell
# The following two statements can be used to effectively suppress output from Write-Host
Write-Host "I won't print" -InformationAction Ignore
Write-Host "I won't print" 6>$null
```

```output

```

<span data-ttu-id="2506f-133">Эти команды эффективно подавляют вывод `Write-Host` командлета.</span><span class="sxs-lookup"><span data-stu-id="2506f-133">These commands effectively suppress output of the `Write-Host` cmdlet.</span></span> <span data-ttu-id="2506f-134">В первом из них используется `InformationAction` параметр со `Ignore` значением для подавления вывода в информационный поток.</span><span class="sxs-lookup"><span data-stu-id="2506f-134">The first one uses the `InformationAction` parameter with the `Ignore` Value to suppress output to the information stream.</span></span>
<span data-ttu-id="2506f-135">Во втором примере поток информации команды переправляется в `$null` переменную и, таким образом, подавляется.</span><span class="sxs-lookup"><span data-stu-id="2506f-135">The second example redirects the information stream of the command to the `$null` variable and thereby suppresses it.</span></span>

## <span data-ttu-id="2506f-136">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2506f-136">PARAMETERS</span></span>

### <span data-ttu-id="2506f-137">-BackgroundColor</span><span class="sxs-lookup"><span data-stu-id="2506f-137">-BackgroundColor</span></span>

<span data-ttu-id="2506f-138">Определяет цвет фона.</span><span class="sxs-lookup"><span data-stu-id="2506f-138">Specifies the background color.</span></span> <span data-ttu-id="2506f-139">Значение по умолчанию отсутствует.</span><span class="sxs-lookup"><span data-stu-id="2506f-139">There is no default.</span></span> <span data-ttu-id="2506f-140">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="2506f-140">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="2506f-141">Черный</span><span class="sxs-lookup"><span data-stu-id="2506f-141">Black</span></span>
- <span data-ttu-id="2506f-142">даркблуе</span><span class="sxs-lookup"><span data-stu-id="2506f-142">DarkBlue</span></span>
- <span data-ttu-id="2506f-143">даркгрин</span><span class="sxs-lookup"><span data-stu-id="2506f-143">DarkGreen</span></span>
- <span data-ttu-id="2506f-144">даркциан</span><span class="sxs-lookup"><span data-stu-id="2506f-144">DarkCyan</span></span>
- <span data-ttu-id="2506f-145">даркред</span><span class="sxs-lookup"><span data-stu-id="2506f-145">DarkRed</span></span>
- <span data-ttu-id="2506f-146">даркмажента</span><span class="sxs-lookup"><span data-stu-id="2506f-146">DarkMagenta</span></span>
- <span data-ttu-id="2506f-147">даркеллов</span><span class="sxs-lookup"><span data-stu-id="2506f-147">DarkYellow</span></span>
- <span data-ttu-id="2506f-148">Серый</span><span class="sxs-lookup"><span data-stu-id="2506f-148">Gray</span></span>
- <span data-ttu-id="2506f-149">даркграй</span><span class="sxs-lookup"><span data-stu-id="2506f-149">DarkGray</span></span>
- <span data-ttu-id="2506f-150">Синий</span><span class="sxs-lookup"><span data-stu-id="2506f-150">Blue</span></span>
- <span data-ttu-id="2506f-151">Зеленый</span><span class="sxs-lookup"><span data-stu-id="2506f-151">Green</span></span>
- <span data-ttu-id="2506f-152">Цвет</span><span class="sxs-lookup"><span data-stu-id="2506f-152">Cyan</span></span>
- <span data-ttu-id="2506f-153">Красный</span><span class="sxs-lookup"><span data-stu-id="2506f-153">Red</span></span>
- <span data-ttu-id="2506f-154">Пурпурный</span><span class="sxs-lookup"><span data-stu-id="2506f-154">Magenta</span></span>
- <span data-ttu-id="2506f-155">Желтый</span><span class="sxs-lookup"><span data-stu-id="2506f-155">Yellow</span></span>
- <span data-ttu-id="2506f-156">White</span><span class="sxs-lookup"><span data-stu-id="2506f-156">White</span></span>

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

### <span data-ttu-id="2506f-157">-ForegroundColor</span><span class="sxs-lookup"><span data-stu-id="2506f-157">-ForegroundColor</span></span>

<span data-ttu-id="2506f-158">Определяет цвет текста.</span><span class="sxs-lookup"><span data-stu-id="2506f-158">Specifies the text color.</span></span> <span data-ttu-id="2506f-159">Значение по умолчанию отсутствует.</span><span class="sxs-lookup"><span data-stu-id="2506f-159">There is no default.</span></span> <span data-ttu-id="2506f-160">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="2506f-160">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="2506f-161">Черный</span><span class="sxs-lookup"><span data-stu-id="2506f-161">Black</span></span>
- <span data-ttu-id="2506f-162">даркблуе</span><span class="sxs-lookup"><span data-stu-id="2506f-162">DarkBlue</span></span>
- <span data-ttu-id="2506f-163">даркгрин</span><span class="sxs-lookup"><span data-stu-id="2506f-163">DarkGreen</span></span>
- <span data-ttu-id="2506f-164">даркциан</span><span class="sxs-lookup"><span data-stu-id="2506f-164">DarkCyan</span></span>
- <span data-ttu-id="2506f-165">даркред</span><span class="sxs-lookup"><span data-stu-id="2506f-165">DarkRed</span></span>
- <span data-ttu-id="2506f-166">даркмажента</span><span class="sxs-lookup"><span data-stu-id="2506f-166">DarkMagenta</span></span>
- <span data-ttu-id="2506f-167">даркеллов</span><span class="sxs-lookup"><span data-stu-id="2506f-167">DarkYellow</span></span>
- <span data-ttu-id="2506f-168">Серый</span><span class="sxs-lookup"><span data-stu-id="2506f-168">Gray</span></span>
- <span data-ttu-id="2506f-169">даркграй</span><span class="sxs-lookup"><span data-stu-id="2506f-169">DarkGray</span></span>
- <span data-ttu-id="2506f-170">Синий</span><span class="sxs-lookup"><span data-stu-id="2506f-170">Blue</span></span>
- <span data-ttu-id="2506f-171">Зеленый</span><span class="sxs-lookup"><span data-stu-id="2506f-171">Green</span></span>
- <span data-ttu-id="2506f-172">Цвет</span><span class="sxs-lookup"><span data-stu-id="2506f-172">Cyan</span></span>
- <span data-ttu-id="2506f-173">Красный</span><span class="sxs-lookup"><span data-stu-id="2506f-173">Red</span></span>
- <span data-ttu-id="2506f-174">Пурпурный</span><span class="sxs-lookup"><span data-stu-id="2506f-174">Magenta</span></span>
- <span data-ttu-id="2506f-175">Желтый</span><span class="sxs-lookup"><span data-stu-id="2506f-175">Yellow</span></span>
- <span data-ttu-id="2506f-176">White</span><span class="sxs-lookup"><span data-stu-id="2506f-176">White</span></span>

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

### <span data-ttu-id="2506f-177">-Новая строка</span><span class="sxs-lookup"><span data-stu-id="2506f-177">-NoNewline</span></span>

<span data-ttu-id="2506f-178">Строковые представления входных объектов сцепляются для формирования выходных данных.</span><span class="sxs-lookup"><span data-stu-id="2506f-178">The string representations of the input objects are concatenated to form the output.</span></span> <span data-ttu-id="2506f-179">Между выходными строками не вставляются пробелы и символы новой строки.</span><span class="sxs-lookup"><span data-stu-id="2506f-179">No spaces or newlines are inserted between the output strings.</span></span> <span data-ttu-id="2506f-180">После последней выходной строки не добавляется новая строка.</span><span class="sxs-lookup"><span data-stu-id="2506f-180">No newline is added after the last output string.</span></span>

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

### <span data-ttu-id="2506f-181">-Object</span><span class="sxs-lookup"><span data-stu-id="2506f-181">-Object</span></span>

<span data-ttu-id="2506f-182">Объекты, отображаемые на узле.</span><span class="sxs-lookup"><span data-stu-id="2506f-182">Objects to display in the host.</span></span>

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

### <span data-ttu-id="2506f-183">-Separator</span><span class="sxs-lookup"><span data-stu-id="2506f-183">-Separator</span></span>

<span data-ttu-id="2506f-184">Задает разделительную строку для вставки между объектами, отображаемыми узлом.</span><span class="sxs-lookup"><span data-stu-id="2506f-184">Specifies a separator string to insert between objects displayed by the host.</span></span>

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

### <span data-ttu-id="2506f-185">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="2506f-185">CommonParameters</span></span>
<span data-ttu-id="2506f-186">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="2506f-186">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2506f-187">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="2506f-187">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2506f-188">Входные данные</span><span class="sxs-lookup"><span data-stu-id="2506f-188">INPUTS</span></span>

### <span data-ttu-id="2506f-189">System.Object</span><span class="sxs-lookup"><span data-stu-id="2506f-189">System.Object</span></span>

<span data-ttu-id="2506f-190">Объекты, которые необходимо записать в хост, можно передавать по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="2506f-190">You can pipe objects to be written to the host.</span></span>

## <span data-ttu-id="2506f-191">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="2506f-191">OUTPUTS</span></span>

### <span data-ttu-id="2506f-192">None</span><span class="sxs-lookup"><span data-stu-id="2506f-192">None</span></span>

<span data-ttu-id="2506f-193">`Write-Host` отправляет объекты на узел.</span><span class="sxs-lookup"><span data-stu-id="2506f-193">`Write-Host` sends the objects to the host.</span></span> <span data-ttu-id="2506f-194">Он не возвращает никакие объекты.</span><span class="sxs-lookup"><span data-stu-id="2506f-194">It does not return any objects.</span></span> <span data-ttu-id="2506f-195">Однако узел отображает объекты, которые `Write-Host` отправляются в него.</span><span class="sxs-lookup"><span data-stu-id="2506f-195">However, the host displays the objects that `Write-Host` sends to it.</span></span>

## <span data-ttu-id="2506f-196">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="2506f-196">NOTES</span></span>

- <span data-ttu-id="2506f-197">При записи коллекции на узел элементы коллекции выводятся на той же строке, разделенной одним пробелом.</span><span class="sxs-lookup"><span data-stu-id="2506f-197">When writing a collection to the host, elements of the collection are printed on the same line separated by a single space.</span></span> <span data-ttu-id="2506f-198">Это можно переопределить с помощью параметра **разделителя** .</span><span class="sxs-lookup"><span data-stu-id="2506f-198">This can be overridden with the **Separator** parameter.</span></span>

- <span data-ttu-id="2506f-199">Типы данных, отличные от примитивов, такие как объекты со свойствами, могут вызвать непредвиденные результаты и не предоставить осмысленные выходные данные.</span><span class="sxs-lookup"><span data-stu-id="2506f-199">Non-primitive data types such as objects with properties can cause unexpected results and not provide meaningful output.</span></span> <span data-ttu-id="2506f-200">Например, `Write-Host @{a = 1; b = 2}` выполнит печать `System.Collections.DictionaryEntry System.Collections.DictionaryEntry` на узле.</span><span class="sxs-lookup"><span data-stu-id="2506f-200">For example, `Write-Host @{a = 1; b = 2}` will print `System.Collections.DictionaryEntry System.Collections.DictionaryEntry` to the host.</span></span>

## <span data-ttu-id="2506f-201">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="2506f-201">RELATED LINKS</span></span>

[<span data-ttu-id="2506f-202">Clear-Host;</span><span class="sxs-lookup"><span data-stu-id="2506f-202">Clear-Host</span></span>](../Microsoft.PowerShell.Core/Clear-Host.md)

[<span data-ttu-id="2506f-203">Out-Host</span><span class="sxs-lookup"><span data-stu-id="2506f-203">Out-Host</span></span>](../Microsoft.PowerShell.Core/Out-Host.md)

[<span data-ttu-id="2506f-204">Write-Debug</span><span class="sxs-lookup"><span data-stu-id="2506f-204">Write-Debug</span></span>](Write-Debug.md)

[<span data-ttu-id="2506f-205">Write-Error</span><span class="sxs-lookup"><span data-stu-id="2506f-205">Write-Error</span></span>](Write-Error.md)

[<span data-ttu-id="2506f-206">Write-Output</span><span class="sxs-lookup"><span data-stu-id="2506f-206">Write-Output</span></span>](Write-Output.md)

[<span data-ttu-id="2506f-207">Write-Progress</span><span class="sxs-lookup"><span data-stu-id="2506f-207">Write-Progress</span></span>](Write-Progress.md)

[<span data-ttu-id="2506f-208">Write-Verbose</span><span class="sxs-lookup"><span data-stu-id="2506f-208">Write-Verbose</span></span>](Write-Verbose.md)

[<span data-ttu-id="2506f-209">Write-Warning</span><span class="sxs-lookup"><span data-stu-id="2506f-209">Write-Warning</span></span>](Write-Warning.md)
