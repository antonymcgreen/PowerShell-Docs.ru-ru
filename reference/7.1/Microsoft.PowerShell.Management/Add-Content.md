---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 08/19/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/add-content?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-Content
ms.openlocfilehash: 3ae91d03e6882eeaf6743d11cfeed5d0ed1aae0c
ms.sourcegitcommit: 9a8bb1b459b5939c95e1f6d9499fcb13d01a58c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "93230498"
---
# Add-Content

## Краткий обзор
Добавляет содержимое в указанные элементы, например слова в файл.

## SYNTAX

### Путь (по умолчанию)

```
Add-Content [-Path] <string[]> [-Value] <Object[]> [-PassThru] [-Filter <string>]
 [-Include <string[]>] [-Exclude <string[]>] [-Force] [-Credential <pscredential>] [-WhatIf]
 [-Confirm] [-NoNewline] [-Encoding <Encoding>] [-AsByteStream] [-Stream <string>]
 [<CommonParameters>]
```

### LiteralPath

```
Add-Content [-Value] <Object[]> -LiteralPath <string[]> [-PassThru] [-Filter <string>]
 [-Include <string[]>] [-Exclude <string[]>] [-Force] [-Credential <pscredential>] [-WhatIf]
 [-Confirm] [-NoNewline] [-Encoding <Encoding>] [-AsByteStream] [-Stream <string>]
 [<CommonParameters>]
```

## DESCRIPTION

`Add-Content`Командлет добавляет содержимое в указанный элемент или файл. Содержимое можно задать прямо в команде либо путем указания объекта, в котором оно хранится.

Если необходимо создать файлы или каталоги для следующих примеров, см. раздел [New-Item](New-Item.md).

## Примеры

### Пример 1. Добавление строки во все текстовые файлы с исключением

Этот пример добавляет значение к текстовым файлам в текущем каталоге, но исключает файлы на основе имени файла.

```powershell
Add-Content -Path .\*.txt -Exclude help* -Value 'End of file'
```

Параметр **path** указывает все `.txt` файлы в текущем каталоге, но параметр **Exclude** игнорирует имена файлов, соответствующие указанному шаблону. Параметр **value** задает текстовую строку, которая записывается в файлы.

### Пример 2. добавление даты в конец указанных файлов

Этот пример добавляет дату к файлам в текущем каталоге и отображает дату в консоли PowerShell.

```powershell
Add-Content -Path .\DateTimeFile1.log, .\DateTimeFile2.log -Value (Get-Date) -PassThru
Get-Content -Path .\DateTimeFile1.log
```

```Output
Tuesday, May 14, 2019 8:24:27 AM
Tuesday, May 14, 2019 8:24:27 AM
5/14/2019 8:24:27 AM
```

`Add-Content`Командлет создает два новых файла в текущем каталоге. Параметр **value** содержит выходные данные `Get-Date` командлета. Параметр **PassThru** выводит добавленное содержимое в конвейер.
Так как нет других командлетов для получения выходных данных, он отображается в консоли PowerShell.
`Get-Content`Командлет отображает обновленный файл, `DateTimeFile1.log` .

### Пример 3. Добавление содержимого указанного файла в другой файл

Этот пример получает содержимое из файла и сохраняет содержимое в переменной. Переменная используется для добавления содержимого в другой файл.

```powershell
$From = Get-Content -Path .\CopyFromFile.txt
Add-Content -Path .\CopyToFile.txt -Value $From
Get-Content -Path .\CopyToFile.txt
```

- `Get-Content`Командлет получает содержимое `CopyFromFile.txt` и сохраняет содержимое `$From` переменной.
- `Add-Content`Командлет обновляет файл, `CopyToFile.txt` используя содержимое `$From` переменной.
- `Get-Content`Командлет отображает CopyToFile.txt.

### Пример 4. Добавление содержимого указанного файла в другой файл с помощью конвейера

Этот пример получает содержимое из файла и передает его в `Add-Content` командлет.

```powershell
Get-Content -Path .\CopyFromFile.txt | Add-Content -Path .\CopyToFile.txt
Get-Content -Path .\CopyToFile.txt
```

`Get-Content`Командлет возвращает содержимое `CopyFromFile.txt` . Результаты передаются в `Add-Content` командлет, который обновляет `CopyToFile.txt` .
Последний `Get-Content` командлет выводит на экран `CopyToFile.txt` .

### Пример 5. Создание нового файла и копирование содержимого

В этом примере создается новый файл и копируется содержимое существующего файла в новый файл.

```powershell
Add-Content -Path .\NewFile.txt -Value (Get-Content -Path .\CopyFromFile.txt)
Get-Content -Path .\NewFile.txt
```

- `Add-Content`Командлет использует параметры **path** и **value** для создания нового файла в текущем каталоге.
- `Get-Content`Командлет получает содержимое существующего файла `CopyFromFile.txt` и передает его в параметр **value** . Круглые скобки вокруг `Get-Content` командлета гарантируют, что команда завершится до `Add-Content` начала выполнения команды.
- `Get-Content`Командлет отображает содержимое нового файла, `NewFile.txt` .

### Пример 6. Добавление содержимого в файл, который доступен только для чтения

Эта команда добавляет значение в файл, даже если атрибуту файла **IsReadOnly** присвоено значение **true** .
В примере содержатся инструкции по созданию файла, доступного только для чтения.

```powershell
New-Item -Path .\IsReadOnlyTextFile.txt -ItemType File
Set-ItemProperty -Path .\IsReadOnlyTextFile.txt -Name IsReadOnly -Value $True
Get-ChildItem -Path .\IsReadOnlyTextFile.txt
Add-Content -Path .\IsReadOnlyTextFile.txt -Value 'Add value to read-only text file' -Force
Get-Content -Path .\IsReadOnlyTextFile.txt
```

```Output
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-ar--         1/28/2019     13:35              0 IsReadOnlyTextFile.txt
```

- `New-Item`Командлет использует параметры **path** и **ItemType** для создания файла `IsReadOnlyTextFile.txt` в текущем каталоге.
- `Set-ItemProperty`Командлет использует параметры **Name** и **value** , чтобы изменить свойство **IsReadOnly** для файла на true.
- `Get-ChildItem`Командлет показывает, что файл пуст (0) и имеет атрибут "только для чтения" ( `r` ).
- `Add-Content`Командлет использует параметр **path** для указания файла. Параметр **value** содержит текстовую строку, добавляемую к файлу. Параметр **Force** записывает текст в файл, который доступен только для чтения.
- `Get-Content`Командлет использует параметр **path** для вывода содержимого файла.

Чтобы удалить атрибут только для чтения, используйте `Set-ItemProperty` команду с параметром **value** , имеющим значение `False` .

### Пример 7. Использование фильтров с Add-Content

Можно указать фильтр для `Add-Content` командлета. При использовании фильтров для уточнения параметра **path** необходимо включить конечную звездочку ( `*` ), чтобы указать содержимое пути.

Следующая команда добавляет слово "Готово" к содержимому всех `*.txt` файлов в `C:\Temp` каталоге.

```powershell
Add-Content -Path C:\Temp\* -Filter *.txt -Value "Done"
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

Кодирование — это динамический параметр, который поставщик FileSystem добавляет в `Add-Content` командлет. Этот параметр работает только на дисках с файловой системой.

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
> Больше не рекомендуется использовать **UTF-7** *. В PowerShell 7,1 при указании параметра Encoding записывается предупреждение `utf7` . **Encoding**

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

Указывает в виде массива строк элемент или элементы, которые этот командлет исключает в операции. Значение этого параметра определяет параметр **Path** . Введите элемент пути или шаблон, например `*.txt` . Можно использовать подстановочные знаки. Параметр **Exclude** эффективен, только если команда включает содержимое элемента, например `C:\Windows\*` , где подстановочный знак указывает содержимое `C:\Windows` каталога.

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

Переопределяет атрибут «только для чтения», позволяя добавлять содержимое в файл, доступный только для чтения. Например, параметр **Force** позволяет переопределить атрибут «только для чтения» или создать дополнительные каталоги в пути, не меняя разрешения на доступ к файлу.

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

Указывает в виде массива строк элемент или элементы, которые этот командлет включает в операцию. Значение этого параметра определяет параметр **Path** . Введите элемент пути или шаблон, например `"*.txt"` . Можно использовать подстановочные знаки. Параметр **include** действует только в том случае, если команда включает содержимое элемента, например `C:\Windows\*` , где подстановочный знак указывает содержимое `C:\Windows` каталога.

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

Указывает, что этот командлет не добавляет новую строку или возврат каретки к содержимому.

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

Возвращает объект, представляющий добавленное содержимое. По умолчанию этот командлет не создает выходные данные.

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

Указывает путь к элементам, которые получают дополнительное содержимое.
Можно использовать подстановочные знаки.
Пути должны вести к элементам, а не к контейнерам.
Например, нужно указать путь к одному или нескольким файлам, а не путь к каталогу.
Если нужно указать несколько путей, разделите их запятыми.

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

Указывает альтернативный поток данных для содержимого. Если поток не существует, этот командлет создаст его. Подстановочные знаки не поддерживаются.

**Stream** — это динамический параметр, к которому добавляется поставщик FileSystem `Add-Content` . Этот параметр работает только на дисках с файловой системой.

`Add-Content`С помощью командлета можно изменить содержимое **зоны.** альтернативный поток данных идентификатора. Однако не рекомендуется использовать этот способ для устранения проверок безопасности, блокирующих файлы, загружаемые из Интернета. Если вы убедитесь, что скачанный файл является надежным, используйте `Unblock-File` командлет.

Этот параметр появился в PowerShell 3,0.

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

Задает добавляемое содержимое. Введите строку в кавычках, например **данные, предназначенные только для внутреннего использования** , или укажите объект, содержащий содержимое, например объект **DateTime** , который `Get-Date` создает.

Нельзя указать содержимое файла, введя его путь, поскольку путь является просто строкой.
`Get-Content`Для получения содержимого и передачи его в параметр **value** можно использовать команду.

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

### System. Object, System. Management. Automation. PSCredential

Можно передать значения, пути или учетные данные в `Set-Content` .

## Выходные данные

### Нет или System.String

При использовании параметра **PassThru** `Add-Content` создает объект **System. String** , представляющий содержимое. В противном случае командлет не формирует никаких выходных данных.

## ПРИМЕЧАНИЯ

- При передаче объекта в `Add-Content` объект преобразуется в строку перед добавлением в элемент. Формат строки определяется типом объекта, но может отличаться от используемого по умолчанию формата отображения объекта. Для управления форматом строки используйте параметры форматирования отправляющего командлета.
- Также можно ссылаться `Add-Content` по встроенному псевдониму `ac` . Дополнительные сведения см. в разделе [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).
- `Add-Content`Командлет предназначен для работы с данными, предоставляемыми любым поставщиком. Чтобы вывести список поставщиков, доступных в данном сеансе, введите командлет `Get-PSProvider`. Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).

## Связанные ссылки

[about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md)

[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)

[Clear-Content](Clear-Content.md)

[Get-Content](Get-Content.md)

[Get-Item](Get-Item.md)

[New-Item](New-Item.md)

[Set-Content](Set-Content.md)

