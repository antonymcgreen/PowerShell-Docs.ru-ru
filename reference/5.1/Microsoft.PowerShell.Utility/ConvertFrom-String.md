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
# ConvertFrom-String

## Краткий обзор
Извлекает и анализирует структурированные свойства из содержимого строки.

## SYNTAX

### Биделимитер (по умолчанию)

```
ConvertFrom-String [-Delimiter <String>] [-PropertyNames <String[]>] [-InputObject] <String>
 [<CommonParameters>]
```

### темплатепарсинг

```
ConvertFrom-String [-TemplateFile <String[]>] [-TemplateContent <String[]>] [-IncludeExtent] [-UpdateTemplate]
 [-InputObject] <String> [<CommonParameters>]
```

## DESCRIPTION

Командлет **ConvertFrom-String** извлекает и анализирует структурированные свойства из содержимого строки.
Этот командлет создает объект путем анализа текста из традиционного текстового потока.
Для каждой строки в конвейере командлет разбивает входные данные на разделитель или выражение синтаксического анализа, а затем присваивает имена свойств каждому из результирующих разделенных элементов.
Можно указать имена этих свойств. в противном случае они будут созданы автоматически.

Набор параметров по умолчанию командлета, **биделимитер** , точно разбивается на разделителе регулярных выражений.
Он не выполняет сопоставление или разделители кавычек, как это `Import-Csv` делает командлет.

Альтернативный набор параметров командлета **темплатепарсинг** создает элементы из групп, захваченных регулярным выражением. Дополнительные сведения о регулярных выражениях см. в разделе [about_Regular_Expressions](../Microsoft.PowerShell.Core/About/about_Regular_Expressions.md).

Этот командлет поддерживает два режима: базовый синтаксический анализ с разделителями и автоматически созданный, основанный на примерах анализ.

Анализ с разделением, используемый по умолчанию, разбивает входные данные с помощью пробелов и присваивает имена свойств получаемым группам.

Можно настроить разделитель, передав `ConvertFrom-String` результаты в один из `Format-*` командлетов, или можно использовать параметр **разделителя** .

Командлет также поддерживает автоматически созданный, основанный на примерах синтаксический анализ на основе [FlashExtract, исследование работы в Microsoft Research](https://www.microsoft.com/research/publication/flashextract-framework-data-extraction-examples/).

## Примеры

### Пример 1. Создание объекта с именами свойств по умолчанию

```powershell
"Hello World" | ConvertFrom-String
```

```Output
P1    P2
--    --
Hello World
```

Эта команда создает объект с именами свойств по умолчанию **P1** и **P2** .

### Пример 1A: Get для получения сведений о созданном объекте

Эта команда создает один объект со свойствами **P1** , **P2** ; по умолчанию оба свойства имеют **строковый** тип.

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

### Пример 2. Создание объекта с именами свойств по умолчанию с помощью разделителя

Эта команда создает объект с доменом и именем пользователя, используя обратную косую черту ( `\` ) в качестве разделителя. При использовании регулярных выражений символ обратной косой черты должен быть экранирован с помощью другой обратной косой черты.

```powershell
"Contoso\Administrator" | ConvertFrom-String -Delimiter "\\"
```

```Output
P1      P2
--      --
Contoso Administrator
```

### Пример 3. Создание объекта, содержащего два именованных свойства

В следующем примере создаются объекты в записях файлов Windows hosts.

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

`Get-Content`Командлет сохраняет содержимое файла узлов Windows в `$content` . Вторая команда удаляет комментарии в начале файла hosts с помощью регулярного выражения, которое соответствует любой строке, не начинающейся с ( `#` ). Последняя команда преобразует оставшийся текст в объекты с помощью свойств **сервера** и **IP-адреса** .

### Пример 4. Использование выражения в качестве значения параметра TemplateContent. Сохраните результаты в переменной.

Эта команда использует выражение в качестве значения параметра **TemplateContent** .
Выражение сохраняется в переменной для простоты.
Windows PowerShell теперь понимает, что строка, используемая в конвейере, `ConvertFrom-String` имеет три свойства:

- **имя** ;
- **phone**
- **интервал**

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

Каждая строка во входных данных оценивается с помощью результатов выборки. Если строка совпадает с примерами, указанными в шаблоне, значения извлекаются и передаются в выходную переменную.

Образец данных `$template` предоставляет два различных формата телефона:

- `425-123-6789`
- `(206) 987-4321`

Образец данных также предоставляет два разных формата возраста:

- `6`
- `12`

Это означает, что телефонные `(206) 987 4321` номера не будут распознаны, так как нет демонстрационных данных, соответствующих этому шаблону, так как нет дефисов.

### Пример 5. Указание типов данных для созданных свойств

Это тот же пример, что и в примере 4.
Разница заключается в том, что строка шаблона включает тип данных для каждого требуемого свойства.

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

`Get-Member`Командлет показывает, что свойство **Age** является целым числом.

## PARAMETERS

### -Delimiter

Задает регулярное выражение, определяющее границу между элементами.
Элементы, создаваемые при разбиении, становятся свойствами в результирующем объекте.
Разделитель в конечном итоге используется при вызове метода **Split** типа `[System.Text.RegularExpressions.RegularExpression]` .

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

### -Инклудикстент

Указывает, что этот командлет включает свойство текста экстента, которое по умолчанию удаляется.

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

### -InputObject

Указывает строки, полученные из конвейера, или переменную, содержащую объект строки.

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

### -PropertyNames

Задает массив имен свойств, которым присваиваются разделенные значения в результирующем объекте.
Каждая строка текста, в которой разбиваются или анализируются, создает элементы, представляющие значения свойств.
Если элемент является результатом группы записи и имя группы захвата (например, `(?<name>)` или `(?'name')` ), то именем этой группы захвата присваивается свойство.

При предоставлении любых элементов в массиве **PropertyName** эти имена присваиваются свойствам, которые еще не были именованы.

Если указать больше имен свойств, чем количество полей, PowerShell игнорирует дополнительные имена свойств. Если не указать достаточное количество свойств для именования всех полей, PowerShell автоматически назначит числовые имена свойств всем свойствам, которые не имеют имен: **P1** , **P2** и т. д.

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

### -TemplateContent

Указывает выражение или выражение, сохраненное в виде переменной, описывающее свойства, к которым этот командлет назначает строки. Синтаксис спецификации поля шаблона следующий: `{[optional-typecast]<name>:<example-value>}` .

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

### -TemplateFile

Указывает файл в виде массива, который содержит шаблон для требуемого анализа строки.
В файле шаблона свойства и их значения заключаются в квадратные скобки, как показано ниже.
Если свойство, например свойство **Name** и связанные с ним другие свойства, встречается несколько раз, можно добавить звездочку (), `*` чтобы указать, что результатом будет несколько записей. Это позволяет избежать извлечения нескольких свойств в одну запись.

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

### -Упдатетемплате

Указывает, что этот командлет сохраняет результаты алгоритма обучения в комментарий в файле шаблона.
Это ускоряет процесс обучения алгоритма.
Чтобы использовать этот параметр, необходимо также указать файл шаблона с параметром **TemplateFile** .

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

### Общие параметры

Этот командлет поддерживает общие параметры: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` и `-WarningVariable` . См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## Входные данные

### System.String

## Выходные данные

## ПРИМЕЧАНИЯ

## Связанные ссылки

[ConvertFrom-String: синтаксический анализ текста на основе примера](https://devblogs.microsoft.com/powershell/convertfrom-string-example-based-text-parsing/)

[ConvertFrom-StringData](ConvertFrom-StringData.md)

[ConvertFrom-Csv](ConvertFrom-Csv.md)

[ConvertTo-Xml](ConvertTo-Xml.md)
