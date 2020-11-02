---
ms.date: 12/31/2019
title: Объект ISESnippetCollection
description: Объект ISESnippetCollection — это коллекция объектов ISESnippet. Коллекция файлов, с которой связан объект PowerShellTab, является членом этого класса.
ms.openlocfilehash: e6170ddf72d5ead840aa3015d4de1dcb21dbfeff
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92655970"
---
# <a name="the-isesnippetcollection-object"></a>Объект ISESnippetCollection

Объект **ISESnippetCollection**  — это коллекция объектов **ISESnippet** . Коллекция файлов, с которой связан объект **PowerShellTab** , является членом этого класса. Примером является коллекция `$psISE.CurrentPowerShellTab.Files`.

## <a name="methods"></a>Методы

### <a name="load-filepathname-"></a>Load\( FilePathName \)

Поддерживается в интегрированной среде сценариев Windows PowerShell 3.0 и более поздних версия и отсутствует в более ранних версиях.

Скачивает файл `.snippets.ps1xml`, содержащий определяемые пользователем фрагменты кода. Для создания фрагментов кода проще всего использовать командлет `New-IseSnippet`, который автоматически сохраняет фрагменты в папке профиля, чтобы загружать их при каждом запуске интегрированной среды сценариев Windows PowerShell.

**FilePathName**  — строка. Путь к файлу с расширением SNIPPETS.PS1XML и его имя. В нем содержатся определения фрагментов.

```powershell
# Loads a custom snippet file into the current PowerShell tab.
$SnipFile = Join-Path ( Split-Path $profile) 'Snippets\MySnips.snippets.ps1xml' $psISE.CurrentPowerShellTab.Snippets.Add($SnipPath)
```

## <a name="see-also"></a>См. также

- [Объект ISESnippet](The-ISESnippetObject.md)
- [Назначение объектной модели сценариев интегрированной среды сценариев Windows PowerShell](Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [Иерархия объектной модели интегрированной среды скриптов](The-ISE-Object-Model-Hierarchy.md)
