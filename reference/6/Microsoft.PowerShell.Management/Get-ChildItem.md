---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 03/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-childitem?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ChildItem
ms.openlocfilehash: 14b1c5d0f37301a5312f37a115f0abc1c7b5990e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228838"
---
# Get-ChildItem

## Краткий обзор

Получает элементы и дочерние элементы в одном или нескольких указанных расположениях

## SYNTAX

### Элементы (по умолчанию)

```
Get-ChildItem [[-Path] <string[]>] [[-Filter] <string>] [-Include <string[]>] [-Exclude <string[]>]
 [-Recurse] [-Depth <uint32>] [-Force] [-Name] [-Attributes <FlagsExpression[FileAttributes]>]
 [-FollowSymlink] [-Directory] [-File] [-Hidden] [-ReadOnly] [-System] [<CommonParameters>]
```

### литералитемс

```
Get-ChildItem [[-Filter] <string>] -LiteralPath <string[]> [-Include <string[]>]
 [-Exclude <string[]>] [-Recurse] [-Depth <uint32>] [-Force] [-Name]
 [-Attributes <FlagsExpression[FileAttributes]>] [-FollowSymlink] [-Directory] [-File] [-Hidden]
 [-ReadOnly] [-System] [<CommonParameters>]
```

## DESCRIPTION

`Get-ChildItem`Командлет возвращает элементы в одном или нескольких указанных расположениях. Если элемент является контейнером, командлет получает элементы внутри контейнера, называемые дочерними элементами. Можно использовать параметр **рекурсии** для получения элементов во всех дочерних контейнерах и использовать параметр **Depth** , чтобы ограничить число уровней для рекурсии.

`Get-ChildItem` не отображает пустые каталоги. Если `Get-ChildItem` команда содержит **глубину** или **Рекурсивные** параметры, в выходные данные не включаются пустые каталоги.

Расположения предоставляются `Get-ChildItem` поставщиками PowerShell. Расположением может быть каталог файловой системы, куст реестра или хранилище сертификатов. Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).

## Примеры

### Пример 1. Получение дочерних элементов из каталога файловой системы

Этот пример получает дочерние элементы из каталога файловой системы. Отобразятся имена файлов и подкаталогов. Для пустых расположений команда не возвращает никаких выходных данных и возвращается в командную строку PowerShell.

`Get-ChildItem`Командлет использует параметр **path** для указания каталога `C:\Test` .
`Get-ChildItem` Отображает файлы и каталоги в консоли PowerShell.

```powershell
Get-ChildItem -Path C:\Test
```

```Output
   Directory: C:\Test

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----        2/15/2019     08:29                Logs
-a----        2/13/2019     08:55             26 anotherfile.txt
-a----        2/12/2019     15:40         118014 Command.txt
-a----         2/1/2019     08:43            183 CreateTestFile.ps1
-ar---        2/12/2019     14:31             27 ReadOnlyFile.txt
```

По умолчанию `Get-ChildItem` перечисляет режим ( **атрибуты** ), **LastWriteTime** , размер файла ( **Длина** ) и **имя** элемента. Буквы в свойстве **mode** можно интерпретировать следующим образом:

- `l` ссылку
- `d` каталоги
- `a` упражнени
- `r` (только для чтения)
- `h` служеб
- `s` (система).

Дополнительные сведения о флагах режима см. в разделе [about_Filesystem_Provider](../microsoft.powershell.core/about/about_filesystem_provider.md#attributes-flagsexpression).

### Пример 2. Получение имен дочерних элементов в каталоге

В этом примере выводятся только имена элементов в каталоге.

`Get-ChildItem`Командлет использует параметр **path** для указания каталога `C:\Test` . Параметр **Name** возвращает только имена файлов или каталогов из указанного пути.

```powershell
Get-ChildItem -Path C:\Test -Name
```

```Output
Logs
anotherfile.txt
Command.txt
CreateTestFile.ps1
ReadOnlyFile.txt
```

### Пример 3. Получение дочерних элементов в текущем каталоге и подкаталогах

В этом примере отображаются **txt** файлы, расположенные в текущем каталоге и его подкаталогах.

```powershell
Get-ChildItem -Path C:\Test\*.txt -Recurse -Force
```

```Output
    Directory: C:\Test\Logs\Adirectory

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        2/12/2019     16:16             20 Afile4.txt
-a-h--        2/12/2019     15:52             22 hiddenfile.txt
-a----        2/13/2019     13:26             20 LogFile4.txt

    Directory: C:\Test\Logs\Backup

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        2/12/2019     16:16             20 ATextFile.txt
-a----        2/12/2019     15:50             20 LogFile3.txt

    Directory: C:\Test\Logs

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        2/12/2019     16:16             20 Afile.txt
-a-h--        2/12/2019     15:52             22 hiddenfile.txt
-a----        2/13/2019     13:26             20 LogFile1.txt

    Directory: C:\Test

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        2/13/2019     08:55             26 anotherfile.txt
-a----        2/12/2019     15:40         118014 Command.txt
-a-h--        2/12/2019     15:52             22 hiddenfile.txt
-ar---        2/12/2019     14:31             27 ReadOnlyFile.txt
```

`Get-ChildItem`Командлет использует параметр **path** для указания `C:\Test\*.txt` . В **пути** используется `*` подстановочный знак звездочки () для указания всех файлов с расширением имени файла `.txt` . Параметр **рекурсии** выполняет поиск в каталоге **пути к** подкаталогам, как показано в **каталоге:** заголовки. Параметр **Force** отображает скрытые файлы `hiddenfile.txt` , например, с режимом **h** .

### Пример 4. Получение дочерних элементов с помощью параметра Include

В этом примере `Get-ChildItem` параметр **include** используется для поиска определенных элементов из каталога, указанного параметром **path** .

```powershell
# When using the -Include parameter, if you don't include an asterisk in the path
# the command returns no output.
Get-ChildItem -Path C:\Test\ -Include *.txt
```

```Output

```

```powershell
Get-ChildItem -Path C:\Test\* -Include *.txt
```

```Output
    Directory: C:\Test

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        2/13/2019     08:55             26 anotherfile.txt
-a----        2/12/2019     15:40         118014 Command.txt
-ar---        2/12/2019     14:31             27 ReadOnlyFile.txt
```

`Get-ChildItem`Командлет использует параметр **path** для указания каталога **C:\test** . Параметр **path** включает в себя `*` подстановочный знак звездочки () для указания содержимого каталога.
Параметр **include** использует `*` подстановочный знак звездочки (), чтобы указать все файлы с расширением **txt** .

Если используется параметр **include** , для указания содержимого каталога параметру **path** требуется символ-шаблон звездочки ( `*` ). Например, `-Path C:\Test\*`.

- Если в команду добавляется **рекурсивный** параметр, то символ звездочки ( `*` ) в параметре **path** является необязательным. Параметр **рекурсии** возвращает элементы из каталога **пути** и его подкаталогов. Например `-Path C:\Test\ -Recurse -Include *.txt`.
- Если конечная звездочка ( `*` ) не включена в параметр **path** , команда не возвращает никаких выходных данных и возвращается в командную строку PowerShell. Например, `-Path C:\Test\`.

### Пример 5. Получение дочерних элементов с помощью параметра Exclude

В выходных данных примера показано содержимое каталога **к:\тест\логс** . Выходные данные представляют собой ссылку на другие команды, в которых используются параметры **Exclude** и **recurse** .

```powershell
Get-ChildItem -Path C:\Test\Logs
```

```Output
    Directory: C:\Test\Logs

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----        2/15/2019     13:21                Adirectory
d-----        2/15/2019     08:28                AnEmptyDirectory
d-----        2/15/2019     13:21                Backup
-a----        2/12/2019     16:16             20 Afile.txt
-a----        2/13/2019     13:26             20 LogFile1.txt
-a----        2/12/2019     16:24             23 systemlog1.log
```

```powershell
Get-ChildItem -Path C:\Test\Logs\* -Exclude A*
```

```Output
    Directory: C:\Test\Logs

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----        2/15/2019     13:21                Backup
-a----        2/13/2019     13:26             20 LogFile1.txt
-a----        2/12/2019     16:24             23 systemlog1.log
```

`Get-ChildItem`Командлет использует параметр **path** для указания каталога `C:\Test\Logs` .
Параметр **Exclude** использует `*` подстановочный знак звездочки (), чтобы указать файлы или каталоги, которые **A** начинаются с **a** или, исключаются из выходных данных.

При использовании параметра **Exclude** символ звездочки ( `*` ) в параметре **path** является необязательным. Например, `-Path C:\Test\Logs` или `-Path C:\Test\Logs\*`.

- Если конечная звездочка ( `*` ) не включена в параметр **path** , отображается содержимое параметра **path** . Исключениями являются имена файлов или подкаталогов, соответствующие значению параметра **Exclude** .
- Если в параметр пути включена конечная звездочка ( `*` ) **Path** , команда выполняет рекурсивный путь к подкаталогам параметра **path** . Исключениями являются имена файлов или подкаталогов, соответствующие значению параметра **Exclude** .
- Если в команду добавляется **рекурсивный** параметр, то выходные данные рекурсии одинаковы, независимо от того, содержит ли параметр **пути** конечную звездочку ( `*` ).

### Пример 6. получение разделов реестра из куста реестра

Этот пример получает все разделы реестра из `HKEY_LOCAL_MACHINE\HARDWARE` .

`Get-ChildItem` использует параметр **path** для указания раздела реестра `HKLM:\HARDWARE` . Путь к кусту и его верхний уровень разделов реестра отображаются в консоли PowerShell.

Дополнительные сведения см. в разделе [about_Registry_Provider](../Microsoft.PowerShell.Core/About/about_Registry_Provider.md).

```powershell
Get-ChildItem -Path HKLM:\HARDWARE
```

```Output
    Hive: HKEY_LOCAL_MACHINE\HARDWARE

Name             Property
----             --------
ACPI
DESCRIPTION
DEVICEMAP
RESOURCEMAP
UEFI
```

```powershell
Get-ChildItem -Path HKLM:\HARDWARE -Exclude D*
```

```Output
   Hive: HKEY_LOCAL_MACHINE\HARDWARE

Name                           Property
----                           --------
ACPI
RESOURCEMAP
```

Первая команда отображает содержимое `HKLM:\HARDWARE` раздела реестра. Параметр **Exclude** `Get-ChildItem` не возвращает никаких подразделов, начинающихся с `D*` . В настоящее время параметр **Exclude** работает только для подразделов, а не для свойств элемента.

### Пример 7. получение всех сертификатов с помощью центра подписывания кода

В этом примере каждый сертификат создается на диске **сертификата PowerShell:** с центром подписывания кода.

`Get-ChildItem`Командлет использует параметр **path** для указания **CERT:** provider. Параметр **рекурсии** выполняет поиск в каталоге, указанном по **пути** и его подкаталогам. Параметр **CodeSigningCert** возвращает только сертификаты, имеющие центр подписывания кода.

```powershell
Get-ChildItem -Path Cert:\* -Recurse -CodeSigningCert
```

Дополнительные сведения о поставщике сертификатов и диске CERT: см. в разделе [about_Certificate_Provider](../Microsoft.PowerShell.Security/About/about_Certificate_Provider.md).

### Пример 8. Получение элементов с помощью параметра Depth

В этом примере отображаются элементы в каталоге и его подкаталогах. Параметр **Depth** определяет число уровней подкаталогов, включаемых в рекурсию. Пустые каталоги исключаются из выходных данных.

```powershell
Get-ChildItem -Path C:\Parent -Depth 2
```

```Output
    Directory: C:\Parent

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----        2/14/2019     10:24                SubDir_Level1
-a----        2/13/2019     08:55             26 file.txt

    Directory: C:\Parent\SubDir_Level1

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----        2/14/2019     10:24                SubDir_Level2
-a----        2/13/2019     08:55             26 file.txt

    Directory: C:\Parent\SubDir_Level1\SubDir_Level2

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----        2/14/2019     10:22                SubDir_Level3
-a----        2/13/2019     08:55             26 file.txt
```

`Get-ChildItem`Командлет использует параметр **path** для указания **к:\парент** . Параметр **Depth** указывает два уровня рекурсии. `Get-ChildItem` Отображает содержимое каталога, указанного параметром **path** , и двух уровней вложенных каталогов.

### Пример 9. Получение сведений о жесткой связи

В PowerShell 6,2 для получения сведений о жесткой связи было добавлено альтернативное представление.

```powershell
Get-ChildItem -Path C:\PathContainingHardLink | Format-Table -View childrenWithHardLink
```

## Параметры

### Атрибуты

Извлекает файлы и папки с указанными атрибутами. Этот параметр поддерживает все атрибуты и позволяет указывать сложные сочетания атрибутов.

Например, чтобы извлечь зашифрованные или сжатые файлы, не являющиеся системными (которые не являются каталогами), введите следующее:

`Get-ChildItem -Attributes !Directory+!System+Encrypted, !Directory+!System+Compressed`

Чтобы найти файлы и папки с часто используемыми атрибутами, используйте параметр **Attributes** . Или — **Каталог** параметров, **файл** , **скрытый** , **только для чтения** и **System** .

Параметр **Attributes** поддерживает следующие свойства:

- **Архив**
- **Compressed**
- **Устройство**
- **Каталог**
- **Зашифрована**
- **Скрыта**
- **интегритистреам**
- **Обычный**
- **носкрубдата**
- **нотконтентиндексед**
- **Работа**
- **ReadOnly**
- **репарсепоинт**
- **спарсефиле**
- **Системные функции**
- **Временные процедуры**

Описание этих атрибутов см. в описании [перечисления FileAttributes](/dotnet/api/system.io.fileattributes).

Чтобы объединить атрибуты, используйте следующие операторы:

- `!` НЕДОСТАТОЧНО
- `+` ПЕРЕТАСКИВАНИ
- `,` НИ

Не используйте пробелы между оператором и его атрибутом. Пробелы принимаются после запятых.

Для общих атрибутов используйте следующие сокращения:

- `D` Каталоги
- `H` Служеб
- `R` (Только для чтения)
- `S` Системой

```yaml
Type: System.Management.Automation.FlagsExpression`1[System.IO.FileAttributes]
Parameter Sets: (All)
Aliases:
Accepted values: Archive, Compressed, Device, Directory, Encrypted, Hidden, IntegrityStream, Normal, NoScrubData, NotContentIndexed, Offline, ReadOnly, ReparsePoint, SparseFile, System, Temporary

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Depth

Этот параметр был добавлен в PowerShell 5,0 и позволяет управлять глубиной рекурсии. По умолчанию `Get-ChildItem` отображает содержимое родительского каталога. Параметр **Depth** определяет количество уровней подкаталогов, включаемых в рекурсию, и отображает содержимое.

Например, `Depth 2` включает каталог параметра **path** , первый уровень подкаталогов и второй уровень вложенных каталогов. По умолчанию в выходные данные включаются имена каталогов и имен файлов.

> [!NOTE]
> На компьютере Windows из PowerShell или **cmd.exe** можно отобразить графическое представление структуры каталогов с помощью команды **Tree.com** .

```yaml
Type: System.UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Directory

Чтобы получить список каталогов, используйте параметр **Directory** или параметр **Attributes** со свойством **Directory** . Можно использовать параметр **рекурсии** с **каталогом** .

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: ad, d

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Exclude

Указывает свойство или свойства, исключаемые этим командлетом из операции, в виде массива строк.
Значение этого параметра определяет параметр **Path** . Введите элемент пути или шаблон, например `*.txt` или `A*` . Принимаются символы-шаблоны.

Конечная звездочка ( `*` ) в параметре **path** является необязательной. Например, `-Path C:\Test\Logs` или `-Path C:\Test\Logs\*`. Если включена конечная звездочка ( `*` ), команда выполняет рекурсивный путь к подкаталогам параметра **path** . Без звездочки ( `*` ) отображается содержимое параметра **path** . Дополнительные сведения см. в примере 5 и в разделе "Примечания".

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

### -File

Чтобы получить список файлов, используйте параметр **File** . Параметр **рекурсии** можно использовать с **File** .

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: af

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Filter

Задает фильтр для уточнения параметра **пути** . Поставщик [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) является единственным установленным поставщиком PowerShell, поддерживающим фильтры. Фильтры более эффективны, чем другие параметры. Поставщик применяет фильтр, когда командлет получает объекты, вместо того, чтобы PowerShell отфильтровывает объекты после их извлечения. Строка фильтра передается в API .NET для перечисления файлов. API поддерживает только `*` `?` подстановочные знаки и.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Фолловсимлинк

По умолчанию `Get-ChildItem` командлет отображает символические ссылки на каталоги, найденные во время рекурсии, но не выполняет их рекурсивный переход. Используйте параметр **фолловсимлинк** для поиска в каталогах, предназначенных для этих символьных ссылок. **Фолловсимлинк** является динамическим параметром и поддерживается только в поставщике **FileSystem** .

Этот параметр появился в PowerShell 6,0.

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

### -Force

Позволяет командлету получать элементы, к которым не может получить доступ пользователь, например скрытый или системный файл. Параметр **Force** не переопределяет ограничения безопасности. Реализация зависит от поставщика. Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).

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

### -Hidden

Чтобы получить только скрытые элементы, используйте параметр **Hidden** или **Attributes** со свойством **Hidden** . По умолчанию `Get-ChildItem` скрытые элементы не отображаются. Для получения скрытых элементов используйте параметр **Force** .

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: ah, h

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

Указывает путь к одному или нескольким расположениям. Значение **LiteralPath** используется точно так же, как типизировано. Никакие символы не интерпретируются как знаки подстановки. Если путь содержит escape-символы, заключите его в одинарные кавычки. Одинарные кавычки указывают PowerShell не интерпретировать символы как escape-последовательности.

Дополнительные сведения см. в разделе [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).

```yaml
Type: System.String[]
Parameter Sets: LiteralItems
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name

Возвращает только имена элементов в расположении. Выходные данные представляют собой строковый объект, который может быть отправлен по конвейеру другим командам. Разрешено использовать подстановочные знаки.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Path

Указывает путь к одному или нескольким расположениям. Подстановочные знаки принимаются. Расположение по умолчанию — текущий каталог ( `.` ).

```yaml
Type: System.String[]
Parameter Sets: Items
Aliases:

Required: False
Position: 0
Default value: Current directory
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -ReadOnly

Чтобы получить только элементы, доступные только для чтения, используйте параметр **ReadOnly** или свойство **Attributes** **ReadOnly** .

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: ar

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Recurse

Получает элементы в указанных расположениях и всех дочерних элементах расположений.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: s

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -System

Возвращает только системные файлы и каталоги. Чтобы получить только системные файлы и папки, используйте свойство **System системного параметра или** параметра **System** **Attributes** .

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: as

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.String

Можно передать строку, содержащую путь, в `Get-ChildItem` .

## Выходные данные

### System.Object

Тип `Get-ChildItem` возвращаемого объекта определяется объектами в пути к диску поставщика.

### System.String

При использовании параметра **Name** `Get-ChildItem` возвращает имена объектов в виде строк.

## ПРИМЕЧАНИЯ

- `Get-ChildItem` может выполняться с помощью любого встроенного псевдонима,, `ls` `dir` и `gci` . Дополнительные сведения см. в разделе [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).
- `Get-ChildItem` не получает скрытые элементы по умолчанию. Чтобы получить скрытые элементы, используйте параметр **Force** .
- `Get-ChildItem`Командлет предназначен для работы с данными, предоставляемыми любым поставщиком. Чтобы вывести список поставщиков, доступных в данном сеансе, введите командлет `Get-PSProvider`.
  Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).

## Связанные ссылки

[about_Certificate_Provider](../Microsoft.PowerShell.Security/About/about_Certificate_Provider.md)

[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)

[about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)

[about_Registry_Provider](../Microsoft.PowerShell.Core/About/about_Registry_Provider.md)

[ForEach-Object](../Microsoft.PowerShell.Core/ForEach-Object.md)

[Get-Alias](../Microsoft.PowerShell.Utility/Get-Alias.md)

[Get-Item](Get-Item.md)

[Get-Location](Get-Location.md)

[Get-Process](Get-Process.md)

[Get-PSProvider](Get-PSProvider.md)

[Split-Path](Split-Path.md)
