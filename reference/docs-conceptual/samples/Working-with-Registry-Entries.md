---
ms.date: 06/05/2017
keywords: powershell,командлет
title: Работа с записями реестра
ms.assetid: fd254570-27ac-4cc9-81d4-011afd29b7dc
ms.openlocfilehash: 8483b6f98739697b24a13055dfffbc7b5bacc2cc
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "55681544"
---
# <a name="working-with-registry-entries"></a>Работа с записями реестра

Так как записи реестра являются свойствами разделов и их невозможно открыть напрямую, при работе с ними необходимо использовать немного другой подход.

### <a name="listing-registry-entries"></a>Создание списков записей реестра

Существует несколько способов просмотра реестра. Самый простой — получить имена свойств, связанные с разделом. Например, чтобы увидеть имена записей в разделе реестра `HKEY_LOCAL_MACHINE\Software\Microsoft\Windows\CurrentVersion`, используйте `Get-Item`. Разделы реестра содержат свойство с универсальным именем Property, которое является списком записей реестра в разделе.
Следующая команда выбирает свойство Property и расширяет элементы так, чтобы они отображались в списке:

```powershell
Get-Item -Path Registry::HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion |
  Select-Object -ExpandProperty Property
```

```Output
DevicePath
MediaPathUnexpanded
ProgramFilesDir
CommonFilesDir
ProductId
```

Чтобы просмотреть записи реестра в более удобочитаемой форме, используйте `Get-ItemProperty`:

```powershell
Get-ItemProperty -Path Registry::HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion
```

```Output
PSPath              : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\SO
                      FTWARE\Microsoft\Windows\CurrentVersion
PSParentPath        : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\SO
                      FTWARE\Microsoft\Windows
PSChildName         : CurrentVersion
PSDrive             : HKLM
PSProvider          : Microsoft.PowerShell.Core\Registry
DevicePath          : C:\WINDOWS\inf
MediaPathUnexpanded : C:\WINDOWS\Media
ProgramFilesDir     : C:\Program Files
CommonFilesDir      : C:\Program Files\Common Files
ProductId           : 76487-338-1167776-22465
WallPaperDir        : C:\WINDOWS\Web\Wallpaper
MediaPath           : C:\WINDOWS\Media
ProgramFilesPath    : C:\Program Files
PF_AccessoriesName  : Accessories
(default)           :
```

Все свойства Windows PowerShell раздела имеют префиксы PS, например **PSPath**, **PSParentPath**, **PSChildName** и **PSProvider**.

Для ссылки на текущее расположение можно использовать нотацию "`*.*`.". Можно использовать `Set-Location` менять **CurrentVersion** контейнер реестра первого:

```powershell
Set-Location -Path Registry::HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion
```

Кроме того, можно использовать встроенный диск HKLM PSDrive с `Set-Location`:

```powershell
Set-Location -Path hklm:\SOFTWARE\Microsoft\Windows\CurrentVersion
```

Затем можно использовать нотацию "`*.*`." для текущего расположения, чтобы перечислить свойства без указания полного пути:

```powershell
Get-ItemProperty -Path .
```

```Output
...
DevicePath          : C:\WINDOWS\inf
MediaPathUnexpanded : C:\WINDOWS\Media
ProgramFilesDir     : C:\Program Files
...
```

Расширение пути работает так же, как и в файловой системе, поэтому в этом расположении можно получить **ItemProperty** листинг для `HKLM:\SOFTWARE\Microsoft\Windows\Help` с помощью `Get-ItemProperty -Path ..\Help`.

### <a name="getting-a-single-registry-entry"></a>Получение одной записи реестра

Если необходимо получить конкретную запись в разделе реестра, можно использовать один из нескольких возможных подходов. Этот пример находит значение **DevicePath** в `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion`.

С помощью `Get-ItemProperty`, использовать **путь** параметр для указания имени ключа и **имя** параметр, чтобы указать имя **DevicePath** запись.

```powershell
Get-ItemProperty -Path HKLM:\Software\Microsoft\Windows\CurrentVersion -Name DevicePath
```

```Output
PSPath       : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\Software\
               Microsoft\Windows\CurrentVersion
PSParentPath : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\Software\
               Microsoft\Windows
PSChildName  : CurrentVersion
PSDrive      : HKLM
PSProvider   : Microsoft.PowerShell.Core\Registry
DevicePath   : C:\WINDOWS\inf
```

Эта команда возвращает стандартные свойства Windows PowerShell, а также свойство **DevicePath**.

> [!NOTE]
> Несмотря на то что `Get-ItemProperty` имеет **фильтра**, **Include**, и **исключить** параметры, они не может использоваться для фильтрации по имени свойства. Эти параметры относятся к разделам реестра, пути к элементам и не к записям реестра. Записи реестра, которые являются свойствами элемента.

Другой вариант — использовать средство командной строки Reg.exe. Для получения справки по reg.exe введите `reg.exe /?` в командной строке. Чтобы найти запись DevicePath, используйте reg.exe, как показано в следующей команде:

```powershell
reg query HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion /v DevicePath
```

```Output
! REG.EXE VERSION 3.0

HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion
    DevicePath  REG_EXPAND_SZ   %SystemRoot%\inf
```

Также можно использовать объект **WshShell COM**, чтобы найти некоторые записи реестра, хотя этот метод не работает с большими двоичными данными или именами записей реестра, включающими такие символы, как "\\". Добавьте имя свойства с разделителем "\\" в путь элемента:

```powershell
(New-Object -ComObject WScript.Shell).RegRead("HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\DevicePath")
```

```Output
%SystemRoot%\inf
```

### <a name="setting-a-single-registry-entry"></a>Настройка одной записи реестра

Если вы хотите изменить определенную запись в раздел реестра, можно использовать один из нескольких возможных подходов. В этом примере изменяется **путь** запись в разделе `HKEY_CURRENT_USER\Environment`. **Путь** запись указывает место для поиска исполняемых файлов.

1. Получить текущее значение **путь** с использованием `Get-ItemProperty`.
2. Добавить новое значение, отделив его с `;`.
3. Используйте `Set-ItemProperty` с указанным ключом, именем записи и значение, чтобы изменить запись в реестр.

```powershell
$value = Get-ItemProperty -Path HKCU:\Environment -Name Path
$newpath = $value.Path += ";C:\src\bin\"
Set-ItemProperty -Path HKCU:\Environment -Name Path -Value $newpath
```

> [!NOTE]
> Несмотря на то что `Set-ItemProperty` имеет **фильтра**, **Include**, и **исключить** параметры, они не может использоваться для фильтрации по имени свойства. Эти параметры относятся в разделам реестра (путям элементов), а не к записям реестра (свойствам элементов).

Другой вариант — использовать средство командной строки Reg.exe. Для получения справки по reg.exe введите **reg.exe /?**.
в командной строке.

В следующем примере изменяется **путь** записи путем удаления пути, добавленные в приведенном выше примере.
`Get-ItemProperty` по-прежнему используется для получения текущего значения, чтобы избежать необходимости анализировать строки, возвращаемой `reg query`. **Подстроки** и **LastIndexOf** методы используются для получения добавляемый путь последнего **путь** запись.

```powershell
$value = Get-ItemProperty -Path HKCU:\Environment -Name Path
$newpath = $value.Path.SubString(0, $value.Path.LastIndexOf(';'))
reg add HKCU\Environment /v Path /d $newpath /f
```

```Output
The operation completed successfully.
```

### <a name="creating-new-registry-entries"></a>Создание новых записей реестра

Чтобы добавить новую запись с именем «PowerShellPath» **CurrentVersion** использования ключей, `New-ItemProperty` с путем к разделу, именем записи и значение записи. В этом примере использовано значение переменной Windows PowerShell `$PSHome`, которой хранится путь к каталогу установки для Windows PowerShell.

Вы можете добавить новую запись в раздел с помощью следующей команды, и команда также вернет сведения о новой записи:

```powershell
New-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion -Name PowerShellPath -PropertyType String -Value $PSHome
```

```Output
PSPath         : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion
PSParentPath   : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows
PSChildName    : CurrentVersion
PSDrive        : HKLM
PSProvider     : Microsoft.PowerShell.Core\Registry
PowerShellPath : C:\Program Files\Windows PowerShell\v1.0
```

Значение **PropertyType** должно быть именем элемента перечисления **Microsoft.Win32.RegistryValueKind** из следующей таблицы:

|Значение PropertyType|Значение|
|----------------------|-----------|
|Двоичные данные|Двоичные данные|
|DWord|Число, которое является допустимым UInt32|
|ExpandString|Строка, которая может содержать динамически раскрывающиеся переменные среды|
|MultiString|Многострочная строка|
|Строка|Любое строковое значение|
|QWord|8 байтов двоичных данных|

> [!NOTE]
> Запись реестра можно добавить в несколько расположений, указав массив значений для параметра **Path**:

```powershell
New-ItemProperty -Name PowerShellPath -PropertyType String -Value $PSHome `
  -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion, HKCU:\SOFTWARE\Microsoft\Windows\CurrentVersion
```

Кроме того, можно перезаписать существующие значение записи реестра, добавив **Force** параметра к любому `New-ItemProperty` команды.

### <a name="renaming-registry-entries"></a>Переименование записей реестра

Чтобы переименовать **PowerShellPath** записи в «PSHome», используйте `Rename-ItemProperty`:

```powershell
Rename-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion -Name PowerShellPath -NewName PSHome
```

Чтобы отобразить переименованное значение, добавьте параметр **PassThru** в команду.

```powershell
Rename-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion -Name PowerShellPath -NewName PSHome -passthru
```

### <a name="deleting-registry-entries"></a>Удаление записей реестра

Чтобы удалить записи реестра PSHome и PowerShellPath, используйте `Remove-ItemProperty`:

```powershell
Remove-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion -Name PSHome
Remove-ItemProperty -Path HKCU:\SOFTWARE\Microsoft\Windows\CurrentVersion -Name PowerShellPath
```
