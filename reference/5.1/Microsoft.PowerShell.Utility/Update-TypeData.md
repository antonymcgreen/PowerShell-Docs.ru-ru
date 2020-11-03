---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/update-typedata?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Update-TypeData
ms.openlocfilehash: eb7bafff1af34ef34a1b67c1fbe8f9e2db0ca7ad
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227474"
---
# Update-TypeData

## Краткий обзор
Обновляет данные расширенного типа во время сеанса.

## Синтаксис

### FileSet (по умолчанию)

```
Update-TypeData [[-AppendPath] <String[]>] [-PrependPath <String[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### DynamicTypeSet

```
Update-TypeData [-MemberType <PSMemberTypes>] [-MemberName <String>] [-Value <Object>]
 [-SecondValue <Object>] [-TypeConverter <Type>] [-TypeAdapter <Type>]
 [-SerializationMethod <String>] [-TargetTypeForDeserialization <Type>]
 [-SerializationDepth <Int32>] [-DefaultDisplayProperty <String>]
 [-InheritPropertySerializationSet <Nullable`1>] [-StringSerializationSource <String>]
 [-DefaultDisplayPropertySet <String[]>] [-DefaultKeyPropertySet <String[]>]
 [-PropertySerializationSet <String[]>] -TypeName <String> [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### TypeDataSet

```
Update-TypeData [-Force] [-TypeData] <TypeData[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## Описание

`Update-TypeData`Командлет обновляет данные расширенного типа в сеансе путем перезагрузки `Types.ps1xml` файлов в память и добавления новых данных расширенного типа.

По умолчанию PowerShell загружает данные расширенного типа по мере необходимости. Без параметров `Update-TypeData` перезагружает все `Types.ps1xml` файлы, загруженные в сеанс, включая все добавленные файлы типов. С помощью параметров можно `Update-TypeData` добавлять новые файлы типов, а также добавлять и заменять данные расширенного типа.

`Update-TypeData`Командлет можно использовать для предварительной загрузки всех данных типа. Эта функция особенно полезна при разработке собственных типов, так как позволяет загружать их для тестирования.

Начиная с Windows PowerShell 3,0, можно использовать `Update-TypeData` для добавления и замены данных расширенного типа в сеансе без использования `Types.ps1xml` файла. Данные типа, добавленные динамически, то есть без помощи файла, добавляются только в текущий сеанс. Чтобы добавить данные типа во все сеансы, добавьте `Update-TypeData` команду в профиль PowerShell. Дополнительные сведения см. в разделе [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).

Кроме того, начиная с Windows PowerShell 3,0, командлет можно использовать `Get-TypeData` для получения расширенных типов в текущем сеансе и `Remove-TypeData` командлета для удаления расширенных типов из текущего сеанса.

Исключения, возникающие в свойствах или при добавлении свойств в `Update-TypeData` команду, не сообщают об ошибках. Это необходимо для подавления исключений, которые могут возникнуть во многих распространенных типах в процессе форматирования и вывода. Если вы получаете свойства .NET, подавление исключений можно обойти с помощью синтаксиса метода, как показано в следующем примере:

`"hello".get_Length()`

Обратите внимание, что синтаксис метода можно использовать только со свойствами .NET. Свойства, которые добавляются путем запуска `Update-TypeData` командлета, не могут использовать синтаксис метода.

Дополнительные сведения о `Types.ps1xml` файлах в PowerShell см. в разделе [about_Types.ps1XML](../Microsoft.PowerShell.Core/About/about_Types.ps1xml.md).

## Примеры

### Пример 1. обновление расширенных типов

```powershell
Update-TypeData
```

Эта команда обновляет конфигурацию расширенного типа из `Types.ps1xml` файлов, которые уже использовались в сеансе.

### Пример 2. Обновление типов несколько раз

В этом примере показано, как обновить типы в файле типа несколько раз в одном сеансе.

Первая команда обновляет конфигурацию расширенного типа из `Types.ps1xml` файлов, сначала обрабатывая `TypesA.types.ps1xml` файлы и `TypesB.types.ps1xml` .

Вторая команда показывает `TypesA.types.ps1xml` , как выполнить повторное обновление, например, если вы добавили или изменили тип в файле. Можно либо повторить предыдущую команду для `TypesA.types.ps1xml` файла, либо выполнить `Update-TypeData` команду без параметров, поскольку `TypesA.types.ps1xml` уже существует в списке файлов типов для текущего сеанса.

```powershell
Update-TypeData -PrependPath TypesA.types.ps1xml, TypesB.types.ps1xml
Update-TypeData -PrependPath TypesA.types.ps1xml
```

### Пример 3. Добавление свойства скрипта в объекты DateTime

В этом примере используется `Update-TypeData` для добавления свойства сценария **Quarter** в объекты **System. DateTime** в текущем сеансе, например, возвращаемые `Get-Date` командлетом.

```powershell
Update-TypeData -TypeName "System.DateTime" -MemberType ScriptProperty -MemberName "Quarter" -Value {
  if ($this.Month -in @(1,2,3)) {"Q1"}
  elseif ($this.Month -in @(4,5,6)) {"Q2"}
  elseif ($this.Month -in @(7,8,9)) {"Q3"}
  else {"Q4"}
}
(Get-Date).Quarter
```

```Output
Q1
```

`Update-TypeData`Команда использует параметр **TypeName** для указания типа **System. DateTime** , параметр **MemberName** для указания имени нового свойства, свойство **MemberType** для указания типа **ScriptProperty** , а параметр **value** — для указания скрипта, определяющего ежегодный квартал.

Значение свойства **Value**  — это сценарий, вычисляющий текущий годовой квартал. Блок скрипта использует `$this` автоматическую переменную для представления текущего экземпляра объекта и оператор in для определения того, отображается ли значение месяца в каждом массиве целых чисел. Дополнительные сведения об `-in` операторе см. в разделе [about_Comparison_Operators](../Microsoft.PowerShell.Core/about/about_Comparison_Operators.md).

Вторая команда возвращает новое свойство Quarter текущей даты.

### Пример 4. Обновление типа, который по умолчанию отображает в списках

В этом примере показано, как задать свойства типа, который по умолчанию отображает в списках, то есть если свойства не заданы. Поскольку данные типа не указываются в `Types.ps1xml` файле, они вступают в силу только в текущем сеансе.

```powershell
Update-TypeData -TypeName "System.DateTime" -DefaultDisplayPropertySet "DateTime, DayOfYear, Quarter"
Get-Date | Format-List
```

```Output
Thursday, March 15, 2012 12:00:00 AM
DayOfYear : 75
Quarter   : Q1
```

Первая команда использует `Update-TypeData` командлет для задания свойств списка по умолчанию для типа **System. DateTime** . С помощью параметра **TypeName** она определяет тип, а с помощью параметра **DefaultDisplayPropertySet**  — свойства списка по умолчанию. Выбранные свойства включают новое свойство **четвертого** сценария, добавленное в предыдущем примере.

Вторая команда использует `Get-Date` командлет для получения объекта **System. DateTime** , представляющего текущую дату. Команда использует оператор конвейера ( `|` ) для отправки объекта **DateTime** в `Format-List` командлет. Поскольку `Format-List` команда не указывает свойства, которые должны отображаться в списке, PowerShell использует значения по умолчанию, установленные `Update-TypeData` командой.

### Пример 5. обновление данных типа для поконвейерного объекта

```powershell
Get-Module | Update-TypeData -MemberType ScriptProperty -MemberName "SupportsUpdatableHelp" -Value {
  if ($this.HelpInfoUri) {$True} else {$False}
}
Get-Module -ListAvailable | Format-Table Name, SupportsUpdatableHelp
```

```Output
Name                             SupportsUpdatableHelp
----                             ---------------------
Microsoft.PowerShell.Diagnostics                  True
Microsoft.PowerShell.Host                         True
Microsoft.PowerShell.Management                   True
Microsoft.PowerShell.Security                     True
Microsoft.PowerShell.Utility                      True
Microsoft.WSMan.Management                        True
PSDiagnostics                                    False
PSScheduledJob                                    True
PSWorkflow                                        True
ServerManager                                     True
TroubleshootingPack                              False
```

В этом примере показано, что при передаче объекта в `Update-TypeData` объект `Update-TypeData` добавляет Расширенные данные типа для типа объекта.

Этот метод быстрее, чем использование `Get-Member` командлета или `Get-Type` метода для получения типа объекта. Однако при передаче коллекции объектов в `Update-TypeData` объект обновляет данные типа первого типа объектов, а затем возвращает ошибку для всех остальных объектов в коллекции, поскольку этот элемент уже определен в типе.

Первая команда использует `Get-Module` командлет для получения модуля PSScheduledJob. Команда передает объект Module в `Update-TypeData` командлет, который обновляет данные типа для типа **System. Management. Automation. PSModuleInfo** и производных от него типов, например тип модулеинфограупинг, `Get-Module` возвращаемый при использовании параметра **ListAvailable** в команде.

`Update-TypeData`Команды добавляют свойство скрипта **SupportsUpdatableHelp** во все импортированные модули. Значением параметра **value** является скрипт, который возвращает значение, `$True` Если свойство **HelpInfoUri** модуля заполнено и `$False` в противном случае —.

Вторая команда передает объекты модуля из `Get-Module` в `Format-Table` командлет, который отображает свойства **Name** и **SupportsUpdatableHelp** всех модулей в списке.

## Параметры

### -AppendPath

Указывает путь к необязательным `.ps1xml` файлам. Эти файлы загружаются в том порядке, в котором они были указаны, после загрузки встроенных файлов. Можно также передать значение **AppendPath** в `Update-TypeData` .

```yaml
Type: System.String[]
Parameter Sets: FileSet
Aliases: PSPath, Path

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -DefaultDisplayProperty

Указывает свойство типа, отображаемое `Format-Wide` командлетом, если другие свойства не указаны.

Введите имя стандартного или расширенного свойства типа. В качестве значения этого параметра может выступать имя типа, добавленного в рамках той же команды.

Это значение вступает в силу только в том случае, если для типа в файле не определены широкие представления `Format.ps1xml` .

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.String
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultDisplayPropertySet

Определяет одно или несколько свойств типа. Эти свойства отображаются `Format-List` командлетом, если не заданы другие свойства.

Введите имена стандартных или расширенных свойств типа. В качестве значения этого параметра могут выступать имена типов, добавленных в рамках той же команды.

Это значение вступает в силу только при отсутствии представлений списков, определенных для типа в `Format.ps1xml` файле.

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.String[]
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultKeyPropertySet

Определяет одно или несколько свойств типа. Эти свойства используются `Group-Object` командлетами и, `Sort-Object` если другие свойства не указаны.

Введите имена стандартных или расширенных свойств типа. В качестве значения этого параметра могут выступать имена типов, добавленных в рамках той же команды.

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.String[]
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Указывает, что командлет использует указанные данные типа, даже если данные типа уже указаны для этого типа.

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: DynamicTypeSet, TypeDataSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InheritPropertySerializationSet

Указывает, унаследован ли набор сериализованных свойств. Значение по умолчанию — `$Null`. Допустимые значения для этого параметра:

- `$True`. набор свойств наследуется.
- `$False`. набор свойств не наследуется.
- `$Null`. наследование не определено.

Этот параметр допустим только в том случае, если значение параметра **метод serializationmethod** равно `SpecificProperties` . Если значение этого параметра равно `$False` , параметр **пропертисериализатионсет** является обязательным.

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.Nullable`1[System.Boolean]
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MemberName

Определяет имя свойства или метода.

Вместе с параметрами **TypeName** , **MemberType** , **Value** и **SecondValue** этот параметр позволяет добавить или изменить свойство или метод типа.

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.String
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MemberType

Определяет тип элемента для добавления или изменения.

Вместе с параметрами **TypeName** , **MemberType** , **Value** и **SecondValue** этот параметр позволяет добавить или изменить свойство или метод типа. Допустимые значения для этого параметра:

- AliasProperty
- CodeMethod
- CodeProperty
- NoteProperty
- ScriptMethod
- ScriptProperty

Дополнительные сведения об этих значениях см. в разделе [Псмембертипес enumeration](/dotnet/api/system.management.automation.psmembertypes).

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.PSMemberTypes
Parameter Sets: DynamicTypeSet
Aliases:
Accepted values: NoteProperty, AliasProperty, ScriptProperty, CodeProperty, ScriptMethod, CodeMethod

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrependPath

Указывает путь к необязательным `.ps1xml` файлам. Эти файлы загружаются в том порядке, в котором они были указаны, до загрузки встроенных файлов.

```yaml
Type: System.String[]
Parameter Sets: FileSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PropertySerializationSet

Определяет имена сериализуемых свойств. Используйте этот параметр, если параметр **SerializationMethod** имеет значение **SpecificProperties** .

```yaml
Type: System.String[]
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SecondValue

Определяет дополнительные значения для элементов **AliasProperty** , **ScriptProperty** , **CodeProperty** , или **CodeMethod** .

Используйте этот параметр с параметрами **TypeName** , **MemberType** , **value** и **SecondValue** для добавления или изменения свойства или метода типа.

Если значение параметра **MemberType** равно `AliasProperty` , значение параметра **SecondValue** должно быть типом данных. PowerShell преобразует значение свойства Alias в указанный тип (то есть приводит). Например, если добавить свойство Alias, которое предоставляет альтернативное имя для свойства строки, можно также указать **SecondValue** для **System. Int32** , чтобы преобразовать строковое значение с псевдонимом в целое число.

Если значение параметра **MemberType** равно `ScriptProperty` , можно использовать параметр **SecondValue** , чтобы указать дополнительный блок скрипта. Блок скрипта в значении параметра **Value** получает значение переменной. Блок скрипта в значении параметра **SecondValue** устанавливает значение переменной.

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.Object
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SerializationDepth

Определяет, сколько уровней объектов типа будут сериализованы как строки. Значение по умолчанию `1` сериализует объект и его свойства. Значение `0` сериализует объект, но не его свойства. Значение `2` сериализует объект, его свойства и все объекты в значениях свойств.

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.Int32
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: 1
Accept pipeline input: False
Accept wildcard characters: False
```

### -SerializationMethod

Указывает метод сериализации для типа. Метод сериализации определяет сериализуемые свойства типа и метод сериализации. Допустимые значения для этого параметра:

- `AllPublicProperties`. сериализуются все открытые свойства типа. Можно использовать параметр **SerializationDepth** , позволяющий включить сериализацию дочерних свойств.
- `String`. типа сериализуется в виде строки. Можно использовать параметр **StringSerializationSource** , позволяющий указать свойство типа для использования в результате сериализации. В противном случае тип сериализуется с использованием метода объекта **ToString** .
- `SpecificProperties`. Сериализация только указанных свойств этого типа. Параметр **PropertySerializationSet** позволяет указать, какие свойства типа требуют сериализации.
  Можно также использовать параметр **InheritPropertySerializationSet** , определяющий наследование набора свойств, и параметр **SerializationDepth** , определяющий сериализацию дочерних свойств.

В PowerShell методы сериализации хранятся в внутренних объектах **псстандардмемберс** .

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.String
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StringSerializationSource

Определяет имя свойства типа. Значение указанного свойства используется в качестве результате сериализации. Этот параметр допустим только в том случае, если параметр **метод serializationmethod** имеет значение String.

```yaml
Type: System.String
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetTypeForDeserialization

Определяет, в какой типа должны конвертироваться объекты данного типа при десериализации.

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.Type
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TypeAdapter

Указывает тип адаптера типа, например **Microsoft. PowerShell. CIM. Циминстанцеадаптер** . Адаптер типов позволяет PowerShell получать члены типа.

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.Type
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TypeConverter

Определяет преобразователь типов для конвертации значений из одного типа в другой. Если для типа определен преобразователь, для конвертации используется экземпляр этого преобразователя.

Введите значение **System.Type** , которое является производным от класса **System.ComponentModel.TypeConverter** или **System.Management.Automation.PSTypeConverter** .

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.Type
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TypeData

Указывает массив данных типа, который этот командлет добавляет в сеанс. Введите переменную, содержащую объект **TypeData** , или команду, которая получает объект **TypeData** , например `Get-TypeData` команду. Можно также передать объект **TypeData** в `Update-TypeData` .

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.Runspaces.TypeData[]
Parameter Sets: TypeDataSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -TypeName

Определяет имя типа для расширения.

Для типов в пространстве имен **System** необходимо указывать короткое имя. В остальных случаях требуется полное имя типа. Подстановочные знаки не поддерживаются.

Можно передать имена типов в `Update-TypeData` . При передаче объекта в `Update-TypeData` `Update-TypeData` возвращает имя типа объекта и тип данных в тип объекта.

Вместе с параметрами **MemberName** , **MemberType** , **Value** и **SecondValue** этот параметр позволяет добавить или изменить свойство или метод типа.

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.String
Parameter Sets: DynamicTypeSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Value

Определяет значение свойства или метода.

При добавлении `AliasProperty` члена,, `CodeProperty` `ScriptProperty` или `CodeMethod` можно использовать параметр **SecondValue** для добавления дополнительных сведений.

Вместе с параметрами **MemberName** , **MemberType** , **Value** и **SecondValue** этот параметр позволяет добавить или изменить свойство или метод типа.

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.Object
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm

Запрос подтверждения перед выполнением командлета.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

Показывает, что произойдет при запуске командлета. Командлет не выполняется.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.String

Строку, содержащую значения параметров **AppendPath** , **TypeName** или **TypeData** , можно передать в `Update-TypeData` .

## Выходные данные

### Нет

Этот командлет не возвращает никакие выходные данные.

## Примечания

## Связанные ссылки

[about_Types.ps1xml](../Microsoft.PowerShell.Core/About/about_Types.ps1xml.md)

[Get-TypeData](Get-TypeData.md)

[Remove-TypeData](Remove-TypeData.md)
