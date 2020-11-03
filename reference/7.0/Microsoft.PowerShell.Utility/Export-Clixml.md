---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 05/21/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/export-clixml?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-Clixml
ms.openlocfilehash: b75a40dc2a89dd9a170de3037c43eda39b21f3d4
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93226089"
---
# Export-Clixml

## Краткий обзор
Создает XML-представление объекта или объектов и сохраняет его в файл.

## SYNTAX

### ByPath (по умолчанию)

```
Export-Clixml [-Depth <Int32>] [-Path] <String> -InputObject <PSObject> [-Force] [-NoClobber]
 [-Encoding <Encoding>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByLiteralPath

```
Export-Clixml [-Depth <Int32>] -LiteralPath <String> -InputObject <PSObject> [-Force] [-NoClobber]
 [-Encoding <Encoding>] [-WhatIf] [-Confirm] [<CommonParameters>]
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

### Пример 3. шифрование экспортированного объекта учетных данных в Windows

В этом примере с учетными данными, сохраненными в `$Credential` переменной путем запуска `Get-Credential` командлета, можно выполнить `Export-Clixml` командлет, чтобы сохранить учетные данные на диске.

> [!IMPORTANT]
> `Export-Clixml` экспортирует только зашифрованные учетные данные в Windows. В операционных системах, отличных от Windows, таких как macOS и Linux, учетные данные экспортируются в виде обычного текста, хранящегося в виде массива символов Юникода. Это обеспечивает некоторую маскировку, но не обеспечивает шифрование.

```powershell
$Credxmlpath = Join-Path (Split-Path $Profile) TestScript.ps1.credential
$Credential | Export-Clixml $Credxmlpath
$Credxmlpath = Join-Path (Split-Path $Profile) TestScript.ps1.credential
$Credential = Import-Clixml $Credxmlpath
```

`Export-Clixml`Командлет шифрует объекты учетных данных с помощью [API защиты данных](/previous-versions/windows/apps/hh464970(v=win.10))Windows. Шифрование гарантирует, что только учетная запись пользователя на этом компьютере сможет расшифровать содержимое объекта учетных данных.
Экспортированный `CLIXML` файл нельзя использовать на другом компьютере или другом пользователе.

В этом примере файл, в котором хранятся учетные данные, представлен `TestScript.ps1.credential` . Замените **TestScript** именем скрипта, с которым загружаются учетные данные.

Вы отправляете объект учетных данных по конвейеру в `Export-Clixml` и сохраняете его по пути, `$Credxmlpath` указанному в первой команде.

Чтобы автоматически импортировать учетные данные в скрипт, выполните последние две команды. Выполните команду `Import-Clixml` , чтобы импортировать защищенный объект учетных данных в скрипт. Этот импорт устраняет риск предоставления в скрипте обычных текстовых паролей.

### Пример 4. экспорт объекта учетных данных в Linux или macOS

В этом примере мы создаем **PSCredential** в `$Credential` переменной с помощью `Get-Credential` командлета. Затем мы используем `Export-Clixml` для сохранения учетных данных на диске.

> [!IMPORTANT]
> `Export-Clixml` экспортирует только зашифрованные учетные данные в Windows. В операционных системах, отличных от Windows, таких как macOS и Linux, учетные данные экспортируются в виде обычного текста, хранящегося в виде массива символов Юникода. Это обеспечивает некоторую маскировку, но не обеспечивает шифрование.

```powershell
PS> $Credential = Get-Credential

PowerShell credential request
Enter your credentials.
User: User1
Password for user User1: ********

PS> $Credential | Export-Clixml ./cred2.xml
PS> Get-Content ./cred2.xml

...
    <Props>
      <S N="UserName">User1</S>
      <SS N="Password">700061007300730077006f0072006400</SS>
    </Props>
...

PS> 'password' | Format-Hex -Encoding unicode

   Label: String (System.String) <52D60C91>

          Offset Bytes                                           Ascii
                 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F
          ------ ----------------------------------------------- -----
0000000000000000 70 00 61 00 73 00 73 00 77 00 6F 00 72 00 64 00 p a s s w o r d
```

Выходные данные `Get-Content` в этом примере были усечены, чтобы сосредоточиться на учетных данных в XML-файле. Обратите внимание, что обычное текстовое значение пароля хранится в XML-файле в виде массива символов Юникода, проверенного `Format-Hex` . Поэтому значение кодируется, но не шифруется.

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

Указывает тип кодировки для целевого файла. Значение по умолчанию — **UTF8NoBOM**.

Для этого параметра допустимы следующие значения:

- **ASCII** : использует кодировку для набора символов ASCII (7-разрядных).
- **BigEndianUnicode** : кодирует в формате UTF-16 с обратным порядком байтов.
- **OEM** : использует кодировку по умолчанию для программ MS-DOS и консолей.
- **Юникод** : кодирует в формате UTF-16 с прямым порядком байтов.
- **UTF7** : кодирует в формате UTF-7.
- **UTF8** : кодирует в формате UTF-8.
- **UTF8BOM** : кодирует в формате UTF-8 с меткой порядка БАЙТОВ (BOM)
- **UTF8NoBOM** : кодирует в формате UTF-8 без метки порядка БАЙТОВ (BOM)
- **UTF32** : кодирует в формате UTF-32.

Начиная с PowerShell 6,2, параметр **кодировки** также разрешает числовые идентификаторы зарегистрированных кодовых страниц (например `-Encoding 1251` ,) или строковых имен зарегистрированных кодовых страниц (например `-Encoding "windows-1251"` ,). Дополнительные сведения см. в документации .NET по [кодированию. codepage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).

```yaml
Type: System.Text.Encoding
Parameter Sets: (All)
Aliases:
Accepted values: ASCII, BigEndianUnicode, OEM, Unicode, UTF7, UTF8, UTF8BOM, UTF8NoBOM, UTF32

Required: False
Position: Named
Default value: UTF8NoBOM
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
Aliases: PSPath, LP

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
