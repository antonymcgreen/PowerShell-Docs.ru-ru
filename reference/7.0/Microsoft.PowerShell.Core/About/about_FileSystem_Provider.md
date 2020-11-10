---
description: FileSystem
keywords: powershell,командлет
Locale: en-US
ms.date: 06/18/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_filesystem_provider?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Поставщик FileSystem
ms.openlocfilehash: fad55a7fb7651dbb006e1765c513bf2546a73891
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2020
ms.locfileid: "94390836"
---
# <a name="filesystem-provider"></a>Поставщик FileSystem

## <a name="provider-name"></a>Имя поставщика

FileSystem

## <a name="drives"></a>Диски

`C:`, `D:` ...

## <a name="capabilities"></a>Возможности

**Filter** , **ShouldProcess**

## <a name="short-description"></a>Краткое описание

Предоставляет доступ к файлам и каталогам.

## <a name="detailed-description"></a>Подробное описание

Поставщик **файловой** системы PowerShell позволяет получать, добавлять, изменять, очищать и удалять файлы и каталоги в PowerShell.

Диски **файловой** системы — это иерархическое пространство имен, содержащее каталоги и файлы на компьютере. Диск **файловой** системы может быть логическим или физических диском, каталогом или сопоставленной сетевой папкой.

Диск с именем `TEMP:` будет сопоставлен с путем к временному каталогу пользователя.

>[!NOTE]
> Содержимое на диске TEMP: не удаляется автоматически с помощью PowerShell и не может управляться пользователем или операционной системой.

Поставщик **FileSystem** поддерживает следующие командлеты, описанные в этой статье.

- [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location)
- [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location)
- [Get-Item](xref:Microsoft.PowerShell.Management.Get-Item)
- [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem)
- [Invoke-Item](xref:Microsoft.PowerShell.Management.Invoke-Item)
- [Move-Item](xref:Microsoft.PowerShell.Management.Move-Item)
- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)
- [Remove-Item](xref:Microsoft.PowerShell.Management.Remove-Item)
- [Get-ItemProperty](xref:Microsoft.PowerShell.Management.Get-ItemProperty)
- [Set-ItemProperty](xref:Microsoft.PowerShell.Management.Set-ItemProperty)
- [Clear-Item](xref:Microsoft.PowerShell.Management.Clear-Item)
- [Clear-ItemProperty](xref:Microsoft.PowerShell.Management.Clear-ItemProperty)
- [Remove-Item](xref:Microsoft.PowerShell.Management.Remove-Item)
- [Remove-ItemProperty](xref:Microsoft.PowerShell.Management.Remove-ItemProperty)
- [Get-Acl](xref:Microsoft.PowerShell.Security.Get-Acl)
- [Set-Acl](xref:Microsoft.PowerShell.Security.Set-Acl)
- [Get-AuthenticodeSignature](xref:Microsoft.PowerShell.Security.Get-AuthenticodeSignature)
- [Set-AuthenticodeSignature](xref:Microsoft.PowerShell.Security.Set-AuthenticodeSignature)

## <a name="types-exposed-by-this-provider"></a>Типы, предоставляемые этим поставщиком

Файлы являются экземплярами класса [System. IO. FileInfo](/dotnet/api/system.io.fileinfo) .  Каталоги являются экземплярами класса [System. IO. DirectoryInfo](/dotnet/api/system.io.directoryinfo) .

## <a name="navigating-the-filesystem-drives"></a>Навигация по дискам файловой системы

Поставщик **FileSystem** предоставляет свои хранилища данных путем сопоставления логических дисков на компьютере с дисками PowerShell. Для работы с диском **файловой** системы можно изменить расположение на диск, выдающие имя диска, за которым следует двоеточие ( `:` ).

```powershell
Set-Location C:
```

Вы также можете работать с поставщиком **FileSystem** с любого другого диска PowerShell. Чтобы сослаться на файл или каталог из другого расположения, используйте имя диска ( `C:` , `D:` ,...) в пути.

> [!NOTE]
> PowerShell использует Псевдонимы для предоставления привычного способа работы с путями поставщика. Команды, такие как `dir` и `ls` , теперь являются псевдонимами для [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem), `cd` являются псевдонимом для [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location). и `pwd` — это псевдоним для [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location).

## <a name="getting-files-and-directories"></a>Получение файлов и каталогов

`Get-ChildItem`Командлет возвращает все файлы и каталоги в текущем расположении. Можно указать другой путь для поиска и использовать встроенные параметры для фильтрации и управления глубиной рекурсии.

```powershell
Get-ChildItem
```

Дополнительные сведения об использовании командлетов см. в статье [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem).

## <a name="copying-files-and-directories"></a>Копирование файлов и каталогов

`Copy-Item`Командлет копирует файлы и каталоги в указанное расположение.
Параметры можно использовать для фильтрации и рекурсии, аналогично `Get-ChildItem` .

Следующая команда копирует все файлы и каталоги по пути "C:\temp" \" в папку "Папка c:\Windows\Temp".

```powershell
Copy-Item -Path C:\temp\* -Destination C:\Windows\Temp -Recurse -File
```

`Copy-Item` перезаписывает файлы в целевом каталоге без запроса подтверждения.

Эта команда копирует `a.txt` файл из `C:\a` каталога в `C:\a\bb` каталог.

```powershell
Copy-Item -Path C:\a\a.txt -Destination C:\a\bb\a.txt
```

Копирует все каталоги и файлы из каталога в `C:\a` `C:\c` каталог. Если какие-либо копируемые каталоги уже существуют в целевом каталоге, то команда завершится с ошибкой, если не указан параметр Force.

```powershell
Copy-Item -Path C:\a\* -Destination C:\c -Recurse
```

Дополнительные сведения см. в разделе [Copy-Item](xref:Microsoft.PowerShell.Management.Copy-Item).

## <a name="moving-files-and-directories"></a>Перемещение файлов и каталогов

Эта команда перемещает `c.txt` файл в `C:\a` каталог в `C:\a\aa` Каталог:

```powershell
Move-Item -Path C:\a\c.txt -Destination C:\a\aa
```

Команда не перезапишет автоматически существующий файл с тем же именем. Для принудительной перезаписи существующего файла необходимо задать параметр Force.

Нельзя перемещать каталог, если он совпадает с текущим местоположением. При использовании `Move-Item` для перемещения каталога в текущем расположении отображается эта ошибка.

```
C:\temp> Move-Item -Path C:\temp\ -Destination C:\Windows\Temp

Move-Item : Cannot move item because the item at 'C:\temp\' is in use.
At line:1 char:1
+ Move-Item C:\temp\ C:\temp2\
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) [Move-Item], PSInvalidOperationException
    + FullyQualifiedErrorId : InvalidOperation,Microsoft.PowerShell.Commands.MoveItemCommand
```

## <a name="managing-file-content"></a>Управление содержимым файлов

### <a name="get-the-content-of-a-file"></a>Получение содержимого файла

Эта команда возвращает содержимое файла "Test.txt" и отображает их в консоли.

```powershell
Get-Content -Path Test.txt
```

Содержимое файла можно передать другому командлету по конвейеру. Например, следующая команда считывает содержимое `Test.txt` файла и затем передает его в качестве входных данных командлету [ConvertTo-HTML](xref:Microsoft.PowerShell.Utility.ConvertTo-Html) :

```powershell
Get-Content -Path Test.txt | ConvertTo-Html
```

Можно также получить содержимое файла, указав в качестве пути к нему знак доллара ( `$` ). Путь должен быть заключен в фигурные скобки из-за ограничений именования переменных. Дополнительные сведения см. в разделе [about_Variables](about_Variables.md).

```powershell
${C:\Windows\System32\Drivers\etc\hosts}
```

### <a name="add-content-to-a-file"></a>Добавление содержимого в файл

Эта команда добавляет строку "тестовое содержимое" в `Test.txt` файл:

```powershell
Add-Content -Path test.txt -Value "test content"
```

Существующее содержимое в `Test.txt` файле не удаляется.

### <a name="replace-the-content-of-a-file"></a>Замена содержимого файла

Эта команда заменяет содержимое `Test.txt` файла строкой "Test Content":

```powershell
Set-Content -Path test.txt -Value "test content"
```

Он перезаписывает содержимое `Test.txt` . Можно использовать параметр **value** командлета [New-Item](xref:Microsoft.PowerShell.Management.New-Item) , чтобы добавить содержимое в файл при его создании.

### <a name="loop-through-the-contents-of-a-file"></a>Перебрать содержимое файла

По умолчанию `Get-Content` командлет использует символ конца строки в качестве разделителя, поэтому он получает файл в виде коллекции строк, каждая из которых имеет одну строку в файле.

С помощью параметра можно `-Delimiter` указать альтернативный разделитель. Если в качестве его значения будут заданы символы, обозначающие конец раздела или начало следующего раздела, файл можно будет разделить на логические части.

Первая команда получает `Employees.txt` файл и разделяет его на разделы, каждый из которых заканчивается словами "конец записи о сотруднике", и сохраняет его в `$e` переменной.

Вторая команда использует нотацию массива для получения первого элемента в коллекции в `$e` . Он использует индекс 0, так как массивы PowerShell отсчитываются от нуля.

Дополнительные сведения о `Get-Content` командлете см. в разделе справки по разделу [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content).

Дополнительные сведения о массивах см. в разделе [about_Arrays](../About/about_Arrays.md).

```powershell
$e = Get-Content c:\test\employees.txt -Delimited "End Of Employee Record"
$e[0]
```

## <a name="managing-security-descriptors"></a>Управление дескрипторами безопасности

### <a name="view-the-acl-for-a-file"></a>Просмотр списка ACL для файла

Эта команда возвращает объект [System. Security. AccessControl. FileSecurity](/dotnet/api/system.security.accesscontrol.filesecurity) :

```powershell
Get-Acl -Path test.txt | Format-List -Property *
```

Чтобы получить дополнительные сведения об этом объекте, передайте команду в командлет [Get-Member](xref:Microsoft.PowerShell.Utility.Get-Member) по конвейеру. Или см. раздел класс [FileSecurity](/dotnet/api/system.security.accesscontrol.filesecurity) .

### <a name="modify-the-acl-for-a-file"></a>Изменение ACL для файла

### <a name="create-and-set-an-acl-for-a-file"></a>Создание и задание списка управления доступом для файла

## <a name="creating-files-and-directories"></a>Создание файлов и каталогов

### <a name="create-a-directory"></a>Создание каталога

Эта команда создает `logfiles` каталог на `C` диске:

```powershell
New-Item -Path c:\ -Name logfiles -Type directory
```

PowerShell также включает `mkdir` функцию (псевдоним `md` ), которая использует командлет [New-Item](xref:Microsoft.PowerShell.Management.New-Item) для создания нового каталога.

### <a name="create-a-file"></a>Создание файла

Эта команда создает `log2.txt` файл в `C:\logfiles` каталоге, а затем добавляет в файл строку "Журнал теста":

```powershell
New-Item -Path c:\logfiles -Name log2.txt -Type file
```

### <a name="create-a-file-with-content"></a>Создание файла с содержимым

Создает файл с именем `log2.txt` в `C:\logfiles` каталоге и добавляет в файл строку "тестовый журнал".

```powershell
New-Item -Path c:\logfiles -Name log2.txt -Type file -Value "test log"
```

## <a name="renaming-files-and-directories"></a>Переименование файлов и каталогов

### <a name="rename-a-file"></a>Переименование файла

Эта команда переименовывает `a.txt` файл в `C:\a` каталоге `b.txt` следующим образом:

```powershell
Rename-Item -Path c:\a\a.txt -NewName b.txt
```

### <a name="rename-a-directory"></a>Переименование каталога

Эта команда переименовывает `C:\a\cc` каталог в `C:\a\dd` :

```powershell
Rename-Item -Path c:\a\cc -NewName dd
```

## <a name="deleting-files-and-directories"></a>Удаление файлов и каталогов

### <a name="delete-a-file"></a>Удаление файла

Эта команда удаляет `Test.txt` файл в текущем каталоге:

```powershell
Remove-Item -Path test.txt
```

### <a name="delete-files-using-wildcards"></a>Удаление файлов с помощью подстановочных знаков

Эта команда удаляет все файлы в текущем каталоге с `.xml` расширением имени файла:

```powershell
Remove-Item -Path *.xml
```

## <a name="starting-a-program-by-invoking-an-associated-file"></a>Запуск программы путем вызова связанного файла

### <a name="invoke-a-file"></a>Вызов файла

Первая команда использует командлет [Get-Service](xref:Microsoft.PowerShell.Management.Get-Service) для получения сведений о локальных службах.

Он передает сведения в командлет [Export-CSV](xref:Microsoft.PowerShell.Utility.Export-Csv) , а затем сохраняет эти сведения в `Services.csv` файле.

Вторая команда использует [Invoke-Item](xref:Microsoft.PowerShell.Management.Invoke-Item) для открытия `services.csv` файла в программе, связанной с `.csv` расширением:

```powershell
Get-Service | Export-Csv -Path services.csv
Invoke-Item -Path services.csv
```

## <a name="getting-files-and-folders-with-specified-attributes"></a>Получение файлов и папок с указанными атрибутами

### <a name="get-system-files"></a>Получение системных файлов

Эта команда возвращает системные файлы в текущем каталоге и его подкаталогах.

Он использует `-File` параметр для получения только файлов (не каталогов) и `-System` параметр для получения только элементов с атрибутом System.

Он использует `-Recurse` параметр для получения элементов в текущем каталоге и всех подкаталогах.

```powershell
Get-ChildItem -File -System -Recurse
```

### <a name="get-hidden-files"></a>Получение скрытых файлов

Эта команда возвращает все файлы, включая скрытые файлы, в текущем каталоге.

В нем используется параметр **Attributes** с двумя значениями, `!Directory+Hidden` , который получает скрытые файлы, и `!Directory` , который получает все остальные файлы.

```powershell
Get-ChildItem -Attributes !Directory,!Directory+Hidden
```

`dir -att !d,!d+h` эквивалентна этой команде.

### <a name="get-compressed-and-encrypted-files"></a>Получение сжатых и зашифрованных файлов

Эта команда возвращает файлы в текущем каталоге, которые сжаты или зашифрованы.

Он использует `-Attributes` параметр с двумя значениями `Compressed` и `Encrypted` . Значения разделяются запятой, `,` которая представляет оператор "или".

```powershell
Get-ChildItem -Attributes Compressed,Encrypted
```

## <a name="dynamic-parameters"></a>Динамические параметры

Динамические параметры — это параметры командлета, которые добавляются поставщиком PowerShell и доступны только при использовании командлета на диске с поддержкой поставщика.

### <a name="encoding-microsoftpowershellcommandsfilesystemcmdletproviderencoding"></a>Encoding \<Microsoft.PowerShell.Commands.FileSystemCmdletProviderEncoding\>

Указывает кодировку файла. Значение по умолчанию — ASCII.

- **ASCII** : использует кодировку для набора символов ASCII (7-разрядных).
- **BigEndianUnicode** : кодирует в формате UTF-16 с обратным порядком байтов.
- **Строка** : использует тип кодировки для строки.
- **Юникод** : кодирует в формате UTF-16 с прямым порядком байтов.
- **UTF7** : кодирует в формате UTF-7.
- **UTF8** : кодирует в формате UTF-8.
- **UTF8BOM** : кодирует в формате UTF-8 с меткой порядка БАЙТОВ (BOM)
- **UF8NOBOM** : кодирует в формате UTF-8 без метки порядка БАЙТОВ (BOM)
- **UTF32** : кодирует в формате UTF-32.
- **По умолчанию** : кодируется на странице установленного по умолчанию кода.
- **OEM** : использует кодировку по умолчанию для программ MS-DOS и консолей.
- **Неизвестно** : неизвестный или недопустимый тип кодировки. Данные можно обрабатывать как двоичные.

#### <a name="cmdlets-supported"></a>Поддерживаемые командлеты

- [Add-Content](xref:Microsoft.PowerShell.Management.Add-Content)
- [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content)
- [Set-Content](xref:Microsoft.PowerShell.Management.Set-Content)

### <a name="delimiter-systemstring"></a>Delimiter \<System.String\>

Указывает разделитель, используемый командлетом [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) для разделения файла на объекты при чтении.

Значение по умолчанию — `\n` , символ конца строки.

При чтении текстового файла командлет [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) Возвращает коллекцию строковых объектов, каждая из которых заканчивается символом-разделителем.

При вводе разделителя, который не существует в файле, командлет [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) возвращает весь файл как один объект без разделителей.

Этот параметр можно использовать для разбиения большого файла на меньшие файлы, указав разделитель файла, например "Конец примера", в качестве разделителя. Разделитель сохраняется (не удаляется) и становится последним элементом в каждом разделе файла.

> [!NOTE]
> В настоящее время, если значение `-Delimiter` параметра является пустой строкой, командлет [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) не возвращает ничего.
> Это известная проблема Чтобы принудительно применить командлет [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) для возврата всего файла в виде единой неразделенной строки, введите значение, которое не существует в файле.

#### <a name="cmdlets-supported"></a>Поддерживаемые командлеты

- [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content)

### <a name="wait-systemmanagementautomationswitchparameter"></a>Wait \<System.Management.Automation.SwitchParameter\>

Ожидает содержимое для добавления в файл. Если содержимое добавлено, возвращает добавленное содержимое. Если содержимое не изменилось, возвращает весь файл.

Во время ожидания командлет [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) проверяет файл раз в секунду, пока не будет прерван, например, нажатием сочетания клавиш CTRL+C.

#### <a name="cmdlets-supported"></a>Поддерживаемые командлеты

- [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content)

### <a name="attributes-flagsexpression"></a>Attributes \<FlagsExpression\>

Извлекает файлы и папки с указанными атрибутами. Этот параметр поддерживает все атрибуты и позволяет указывать сложные сочетания атрибутов.

`-Attributes`Параметр был представлен в Windows PowerShell 3,0.

`-Attributes`Параметр поддерживает следующие атрибуты:

- **Архив**
- **Compressed**
- **Устройство**
- **Каталоги**
- **Зашифрована**
- **Скрыта**
- **Обычный**
- **нотконтентиндексед**
- **Работа**
- **ReadOnly**
- **репарсепоинт**
- **спарсефиле**
- **Системные функции**
- **Временные процедуры**

Описание этих атрибутов см. в описании перечисления [FileAttributes](/dotnet/api/system.io.fileattributes) .

Используйте следующие операторы для объединения атрибутов.

- `!` — НЕ
- `+` -И
- `,` — ИЛИ

Пробелы между оператором и его атрибутами не допускаются. Однако допустима постановка пробелов перед запятыми.

#### <a name="cmdlets-supported"></a>Поддерживаемые командлеты

- [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem)

### <a name="directory-systemmanagementautomationswitchparameter"></a>Directory \<System.Management.Automation.SwitchParameter\>

Извлекает каталоги (папки).

`-Directory`Параметр был представлен в Windows PowerShell 3,0.

Чтобы получить только каталоги, используйте `-Directory` параметр и опустите `-File` параметр. Чтобы исключить каталоги, используйте `-File` параметр и опустите `-Directory` параметр, либо используйте `-Attributes` параметр.

#### <a name="cmdlets-supported"></a>Поддерживаемые командлеты

- [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem)

### <a name="file-systemmanagementautomationswitchparameter"></a>File \<System.Management.Automation.SwitchParameter\>

Извлекает файлы.

`-File`Параметр был представлен в Windows PowerShell 3,0.

Чтобы получить только файлы, используйте `-File` параметр и опустите `-Directory` параметр. Чтобы исключить файлы, используйте `-Directory` параметр и опустите `-File` параметр, либо используйте `-Attributes` параметр.

#### <a name="cmdlets-supported"></a>Поддерживаемые командлеты

- [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem)

### <a name="hidden-systemmanagementautomationswitchparameter"></a>Hidden \<System.Management.Automation.SwitchParameter\>

Возвращает только скрытые файлы или каталоги (папки). По умолчанию командлет [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem) получает только нескрытые элементы.

`-Hidden`Параметр был представлен в Windows PowerShell 3,0.

Чтобы получить только скрытые элементы, используйте `-Hidden` параметр, его `h` `ah` псевдонимы или **скрытое** значение `-Attributes` параметра. Чтобы исключить скрытые элементы, опустите `-Hidden` параметр или используйте `-Attributes` параметр.

#### <a name="cmdlets-supported"></a>Поддерживаемые командлеты

- [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem)

### <a name="readonly-systemmanagementautomationswitchparameter"></a>ReadOnly \<System.Management.Automation.SwitchParameter\>

Извлекает только файлы или каталоги (папки), доступные для чтения.

`-ReadOnly`Параметр был представлен в Windows PowerShell 3,0.

Чтобы получить только элементы, доступные только для чтения, используйте `-ReadOnly` параметр, его `ar` псевдоним или значение **ReadOnly** `-Attributes` параметра. Чтобы исключить элементы, предназначенные только для чтения, используйте `-Attributes` параметр.

#### <a name="cmdlets-supported"></a>Поддерживаемые командлеты

- [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem)

### <a name="system-systemmanagementautomationswitchparameter"></a>System \<System.Management.Automation.SwitchParameter\>

Извлекает только системные файлы или каталоги (папки).

`-System`Параметр был представлен в Windows PowerShell 3,0.

Чтобы получить только системные файлы и папки, используйте `-System` параметр, его `as` псевдоним или **системное** значение `-Attributes` параметра. Чтобы исключить системные файлы и папки, используйте `-Attributes` параметр.

#### <a name="cmdlets-supported"></a>Поддерживаемые командлеты

- [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem)

### <a name="newerthan-systemdatetime"></a>NewerThan \<System.DateTime\>

Возвращает `$True` , если `LastWriteTime` значение файла больше указанной даты. В противном случае она возвращает `$False`.

Введите объект [DateTime](/dotnet/api/system.datetime) , например, возвращаемый командлетом [Get-Date](xref:Microsoft.PowerShell.Utility.Get-Date) , или строку, которую можно преобразовать в объект [DateTime](/dotnet/api/system.datetime) , например `"August 10, 2011 2:00 PM"` .

#### <a name="cmdlets-supported"></a>Поддерживаемые командлеты

- [Test-Path](xref:Microsoft.PowerShell.Management.Test-Path)

### <a name="olderthan-systemdatetime"></a>OlderThan \<System.DateTime\>

Возвращает `$True` , если `LastWriteTime` значение файла меньше указанной даты. В противном случае она возвращает `$False`.

Введите объект [DateTime](/dotnet/api/system.datetime) , например, возвращаемый командлетом [Get-Date](xref:Microsoft.PowerShell.Utility.Get-Date) , или строку, которую можно преобразовать в объект [DateTime](/dotnet/api/system.datetime) , например `"August 10, 2011 2:00 PM"` .

#### <a name="cmdlets-supported"></a>Поддерживаемые командлеты

- [Test-Path](xref:Microsoft.PowerShell.Management.Test-Path)

### <a name="stream-systemstring"></a>Stream \<System.String\>

Управляет альтернативными потоками данных. Введите имя потока. Подстановочные знаки разрешены только в командах [Get-Item](xref:Microsoft.PowerShell.Management.Get-Item) для и [Remove-Item](xref:Microsoft.PowerShell.Management.Remove-Item) на диске файловой системы.

#### <a name="cmdlets-supported"></a>Поддерживаемые командлеты

- [Add-Content](xref:Microsoft.PowerShell.Management.Add-Content)
- [Clear-Content](xref:Microsoft.PowerShell.Management.Clear-Content)
- [Get-Item](xref:Microsoft.PowerShell.Management.Get-Item)
- [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content)
- [Remove-Item](xref:Microsoft.PowerShell.Management.Remove-Item)
- [Set-Content](xref:Microsoft.PowerShell.Management.Set-Content)

### <a name="raw-switchparameter"></a>Raw \<SwitchParameter\>

Игнорирует символы новой строки. Возвращает содержимое в виде одного элемента.

#### <a name="cmdlets-supported"></a>Поддерживаемые командлеты

- [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content)

### <a name="itemtype-string"></a>ItemType \<String\>

Этот параметр позволяет указать те элемента для создания `New-Item`

Доступные значения этого параметра зависят от текущего используемого поставщика.

В `FileSystem` диске допустимы следующие значения:

- Файл
- Каталог
- SymbolicLink
- Соединение
- HardLink

### <a name="cmdlets-supported"></a>Поддерживаемые командлеты

- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)

## <a name="using-the-pipeline"></a>Использование конвейера

Командлеты поставщика принимают входные данные конвейера. Вы можете использовать конвейер для упрощения задачи, отправив данные поставщика из одного командлета другому командлету поставщика.
Дополнительные сведения об использовании конвейера с командлетами поставщика см. в справочнике по командлетам, приведенным в этой статье.

## <a name="getting-help"></a>Получение справки

Начиная с Windows PowerShell 3.0, стали доступны настраиваемые разделы справки по командлетам поставщика, в которых объясняется поведение этих командлетов на диске файловой системы.

Чтобы получить разделы справки, настроенные для диска файловой системы, выполните команду [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) на диске файловой системы или используйте параметр командлета `-Path` [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) , чтобы указать диск файловой системы.

```powershell
Get-Help Get-ChildItem
```

```powershell
Get-Help Get-ChildItem -Path c:
```

## <a name="see-also"></a>См. также

[about_Providers](../About/about_Providers.md)
