---
ms.date: 12/31/2019
keywords: powershell,командлет
title: Объект ISEFileCollection
ms.openlocfilehash: 4192afa9dc91d9ea4c4c084d3ba0175483620229
ms.sourcegitcommit: 058a6e86eac1b27ca57a11687019df98709ed709
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "75736221"
---
# <a name="the-isefilecollection-object"></a>Объект ISEFileCollection

Объект **ISEFileCollection**  — это коллекция объектов **ISEFile**. Примером является коллекция `$psISE.CurrentPowerShellTab.Files`.

## <a name="methods"></a>Методы

### <a name="add-fullpath-"></a>Add\( \[FullPath\] \)

Поддерживается в интегрированной среде сценариев Windows PowerShell 2.0 и более поздних версий.

Создает и возвращает новый файл без имени и добавляет его в коллекцию. Свойство **IsUntitled** созданного файла имеет значение `$true`.

**\[FullPath\]**  — необязательная строка. Полный путь к файлу. Исключение возникает, если включен параметр **FullPath** и относительный путь или если вместо полного пути используется имя файла.

```powershell
# Adds a new untitled file to the collection of files in the current PowerShell tab.
$newFile = $psISE.CurrentPowerShellTab.Files.Add()

# Adds a file specified by its full path to the collection of files in the current PowerShell tab.
$psISE.CurrentPowerShellTab.Files.Add("$pshome\Examples\profile.ps1")
```

### <a name="remove-file-force-"></a>Remove\( File, \[Force\] \)

Поддерживается в интегрированной среде сценариев Windows PowerShell 2.0 и более поздних версий.

Удаляет указанный файл из текущей вкладки PowerShell.

**File** — строка. Файл ISEFile, удаляемый из коллекции. Если файл не был сохранен, этот метод создает исключение. Используйте параметр **Force** для принудительного удаления несохраненного файла.

**\[Force\]**  — необязательное логическое значение. Если задано значение `$true`, предоставляет разрешение на удаление файла, даже если он не был сохранен с момента последнего использования. Значение по умолчанию — `$false`.

```powershell
# Removes the first opened file from the file collection associated with the current PowerShell tab.
# If the file has not yet been saved, then an exception is generated.
$firstfile = $psISE.CurrentPowerShellTab.Files[0]
$psISE.CurrentPowerShellTab.Files.Remove($firstfile)

# Removes the first opened file from the file collection associated with the current PowerShell tab, even if it has not been saved.
$firstfile = $psISE.CurrentPowerShellTab.Files[0]
$psISE.CurrentPowerShellTab.Files.Remove($firstfile, $true)
```

### <a name="setselectedfile-selectedfile-"></a>SetSelectedFile\( selectedFile \)

Поддерживается в интегрированной среде сценариев Windows PowerShell 2.0 и более поздних версий.

Выбирает файл, который задается параметром **SelectedFile**.

**SelectedFile** — Microsoft.PowerShell.Host.ISE.ISEFile. Выбираемый файл ISEFile.

```powershell
# Selects the specified file.
$firstfile = $psISE.CurrentPowerShellTab.Files[0]
$psISE.CurrentPowerShellTab.Files.SetSelectedFile($firstfile)
```

## <a name="see-also"></a>См. также:

- [Объект ISEFile](The-ISEFile-Object.md)
- [Назначение объектной модели скриптов интегрированной среды скриптов Windows PowerShell](Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [Иерархия объектной модели интегрированной среды скриптов](The-ISE-Object-Model-Hierarchy.md)
