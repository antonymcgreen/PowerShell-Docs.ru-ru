---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Module Name: Microsoft.PowerShell.Utility
ms.date: 12/12/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/join-string?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Join-String
ms.openlocfilehash: f737c8025f9fda3611a44177bd19e928f596d0aa
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600171"
---
# <span data-ttu-id="ea595-102">Join-String</span><span class="sxs-lookup"><span data-stu-id="ea595-102">Join-String</span></span>

## <span data-ttu-id="ea595-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="ea595-103">SYNOPSIS</span></span>
<span data-ttu-id="ea595-104">Объединяет объекты из конвейера в одну строку.</span><span class="sxs-lookup"><span data-stu-id="ea595-104">Combines objects from the pipeline into a single string.</span></span>

## <span data-ttu-id="ea595-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ea595-105">SYNTAX</span></span>

### <span data-ttu-id="ea595-106">Default (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="ea595-106">Default (Default)</span></span>

```
Join-String [[-Property] <PSPropertyExpression>] [[-Separator] <String>] [-OutputPrefix <String>]
 [-OutputSuffix <String>] [-UseCulture] [-InputObject <PSObject[]>] [<CommonParameters>]
```

### <span data-ttu-id="ea595-107">синглекуоте</span><span class="sxs-lookup"><span data-stu-id="ea595-107">SingleQuote</span></span>

```
Join-String [[-Property] <PSPropertyExpression>] [[-Separator] <String>] [-OutputPrefix <String>]
 [-OutputSuffix <String>] [-SingleQuote] [-UseCulture] [-InputObject <PSObject[]>]
 [<CommonParameters>]
```

### <span data-ttu-id="ea595-108">даублекуоте</span><span class="sxs-lookup"><span data-stu-id="ea595-108">DoubleQuote</span></span>

```
Join-String [[-Property] <PSPropertyExpression>] [[-Separator] <String>] [-OutputPrefix <String>]
 [-OutputSuffix <String>] [-DoubleQuote] [-UseCulture] [-InputObject <PSObject[]>]
 [<CommonParameters>]
```

### <span data-ttu-id="ea595-109">Формат</span><span class="sxs-lookup"><span data-stu-id="ea595-109">Format</span></span>

```
Join-String [[-Property] <PSPropertyExpression>] [[-Separator] <String>] [-OutputPrefix <String>]
 [-OutputSuffix <String>] [-FormatString <String>] [-UseCulture] [-InputObject <PSObject[]>]
 [<CommonParameters>]
```

## <span data-ttu-id="ea595-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ea595-110">DESCRIPTION</span></span>

<span data-ttu-id="ea595-111">`Join-String`Командлет присоединяет или объединяет текст из объектов конвейера в одну строку.</span><span class="sxs-lookup"><span data-stu-id="ea595-111">The `Join-String` cmdlet joins, or combines, text from pipeline objects into a single string.</span></span>

<span data-ttu-id="ea595-112">Если параметры не указаны, объекты конвейера преобразуются в строку и соединяются с разделителем по умолчанию `$OFS` .</span><span class="sxs-lookup"><span data-stu-id="ea595-112">If no parameters are specified, the pipeline objects are converted to a string and joined with the default separator `$OFS`.</span></span>

<span data-ttu-id="ea595-113">При указании имени свойства значение свойства преобразуется в строку и присоединяется к строке.</span><span class="sxs-lookup"><span data-stu-id="ea595-113">By specifying a property name, the property's value is converted to a string and joined into a string.</span></span>

<span data-ttu-id="ea595-114">Вместо имени свойства можно использовать блок скрипта.</span><span class="sxs-lookup"><span data-stu-id="ea595-114">Instead of a property name, a script block can be used.</span></span> <span data-ttu-id="ea595-115">Результат блока сценария преобразуется в строку перед присоединением для формирования результата.</span><span class="sxs-lookup"><span data-stu-id="ea595-115">The script block's result is converted to a string before it's joined to form the result.</span></span> <span data-ttu-id="ea595-116">Он может либо объединить текст свойства объекта, либо результат объекта, который был преобразован в строку.</span><span class="sxs-lookup"><span data-stu-id="ea595-116">It can either combine the text of an object's property or the result of the object that was converted to a string.</span></span>

<span data-ttu-id="ea595-117">Этот командлет появился в PowerShell 6,2.</span><span class="sxs-lookup"><span data-stu-id="ea595-117">This cmdlet was introduced in PowerShell 6.2.</span></span>

## <span data-ttu-id="ea595-118">Примеры</span><span class="sxs-lookup"><span data-stu-id="ea595-118">EXAMPLES</span></span>

### <span data-ttu-id="ea595-119">Пример 1. соединение имен каталогов</span><span class="sxs-lookup"><span data-stu-id="ea595-119">Example 1: Join directory names</span></span>

<!-- markdownlint-disable MD038 -->
<span data-ttu-id="ea595-120">В этом примере объединяются имена каталогов, выходные данные переносятся в двойные кавычки и имена каталогов разделяются запятыми и пробелами ( `, ` ).</span><span class="sxs-lookup"><span data-stu-id="ea595-120">This example joins directory names, wraps the output in double-quotes, and separates the directory names with a comma and space (`, `).</span></span> <span data-ttu-id="ea595-121">Выходные данные представляют собой строковый объект.</span><span class="sxs-lookup"><span data-stu-id="ea595-121">The output is a string object.</span></span>

```powershell
Get-ChildItem -Directory C:\ | Join-String -Property Name -DoubleQuote -Separator ', '
```

```Output
"PerfLogs", "Program Files", "Program Files (x86)", "Users", "Windows"
```

<span data-ttu-id="ea595-122">`Get-ChildItem` использует параметр **Directory** для получения всех имен каталогов для `C:\` диска.</span><span class="sxs-lookup"><span data-stu-id="ea595-122">`Get-ChildItem` uses the **Directory** parameter to get all the directory names for the `C:\` drive.</span></span>
<span data-ttu-id="ea595-123">Объекты отправляются по конвейеру в `Join-String` .</span><span class="sxs-lookup"><span data-stu-id="ea595-123">The objects are sent down the pipeline to `Join-String`.</span></span> <span data-ttu-id="ea595-124">Параметр **Property** указывает имена каталогов.</span><span class="sxs-lookup"><span data-stu-id="ea595-124">The **Property** parameter specifies the directory names.</span></span> <span data-ttu-id="ea595-125">Параметр **даублекуоте** заключает имена каталогов в двойные кавычки.</span><span class="sxs-lookup"><span data-stu-id="ea595-125">The **DoubleQuote** parameter wraps the directory names with double-quote marks.</span></span>
<span data-ttu-id="ea595-126">Параметр **разделителя** задает использование запятой и пробела ( `, ` ) для разделения имен каталогов.</span><span class="sxs-lookup"><span data-stu-id="ea595-126">The **Separator** parameter specifies to use a comma and space (`, `) to separate the directory names.</span></span>

<span data-ttu-id="ea595-127">`Get-ChildItem`Объекты являются **System. IO. DirectoryInfo** и `Join-String` преобразуют объекты в **System. String**.</span><span class="sxs-lookup"><span data-stu-id="ea595-127">The `Get-ChildItem` objects are **System.IO.DirectoryInfo** and `Join-String` converts the objects to **System.String**.</span></span>

### <span data-ttu-id="ea595-128">Пример 2. Использование подстроки свойства для объединения имен каталогов</span><span class="sxs-lookup"><span data-stu-id="ea595-128">Example 2: Use a property substring to join directory names</span></span>

<span data-ttu-id="ea595-129">В этом примере используется метод подстроки для получения первых четырех букв имен каталогов, заключенный в одинарные кавычки, а имена каталогов разделяются точкой с запятой ( `;` ).</span><span class="sxs-lookup"><span data-stu-id="ea595-129">This example uses a substring method to get the first four letters of directory names, wraps the output in single-quotes, and separates the directory names with a semicolon (`;`).</span></span>

```powershell
Get-ChildItem -Directory C:\ | Join-String -Property {$_.Name.SubString(0,4)} -SingleQuote -Separator ';'
```

```Output
'Perf';'Prog';'Prog';'User';'Wind'
```

<span data-ttu-id="ea595-130">`Get-ChildItem` использует параметр **Directory** для получения всех имен каталогов для `C:\` диска.</span><span class="sxs-lookup"><span data-stu-id="ea595-130">`Get-ChildItem` uses the **Directory** parameter to get all the directory names for the `C:\` drive.</span></span>
<span data-ttu-id="ea595-131">Объекты отправляются по конвейеру в `Join-String` .</span><span class="sxs-lookup"><span data-stu-id="ea595-131">The objects are sent down the pipeline to `Join-String`.</span></span>

<span data-ttu-id="ea595-132">Блок скрипта параметра **Свойства** использует автоматическую переменную ( `$_` ) для указания подстроки свойства **Name** каждого объекта.</span><span class="sxs-lookup"><span data-stu-id="ea595-132">The **Property** parameter script block uses automatic variable (`$_`) to specify each object's **Name** property substring.</span></span> <span data-ttu-id="ea595-133">Подстрока получает первые четыре буквы имени каждого каталога.</span><span class="sxs-lookup"><span data-stu-id="ea595-133">The substring gets the first four letters of each directory name.</span></span> <span data-ttu-id="ea595-134">Подстрока указывает начальную и конечную позиции символа.</span><span class="sxs-lookup"><span data-stu-id="ea595-134">The substring specifies the character start and end positions.</span></span> <span data-ttu-id="ea595-135">Параметр **синглекуоте** заключает имена каталогов в двойные кавычки.</span><span class="sxs-lookup"><span data-stu-id="ea595-135">The **SingleQuote** parameter wraps the directory names with single-quote marks.</span></span> <span data-ttu-id="ea595-136">Параметр **разделителя** задает использование точки с запятой ( `;` ) для разделения имен каталогов.</span><span class="sxs-lookup"><span data-stu-id="ea595-136">The **Separator** parameter specifies to use a semicolon (`;`) to separate the directory names.</span></span>

<span data-ttu-id="ea595-137">Дополнительные сведения об автоматических переменных и подстроках см. в разделе [about_Automatic_Variables](../microsoft.powershell.core/about/about_automatic_variables.md) и [substring](/dotnet/api/system.string.substring).</span><span class="sxs-lookup"><span data-stu-id="ea595-137">For more information about automatic variables and substrings, see [about_Automatic_Variables](../microsoft.powershell.core/about/about_automatic_variables.md) and [Substring](/dotnet/api/system.string.substring).</span></span>

### <span data-ttu-id="ea595-138">Пример 3. Отображение выходных данных присоединение на отдельной строке</span><span class="sxs-lookup"><span data-stu-id="ea595-138">Example 3: Display join output on a separate line</span></span>

<span data-ttu-id="ea595-139">В этом примере имена служб объединяются с каждой службой в отдельной строке с отступом на вкладке.</span><span class="sxs-lookup"><span data-stu-id="ea595-139">This example joins service names with each service on a separate line and indented by a tab.</span></span>

```powershell
Get-Service -Name se* | Join-String -Property Name -Separator "`r`n`t" -OutputPrefix "Services:`n`t"
```

```Output
Services:
    seclogon
    SecurityHealthService
    SEMgrSvc
    SENS
    Sense
    SensorDataService
    SensorService
    SensrSvc
    SessionEnv
```

<span data-ttu-id="ea595-140">`Get-Service` использует параметр **Name** с аргументом для указания служб, начинающихся с `se*` .</span><span class="sxs-lookup"><span data-stu-id="ea595-140">`Get-Service` uses the **Name** parameter with to specify services that begin with `se*`.</span></span> <span data-ttu-id="ea595-141">Звездочка ( `*` ) является подстановочным знаком для любого символа.</span><span class="sxs-lookup"><span data-stu-id="ea595-141">The asterisk (`*`) is a wildcard for any character.</span></span>

<span data-ttu-id="ea595-142">Объекты отправляются по конвейеру в `Join-String` , в котором для указания имен служб используется параметр **Property** .</span><span class="sxs-lookup"><span data-stu-id="ea595-142">The objects are sent down the pipeline to `Join-String` that uses the **Property** parameter to specify the service names.</span></span> <span data-ttu-id="ea595-143">Параметр **разделителя** задает три специальных символа, представляющих возврат каретки ( `` `r `` ), символ новой строки ( `` `n `` ) и знак табуляции ( `` `t `` ).</span><span class="sxs-lookup"><span data-stu-id="ea595-143">The **Separator** parameter specifies three special characters that represent a carriage return (`` `r ``), newline (`` `n ``), and tab (`` `t ``).</span></span> <span data-ttu-id="ea595-144">**Аутпутпрефикс** вставляет **службы меток:** с новой строкой и вкладкой перед первой строкой выходных данных.</span><span class="sxs-lookup"><span data-stu-id="ea595-144">The **OutputPrefix** inserts a label **Services:** with a new line and tab before the first line of output.</span></span>

<span data-ttu-id="ea595-145">Дополнительные сведения о специальных символах см. в разделе [about_Special_Characters](..//microsoft.powershell.core/about/about_special_characters.md).</span><span class="sxs-lookup"><span data-stu-id="ea595-145">For more information about special characters, see [about_Special_Characters](..//microsoft.powershell.core/about/about_special_characters.md).</span></span>

### <span data-ttu-id="ea595-146">Пример 4. Создание определения класса на основе объекта</span><span class="sxs-lookup"><span data-stu-id="ea595-146">Example 4: Create a class definition from an object</span></span>

<span data-ttu-id="ea595-147">В этом примере создается определение класса PowerShell с использованием существующего объекта в качестве шаблона.</span><span class="sxs-lookup"><span data-stu-id="ea595-147">This example generates a PowerShell class definition using an existing object as a template.</span></span>

<span data-ttu-id="ea595-148">В этом примере кода используется Сплаттинг для уменьшения длины строки и улучшения удобочитаемости.</span><span class="sxs-lookup"><span data-stu-id="ea595-148">This code sample uses splatting to reduce the line length and improve readability.</span></span> <span data-ttu-id="ea595-149">Дополнительные сведения см. в разделе [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md).</span><span class="sxs-lookup"><span data-stu-id="ea595-149">For more information, see [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md).</span></span>

```powershell
$obj = [pscustomobject] @{Name = "Joe"; Age = 42}
$parms = @{
  Property = "Name"
  FormatString = '  ${0}'
  OutputPrefix = "class {`n"
  OutputSuffix = "`n}`n"
  Separator = "`n"
}
$obj.PSObject.Properties | Join-String @parms
```

```Output
class {
  $Name
  $Age
}
```

## <span data-ttu-id="ea595-150">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ea595-150">PARAMETERS</span></span>

### <span data-ttu-id="ea595-151">-Даублекуоте</span><span class="sxs-lookup"><span data-stu-id="ea595-151">-DoubleQuote</span></span>

<span data-ttu-id="ea595-152">Заключает строковое значение каждого объекта конвейера в двойные кавычки.</span><span class="sxs-lookup"><span data-stu-id="ea595-152">Wraps the string value of each pipeline object in double-quotes.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: DoubleQuote
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ea595-153">— FormatString</span><span class="sxs-lookup"><span data-stu-id="ea595-153">-FormatString</span></span>

<span data-ttu-id="ea595-154">Строка формата, задающая способ форматирования каждого элемента.</span><span class="sxs-lookup"><span data-stu-id="ea595-154">A format string that specifies how each item should be formatted.</span></span>

```yaml
Type: System.String
Parameter Sets: Format
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ea595-155">-InputObject</span><span class="sxs-lookup"><span data-stu-id="ea595-155">-InputObject</span></span>

<span data-ttu-id="ea595-156">Указывает текст для присоединения.</span><span class="sxs-lookup"><span data-stu-id="ea595-156">Specifies the text to be joined.</span></span> <span data-ttu-id="ea595-157">Введите переменную, содержащую текст, или введите команду или выражение, которое получает объекты для объединения в строки.</span><span class="sxs-lookup"><span data-stu-id="ea595-157">Enter a variable that contains the text, or type a command or expression that gets the objects to join into strings.</span></span>

```yaml
Type: System.Management.Automation.PSObject[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="ea595-158">-Аутпутпрефикс</span><span class="sxs-lookup"><span data-stu-id="ea595-158">-OutputPrefix</span></span>

<span data-ttu-id="ea595-159">Текст, вставленный перед выходной строкой.</span><span class="sxs-lookup"><span data-stu-id="ea595-159">Text that's inserted before the output string.</span></span> <span data-ttu-id="ea595-160">Строка может содержать специальные символы, такие как возврат каретки ( `` `r `` ), строка ( `` `n `` ) и знак табуляции ( `` `t `` ).</span><span class="sxs-lookup"><span data-stu-id="ea595-160">The string can contain special characters such as carriage return (`` `r ``), newline (`` `n ``), and tab (`` `t ``).</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: op

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ea595-161">-Аутпутсуффикс</span><span class="sxs-lookup"><span data-stu-id="ea595-161">-OutputSuffix</span></span>

<span data-ttu-id="ea595-162">Текст, добавляемый к выходной строке.</span><span class="sxs-lookup"><span data-stu-id="ea595-162">Text that's appended to the output string.</span></span> <span data-ttu-id="ea595-163">Строка может содержать специальные символы, такие как возврат каретки ( `` `r `` ), строка ( `` `n `` ) и знак табуляции ( `` `t `` ).</span><span class="sxs-lookup"><span data-stu-id="ea595-163">The string can contain special characters such as carriage return (`` `r ``), newline (`` `n ``), and tab (`` `t ``).</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: os

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ea595-164">-Property</span><span class="sxs-lookup"><span data-stu-id="ea595-164">-Property</span></span>

<span data-ttu-id="ea595-165">Имя свойства или выражение свойства, которое будет проецировать объект конвейера в текст.</span><span class="sxs-lookup"><span data-stu-id="ea595-165">The name of a property, or a property expression, that will project the pipeline object to text.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.PSPropertyExpression
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ea595-166">-Separator</span><span class="sxs-lookup"><span data-stu-id="ea595-166">-Separator</span></span>

<span data-ttu-id="ea595-167">Текст или символы, такие как запятая или точка с запятой, вставленные между текстом для каждого объекта конвейера.</span><span class="sxs-lookup"><span data-stu-id="ea595-167">Text or characters such as a comma or semicolon that's inserted between the text for each pipeline object.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ea595-168">-Синглекуоте</span><span class="sxs-lookup"><span data-stu-id="ea595-168">-SingleQuote</span></span>

<span data-ttu-id="ea595-169">Заключает строковое значение каждого объекта конвейера в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="ea595-169">Wraps the string value of each pipeline object in single quotes.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: SingleQuote
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ea595-170">-UseCulture</span><span class="sxs-lookup"><span data-stu-id="ea595-170">-UseCulture</span></span>

<span data-ttu-id="ea595-171">Использует разделитель списка для текущего языка и региональных параметров в качестве разделителя элементов.</span><span class="sxs-lookup"><span data-stu-id="ea595-171">Uses the list separator for the current culture as the item delimiter.</span></span> <span data-ttu-id="ea595-172">Чтобы найти разделитель списка для языка и региональных параметров, используйте следующую команду: `(Get-Culture).TextInfo.ListSeparator` .</span><span class="sxs-lookup"><span data-stu-id="ea595-172">To find the list separator for a culture, use the following command: `(Get-Culture).TextInfo.ListSeparator`.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ea595-173">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="ea595-173">CommonParameters</span></span>

<span data-ttu-id="ea595-174">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="ea595-174">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ea595-175">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="ea595-175">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ea595-176">Входные данные</span><span class="sxs-lookup"><span data-stu-id="ea595-176">INPUTS</span></span>

### <span data-ttu-id="ea595-177">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="ea595-177">System.Management.Automation.PSObject</span></span>

## <span data-ttu-id="ea595-178">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="ea595-178">OUTPUTS</span></span>

### <span data-ttu-id="ea595-179">System.String</span><span class="sxs-lookup"><span data-stu-id="ea595-179">System.String</span></span>

## <span data-ttu-id="ea595-180">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="ea595-180">NOTES</span></span>

## <span data-ttu-id="ea595-181">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="ea595-181">RELATED LINKS</span></span>

[<span data-ttu-id="ea595-182">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="ea595-182">about_Automatic_Variables</span></span>](../microsoft.powershell.core/about/about_automatic_variables.md)

[<span data-ttu-id="ea595-183">about_Special_Characters</span><span class="sxs-lookup"><span data-stu-id="ea595-183">about_Special_Characters</span></span>](..//microsoft.powershell.core/about/about_special_characters.md)

[<span data-ttu-id="ea595-184">Подстроки</span><span class="sxs-lookup"><span data-stu-id="ea595-184">Substring</span></span>](/dotnet/api/system.string.substring)

