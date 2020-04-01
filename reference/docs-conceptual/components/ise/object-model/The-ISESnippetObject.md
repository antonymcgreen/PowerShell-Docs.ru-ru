---
ms.date: 06/05/2017
keywords: powershell,командлет
title: Объект ISESnippet
ms.openlocfilehash: f810e6b26f0ded04be15bdc37f336d7890e29dad
ms.sourcegitcommit: 30ccbbb32915b551c4cd4c91ef1df96b5b7514c4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2020
ms.locfileid: "80500926"
---
# <a name="the-isesnippetobject"></a><span data-ttu-id="83b7b-103">Объект ISESnippet</span><span class="sxs-lookup"><span data-stu-id="83b7b-103">The ISESnippetObject</span></span>

<span data-ttu-id="83b7b-104">Объект **ISESnippet** является экземпляром класса Microsoft.PowerShell.Host.ISE.ISESnippet.</span><span class="sxs-lookup"><span data-stu-id="83b7b-104">An **ISESnippet** object is an instance of the Microsoft.PowerShell.Host.ISE.ISESnippet class.</span></span> <span data-ttu-id="83b7b-105">Элементы коллекции `$psISE.CurrentPowerShellTab.Snippets` являются примерами объектов **ISESnippet**.</span><span class="sxs-lookup"><span data-stu-id="83b7b-105">The members of the `$psISE.CurrentPowerShellTab.Snippets` collection are all examples of **ISESnippet** objects.</span></span> <span data-ttu-id="83b7b-106">Самый простой способ создать фрагмент кода — использовать командлет [New-IseSnippet](/powershell/module/ISE/New-IseSnippet).</span><span class="sxs-lookup"><span data-stu-id="83b7b-106">The easiest way to create a snippet is to use the [New-IseSnippet](/powershell/module/ISE/New-IseSnippet) cmdlet.</span></span>

## <a name="properties"></a><span data-ttu-id="83b7b-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="83b7b-107">Properties</span></span>

### <a name="author"></a><span data-ttu-id="83b7b-108">Автор</span><span class="sxs-lookup"><span data-stu-id="83b7b-108">Author</span></span>

<span data-ttu-id="83b7b-109">Поддерживается в интегрированной среде сценариев Windows PowerShell 3.0 и более поздних версия и отсутствует в более ранних версиях.</span><span class="sxs-lookup"><span data-stu-id="83b7b-109">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

<span data-ttu-id="83b7b-110">Свойство только для чтения, которое получает имя автора фрагмента.</span><span class="sxs-lookup"><span data-stu-id="83b7b-110">The read-only property that gets the name of the author of the snippet.</span></span>

```powershell
# Get the author of the first snippet item
$psISE.CurrentPowerShellTab.Snippets.Item(0).Author
```

### <a name="codefragment"></a><span data-ttu-id="83b7b-111">CodeFragment</span><span class="sxs-lookup"><span data-stu-id="83b7b-111">CodeFragment</span></span>

<span data-ttu-id="83b7b-112">Поддерживается в интегрированной среде сценариев Windows PowerShell 3.0 и более поздних версия и отсутствует в более ранних версиях.</span><span class="sxs-lookup"><span data-stu-id="83b7b-112">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

<span data-ttu-id="83b7b-113">Свойство только для чтения, которое получает фрагмент кода, вставляемый в редактор.</span><span class="sxs-lookup"><span data-stu-id="83b7b-113">The read-only property that gets the code fragment to be inserted into the editor.</span></span>

```powershell
# Get the code fragment associated with the first snippet item.
$psISE.CurrentPowerShellTab.Snippets.Item(0).CodeFragment
```

### <a name="shortcut"></a><span data-ttu-id="83b7b-114">Клавиша</span><span class="sxs-lookup"><span data-stu-id="83b7b-114">Shortcut</span></span>

<span data-ttu-id="83b7b-115">Поддерживается в интегрированной среде сценариев Windows PowerShell 3.0 и более поздних версия и отсутствует в более ранних версиях.</span><span class="sxs-lookup"><span data-stu-id="83b7b-115">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

<span data-ttu-id="83b7b-116">Свойство только для чтения, которое получает сочетания клавиш Windows для пункта меню.</span><span class="sxs-lookup"><span data-stu-id="83b7b-116">The read-only property that gets the Windows keyboard shortcut for the menu item.</span></span>

```powershell
# Get the shortcut for the first submenu item.
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Clear()
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Add('_Process', {Get-Process}, 'Alt+P')
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus[0].Shortcut
```

## <a name="see-also"></a><span data-ttu-id="83b7b-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="83b7b-117">See Also</span></span>

- [<span data-ttu-id="83b7b-118">Объект ISESnippetCollection</span><span class="sxs-lookup"><span data-stu-id="83b7b-118">The ISESnippetCollection Object</span></span>](The-ISESnippetCollection-Object.md)
- [<span data-ttu-id="83b7b-119">Назначение объектной модели скриптов интегрированной среды скриптов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="83b7b-119">Purpose of the Windows PowerShell ISE Scripting Object Model</span></span>](purpose-of-the-windows-powershell-ise-scripting-object-model.md)
- [<span data-ttu-id="83b7b-120">Иерархия объектной модели интегрированной среды скриптов</span><span class="sxs-lookup"><span data-stu-id="83b7b-120">The ISE Object Model Hierarchy</span></span>](The-ISE-Object-Model-Hierarchy.md)
