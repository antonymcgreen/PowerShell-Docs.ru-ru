---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 04/23/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/add-content?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-Content
ms.openlocfilehash: 903c4eb784c1bb86b66766c7dfb563f586545dc1
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228470"
---
# Add-Content

## Краткий обзор
Добавляет содержимое в указанные элементы, например слова в файл.

## SYNTAX

### Путь (по умолчанию)

```
Add-Content [-Path] <string[]> [-Value] <Object[]> [-PassThru] [-Filter <string>]
 [-Include <string[]>] [-Exclude <string[]>] [-Force] [-Credential <pscredential>] [-WhatIf]
 [-Confirm] [-UseTransaction] [-NoNewline] [-Encoding <FileSystemCmdletProviderEncoding>]
 [-Stream <string>] [<CommonParameters>]
```

### LiteralPath

```
Add-Content [-Value] <Object[]> -LiteralPath <string[]> [-PassThru] [-Filter <string>]
 [-Include <string[]>] [-Exclude <string[]>] [-Force] [-Credential <pscredential>] [-WhatIf]
 [-Confirm] [-UseTransaction] [-NoNewline] [-Encoding <FileSystemCmdletProviderEncoding>]
 [-Stream <string>] [<CommonParameters>]
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

`Add-Content`Командлет использует параметр **path** для указания всех TXT файлов в текущем каталоге. Параметр **Exclude** игнорирует имена файлов, соответствующие указанному шаблону. Параметр **value** задает текстовую строку, которая записывается в файлы.

Чтобы отобразить содержимое этих файлов, используйте [Get-Content](Get-Content.md) .

### Пример 2. добавление даты в конец указанных файлов

Этот пример добавляет дату к файлам в текущем каталоге и отображает дату в консоли PowerShell.

```powershell
Add-Content -Path .\DateTimeFile1.log, .\DateTimeFile2.log -Value (Get-Date) -PassThru
Get-Content -Path .\DateTimeFile1.log
```

`Add-Content`Командлет использует параметры **path** и **value** для создания двух новых файлов в текущем каталоге. Параметр **value** задает `Get-Date` командлет для получения даты и передает дату в `Add-Content` . `Add-Content`Командлет записывает дату в каждый файл. Параметр **PassThru** передает объект, представляющий объект Date. Так как нет других командлетов для получения переданного объекта, он отображается в консоли PowerShell. `Get-Content`Командлет отображает обновленный файл DateTimeFile1. log.

### Пример 3. Добавление содержимого указанного файла в другой файл

Этот пример получает содержимое из файла и добавляет содержимое в другой файл.

```powershell
Add-Content -Path .\CopyToFile.txt -Value (Get-Content -Path .\CopyFromFile.txt)
Get-Content -Path .\CopyToFile.txt
```

`Add-Content`Командлет использует параметр **path** для указания нового файла в текущем каталоге CopyToFile.txt. Параметр **value** использует `Get-Content` командлет для получения содержимого файла, CopyFromFile.txt. Круглые скобки вокруг `Get-Content` командлета гарантируют, что команда завершится до `Add-Content` начала выполнения команды. Параметр **value** передается в `Add-Content` . `Add-Content`Командлет добавляет данные в файл CopyToFile.txt. `Get-Content`Командлет отображает обновленный файл CopyToFile.txt.

### Пример 4. Использование переменной для добавления содержимого указанного файла в другой файл

Этот пример получает содержимое из файла и сохраняет содержимое в переменной. Переменная используется для добавления содержимого в другой файл.

```powershell
$From = Get-Content -Path .\CopyFromFile.txt
Add-Content -Path .\CopyToFile.txt -Value $From
Get-Content -Path .\CopyToFile.txt
```

`Get-Content`Командлет возвращает содержимое CopyFromFile.txt и сохраняет содержимое в `$From` переменной. `Add-Content`Командлет использует параметр **path** для указания файла CopyToFile.txt в текущем каталоге. Параметр **value** использует `$From` переменную и передает содержимое в `Add-Content` . `Add-Content`Командлет обновляет файл CopyToFile.txt. `Get-Content`Командлет отображает CopyToFile.txt.

### Пример 5. Создание нового файла и копирование содержимого

В этом примере создается новый файл и копируется содержимое существующего файла в новый файл.

```powershell
Add-Content -Path .\NewFile.txt -Value (Get-Content -Path .\CopyFromFile.txt)
Get-Content -Path .\NewFile.txt
```

`Add-Content`Командлет использует параметры **path** и **value** для создания нового файла в текущем каталоге. Параметр **value** использует `Get-Content` командлет для получения содержимого существующего файла, CopyFromFile.txt. Круглые скобки вокруг `Get-Content` командлета гарантируют, что команда завершится до `Add-Content` начала выполнения команды. Параметр **value** передает содержимое, в `Add-Content` которое обновляется файл NewFile.txt. `Get-Content`Командлет отображает содержимое нового файла, NewFile.txt.

### Пример 6. Добавление содержимого в файл, который доступен только для чтения

Эта команда добавляет значение в файл, даже если атрибуту файла **IsReadOnly** присвоено значение true.
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
-ar---        1/28/2019     13:35              0 IsReadOnlyTextFile.txt
```

`New-Item`Командлет использует параметры **path** и **ItemType** для создания файла IsReadOnlyTextFile.txt в текущем каталоге. `Set-ItemProperty`Командлет использует параметры **Name** и **value** , чтобы изменить свойство **IsReadOnly** для файла на true. `Get-ChildItem`Командлет показывает, что файл пуст (0) и имеет атрибут "только для чтения" ( `r` ). `Add-Content`Командлет использует параметр **path** для указания файла. Параметр **value** содержит текстовую строку, добавляемую к файлу. Параметр **Force** записывает текст в файл, который доступен только для чтения. `Get-Content`Командлет использует параметр **path** для вывода содержимого файла.

Чтобы удалить атрибут только для чтения, используйте `Set-ItemProperty` команду с параметром **value** , имеющим значение `False` .

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

### -Credential

Указывает учетную запись пользователя с разрешением на выполнение этого действия. По умолчанию используется текущий пользователь.

Введите имя пользователя, например **User01** или **Domain01\User01** , либо введите объект **PSCredential** , например, созданный `Get-Credential` командлетом. При вводе имени пользователя запрашивается пароль.

> [!WARNING]
> Этот параметр не поддерживается какими-либо поставщиками, установленными с помощью PowerShell.

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

Указывает тип кодировки для целевого файла. Значение по умолчанию — `Default`.

Для этого параметра допустимы следующие значения:

- `Ascii` Использует кодировку ASCII (7-разрядных).
- `BigEndianUnicode` Использует UTF-16 с обратным порядком байтов.
- `BigEndianUTF32` Использует UTF-32 с обратным порядком байтов.
- `Byte` Кодирует набор символов в последовательность байтов.
- `Default` Использует кодировку, соответствующую активной кодовой странице системы (обычно ANSI).
- `Oem` Использует кодировку, соответствующую текущей кодовой странице OEM системы.
- `String` То же, что и **Юникод** .
- `Unicode` Использует UTF-16 с прямым порядком байтов.
- `Unknown` То же, что и **Юникод** .
- `UTF7` Использует UTF-7.
- `UTF8` Использует UTF-8.
- `UTF32` Использует UTF-32 с прямым порядком байтов.

Кодирование — это динамический параметр, который поставщик FileSystem добавляет в `Add-Content` командлет. Этот параметр работает только на дисках с файловой системой.

```yaml
Type: Microsoft.PowerShell.Commands.FileSystemCmdletProviderEncoding
Parameter Sets: (All)
Aliases:
Accepted values: ASCII, BigEndianUnicode, BigEndianUTF32, Byte, Default, OEM, String, Unicode, Unknown, UTF7, UTF8, UTF32

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### -Exclude

Исключает указанные элементы. Значение этого параметра определяет параметр **Path** . Введите элемент пути или шаблон, например **\* txt** . Разрешено использовать подстановочные знаки.

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

Задает фильтр в формате или на языке поставщика. Значение этого параметра определяет параметр **Path** . Синтаксис фильтра, включая использование подстановочных знаков, зависит от поставщика. **Фильтры** более эффективны, чем другие параметры, так как поставщик применяет фильтры при извлечении объектов. В противном случае PowerShell обрабатывает фильтры после извлечения объектов.

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

Добавляет только указанные элементы. Значение этого параметра определяет параметр **Path** . Введите элемент пути или шаблон, например **\* txt** . Разрешено использовать подстановочные знаки.

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

Указывает путь к элементам, которые получают дополнительное содержимое. В отличие от параметра **Path** , значение параметра **LiteralPath** используется строго в том виде, в котором оно указано. Никакие символы не интерпретируются как знаки подстановки. Если путь содержит escape-символы, заключите его в одинарные кавычки. Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath

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

Указывает путь к элементам, которые получают дополнительное содержимое. Разрешено использовать подстановочные знаки. Если нужно указать несколько путей, разделите их запятыми.

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

### -UseTransaction

Включает команду в активную транзакцию. Этот параметр доступен только при выполнении транзакции. Дополнительные сведения см. в разделе [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md).

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: usetx

Required: False
Position: Named
Default value: False
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

Этот командлет поддерживает общие параметры: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` и `-WarningVariable` . См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System. Object, System. Management. Automation. PSCredential

Можно передать значения, пути или учетные данные в `Set-Content` .

## Выходные данные

### Нет или System.String

При использовании параметра **PassThru** `Add-Content` создает объект **System. String** , представляющий содержимое. В противном случае командлет не формирует никаких выходных данных.

## ПРИМЕЧАНИЯ

При передаче объекта в `Add-Content` объект преобразуется в строку перед добавлением в элемент. Формат строки определяется типом объекта, но может отличаться от используемого по умолчанию формата отображения объекта. Для управления форматом строки используйте параметры форматирования отправляющего командлета.

Также можно ссылаться `Add-Content` по встроенному псевдониму `ac` . Дополнительные сведения см. в разделе [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).

`Add-Content`Командлет предназначен для работы с данными, предоставляемыми любым поставщиком. Чтобы вывести список поставщиков, доступных в данном сеансе, введите командлет `Get-PSProvider`. Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).

## Связанные ссылки

[about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md)

[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)

[about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md)

[Clear-Content](Clear-Content.md)

[Get-Content](Get-Content.md)

[Get-Item](Get-Item.md)

[New-Item](New-Item.md)

[Set-Content](Set-Content.md)
