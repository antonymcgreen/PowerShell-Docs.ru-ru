---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 12/18/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-content?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Content
ms.openlocfilehash: d85e0219c325de998c5874224a33ac4263b787a3
ms.sourcegitcommit: bf07cffb2a66dec94bf3576e197090f958701f18
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/19/2020
ms.locfileid: "99605287"
---
# Set-Content

## Краткий обзор
Записывает новое содержимое или заменяет существующее содержимое в файле.

## SYNTAX

### Путь (по умолчанию)

```
Set-Content [-Path] <string[]> [-Value] <Object[]> [-PassThru] [-Filter <string>]
 [-Include <string[]>] [-Exclude <string[]>] [-Force] [-Credential <pscredential>]
 [-WhatIf] [-Confirm] [-NoNewline] [-Encoding <Encoding>] [-AsByteStream] [-Stream <string>]
 [<CommonParameters>]
```

### LiteralPath

```
Set-Content [-Value] <Object[]> -LiteralPath <string[]> [-PassThru] [-Filter <string>]
 [-Include <string[]>] [-Exclude <string[]>] [-Force] [-Credential <pscredential>]
 [-WhatIf] [-Confirm] [-NoNewline] [-Encoding <Encoding>] [-AsByteStream] [-Stream <string>]
 [<CommonParameters>]
```

## DESCRIPTION

`Set-Content` — Это командлет обработки строк, который записывает новое содержимое или заменяет содержимое в файле. `Set-Content` Заменяет существующее содержимое и отличается от `Add-Content` командлета, который добавляет содержимое в файл. Чтобы отправить содержимое в `Set-Content` , можно использовать параметр **value** в командной строке или отправить содержимое через конвейер.

Если необходимо создать файлы или каталоги для следующих примеров, см. раздел [New-Item](New-Item.md).

## Примеры

### Пример 1. Замена содержимого нескольких файлов в каталоге

Этот пример заменяет содержимое для нескольких файлов в текущем каталоге.

```powershell
Get-ChildItem -Path .\Test*.txt
```

```Output
Test1.txt
Test2.txt
Test3.txt
```

```powershell
Set-Content -Path .\Test*.txt -Value 'Hello, World'
Get-Content -Path .\Test*.txt
```

```Output
Hello, World
Hello, World
Hello, World
```

`Get-ChildItem`Командлет использует параметр **path** для вывода файлов **. txt** , начинающихся с `Test*` в текущем каталоге. `Set-Content`Командлет использует параметр **path** для указания `Test*.txt` файлов. Параметр **value** предоставляет текстовую строку **Hello, World** , заменяющую существующее содержимое в каждом файле. `Get-Content`Командлет использует параметр **path** для указания `Test*.txt` файлов и отображает содержимое каждого файла в консоли PowerShell.

### Пример 2. Создание нового файла и запись содержимого

В этом примере создается новый файл и записывается текущая дата и время в файл.

```powershell
Set-Content -Path .\DateTime.txt -Value (Get-Date)
Get-Content -Path .\DateTime.txt
```

```Output
1/30/2019 09:55:08
```

`Set-Content` использует параметры **path** и **value** для создания нового файла с именем **DateTime.txt** в текущем каталоге. Параметр **value** используется `Get-Date` для получения текущих даты и времени.
`Set-Content` Записывает объект **DateTime** в файл в виде строки. `Get-Content`Командлет использует параметр **path** для вывода содержимого **DateTime.txt** в консоли PowerShell.

### Пример 3. Замена текста в файле

Эта команда заменяет все экземпляры Word в существующем файле.

```powershell
Get-Content -Path .\Notice.txt
```

```Output
Warning
Replace Warning with a new word.
The word Warning was replaced.
```

```powershell
(Get-Content -Path .\Notice.txt) |
    ForEach-Object {$_ -Replace 'Warning', 'Caution'} |
        Set-Content -Path .\Notice.txt
Get-Content -Path .\Notice.txt
```

```Output
Caution
Replace Caution with a new word.
The word Caution was replaced.
```

`Get-Content`Командлет использует параметр **path** для указания файла **Notice.txt** в текущем каталоге. `Get-Content`Команда заключена в круглые скобки, чтобы команда закончится перед отправкой конвейера.

Содержимое файла **Notice.txt** отправляется в командлет по конвейеру `ForEach-Object` .
`ForEach-Object` использует автоматическую переменную `$_` и заменяет каждое вхождение **предупреждения** с **осторожностью**. Объекты отправляются по конвейеру в `Set-Content` командлет. `Set-Content` использует параметр **path** для указания файла **Notice.txt** и записи обновленного содержимого в файл.

Последний `Get-Content` командлет отображает обновленное содержимое файла в консоли PowerShell.

### Пример 4. Использование фильтров с Set-Content

Можно указать фильтр для `Set-Content` командлета. При использовании фильтров для уточнения параметра **path** необходимо включить конечную звездочку ( `*` ), чтобы указать содержимое пути.

Следующая команда задает для содержимого всех `*.txt` файлов в `C:\Temp` каталоге пустое **значение** .

```powershell
Set-Content -Path C:\Temp\* -Filter *.txt -Value "Empty"
```

## PARAMETERS

### -Асбитестреам

Указывает, что содержимое должно считываться как поток байтов. Этот параметр появился в PowerShell 6,0.

При использовании параметра **асбитестреам** с параметром **Encoding** возникает предупреждение. Параметр **асбитестреам** игнорирует любую кодировку, и выходные данные возвращаются в виде потока байтов.

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

### -Credential

> [!NOTE]
> Этот параметр не поддерживается какими-либо поставщиками, установленными с помощью PowerShell.
> Чтобы выполнить олицетворение другого пользователя или повысить свои учетные данные при выполнении этого командлета, используйте [команду Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Encoding

Указывает тип кодировки для целевого файла. Значение по умолчанию — `utf8NoBOM`.

Кодирование — это динамический параметр, к которому добавляется поставщик FileSystem `Set-Content` . Этот параметр работает только на дисках с файловой системой.

Для этого параметра допустимы следующие значения:

- `ascii`: Использует кодировку для набора символов ASCII (7-разрядных).
- `bigendianunicode`: Кодируется в формате UTF-16 с обратным порядком байтов.
- `bigendianutf32`: Кодируется в формате UTF-32 с обратным порядком байтов.
- `oem`: Использует кодировку по умолчанию для программ MS-DOS и консолей.
- `unicode`: Кодируется в формате UTF-16 с прямым порядком байтов.
- `utf7`: Кодируется в формате UTF-7.
- `utf8`: Кодируется в формате UTF-8.
- `utf8BOM`: Кодирует в формате UTF-8 с меткой порядка байтов (BOM)
- `utf8NoBOM`: Кодирует в формате UTF-8 без метки порядка байтов (BOM)
- `utf32`: Кодируется в формате UTF-32.

Начиная с PowerShell 6,2, параметр **кодировки** также разрешает числовые идентификаторы зарегистрированных кодовых страниц (например `-Encoding 1251` ,) или строковых имен зарегистрированных кодовых страниц (например `-Encoding "windows-1251"` ,). Дополнительные сведения см. в документации .NET по [кодированию. codepage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).

> [!NOTE]
> Больше не рекомендуется использовать **UTF-7** _. В PowerShell 7,1 записывается предупреждение, если указано `utf7` для параметра _ *Encoding**.

```yaml
Type: System.Text.Encoding
Parameter Sets: (All)
Aliases:
Accepted values: ASCII, BigEndianUnicode, BigEndianUTF32, OEM, Unicode, UTF7, UTF8, UTF8BOM, UTF8NoBOM, UTF32

Required: False
Position: Named
Default value: UTF8NoBOM
Accept pipeline input: False
Accept wildcard characters: False
```

### -Exclude

Указывает в виде массива строк элемент или элементы, которые этот командлет исключает в операции. Значение этого параметра определяет параметр **Path**. Введите элемент пути или шаблон, например `*.txt` . Можно использовать подстановочные знаки. Параметр **Exclude** эффективен, только если команда включает содержимое элемента, например `C:\Windows\*` , где подстановочный знак указывает содержимое `C:\Windows` каталога.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Filter

Задает фильтр для уточнения параметра **пути** . Поставщик [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) является единственным установленным поставщиком PowerShell, поддерживающим использование фильтров. Синтаксис для языка фильтра **файловой** системы можно найти в [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).
Фильтры более эффективны, чем другие параметры, так как поставщик применяет их, когда командлет получает объекты, а не использует фильтры PowerShell для объектов после их извлечения.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Force

Заставляет командлет задать содержимое файла, даже если он доступен только для чтения. Применение этого параметра зависит от конкретного поставщика. Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).
Параметр **Force** не переопределяет ограничения безопасности.

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

### -Include

Указывает в виде массива строк элемент или элементы, которые этот командлет включает в операцию. Значение этого параметра определяет параметр **Path**. Введите элемент пути или шаблон, например `"*.txt"` . Можно использовать подстановочные знаки. Параметр **include** действует только в том случае, если команда включает содержимое элемента, например `C:\Windows\*` , где подстановочный знак указывает содержимое `C:\Windows` каталога.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -LiteralPath

Указывает путь к одному или нескольким расположениям. Значение **LiteralPath** используется точно так же, как оно введено. Никакие символы не интерпретируются как знаки подстановки. Если путь содержит escape-символы, заключите его в одинарные кавычки. Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.

Дополнительные сведения см. в разделе [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Новая строка

Строковые представления входных объектов сцепляются для формирования выходных данных. Между выходными строками не вставляются пробелы и символы новой строки. После последней выходной строки не добавляется новая строка.

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

### -PassThru

Возвращает объект, представляющий содержимое. По умолчанию этот командлет не создает выходные данные.

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

### -Path

Указывает путь к элементу, который получает содержимое.
Можно использовать подстановочные знаки.

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Stream

> [!NOTE]
> Этот параметр доступен только в Windows.

Указывает альтернативный поток данных для содержимого. Если поток не существует, этот командлет создаст его. Подстановочные знаки не поддерживаются.

**Stream** — это динамический параметр, к которому добавляется поставщик **FileSystem** `Set-Content` . Этот параметр работает только на дисках с файловой системой.

Командлет можно использовать `Set-Content` для создания или обновления содержимого любого альтернативного потока данных, например `Zone.Identifier` . Однако не рекомендуется использовать этот способ для устранения проверок безопасности, блокирующих файлы, загружаемые из Интернета. Если вы убедитесь, что скачанный файл является надежным, используйте `Unblock-File` командлет.

Этот параметр появился в PowerShell 3,0. Начиная с PowerShell 7,2, `Set-Content` может устанавливать содержимое альтернативных потоков данных из каталогов, а также файлов.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Value

Указывает новое содержимое для элемента.

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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

### System.Object

Объект, содержащий новое значение для элемента, можно передать по конвейеру `Set-Content` .

## Выходные данные

### Нет или System.String

При использовании параметра **PassThru** `Set-Content` создает объект **System. String** , представляющий содержимое. В противном случае командлет не формирует никаких выходных данных.

## ПРИМЕЧАНИЯ

- Также можно ссылаться `Set-Content` по встроенному псевдониму `sc` .
  Дополнительные сведения см. в разделе [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).
- `Set-Content` предназначен для обработки строк. При передаче нестроковых объектов в `Set-Content` объект преобразуется в строку перед записью. Для записи объектов в файлы используйте `Out-File` .
- `Set-Content`Командлет предназначен для работы с данными, предоставляемыми любым поставщиком. Чтобы вывести список поставщиков, доступных в данном сеансе, введите командлет `Get-PsProvider`. Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).

## Связанные ссылки

[about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md)

[about_Automatic_Variables. md](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md)

[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)

[Add-Content](Add-Content.md)

[Clear-Content](Clear-Content.md)

[Get-ChildItem](Get-ChildItem.md)

[Get-Content](Get-Content.md)

[ForEach-Object](../Microsoft.PowerShell.Core/ForEach-Object.md)

[New-Item](New-Item.md)
