---
external help file: Microsoft.PowerShell.Archive-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Archive
ms.date: 02/20/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.archive/compress-archive?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Compress-Archive
ms.openlocfilehash: 796d510a1f7fd9bd7206e313dd23409fd8b2de1d
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93226853"
---
# Compress-Archive

## Краткий обзор
Создает сжатый архив или ZIP-файл из указанных файлов и каталогов.

## SYNTAX

### Путь (по умолчанию)

```
Compress-Archive [-Path] <String[]> [-DestinationPath] <String> [-CompressionLevel <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### пасвисупдате

```
Compress-Archive [-Path] <String[]> [-DestinationPath] <String> [-CompressionLevel <String>] -Update
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### пасвисфорце

```
Compress-Archive [-Path] <String[]> [-DestinationPath] <String> [-CompressionLevel <String>] -Force
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### литералпасвисупдате

```
Compress-Archive -LiteralPath <String[]> [-DestinationPath] <String> [-CompressionLevel <String>]
 -Update [-WhatIf] [-Confirm] [<CommonParameters>]
```

### литералпасвисфорце

```
Compress-Archive -LiteralPath <String[]> [-DestinationPath] <String> [-CompressionLevel <String>]
 -Force [-WhatIf] [-Confirm] [<CommonParameters>]
```

### LiteralPath

```
Compress-Archive -LiteralPath <String[]> [-DestinationPath] <String> [-CompressionLevel <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

`Compress-Archive`Командлет создает сжатый или ZIP-файл архива из одного или нескольких указанных файлов или каталогов. Архив упаковывает несколько файлов с необязательным сжатием в один ZIP-файл для упрощения распространения и хранения. Файл архива можно сжать с помощью алгоритма сжатия, заданного параметром **CompressionLevel** .

`Compress-Archive`Командлет использует Microsoft .NET API [System.IO.Compression.ZipArchive](/dotnet/api/system.io.compression.ziparchive) для сжатия файлов.
Максимальный размер файла составляет 2 ГБ, так как имеется ограничение на базовый API.

В некоторых примерах Сплаттинг используется для сокращения длины строки примеров кода. Дополнительные сведения см. в разделе [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md).

## Примеры

### Пример 1. сжатие файлов для создания файла архива

В этом примере производится сжатие файлов из разных каталогов и создание файла архива. Для получения всех файлов с определенным расширением файла используется подстановочный знак. В файле архива нет структуры каталогов, так как **путь** указывает только имена файлов.

```powershell
$compress = @{
  Path = "C:\Reference\Draftdoc.docx", "C:\Reference\Images\*.vsd"
  CompressionLevel = "Fastest"
  DestinationPath = "C:\Archives\Draft.Zip"
}
Compress-Archive @compress
```

Параметр **path** принимает определенные имена файлов и имена файлов с подстановочными знаками, `*.vsd` . **Путь** использует список с разделителями-запятыми для получения файлов из разных каталогов. Уровень сжатия **быстрее** всего используется для сокращения времени обработки. Параметр **DestinationPath** задает расположение `Draft.zip` файла. `Draft.zip`Файл содержит `Draftdoc.docx` и все файлы с `.vsd` расширением.

### Пример 2. сжатие файлов с помощью LiteralPath

Этот пример сжимает определенные именованные файлы и создает новый файл архива. В файле архива нет структуры каталогов, так как **путь** указывает только имена файлов.

```powershell
$compress = @{
LiteralPath= "C:\Reference\Draft Doc.docx", "C:\Reference\Images\diagram2.vsd"
CompressionLevel = "Fastest"
DestinationPath = "C:\Archives\Draft.Zip"
}
Compress-Archive @compress
```

Используется абсолютный путь и имена файлов, так как параметр **LiteralPath** не принимает подстановочные знаки. **Путь** использует список с разделителями-запятыми для получения файлов из разных каталогов. Уровень сжатия **быстрее** всего используется для сокращения времени обработки. Параметр **DestinationPath** задает расположение `Draft.zip` файла. `Draft.zip`Файл содержит только `Draftdoc.docx` и `diagram2.vsd` .

### Пример 3. Сжатие каталога, содержащего корневой каталог

В этом примере сжимается каталог и создается файл архива, **содержащий** корневой каталог и все его файлы и подкаталоги. Файл архива имеет структуру каталогов, так как **путь** указывает корневой каталог.

```powershell
Compress-Archive -Path C:\Reference -DestinationPath C:\Archives\Draft.zip
```

`Compress-Archive` использует параметр **path** для указания корневого каталога `C:\Reference` . Параметр **DestinationPath** указывает расположение файла архива. `Draft.zip`Архив включает `Reference` корневой каталог и все его файлы и подкаталоги.

### Пример 4. Сжатие каталога, который исключает корневой каталог

В этом примере выполняется сжатие каталога и создается файл архива, который **исключает** корневой каталог, поскольку **путь** использует `*` подстановочный знак звездочки (). Архив содержит структуру каталогов, содержащую файлы и подкаталоги корневого каталога.

```powershell
Compress-Archive -Path C:\Reference\* -DestinationPath C:\Archives\Draft.zip
```

`Compress-Archive` использует параметр **path** для указания корневого каталога `C:\Reference` с `*` подстановочным знаком звездочки (). Параметр **DestinationPath** указывает расположение файла архива. `Draft.zip`Архив содержит файлы и подкаталоги корневого каталога. `Reference`Корневой каталог исключается из архива.

### Пример 5. сжатие только файлов в корневом каталоге

В этом примере выполняется сжатие только файлов в корневом каталоге и создание файла архива. В архиве нет структуры каталогов, поскольку сжаты только файлы.

```powershell
Compress-Archive -Path C:\Reference\*.* -DestinationPath C:\Archives\Draft.zip
```

`Compress-Archive` использует параметр **path** для указания корневого каталога `C:\Reference` с подстановочным знаком **"звезда-точка-звезда** " ( `*.*` ). Параметр **DestinationPath** указывает расположение файла архива. `Draft.zip`Архив содержит только `Reference` файлы корневого каталога, а корневой каталог исключается.

### Пример 6. Использование конвейера для архивации файлов

В этом примере файлы посылаются по конвейеру для создания архива. В файле архива нет структуры каталогов, так как **путь** указывает только имена файлов.

```powershell
Get-ChildItem -Path C:\Reference\Afile.txt, C:\Reference\Images\Bfile.txt |
  Compress-Archive -DestinationPath C:\Archives\PipelineFiles.zip
```

`Get-ChildItem` использует параметр **path** для указания двух файлов из разных каталогов. Каждый файл представлен объектом **FileInfo** и отправляется по конвейеру в `Compress-Archive` .
Два указанных файла архивируются в `PipelineFiles.zip` .

### Пример 7. Использование конвейера для архивации каталога

В этом примере каталог посылается по конвейеру для создания архива. Файлы отправляются как объекты и каталоги **FileInfo** как объекты **DirectoryInfo** . Структура каталогов архива не включает корневой каталог, но его файлы и подкаталоги включены в архив.

```powershell
Get-ChildItem -Path C:\LogFiles | Compress-Archive -DestinationPath C:\Archives\PipelineDir.zip
```

`Get-ChildItem` использует параметр **path** для указания `C:\LogFiles` корневого каталога. Каждый объект **FileInfo** и **DirectoryInfo** отправляется по конвейеру.

`Compress-Archive` добавляет каждый объект в `PipelineDir.zip` Архив. Параметр **пути** не указан, так как объекты конвейера получены в положении параметра 0.

### Пример 8. как рекурсия может повлиять на архивы

В этом примере показано, как рекурсия может дублировать файлы в архиве. Например, при использовании `Get-ChildItem` с параметром **рекурсии** . В качестве процессов рекурсии каждый объект **FileInfo** и **DirectoryInfo** отсылается по конвейеру и добавляется в архив.

```powershell
Get-ChildItem -Path C:\TestLog -Recurse |
  Compress-Archive -DestinationPath C:\Archives\PipelineRecurse.zip
```

`C:\TestLog`Каталог не содержит файлов. Он содержит подкаталог с именем `testsub` , содержащий `testlog.txt` файл.

`Get-ChildItem` использует параметр **path** для указания корневого каталога `C:\TestLog` . **Рекурсивный** параметр обрабатывает файлы и каталоги. Создается объект **DirectoryInfo** для `testsub` и объекта **FileInfo** `testlog.txt` .

Каждый объект отправляется по конвейеру в `Compress-Archive` . **DestinationPath** указывает расположение файла архива. Параметр **пути** не указан, так как объекты конвейера получены в положении параметра 0.

Следующая сводка описывает `PipelineRecurse.zip` содержимое архива, которое содержит дубликат файла:

- Объект **DirectoryInfo** создает `testsub` каталог и содержит `testlog.txt` файл, который отражает исходную структуру каталогов.
- Объект **FileInfo** создает дубликат `testlog.txt` в корне архива. Создается повторяющийся файл, так как рекурсия отправляет объект File в `Compress-Archive` . Это ожидаемое поведение, поскольку каждый объект, отправленный по конвейеру, добавляется в архив.

### Пример 9. Обновление существующего файла архива

В этом примере выполняется обновление существующего файла архива `Draft.Zip` в `C:\Archives` каталоге. В этом примере существующий файл архива содержит корневой каталог, а также его файлы и подкаталоги.

```powershell
Compress-Archive -Path C:\Reference -Update -DestinationPath C:\Archives\Draft.Zip
```

Команда обновляется `Draft.Zip` с использованием более новых версий существующих файлов в `C:\Reference` каталоге и его подкаталогах. Новые файлы, добавленные в `C:\Reference` или его подкаталоги, включаются в обновленный `Draft.Zip` Архив.

## PARAMETERS

### -CompressionLevel

Задает степень сжатия, применяемого при создании файла архива. Более быстрое сжатие требует меньше времени на создание файла, но может привести к увеличению размеров файлов.

Если этот параметр не указан, команда использует значение по умолчанию — **оптимальный**.

Ниже приведены допустимые значения для этого параметра.

- **Самый быстрый**. Используйте самый быстрый метод сжатия, чтобы сократить время обработки. Более быстрое сжатие может привести к увеличению размеров файлов.
- **Несжатие**. Не сжимает исходные файлы.
- **Оптимальный**. Время обработки зависит от размера файла.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Optimal, NoCompression, Fastest

Required: False
Position: Named
Default value: Optimal
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

### -DestinationPath

Этот параметр является обязательным и указывает путь к выходному файлу архива. **DestinationPath** должен включать имя ZIP-файла, а также абсолютный или относительный путь к ZIP-файлу.

Если имя файла в **DestinationPath** не имеет `.zip` расширения имени файла, командлет добавляет `.zip` расширение имени файла.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Принудительное выполнение команды без запроса на подтверждение пользователем.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PathWithForce, LiteralPathWithForce
Aliases:

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -LiteralPath

Указывает путь или пути к файлам, которые необходимо добавить в архивный zip-файл. В отличие от параметра **path** , значение **LiteralPath** используется точно так же, как типизировано. Никакие символы не интерпретируются как знаки подстановки. Если путь содержит escape-символы, заключите каждый escape-символ в одинарные кавычки, чтобы заставить PowerShell не интерпретировать какие-либо символы как escape-последовательности.
Чтобы указать несколько путей и включить файлы в несколько расположений в выходном ZIP-файле, используйте запятые для разделения путей.

```yaml
Type: System.String[]
Parameter Sets: LiteralPathWithUpdate, LiteralPathWithForce, LiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path

Указывает путь или пути к файлам, которые необходимо добавить в архивный zip-файл. Чтобы указать несколько путей и включить файлы в нескольких местах, используйте запятые для разделения путей.

Этот параметр принимает подстановочные знаки. Подстановочные знаки позволяют добавлять все файлы в каталоге в файл архива.

Использование подстановочных знаков с корневым каталогом влияет на содержимое архива:

- Чтобы создать архив, **включающий** корневой каталог и все его файлы и подкаталоги, укажите корневой каталог в **пути** без подстановочных знаков. Пример: `-Path C:\Reference`
- Чтобы создать архив, **исключающий** корневой каталог, но zips все его файлы и подкаталоги, используйте подстановочный знак "звездочка" ( `*` ). Пример: `-Path C:\Reference\*`
- Чтобы создать архив, zips только файлы в корневом каталоге, используйте подстановочный знак **"звезда-точка-звезда** " ( `*.*` ). Подкаталоги корневого каталога не включаются в архив. Пример: `-Path C:\Reference\*.*`

```yaml
Type: System.String[]
Parameter Sets: Path, PathWithUpdate, PathWithForce
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### — Обновление

Обновляет указанный архив, заменяя старые версии файлов в архиве более новыми версиями с теми же именами. Можно также добавить этот параметр, чтобы добавить файлы в существующий архив.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PathWithUpdate, LiteralPathWithUpdate
Aliases:

Required: True
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

Строку, содержащую путь, можно передать в один или несколько файлов.

## Выходные данные

### Нет

## ПРИМЕЧАНИЯ

Использование рекурсии и отправка объектов вниз по конвейеру могут дублировать файлы в архиве. Например, при использовании `Get-ChildItem` с параметром **рекурсии** каждый объект **FileInfo** и **DirectoryInfo** , отправленный по конвейеру, добавляется в архив.

В [спецификации ZIP-файла](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT) не указан стандартный способ кодирования имен файлов, содержащих символы, не входящие в набор ASCII. `Compress-Archive`Командлет использует кодировку UTF-8. Другие средства архивирования ZIP могут использовать другую схему кодирования. При извлечении файлов с именами, которые не хранятся в кодировке UTF-8, `Expand-Archive` использует необработанное значение, найденное в архиве. Это может привести к тому, что имя файла будет отличаться от исходного имени файла, хранящегося в архиве.

## Связанные ссылки

[Expand-Archive](Expand-Archive.md)

[Get-ChildItem](../Microsoft.PowerShell.Management/Get-ChildItem.md)
