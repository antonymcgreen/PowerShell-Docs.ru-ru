---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/export-clixml?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-Clixml
ms.openlocfilehash: 8485591165cce0425c85d52fbd31d40614af6249
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227697"
---
# Export-Clixml

## Краткий обзор
Создает XML-представление объекта или объектов и сохраняет его в файл.

## SYNTAX

### ByPath (по умолчанию)

```
Export-Clixml [-Path] <String> -InputObject <PSObject> [-Depth <Int32>] [-Force] [-NoClobber]
 [-Encoding <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByLiteralPath

```
Export-Clixml -LiteralPath <String> -InputObject <PSObject> [-Depth <Int32>] [-Force] [-NoClobber]
 [-Encoding <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

`Export-Clixml`Командлет создает Common Language Infrastructure представление объекта или объектов (CLI) на основе XML и сохраняет их в файле. Затем можно использовать `Import-Clixml` командлет для повторного создания сохраненного объекта на основе содержимого этого файла.
Дополнительные сведения о интерфейсе командной строки см. в разделе [независимость от языка](/dotnet/standard/language-independence).

Этот командлет аналогичен `ConvertTo-Xml` , за исключением того, что `Export-Clixml` сохраняет результирующий XML в файле. `ConvertTo-XML` Возвращает XML, поэтому вы можете продолжить его обработку в PowerShell.

Важным применением `Export-Clixml` на компьютерах с Windows является экспорт учетных данных и защита строк безопасно в виде XML. Пример см. в примере 3.

## Примеры

### Пример 1. Экспорт строки в XML-файл

В этом примере создается XML-файл, хранящийся в текущем каталоге, представление строки, которая **является тестом**.

```powershell
"This is a test" | Export-Clixml -Path .\sample.xml
```

Строка, в которой **тест** отправляется по конвейеру. `Export-Clixml` использует параметр **path** для создания XML-файла с именем `sample.xml` в текущем каталоге.

### Пример 2. экспорт объекта в XML-файл

В этом примере показано, как экспортировать объект в XML-файл и затем создать объект путем импорта из XML-файла.

```powershell
Get-Acl C:\test.txt | Export-Clixml -Path .\FileACL.xml
$fileacl = Import-Clixml -Path .\FileACL.xml
```

`Get-Acl`Командлет возвращает дескриптор безопасности `Test.txt` файла. Он отправляет объект по конвейеру, чтобы передать дескриптор безопасности в `Export-Clixml` . Представление объекта, основанное на XML, хранится в файле с именем `FileACL.xml` .

`Import-Clixml`Командлет создает объект из XML- `FileACL.xml` файла в файле. Затем объект сохраняется в `$fileacl` переменной.

### Пример 3. шифрование экспортированного объекта учетных данных

В этом примере с учетными данными, сохраненными в `$Credential` переменной путем запуска `Get-Credential` командлета, можно выполнить `Export-Clixml` командлет, чтобы сохранить учетные данные на диске.

> [!IMPORTANT]
> `Export-Clixml` экспортирует только зашифрованные учетные данные в Windows. В операционных системах, отличных от Windows, таких как macOS и Linux, учетные данные экспортируются в виде обычного текста.

```powershell
$Credxmlpath = Join-Path (Split-Path $Profile) TestScript.ps1.credential
$Credential | Export-Clixml $Credxmlpath
$Credxmlpath = Join-Path (Split-Path $Profile) TestScript.ps1.credential
$Credential = Import-Clixml $Credxmlpath
```

`Export-Clixml`Командлет шифрует объекты учетных данных с помощью [API защиты данных](/previous-versions/windows/apps/hh464970(v=win.10))Windows.
Шифрование гарантирует, что только учетная запись пользователя на этом компьютере сможет расшифровать содержимое объекта учетных данных. Экспортированный `CLIXML` файл нельзя использовать на другом компьютере или другом пользователе.

В этом примере файл, в котором хранятся учетные данные, представлен `TestScript.ps1.credential` . Замените **TestScript** именем скрипта, с которым загружаются учетные данные.

Вы отправляете объект учетных данных по конвейеру в `Export-Clixml` и сохраняете его по пути, `$Credxmlpath` указанному в первой команде.

Чтобы автоматически импортировать учетные данные в скрипт, выполните последние две команды. Выполните команду `Import-Clixml` , чтобы импортировать защищенный объект учетных данных в скрипт. Этот импорт устраняет риск предоставления в скрипте обычных текстовых паролей.

## PARAMETERS

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

### -Depth

Указывает, сколько уровней вложенных объектов включается в XML-представление. Значение по умолчанию — `2`.

Значение по умолчанию может быть переопределено для типа объекта в `Types.ps1xml` файлах. Дополнительные сведения см. в разделе [about_Types.ps1XML](../Microsoft.PowerShell.Core/About/about_Types.ps1xml.md).

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 2
Accept pipeline input: False
Accept wildcard characters: False
```

### -Encoding

Указывает тип кодировки для целевого файла. Значение по умолчанию — **Unicode**.

Для этого параметра допустимы следующие значения:

- `ASCII` Использует кодировку ASCII (7-разрядных).
- `BigEndianUnicode` Использует UTF-16 с обратным порядком байтов.
- `Default` Использует кодировку, соответствующую активной кодовой странице системы (обычно ANSI).
- `OEM` Использует кодировку, соответствующую текущей кодовой странице OEM системы.
- `Unicode` Использует UTF-16 с прямым порядком байтов.
- `UTF7` Использует UTF-7.
- `UTF8` Использует UTF-8.
- `UTF32` Использует UTF-32 с прямым порядком байтов.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: ASCII, BigEndianUnicode, Default, OEM, Unicode, UTF7, UTF8, UTF32

Required: False
Position: Named
Default value: Unicode
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Принудительное выполнение команды без запроса на подтверждение пользователем.

В результате командлет снимает атрибут только для чтения выходного файла при необходимости. Командлет попытается сбросить атрибут "только для чтения" после выполнения команды.

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

### -InputObject

Задает объект для преобразования. Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты. Также можно передать объекты в `Export-Clixml` .

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

### -LiteralPath

Указывает путь к файлу, где будет храниться XML-представление объекта. В отличие от **path** , значение параметра **LiteralPath** используется точно так же, как типизировано. Никакие символы не интерпретируются как знаки подстановки. Если путь содержит escape-символы, заключите его в одинарные кавычки. Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.

```yaml
Type: System.String
Parameter Sets: ByLiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoClobber

Указывает, что командлет не перезаписывает содержимое существующего файла. По умолчанию, если файл существует по указанному пути, `Export-Clixml` перезаписывает файл без предупреждения.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: NoOverwrite

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path

Указывает путь к файлу, где будет храниться XML-представление объекта.

```yaml
Type: System.String
Parameter Sets: ByPath
Aliases:

Required: True
Position: 0
Default value: None
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

### System.Management.Automation.PSObject

Можно выполнить конвейер любого объекта в `Export-Clixml` .

## Выходные данные

### System. IO. FileInfo

`Export-Clixml` создает файл, содержащий XML.

## ПРИМЕЧАНИЯ

## Связанные ссылки

[ConvertTo-Html](ConvertTo-Html.md)

[ConvertTo-Xml](ConvertTo-Xml.md)

[Export-Csv](Export-Csv.md)

[Import-Clixml](Import-Clixml.md)

[Join-Path](../Microsoft.PowerShell.Management/Join-Path.md)

[Securely Store Credentials on Disk](https://powershellcookbook.com/recipe/PukO/securely-store-credentials-on-disk) (Безопасное хранение учетных данных на диске)

[Use PowerShell to Pass Credentials to Legacy Systems](https://devblogs.microsoft.com/scripting/use-powershell-to-pass-credentials-to-legacy-systems/) (Передача учетных данных в устаревшие системы с помощью PowerShell)

[Windows.Security.Cryptography.DataProtection](/uwp/api/windows.security.cryptography.dataprotection)
