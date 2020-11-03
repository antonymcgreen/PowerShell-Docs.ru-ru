---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertfrom-string?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertFrom-String
ms.openlocfilehash: 665a0ca8332c4052b59362c7947e408ba811c5f2
ms.sourcegitcommit: c4906f4c9fa4ef1a16dcd6dd00ff960d19446d71
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/01/2020
ms.locfileid: "93230562"
---
# <span data-ttu-id="65458-103">ConvertFrom-String</span><span class="sxs-lookup"><span data-stu-id="65458-103">ConvertFrom-String</span></span>

## <span data-ttu-id="65458-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="65458-104">SYNOPSIS</span></span>
<span data-ttu-id="65458-105">Извлекает и анализирует структурированные свойства из содержимого строки.</span><span class="sxs-lookup"><span data-stu-id="65458-105">Extracts and parses structured properties from string content.</span></span>

## <span data-ttu-id="65458-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="65458-106">SYNTAX</span></span>

### <span data-ttu-id="65458-107">Биделимитер (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="65458-107">ByDelimiter (Default)</span></span>

```
ConvertFrom-String [-Delimiter <String>] [-PropertyNames <String[]>] [-InputObject] <String>
 [<CommonParameters>]
```

### <span data-ttu-id="65458-108">темплатепарсинг</span><span class="sxs-lookup"><span data-stu-id="65458-108">TemplateParsing</span></span>

```
ConvertFrom-String [-TemplateFile <String[]>] [-TemplateContent <String[]>] [-IncludeExtent] [-UpdateTemplate]
 [-InputObject] <String> [<CommonParameters>]
```

## <span data-ttu-id="65458-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="65458-109">DESCRIPTION</span></span>

<span data-ttu-id="65458-110">Командлет **ConvertFrom-String** извлекает и анализирует структурированные свойства из содержимого строки.</span><span class="sxs-lookup"><span data-stu-id="65458-110">The **ConvertFrom-String** cmdlet extracts and parses structured properties from string content.</span></span>
<span data-ttu-id="65458-111">Этот командлет создает объект путем анализа текста из традиционного текстового потока.</span><span class="sxs-lookup"><span data-stu-id="65458-111">This cmdlet generates an object by parsing text from a traditional text stream.</span></span>
<span data-ttu-id="65458-112">Для каждой строки в конвейере командлет разбивает входные данные на разделитель или выражение синтаксического анализа, а затем присваивает имена свойств каждому из результирующих разделенных элементов.</span><span class="sxs-lookup"><span data-stu-id="65458-112">For each string in the pipeline, the cmdlet splits the input by either a delimiter or a parse expression, and then assigns property names to each of the resulting split elements.</span></span>
<span data-ttu-id="65458-113">Можно указать имена этих свойств. в противном случае они будут созданы автоматически.</span><span class="sxs-lookup"><span data-stu-id="65458-113">You can provide these property names; if you do not, they are automatically generated for you.</span></span>

<span data-ttu-id="65458-114">Набор параметров по умолчанию командлета, **биделимитер** , точно разбивается на разделителе регулярных выражений.</span><span class="sxs-lookup"><span data-stu-id="65458-114">The cmdlet's default parameter set, **ByDelimiter** , splits exactly on the regular expression delimiter.</span></span>
<span data-ttu-id="65458-115">Он не выполняет сопоставление или разделители кавычек, как это `Import-Csv` делает командлет.</span><span class="sxs-lookup"><span data-stu-id="65458-115">It does not perform quote matching or delimiter escaping as the `Import-Csv` cmdlet does.</span></span>

<span data-ttu-id="65458-116">Альтернативный набор параметров командлета **темплатепарсинг** создает элементы из групп, захваченных регулярным выражением.</span><span class="sxs-lookup"><span data-stu-id="65458-116">The cmdlet's alternate parameter set, **TemplateParsing** , generates elements from the groups that are captured by a regular expression.</span></span> <span data-ttu-id="65458-117">Дополнительные сведения о регулярных выражениях см. в разделе [about_Regular_Expressions](../Microsoft.PowerShell.Core/About/about_Regular_Expressions.md).</span><span class="sxs-lookup"><span data-stu-id="65458-117">For more information on regular expressions, see [about_Regular_Expressions](../Microsoft.PowerShell.Core/About/about_Regular_Expressions.md).</span></span>

<span data-ttu-id="65458-118">Этот командлет поддерживает два режима: базовый синтаксический анализ с разделителями и автоматически созданный, основанный на примерах анализ.</span><span class="sxs-lookup"><span data-stu-id="65458-118">This cmdlet supports two modes: basic delimited parsing, and automatically-generated, example-driven parsing.</span></span>

<span data-ttu-id="65458-119">Анализ с разделением, используемый по умолчанию, разбивает входные данные с помощью пробелов и присваивает имена свойств получаемым группам.</span><span class="sxs-lookup"><span data-stu-id="65458-119">Delimited parsing, by default, splits the input at white space, and assigns property names to the resulting groups.</span></span>

<span data-ttu-id="65458-120">Можно настроить разделитель, передав `ConvertFrom-String` результаты в один из `Format-*` командлетов, или можно использовать параметр **разделителя** .</span><span class="sxs-lookup"><span data-stu-id="65458-120">You can customize the delimiter by piping the `ConvertFrom-String` results into one of the `Format-*` cmdlets, or you can use the **Delimiter** parameter.</span></span>

<span data-ttu-id="65458-121">Командлет также поддерживает автоматически созданный, основанный на примерах синтаксический анализ на основе [FlashExtract, исследование работы в Microsoft Research](https://www.microsoft.com/research/publication/flashextract-framework-data-extraction-examples/).</span><span class="sxs-lookup"><span data-stu-id="65458-121">The cmdlet also supports automatically-generated, example-driven parsing based on the [FlashExtract, research work by Microsoft Research](https://www.microsoft.com/research/publication/flashextract-framework-data-extraction-examples/).</span></span>

## <span data-ttu-id="65458-122">Примеры</span><span class="sxs-lookup"><span data-stu-id="65458-122">EXAMPLES</span></span>

### <span data-ttu-id="65458-123">Пример 1. Создание объекта с именами свойств по умолчанию</span><span class="sxs-lookup"><span data-stu-id="65458-123">Example 1: Generate an object with default property names</span></span>

```powershell
"Hello World" | ConvertFrom-String
```

```Output
P1    P2
--    --
Hello World
```

<span data-ttu-id="65458-124">Эта команда создает объект с именами свойств по умолчанию **P1** и **P2** .</span><span class="sxs-lookup"><span data-stu-id="65458-124">This command generates an object with default property names, **P1** and **P2** .</span></span>

### <span data-ttu-id="65458-125">Пример 1A: Get для получения сведений о созданном объекте</span><span class="sxs-lookup"><span data-stu-id="65458-125">Example 1A: Get to know the generated object</span></span>

<span data-ttu-id="65458-126">Эта команда создает один объект со свойствами **P1** , **P2** ; по умолчанию оба свойства имеют **строковый** тип.</span><span class="sxs-lookup"><span data-stu-id="65458-126">This command generates one object with properties **P1** , **P2** ; both properties are of **String** type, by default.</span></span>

```powershell
"Hello World" | ConvertFrom-String | Get-Member
```

```Output

   TypeName: System.Management.Automation.PSCustomObject

Name        MemberType   Definition
----        ----------   ----------
Equals      Method       bool Equals(System.Object obj)
GetHashCode Method       int GetHashCode()
GetType     Method       type GetType()
ToString    Method       string ToString()
P1          NoteProperty string P1=Hello
P2          NoteProperty string P2=World
```

### <span data-ttu-id="65458-127">Пример 2. Создание объекта с именами свойств по умолчанию с помощью разделителя</span><span class="sxs-lookup"><span data-stu-id="65458-127">Example 2: Generate an object with default property names using a delimiter</span></span>

<span data-ttu-id="65458-128">Эта команда создает объект с доменом и именем пользователя, используя обратную косую черту ( `\` ) в качестве разделителя.</span><span class="sxs-lookup"><span data-stu-id="65458-128">This command generates an object with a domain and username using the backslash (`\`) as the delimiter.</span></span> <span data-ttu-id="65458-129">При использовании регулярных выражений символ обратной косой черты должен быть экранирован с помощью другой обратной косой черты.</span><span class="sxs-lookup"><span data-stu-id="65458-129">The backslash character must be escaped with another backslash when using regular expressions.</span></span>

```powershell
"Contoso\Administrator" | ConvertFrom-String -Delimiter "\\"
```

```Output
P1      P2
--      --
Contoso Administrator
```

### <span data-ttu-id="65458-130">Пример 3. Создание объекта, содержащего два именованных свойства</span><span class="sxs-lookup"><span data-stu-id="65458-130">Example 3: Generate an object that contains two named properties</span></span>

<span data-ttu-id="65458-131">В следующем примере создаются объекты в записях файлов Windows hosts.</span><span class="sxs-lookup"><span data-stu-id="65458-131">The following example creates objects from Windows hosts file entries.</span></span>

```powershell
$content = Get-Content C:\Windows\System32\drivers\etc\hosts
$content = $content -match "^[^#]"
$content | ConvertFrom-String -PropertyNames IP, Server
```

```Output
IP             Server
--             ------
192.168.7.10   W2012R2
192.168.7.20   W2016
192.168.7.101  WIN8
192.168.7.102  WIN10
```

<span data-ttu-id="65458-132">`Get-Content`Командлет сохраняет содержимое файла узлов Windows в `$content` .</span><span class="sxs-lookup"><span data-stu-id="65458-132">The `Get-Content` cmdlet stores the content of a Windows hosts file in `$content`.</span></span> <span data-ttu-id="65458-133">Вторая команда удаляет комментарии в начале файла hosts с помощью регулярного выражения, которое соответствует любой строке, не начинающейся с ( `#` ).</span><span class="sxs-lookup"><span data-stu-id="65458-133">The second command removes any comments at the beginning of the hosts file using a regular expression that matches any line that does not start with (`#`).</span></span> <span data-ttu-id="65458-134">Последняя команда преобразует оставшийся текст в объекты с помощью свойств **сервера** и **IP-адреса** .</span><span class="sxs-lookup"><span data-stu-id="65458-134">The last command converts the remaining text into objects with **Server** and **IP** properties.</span></span>

### <span data-ttu-id="65458-135">Пример 4. Использование выражения в качестве значения параметра TemplateContent. Сохраните результаты в переменной.</span><span class="sxs-lookup"><span data-stu-id="65458-135">Example 4: Use an expression as the value of the TemplateContent parameter, save the results in a variable.</span></span>

<span data-ttu-id="65458-136">Эта команда использует выражение в качестве значения параметра **TemplateContent** .</span><span class="sxs-lookup"><span data-stu-id="65458-136">This command uses an expression as the value of the **TemplateContent** parameter.</span></span>
<span data-ttu-id="65458-137">Выражение сохраняется в переменной для простоты.</span><span class="sxs-lookup"><span data-stu-id="65458-137">The expression is saved in a variable for simplicity.</span></span>
<span data-ttu-id="65458-138">Windows PowerShell теперь понимает, что строка, используемая в конвейере, `ConvertFrom-String` имеет три свойства:</span><span class="sxs-lookup"><span data-stu-id="65458-138">Windows PowerShell understands now that the string that is used on the pipeline to `ConvertFrom-String` has three properties:</span></span>

- <span data-ttu-id="65458-139">**имя** ;</span><span class="sxs-lookup"><span data-stu-id="65458-139">**Name**</span></span>
- <span data-ttu-id="65458-140">**phone**</span><span class="sxs-lookup"><span data-stu-id="65458-140">**phone**</span></span>
- <span data-ttu-id="65458-141">**интервал**</span><span class="sxs-lookup"><span data-stu-id="65458-141">**age**</span></span>

```powershell
$template = @'
{Name*:Phoebe Cat}, {phone:425-123-6789}, {age:6}
{Name*:Lucky Shot}, {phone:(206) 987-4321}, {age:12}
'@

$testText = @'
Phoebe Cat, 425-123-6789, 6
Lucky Shot, (206) 987-4321, 12
Elephant Wise, 425-888-7766, 87
Wild Shrimp, (111)  222-3333, 1
'@

$PersonalData = $testText | ConvertFrom-String -TemplateContent $template
Write-output ("Pet items found: " + ($PersonalData.Count))
$PersonalData
```

```Output
Pet items found: 4

Name          phone           age
----          -----           ---
Phoebe Cat    425-123-6789    6
Lucky Shot    (206) 987-4321  12
Elephant Wise 425-888-7766    87
Wild Shrimp   (111)  222-3333 1
```

<span data-ttu-id="65458-142">Каждая строка во входных данных оценивается с помощью результатов выборки.</span><span class="sxs-lookup"><span data-stu-id="65458-142">Each line in the input is evaluated by the sample matches.</span></span> <span data-ttu-id="65458-143">Если строка совпадает с примерами, указанными в шаблоне, значения извлекаются и передаются в выходную переменную.</span><span class="sxs-lookup"><span data-stu-id="65458-143">If the line matches the examples given in the pattern, values are extracted and passed to the output variable.</span></span>

<span data-ttu-id="65458-144">Образец данных `$template` предоставляет два различных формата телефона:</span><span class="sxs-lookup"><span data-stu-id="65458-144">The sample data, `$template`, provides two different phone formats:</span></span>

- `425-123-6789`
- `(206) 987-4321`

<span data-ttu-id="65458-145">Образец данных также предоставляет два разных формата возраста:</span><span class="sxs-lookup"><span data-stu-id="65458-145">The sample data also provides two different age formats:</span></span>

- `6`
- `12`

<span data-ttu-id="65458-146">Это означает, что телефонные `(206) 987 4321` номера не будут распознаны, так как нет демонстрационных данных, соответствующих этому шаблону, так как нет дефисов.</span><span class="sxs-lookup"><span data-stu-id="65458-146">This implies that phones like `(206) 987 4321` will not be recognized, because there's no sample data that matches that pattern because there are no hyphens.</span></span>

### <span data-ttu-id="65458-147">Пример 5. Указание типов данных для созданных свойств</span><span class="sxs-lookup"><span data-stu-id="65458-147">Example 5: Specifying data types to the generated properties</span></span>

<span data-ttu-id="65458-148">Это тот же пример, что и в примере 4.</span><span class="sxs-lookup"><span data-stu-id="65458-148">This is the same example as Example 4, above.</span></span>
<span data-ttu-id="65458-149">Разница заключается в том, что строка шаблона включает тип данных для каждого требуемого свойства.</span><span class="sxs-lookup"><span data-stu-id="65458-149">The difference is that the pattern string includes a data type for each desired property.</span></span>

```powershell
$template = @'
{[string]Name*:Phoebe Cat}, {[string]phone:425-123-6789}, {[int]age:6}
{[string]Name*:Lucky Shot}, {[string]phone:(206) 987-4321}, {[int]age:12}
'@

$testText = @'
Phoebe Cat, 425-123-6789, 6
Lucky Shot, (206) 987-4321, 12
Elephant Wise, 425-888-7766, 87
Wild Shrimp, (111)  222-3333, 1
'@

$PersonalData = $testText | ConvertFrom-String -TemplateContent $template
Write-output ("Pet items found: " + ($PersonalData.Count))
$PersonalData
```

```Output
Pet items found: 4

Name          phone           age
----          -----           ---
Phoebe Cat    425-123-6789      6
Lucky Shot    (206) 987-4321   12
Elephant Wise 425-888-7766     87
Wild Shrimp   (111)  222-3333   1
```

```powershell
$PersonalData | Get-Member
```

```Output
   TypeName: System.Management.Automation.PSCustomObject

Name        MemberType   Definition
----        ----------   ----------
Equals      Method       bool Equals(System.Object obj)
GetHashCode Method       int GetHashCode()
GetType     Method       type GetType()
ToString    Method       string ToString()
age         NoteProperty int age=6
Name        NoteProperty string Name=Phoebe Cat
phone       NoteProperty string phone=425-123-6789
```

<span data-ttu-id="65458-150">`Get-Member`Командлет показывает, что свойство **Age** является целым числом.</span><span class="sxs-lookup"><span data-stu-id="65458-150">The `Get-Member` cmdlet is used to show that the **age** property is an integer.</span></span>

## <span data-ttu-id="65458-151">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="65458-151">PARAMETERS</span></span>

### <span data-ttu-id="65458-152">-Delimiter</span><span class="sxs-lookup"><span data-stu-id="65458-152">-Delimiter</span></span>

<span data-ttu-id="65458-153">Задает регулярное выражение, определяющее границу между элементами.</span><span class="sxs-lookup"><span data-stu-id="65458-153">Specifies a regular expression that identifies the boundary between elements.</span></span>
<span data-ttu-id="65458-154">Элементы, создаваемые при разбиении, становятся свойствами в результирующем объекте.</span><span class="sxs-lookup"><span data-stu-id="65458-154">Elements that are created by the split become properties in the resulting object.</span></span>
<span data-ttu-id="65458-155">Разделитель в конечном итоге используется при вызове метода **Split** типа `[System.Text.RegularExpressions.RegularExpression]` .</span><span class="sxs-lookup"><span data-stu-id="65458-155">The delimiter is ultimately used in a call to the **Split** method of the type `[System.Text.RegularExpressions.RegularExpression]`.</span></span>

```yaml
Type: System.String
Parameter Sets: ByDelimiter
Aliases: DEL

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="65458-156">-Инклудикстент</span><span class="sxs-lookup"><span data-stu-id="65458-156">-IncludeExtent</span></span>

<span data-ttu-id="65458-157">Указывает, что этот командлет включает свойство текста экстента, которое по умолчанию удаляется.</span><span class="sxs-lookup"><span data-stu-id="65458-157">Indicates that this cmdlet includes an extent text property that is removed by default.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: TemplateParsing
Aliases: IE

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="65458-158">-InputObject</span><span class="sxs-lookup"><span data-stu-id="65458-158">-InputObject</span></span>

<span data-ttu-id="65458-159">Указывает строки, полученные из конвейера, или переменную, содержащую объект строки.</span><span class="sxs-lookup"><span data-stu-id="65458-159">Specifies strings received from the pipeline, or a variable that contains a string object.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="65458-160">-PropertyNames</span><span class="sxs-lookup"><span data-stu-id="65458-160">-PropertyNames</span></span>

<span data-ttu-id="65458-161">Задает массив имен свойств, которым присваиваются разделенные значения в результирующем объекте.</span><span class="sxs-lookup"><span data-stu-id="65458-161">Specifies an array of property names to which to assign split values in the resulting object.</span></span>
<span data-ttu-id="65458-162">Каждая строка текста, в которой разбиваются или анализируются, создает элементы, представляющие значения свойств.</span><span class="sxs-lookup"><span data-stu-id="65458-162">Every line of text that you split or parse generates elements that represent property values.</span></span>
<span data-ttu-id="65458-163">Если элемент является результатом группы записи и имя группы захвата (например, `(?<name>)` или `(?'name')` ), то именем этой группы захвата присваивается свойство.</span><span class="sxs-lookup"><span data-stu-id="65458-163">If the element is the result of a capture group, and that capture group is named (for example, `(?<name>)` or `(?'name')` ), then the name of that capture group is assigned to the property.</span></span>

<span data-ttu-id="65458-164">При предоставлении любых элементов в массиве **PropertyName** эти имена присваиваются свойствам, которые еще не были именованы.</span><span class="sxs-lookup"><span data-stu-id="65458-164">If you provide any elements in the **PropertyName** array, those names are assigned to properties that have not yet been named.</span></span>

<span data-ttu-id="65458-165">Если указать больше имен свойств, чем количество полей, PowerShell игнорирует дополнительные имена свойств.</span><span class="sxs-lookup"><span data-stu-id="65458-165">If you provide more property names than there are fields, PowerShell ignores the extra property names.</span></span> <span data-ttu-id="65458-166">Если не указать достаточное количество свойств для именования всех полей, PowerShell автоматически назначит числовые имена свойств всем свойствам, которые не имеют имен: **P1** , **P2** и т. д.</span><span class="sxs-lookup"><span data-stu-id="65458-166">If you do not specify enough property names to name all fields, PowerShell automatically assigns numerical property names to any properties that are not named: **P1** , **P2** , etc.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ByDelimiter
Aliases: PN

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="65458-167">-TemplateContent</span><span class="sxs-lookup"><span data-stu-id="65458-167">-TemplateContent</span></span>

<span data-ttu-id="65458-168">Указывает выражение или выражение, сохраненное в виде переменной, описывающее свойства, к которым этот командлет назначает строки.</span><span class="sxs-lookup"><span data-stu-id="65458-168">Specifies an expression, or an expression saved as a variable, that describes the properties to which this cmdlet assigns strings.</span></span> <span data-ttu-id="65458-169">Синтаксис спецификации поля шаблона следующий: `{[optional-typecast]<name>:<example-value>}` .</span><span class="sxs-lookup"><span data-stu-id="65458-169">The syntax of a template field specification is the following: `{[optional-typecast]<name>:<example-value>}`.</span></span>

```yaml
Type: System.String[]
Parameter Sets: TemplateParsing
Aliases: TC

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="65458-170">-TemplateFile</span><span class="sxs-lookup"><span data-stu-id="65458-170">-TemplateFile</span></span>

<span data-ttu-id="65458-171">Указывает файл в виде массива, который содержит шаблон для требуемого анализа строки.</span><span class="sxs-lookup"><span data-stu-id="65458-171">Specifies a file, as an array, that contains a template for the desired parsing of the string.</span></span>
<span data-ttu-id="65458-172">В файле шаблона свойства и их значения заключаются в квадратные скобки, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="65458-172">In the template file, properties and their values are enclosed in brackets, as shown below.</span></span>
<span data-ttu-id="65458-173">Если свойство, например свойство **Name** и связанные с ним другие свойства, встречается несколько раз, можно добавить звездочку (), `*` чтобы указать, что результатом будет несколько записей.</span><span class="sxs-lookup"><span data-stu-id="65458-173">If a property, such as the **Name** property and its associated other properties, appears multiple times, you can add an asterisk (`*`) to indicate that this results in multiple records.</span></span> <span data-ttu-id="65458-174">Это позволяет избежать извлечения нескольких свойств в одну запись.</span><span class="sxs-lookup"><span data-stu-id="65458-174">This avoids extracting multiple properties into a single record.</span></span>

```
{Name*:David Chew}
{City:Redmond}, {State:WA}
{Name*:Evan Narvaez}    {Name*:Antonio Moreno}
{City:Issaquah}, {State:WA}
```

```yaml
Type: System.String[]
Parameter Sets: TemplateParsing
Aliases: TF

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="65458-175">-Упдатетемплате</span><span class="sxs-lookup"><span data-stu-id="65458-175">-UpdateTemplate</span></span>

<span data-ttu-id="65458-176">Указывает, что этот командлет сохраняет результаты алгоритма обучения в комментарий в файле шаблона.</span><span class="sxs-lookup"><span data-stu-id="65458-176">Indicates that this cmdlet saves the results of a learning algorithm into a comment in the template file.</span></span>
<span data-ttu-id="65458-177">Это ускоряет процесс обучения алгоритма.</span><span class="sxs-lookup"><span data-stu-id="65458-177">This makes the algorithm learning process faster.</span></span>
<span data-ttu-id="65458-178">Чтобы использовать этот параметр, необходимо также указать файл шаблона с параметром **TemplateFile** .</span><span class="sxs-lookup"><span data-stu-id="65458-178">To use this parameter, you must also specify a template file with the **TemplateFile** parameter.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: TemplateParsing
Aliases: UT

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="65458-179">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="65458-179">CommonParameters</span></span>

<span data-ttu-id="65458-180">Этот командлет поддерживает общие параметры: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` и `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="65458-180">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="65458-181">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="65458-181">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="65458-182">Входные данные</span><span class="sxs-lookup"><span data-stu-id="65458-182">INPUTS</span></span>

### <span data-ttu-id="65458-183">System.String</span><span class="sxs-lookup"><span data-stu-id="65458-183">System.String</span></span>

## <span data-ttu-id="65458-184">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="65458-184">OUTPUTS</span></span>

## <span data-ttu-id="65458-185">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="65458-185">NOTES</span></span>

## <span data-ttu-id="65458-186">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="65458-186">RELATED LINKS</span></span>

[<span data-ttu-id="65458-187">ConvertFrom-String: синтаксический анализ текста на основе примера</span><span class="sxs-lookup"><span data-stu-id="65458-187">ConvertFrom-String: Example-based text parsing</span></span>](https://devblogs.microsoft.com/powershell/convertfrom-string-example-based-text-parsing/)

[<span data-ttu-id="65458-188">ConvertFrom-StringData</span><span class="sxs-lookup"><span data-stu-id="65458-188">ConvertFrom-StringData</span></span>](ConvertFrom-StringData.md)

[<span data-ttu-id="65458-189">ConvertFrom-Csv</span><span class="sxs-lookup"><span data-stu-id="65458-189">ConvertFrom-Csv</span></span>](ConvertFrom-Csv.md)

[<span data-ttu-id="65458-190">ConvertTo-Xml</span><span class="sxs-lookup"><span data-stu-id="65458-190">ConvertTo-Xml</span></span>](ConvertTo-Xml.md)
