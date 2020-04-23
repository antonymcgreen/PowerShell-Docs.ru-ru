---
ms.date: 12/31/2019
keywords: powershell,командлет
title: Объект ISESnippetCollection
ms.openlocfilehash: 6cdc43dd1d82e94f66122d7f7b313c02e755fed7
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "75736051"
---
# <a name="the-isesnippetcollection-object"></a>Объект ISESnippetCollection

Объект **ISESnippetCollection** — это коллекция объектов **ISESnippet**. Коллекция файлов, с которой связан объект **PowerShellTab**, является членом этого класса. Примером является коллекция `$psISE.CurrentPowerShellTab.Files`.

## <a name="methods"></a>Методы

### <a name="load-filepathname-"></a>Load\( FilePathName \)

Поддерживается в интегрированной среде сценариев Windows PowerShell 3.0 и более поздних версия и отсутствует в более ранних версиях.

Скачивает файл `.snippets.ps1xml`, содержащий определяемые пользователем фрагменты кода. Для создания фрагментов кода проще всего использовать командлет `New-IseSnippet`, который автоматически сохраняет фрагменты в папке профиля, чтобы загружать их при каждом запуске интегрированной среды сценариев Windows PowerShell.

**FilePathName** — строка. Путь к файлу с расширением SNIPPETS.PS1XML и его имя. В нем содержатся определения фрагментов.

```powershell
# Loads a custom snippet file into the current PowerShell tab.
$SnipFile = Join-Path ( Split-Path $profile) 'Snippets\MySnips.snippets.ps1xml' $psISE.CurrentPowerShellTab.Snippets.Add($SnipPath)
```

## <a name="see-also"></a>См. также:

- [Объект ISESnippet](The-ISESnippetObject.md)
- [Назначение объектной модели скриптов интегрированной среды скриптов Windows PowerShell](Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [Иерархия объектной модели интегрированной среды скриптов](The-ISE-Object-Model-Hierarchy.md)
