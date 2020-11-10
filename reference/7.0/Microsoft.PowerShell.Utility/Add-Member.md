---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 4/26/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/add-member?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-Member
ms.openlocfilehash: 8c27ebe1c5f1a0c53f5012f1faa17a9fdb1cdcff
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2020
ms.locfileid: "94391040"
---
# Add-Member

## Краткий обзор
Добавляет пользовательские свойства и методы в экземпляр объекта PowerShell.

## SYNTAX

### Имя_типа (по умолчанию)

```
Add-Member -InputObject <PSObject> -TypeName <String> [-PassThru] [<CommonParameters>]
```

### нотепропертимултимемберсет

```
Add-Member -InputObject <PSObject> [-TypeName <String>] [-Force] [-PassThru]
 [-NotePropertyMembers] <IDictionary> [<CommonParameters>]
```

### нотепропертисинглемемберсет

```
Add-Member -InputObject <PSObject> [-TypeName <String>] [-Force] [-PassThru] [-NotePropertyName] <String>
 [-NotePropertyValue] <Object> [<CommonParameters>]
```

### MemberSet

```
Add-Member -InputObject <PSObject> [-MemberType] <PSMemberTypes> [-Name] <String> [[-Value] <Object>]
 [[-SecondValue] <Object>] [-TypeName <String>] [-Force] [-PassThru] [<CommonParameters>]
```

## DESCRIPTION

`Add-Member`Командлет позволяет добавлять элементы (свойства и методы) в экземпляр объекта PowerShell. Например, можно добавить элемент NoteProperty, содержащий описание объекта или элемент **ScriptMethod** , который запускает скрипт для изменения объекта.

Чтобы использовать `Add-Member` , передайте объект в `Add-Member` или используйте параметр **InputObject** для указания объекта.

Параметр **MemberType** указывает тип добавляемого члена. Параметр **Name** присваивает имя новому элементу, а параметр **value** задает значение элемента.

Свойства и методы добавляются только в определенный экземпляр указанного объекта. `Add-Member` не изменяет тип объекта. Чтобы создать новый тип объекта, используйте `Add-Type` командлет.

Можно также использовать `Export-Clixml` командлет для сохранения в файле экземпляра объекта, включая дополнительные элементы. Затем можно использовать `Import-Clixml` командлет для повторного создания экземпляра объекта на основе сведений, хранящихся в экспортированном файле.

Начиная с Windows PowerShell 3,0, `Add-Member` содержит новые функции, упрощающие Добавление свойств заметок к объектам.
С помощью параметров **NotePropertyName** и **NotePropertyValue** можно определить свойство примечания, а с помощью параметра **NotePropertyMembers**  — получить хэш-таблицу имен и значений свойств примечаний.

Кроме того, начиная с выпуска Windows PowerShell 3.0 параметр **PassThru** , который создает выходной объект, требуется реже. `Add-Member` Теперь добавляет новые элементы непосредственно в входной объект большего числа типов. Подробнее см. в описании параметра **PassThru**.

## Примеры

### Пример 1. Добавление свойства примечания к PSObject

В следующем **примере к объекту** **FileInfo** , представляющему файл, добавляется свойство «Note» со значением «Done» `Test.txt` .

Первая команда использует `Get-ChildItem` командлет для получения объекта **FileInfo** , представляющего `Test.txt` файл. Он сохраняется в `$a` переменной.

Вторая команда добавляет свойство Note в объект в `$a` .

Третья команда использует точечную нотацию для получения значения свойства **Status** объекта в `$a` . Как видно из выходных данных, значение равно «Done».

```powershell
$A = Get-ChildItem c:\ps-test\test.txt
$A | Add-Member -NotePropertyName Status -NotePropertyValue Done
$A.Status
```

```Output
Done
```

### Пример 2. Добавление свойства Alias к PSObject

В следующем примере в объект, представляющий файл, добавляется свойство псевдонима **размера** `Test.txt` . Новое свойство является псевдонимом для свойства **length** .

Первая команда использует `Get-ChildItem` командлет для получения `Test.txt` объекта **FileInfo** .

Вторая команда добавляет свойство псевдонима **size** .
Третья команда использует точечную нотацию для получения значения нового свойства **size** .

```powershell
$A = Get-ChildItem C:\Temp\test.txt
$A | Add-Member -MemberType AliasProperty -Name Size -Value Length
$A.Size
```

```Output
2394
```

### Пример 3. Добавление свойства заметки Стрингусе в строку

В этом примере в строку добавляется свойство Note **стрингусе** .
Поскольку `Add-Member` не может добавлять типы к **строковым** входным объектам, можно указать параметр **PassThru** для создания выходного объекта. Последняя команда в этом примере выводит новое свойство.

В этом примере используется параметр **нотепропертимемберс** . Значение параметра **NotePropertyMembers** представляет собой хэш-таблицу. Ключ — это имя свойства заметки, **стрингусе** , а значение — значение свойства Note, **Отображаемое**.

```powershell
$A = "A string"
$A = $A | Add-Member -NotePropertyMembers @{StringUse="Display"} -PassThru
$A.StringUse
```

```Output
Display
```

### Пример 4. Добавление метода скрипта в объект FileInfo

В этом примере в объект **FileInfo** добавляется метод скрипта **значение sizeInMB** , который вычисляет размер файла до ближайшего мегабайта. Вторая команда создает блок **ScriptBlock** , который использует метод **Round** -static из `[math]` типа для округления размера файла до второго десятичного знака.

Параметр **value** также использует `$This` автоматическую переменную, которая представляет текущий объект. `$This`Переменная допустима только в блоках скриптов, которые определяют новые свойства и методы.

Последняя команда использует точечную нотацию для вызова нового метода скрипта **значение sizeInMB** для объекта в `$A` переменной.

```powershell
$A = Get-ChildItem C:\Temp\test.txt
$S = {[math]::Round(($this.Length / 1MB), 2)}
$A | Add-Member -MemberType ScriptMethod -Name "SizeInMB" -Value $S
$A.SizeInMB()
```

```Output
0.43
```

### Пример 5. копирование всех свойств объекта в другой

Эта функция копирует все свойства одного объекта в другой объект.

В `foreach` цикле используется `Get-Member` командлет для получения всех свойств объекта **from** . Команды в `foreach` цикле выполняются последовательно в каждом из свойств.

`Add-Member`Команда добавляет свойство объекта **from** в объект **to** в качестве **NoteProperty**. Значение копируется с помощью параметра **value** . Он использует параметр **Force** для добавления членов с одинаковым именем элемента.

```powershell
function Copy-Property ($From, $To)
{
    $properties = Get-Member -InputObject $From -MemberType Property
    foreach ($p in $properties)
    {
        $To | Add-Member -MemberType NoteProperty -Name $p.Name -Value $From.$($p.Name) -Force
    }
}
```

### Пример 6. Создание пользовательского объекта

В этом примере создается настраиваемый объект **ресурса** .

`New-Object`Командлет создает **PSObject**. В примере параметр **PSObject** сохраняется в `$Asset` переменной.

Вторая команда использует `[ordered]` ускоритель типов для создания упорядоченного словаря имен и значений. Команда сохраняет результат в `$D` переменной.

Третья команда использует параметр **нотепропертимемберс** `Add-Member` командлета, чтобы добавить словарь в `$D` переменную в **PSObject**.
Свойство **TypeName** присваивает параметру **PSObject** новое имя, **ресурс-контейнер**.

Последняя команда передает новый объект **Asset** в `Get-Member` командлет. Выходные данные показывают, что объект имеет имя типа **Asset** и свойства примечания, определенные в упорядоченном словаре.

```powershell
$Asset = New-Object -TypeName PSObject
$d = [ordered]@{Name="Server30";System="Server Core";PSVersion="4.0"}
$Asset | Add-Member -NotePropertyMembers $d -TypeName Asset
$Asset | Get-Member
```

```Output
   TypeName: Asset

Name        MemberType   Definition
----        ----------   ----------
Equals      Method       bool Equals(System.Object obj)
GetHashCode Method       int GetHashCode()
GetType     Method       type GetType()
ToString    Method       string ToString()
Name        NoteProperty System.String Name=Server30
PSVersion   NoteProperty System.String PSVersion=4.0
System      NoteProperty System.String System=Server Core
```

## PARAMETERS

### -Force

Указывает, что этот командлет добавляет новый элемент, даже если он имеет пользовательский элемент с таким же именем.
Нельзя использовать параметр **Force** для замены стандартного члена типа.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NotePropertyMultiMemberSet, NotePropertySingleMemberSet, MemberSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Указывает объект, в который добавляется новый член.
Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -MemberType

Указывает тип добавляемого элемента.
Этот параметр обязателен.
Допустимые значения для этого параметра:

- NoteProperty
- AliasProperty
- ScriptProperty
- CodeProperty
- ScriptMethod
- CodeMethod

Дополнительные сведения об этих значениях см. в разделе [перечисление псмембертипес](/dotnet/api/system.management.automation.psmembertypes) в пакете SDK для PowerShell.

Не у всех объектов имеются члены всех типов.
При указании типа элемента, который отсутствует в объекте, PowerShell возвращает ошибку.

```yaml
Type: System.Management.Automation.PSMemberTypes
Parameter Sets: MemberSet
Aliases: Type
Accepted values: AliasProperty, CodeProperty, Property, NoteProperty, ScriptProperty, Properties, PropertySet, Method, CodeMethod, ScriptMethod, Methods, ParameterizedProperty, MemberSet, Event, Dynamic, All

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Указывает имя члена, добавляемого этим командлетом.

```yaml
Type: System.String
Parameter Sets: MemberSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Нотепропертимемберс

Задает хэш-таблицу или упорядоченный словарь имен и значений свойств примечаний.
Введите хэш-таблицу или словарь, в котором ключи представляют имена свойств примечаний, а значения — значения этих свойств.

Дополнительные сведения о хэш-таблицах и упорядоченных словарях в PowerShell см. в разделе [about_Hash_Tables](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md).

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.Collections.IDictionary
Parameter Sets: NotePropertyMultiMemberSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Нотепропертинаме

Указывает имя свойства заметки.

Используйте этот параметр с параметром **NotePropertyValue**.
Это необязательный параметр.

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.String
Parameter Sets: NotePropertySingleMemberSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Нотепропертивалуе

Задает значение свойства Note.

Используйте этот параметр с параметром **нотепропертинаме** .
Это необязательный параметр.

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.Object
Parameter Sets: NotePropertySingleMemberSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru

Возвращает объект, представляющий элемент, с которым вы работаете.
По умолчанию этот командлет не создает выходные данные.

Для большинства объектов `Add-Member` добавляет новые элементы в входной объект.
Однако если входной объект является строкой, то `Add-Member` не может добавить элемент в входной объект.
В случае с такими объектами используйте параметр **PassThru** для создания выходного объекта.

В Windows PowerShell 2,0 `Add-Member` добавлены элементы только в оболочку **PSObject** объектов, а не в объект.
Используйте параметр **PassThru** , чтобы создать выходной объект для любого объекта, имеющего обертку **PSObject** .

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

### -SecondValue

Указывает дополнительные сведения о членах **AliasProperty** , **ScriptProperty** , **CodeProperty** или **CodeMethod**.

Если используется при добавлении **AliasProperty** , этот параметр должен иметь тип данных.
Преобразование к указанному типу данных добавляется к значению **AliasProperty**.

Например, если добавить **AliasProperty** , предоставляющий альтернативное имя для строкового свойства, можно также указать параметр **SecondValue** в **System. Int32** , чтобы указать, что значение этого свойства строки должно быть преобразовано в целое при доступе с помощью соответствующего **AliasProperty**.

Параметр **SecondValue** можно использовать для указания дополнительного **сценария ScriptBlock** при добавлении элемента **ScriptProperty** . Первый блок **ScriptBlock** , указанный в параметре **value** , используется для получения значения переменной. Второй блок **ScriptBlock** , указанный в параметре **SecondValue** , используется для задания значения переменной.

```yaml
Type: System.Object
Parameter Sets: MemberSet
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Value

Задает исходное значение добавленного члена.
При добавлении члена **AliasProperty** , **CodeProperty** , **ScriptProperty** или **CodeMethod** можно указать дополнительные дополнительные сведения с помощью параметра **SecondValue** .

```yaml
Type: System.Object
Parameter Sets: MemberSet
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TypeName

Указывает имя типа.

Если тип является классом в пространстве имен **System** или типом, имеющим ускоритель типа, можно ввести короткое имя типа. В остальных случаях требуется полное имя типа.
Этот параметр эффективен, только если **InputObject** является **PSObject**.

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.String
Parameter Sets: TypeNameSet, NotePropertyMultiMemberSet, NotePropertySingleMemberSet, MemberSet
Aliases:

Required: True (TypeNameSet), False (NotePropertyMultiMemberSet, NotePropertySingleMemberSet, MemberSet)
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## Входные данные

### System.Management.Automation.PSObject

В этот командлет можно передать по конвейеру любой тип объекта.

## Выходные данные

### Нет или системный. Object

При использовании параметра **PassThru** этот командлет возвращает новый расширенный объект.
В противном случае командлет не формирует никаких выходных данных.

## ПРИМЕЧАНИЯ

Элементы можно добавлять только в объекты **PSObject** . Чтобы определить, является ли объект объектом **PSObject** , используйте `-is` оператор.

Например, чтобы проверить объект, хранящийся в `$obj` переменной, введите `$obj -is [PSObject]` .

Имена параметров **MemberType** , **Name** , **value** и **SecondValue** являются необязательными.
Если имена параметров не заданы, то значения неименованных параметров должны отображаться в следующем порядке: **MemberType** , **Name** , **value** и **SecondValue**.

При указании имен параметры могут следовать в любом порядке.

В `$this` блоках сценариев можно использовать автоматическую переменную, определяющую значения новых свойств и методов.
`$this`Переменная ссылается на экземпляр объекта, к которому добавляются свойства и методы. Дополнительные сведения о `$this` переменной см. в разделе [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).

## Связанные ссылки

[Export-Clixml](Export-Clixml.md)

[Get-Member](Get-Member.md)

[Import-Clixml](Import-Clixml.md)

[New-Object](New-Object.md)

[about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md)
