---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Module Name: Microsoft.PowerShell.Utility
ms.date: 12/12/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/join-string?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Join-String
ms.openlocfilehash: e1ec8933f70fab666baa4ce865297deeec37fff9
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228125"
---
# Join-String

## Краткий обзор
Объединяет объекты из конвейера в одну строку.

## SYNTAX

### Default (по умолчанию)

```
Join-String [[-Property] <PSPropertyExpression>] [[-Separator] <String>] [-OutputPrefix <String>]
 [-OutputSuffix <String>] [-UseCulture] [-InputObject <PSObject[]>] [<CommonParameters>]
```

### синглекуоте

```
Join-String [[-Property] <PSPropertyExpression>] [[-Separator] <String>] [-OutputPrefix <String>]
 [-OutputSuffix <String>] [-SingleQuote] [-UseCulture] [-InputObject <PSObject[]>]
 [<CommonParameters>]
```

### даублекуоте

```
Join-String [[-Property] <PSPropertyExpression>] [[-Separator] <String>] [-OutputPrefix <String>]
 [-OutputSuffix <String>] [-DoubleQuote] [-UseCulture] [-InputObject <PSObject[]>]
 [<CommonParameters>]
```

### Формат

```
Join-String [[-Property] <PSPropertyExpression>] [[-Separator] <String>] [-OutputPrefix <String>]
 [-OutputSuffix <String>] [-FormatString <String>] [-UseCulture] [-InputObject <PSObject[]>]
 [<CommonParameters>]
```

## DESCRIPTION

`Join-String`Командлет присоединяет или объединяет текст из объектов конвейера в одну строку.

Если параметры не указаны, объекты конвейера преобразуются в строку и соединяются с разделителем по умолчанию `$OFS` .

При указании имени свойства значение свойства преобразуется в строку и присоединяется к строке.

Вместо имени свойства можно использовать блок скрипта. Результат блока сценария преобразуется в строку перед присоединением для формирования результата. Он может либо объединить текст свойства объекта, либо результат объекта, который был преобразован в строку.

Этот командлет появился в PowerShell 6,2.

## Примеры

### Пример 1. соединение имен каталогов

<!-- markdownlint-disable MD038 -->
В этом примере объединяются имена каталогов, выходные данные переносятся в двойные кавычки и имена каталогов разделяются запятыми и пробелами ( `, ` ). Выходные данные представляют собой строковый объект.

```powershell
Get-ChildItem -Directory C:\ | Join-String -Property Name -DoubleQuote -Separator ', '
```

```Output
"PerfLogs", "Program Files", "Program Files (x86)", "Users", "Windows"
```

`Get-ChildItem` использует параметр **Directory** для получения всех имен каталогов для `C:\` диска.
Объекты отправляются по конвейеру в `Join-String` . Параметр **Property** указывает имена каталогов. Параметр **даублекуоте** заключает имена каталогов в двойные кавычки.
Параметр **разделителя** задает использование запятой и пробела ( `, ` ) для разделения имен каталогов.

`Get-ChildItem`Объекты являются **System. IO. DirectoryInfo** и `Join-String` преобразуют объекты в **System. String** .

### Пример 2. Использование подстроки свойства для объединения имен каталогов

В этом примере используется метод подстроки для получения первых четырех букв имен каталогов, заключенный в одинарные кавычки, а имена каталогов разделяются точкой с запятой ( `;` ).

```powershell
Get-ChildItem -Directory C:\ | Join-String -Property {$_.Name.SubString(0,4)} -SingleQuote -Separator ';'
```

```Output
'Perf';'Prog';'Prog';'User';'Wind'
```

`Get-ChildItem` использует параметр **Directory** для получения всех имен каталогов для `C:\` диска.
Объекты отправляются по конвейеру в `Join-String` .

Блок скрипта параметра **Свойства** использует автоматическую переменную ( `$_` ) для указания подстроки свойства **Name** каждого объекта. Подстрока получает первые четыре буквы имени каждого каталога. Подстрока указывает начальную и конечную позиции символа. Параметр **синглекуоте** заключает имена каталогов в двойные кавычки. Параметр **разделителя** задает использование точки с запятой ( `;` ) для разделения имен каталогов.

Дополнительные сведения об автоматических переменных и подстроках см. в разделе [about_Automatic_Variables](../microsoft.powershell.core/about/about_automatic_variables.md) и [substring](/dotnet/api/system.string.substring).

### Пример 3. Отображение выходных данных присоединение на отдельной строке

В этом примере имена служб объединяются с каждой службой в отдельной строке с отступом на вкладке.

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

`Get-Service` использует параметр **Name** с аргументом для указания служб, начинающихся с `se*` . Звездочка ( `*` ) является подстановочным знаком для любого символа.

Объекты отправляются по конвейеру в `Join-String` , в котором для указания имен служб используется параметр **Property** . Параметр **разделителя** задает три специальных символа, представляющих возврат каретки ( `` `r `` ), символ новой строки ( `` `n `` ) и знак табуляции ( `` `t `` ). **Аутпутпрефикс** вставляет **службы меток:** с новой строкой и вкладкой перед первой строкой выходных данных.

Дополнительные сведения о специальных символах см. в разделе [about_Special_Characters](..//microsoft.powershell.core/about/about_special_characters.md).

### Пример 4. Создание определения класса на основе объекта

В этом примере создается определение класса PowerShell с использованием существующего объекта в качестве шаблона.

В этом примере кода используется Сплаттинг для уменьшения длины строки и улучшения удобочитаемости. Дополнительные сведения см. в разделе [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md).

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

## PARAMETERS

### -Даублекуоте

Заключает строковое значение каждого объекта конвейера в двойные кавычки.

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

### — FormatString

Строка формата, задающая способ форматирования каждого элемента.

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

### -InputObject

Указывает текст для присоединения. Введите переменную, содержащую текст, или введите команду или выражение, которое получает объекты для объединения в строки.

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

### -Аутпутпрефикс

Текст, вставленный перед выходной строкой. Строка может содержать специальные символы, такие как возврат каретки ( `` `r `` ), строка ( `` `n `` ) и знак табуляции ( `` `t `` ).

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

### -Аутпутсуффикс

Текст, добавляемый к выходной строке. Строка может содержать специальные символы, такие как возврат каретки ( `` `r `` ), строка ( `` `n `` ) и знак табуляции ( `` `t `` ).

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

### -Property

Имя свойства или выражение свойства, которое будет проецировать объект конвейера в текст.

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

### -Separator

Текст или символы, такие как запятая или точка с запятой, вставленные между текстом для каждого объекта конвейера.

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

### -Синглекуоте

Заключает строковое значение каждого объекта конвейера в одинарные кавычки.

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

### -UseCulture

Использует разделитель списка для текущего языка и региональных параметров в качестве разделителя элементов. Чтобы найти разделитель списка для языка и региональных параметров, используйте следующую команду: `(Get-Culture).TextInfo.ListSeparator` .

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

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.Management.Automation.PSObject

## Выходные данные

### System.String

## ПРИМЕЧАНИЯ

## Связанные ссылки

[about_Automatic_Variables](../microsoft.powershell.core/about/about_automatic_variables.md)

[about_Special_Characters](..//microsoft.powershell.core/about/about_special_characters.md)

[Подстроки](/dotnet/api/system.string.substring)
