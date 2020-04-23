---
ms.date: 06/05/2017
keywords: powershell,командлет
title: Объект ISESnippet
ms.openlocfilehash: f810e6b26f0ded04be15bdc37f336d7890e29dad
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "80500926"
---
# <a name="the-isesnippetobject"></a>Объект ISESnippet

Объект **ISESnippet** является экземпляром класса Microsoft.PowerShell.Host.ISE.ISESnippet. Элементы коллекции `$psISE.CurrentPowerShellTab.Snippets` являются примерами объектов **ISESnippet**. Самый простой способ создать фрагмент кода — использовать командлет [New-IseSnippet](/powershell/module/ISE/New-IseSnippet).

## <a name="properties"></a>Свойства

### <a name="author"></a>Автор

Поддерживается в интегрированной среде сценариев Windows PowerShell 3.0 и более поздних версия и отсутствует в более ранних версиях.

Свойство только для чтения, которое получает имя автора фрагмента.

```powershell
# Get the author of the first snippet item
$psISE.CurrentPowerShellTab.Snippets.Item(0).Author
```

### <a name="codefragment"></a>CodeFragment

Поддерживается в интегрированной среде сценариев Windows PowerShell 3.0 и более поздних версия и отсутствует в более ранних версиях.

Свойство только для чтения, которое получает фрагмент кода, вставляемый в редактор.

```powershell
# Get the code fragment associated with the first snippet item.
$psISE.CurrentPowerShellTab.Snippets.Item(0).CodeFragment
```

### <a name="shortcut"></a>Клавиша

Поддерживается в интегрированной среде сценариев Windows PowerShell 3.0 и более поздних версия и отсутствует в более ранних версиях.

Свойство только для чтения, которое получает сочетания клавиш Windows для пункта меню.

```powershell
# Get the shortcut for the first submenu item.
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Clear()
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Add('_Process', {Get-Process}, 'Alt+P')
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus[0].Shortcut
```

## <a name="see-also"></a>См. также:

- [Объект ISESnippetCollection](The-ISESnippetCollection-Object.md)
- [Назначение объектной модели скриптов интегрированной среды скриптов Windows PowerShell](purpose-of-the-windows-powershell-ise-scripting-object-model.md)
- [Иерархия объектной модели интегрированной среды скриптов](The-ISE-Object-Model-Hierarchy.md)
