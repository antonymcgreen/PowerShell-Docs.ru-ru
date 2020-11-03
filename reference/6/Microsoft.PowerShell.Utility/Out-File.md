---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 09/21/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/out-file?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Out-File
ms.openlocfilehash: f3cd58bffde8bcb6dab488a9e40e69d7435133e4
ms.sourcegitcommit: d757d64ea8c8af4d92596e8fbe15f2f40d48d3ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "93230697"
---
# Out-File

## Краткий обзор
Отправляет выходные данные в файл.

## SYNTAX

### ByPath (по умолчанию)

```
Out-File [-FilePath] <string> [[-Encoding] <Encoding>] [-Append] [-Force] [-NoClobber]
 [-Width <int>] [-NoNewline] [-InputObject <psobject>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByLiteralPath

```
Out-File [[-Encoding] <Encoding>] -LiteralPath <string> [-Append] [-Force] [-NoClobber]
 [-Width <int>] [-NoNewline] [-InputObject <psobject>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

`Out-File`Командлет отправляет выходные данные в файл. Он неявно использует систему форматирования PowerShell для записи в файл. Файл получает то же отображаемое представление, что и терминал. Это означает, что выходные данные могут быть неидеальными для программной обработки, если только все входные объекты не являются строками.
Если необходимо указать параметры для выходных данных, используйте `Out-File` вместо оператора перенаправления ( `>` ). Дополнительные сведения о перенаправлении см. в разделе [about_Redirection](../Microsoft.PowerShell.Core/About/about_Redirection.md).

## Примеры

### Пример 1. Отправка выходных данных и создание файла

В этом примере показано, как отправить список процессов локального компьютера в файл. Если файл не существует, `Out-File` создает файл по указанному пути.

```powershell
Get-Process | Out-File -FilePath .\Process.txt
Get-Content -Path .\Process.txt
```

```Output
 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
     29    22.39      35.40      10.98   42764   9 Application
     53    99.04     113.96       0.00   32664   0 CcmExec
     27    96.62     112.43     113.00   17720   9 Code
```

`Get-Process`Командлет возвращает список процессов, запущенных на локальном компьютере. Объекты **процесса** отправляются по конвейеру в `Out-File` командлет. `Out-File` использует параметр **FilePath** и создает файл в текущем каталоге с именем **Process.txt** . `Get-Content`Команда получает содержимое из файла и отображает его в консоли PowerShell.

### Пример 2. запрет перезаписи существующего файла

Этот пример предотвращает перезапись существующего файла. По умолчанию `Out-File` перезаписывает существующие файлы.

```powershell
Get-Process | Out-File -FilePath .\Process.txt -NoClobber
```

```Output
Out-File : The file 'C:\Test\Process.txt' already exists.
At line:1 char:15
+ Get-Process | Out-File -FilePath .\Process.txt -NoClobber
+               ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
```

`Get-Process`Командлет возвращает список процессов, запущенных на локальном компьютере. Объекты **процесса** отправляются по конвейеру в `Out-File` командлет. `Out-File` использует параметр **FilePath** и пытается выполнить запись в файл в текущем каталоге с именем **Process.txt** . Параметр **NoClobber** предотвращает перезапись файла и выводит сообщение о том, что файл уже существует.

### Пример 3. Отправка выходных данных в файл в формате ASCII

В этом примере показано, как кодировать выходные данные с конкретным типом кодирования.

```powershell
$Procs = Get-Process
Out-File -FilePath .\Process.txt -InputObject $Procs -Encoding ASCII -Width 50
```

`Get-Process`Командлет возвращает список процессов, запущенных на локальном компьютере. Объекты **процесса** хранятся в переменной `$Procs` . `Out-File` использует параметр **FilePath** и создает файл в текущем каталоге с именем **Process.txt** . Параметр **InputObject** передает объекты процесса в `$Procs` файл **Process.txt** . Параметр **Encoding** преобразует выходные данные в формат **ASCII** . Параметр **Width** ограничивает каждую строку в файле на 50 символов, чтобы некоторые данные могли быть обрезаны.

### Пример 4. Использование поставщика и отправка выходных данных в файл

В этом примере показано, как использовать `Out-File` командлет, если вы не используете диск поставщика **FileSystem** . Используйте `Get-PSProvider` командлет для просмотра поставщиков на локальном компьютере. Дополнительные сведения см. в разделе [about_Providers](../Microsoft.Powershell.Core/About/about_Providers.md).

```
PS> Set-Location -Path Alias:

PS> Get-Location

Path
----
Alias:\

PS> Get-ChildItem | Out-File -FilePath C:\TestDir\AliasNames.txt

PS> Get-Content -Path C:\TestDir\AliasNames.txt

CommandType     Name
-----------     ----
Alias           % -> ForEach-Object
Alias           ? -> Where-Object
Alias           ac -> Add-Content
Alias           cat -> Get-Content
```

`Set-Location`Команда использует параметр **path** , чтобы задать текущее расположение для поставщика реестра `Alias:` . `Get-Location`Командлет выводит полный путь для `Alias:` .
`Get-ChildItem` отправляет объекты по конвейеру в `Out-File` командлет. `Out-File` использует параметр **FilePath** для указания полного пути и имени файла выходных данных, **C:\TestDir\AliasNames.txt** . `Get-Content`Командлет использует параметр **path** и отображает содержимое файла в консоли PowerShell.

## PARAMETERS

### — Добавление

Добавляет выходные данные в конец существующего файла.

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

### -Encoding

Указывает тип кодировки для целевого файла. Значение по умолчанию — `utf8NoBOM`.

Для этого параметра допустимы следующие значения:

- `ascii`: Использует кодировку для набора символов ASCII (7-разрядных).
- `bigendianunicode`: Кодируется в формате UTF-16 с обратным порядком байтов.
- `oem`: Использует кодировку по умолчанию для программ MS-DOS и консолей.
- `unicode`: Кодируется в формате UTF-16 с прямым порядком байтов.
- `utf7`: Кодируется в формате UTF-7.
- `utf8`: Кодируется в формате UTF-8.
- `utf8BOM`: Кодирует в формате UTF-8 с меткой порядка байтов (BOM)
- `utf8NoBOM`: Кодирует в формате UTF-8 без метки порядка байтов (BOM)
- `utf32`: Кодируется в формате UTF-32.

Начиная с PowerShell 6,2, параметр **кодировки** также разрешает числовые идентификаторы зарегистрированных кодовых страниц (например `-Encoding 1251` ,) или строковых имен зарегистрированных кодовых страниц (например `-Encoding "windows-1251"` ,). Дополнительные сведения см. в документации .NET по [кодированию. codepage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).

```yaml
Type: System.Text.Encoding
Parameter Sets: (All)
Aliases:
Accepted values: ASCII, BigEndianUnicode, OEM, Unicode, UTF7, UTF8, UTF8BOM, UTF8NoBOM, UTF32

Required: False
Position: 1
Default value: UTF8NoBOM
Accept pipeline input: False
Accept wildcard characters: False
```

### -FilePath

Указывает путь к выходному файлу.

```yaml
Type: System.String
Parameter Sets: ByPath
Aliases: Path

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Переопределяет атрибут, доступный только для чтения, и перезаписывает существующий файл, доступный только для чтения. Параметр **Force** не переопределяет ограничения безопасности.

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

### -InputObject

Указывает объекты, которые нужно записать в файл. Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -LiteralPath

Указывает путь к выходному файлу. Параметр **LiteralPath** используется точно так же, как он типизирован.
Подстановочные знаки не допускаются. Если путь содержит escape-символы, заключите его в одинарные кавычки. Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности. Дополнительные сведения см. в разделе [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).

```yaml
Type: System.String
Parameter Sets: ByLiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NoClobber

**NoClobber** предотвращает перезапись существующего файла и выводит сообщение о том, что файл уже существует. По умолчанию, если файл существует по указанному пути, `Out-File` перезаписывает файл без предупреждения.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: NoOverwrite

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Новая строка

Указывает, что содержимое, записанное в файл, не заканчивается символом новой строки. Строковые представления входных объектов сцепляются для формирования выходных данных. Между выходными строками не вставляются пробелы и символы новой строки. После последней выходной строки не добавляется новая строка.

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

### -Width

Указывает количество символов в каждой строке выходных данных. Все остальные знаки отсекаются, а не переносятся на следующую строку. Если этот параметр не используется, ширина определяется характеристиками узла. Значение по умолчанию для консоли PowerShell — 80 символов.

```yaml
Type: System.Int32
Parameter Sets: (All)
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

### System.Management.Automation.PSObject

Любой объект можно передать по конвейеру в `Out-File` .

## Выходные данные

### Нет

`Out-File` не создает никаких выходных данных.

## ПРИМЕЧАНИЯ

Входные объекты автоматически форматируются так же, как и в терминале, но можно использовать `Format-*` командлет для явного управления форматированием выходных данных в файле. Например `Get-Date | Format-List | Out-File out.txt`.

Чтобы отправить выходные данные команды PowerShell в `Out-File` командлет, используйте конвейер. Кроме того, можно хранить данные в переменной и использовать параметр **InputObject** для передачи данных в `Out-File` командлет.

`Out-File` сохраняет данные в файл, но не создает выходные объекты в конвейере.

## Связанные ссылки

[about_Providers](../Microsoft.Powershell.Core/About/about_Providers.md)

[about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)

[Out-Default;](../Microsoft.PowerShell.Core/Out-Default.md)

[Out-Host](../Microsoft.PowerShell.Core/Out-Host.md)

[Out-Null](../Microsoft.PowerShell.Core/Out-Null.md)

[Out-String](Out-String.md)

[Tee-Object](Tee-Object.md)
