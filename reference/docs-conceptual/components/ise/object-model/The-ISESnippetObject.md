---
ms.date: 06/05/2017
keywords: powershell,командлет
title: Объект ISESnippet
ms.openlocfilehash: 62d470569deb051fca80005235d4c492319cf5ec
ms.sourcegitcommit: a6f13c16a535acea279c0ddeca72f1f0d8a8ce4c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/12/2019
ms.locfileid: "67028885"
---
# <a name="the-isesnippetobject"></a><span data-ttu-id="9d4e8-103">Объект ISESnippet</span><span class="sxs-lookup"><span data-stu-id="9d4e8-103">The ISESnippetObject</span></span>

<span data-ttu-id="9d4e8-104">Объект **ISESnippet** является экземпляром класса Microsoft.PowerShell.Host.ISE.ISESnippet.</span><span class="sxs-lookup"><span data-stu-id="9d4e8-104">An **ISESnippet** object is an instance of the Microsoft.PowerShell.Host.ISE.ISESnippet class.</span></span> <span data-ttu-id="9d4e8-105">Элементы коллекции **$psISE.CurrentPowerShellTab.Snippets** являются примерами объектов **ISESnippet**.</span><span class="sxs-lookup"><span data-stu-id="9d4e8-105">The members of the **$psISE.CurrentPowerShellTab.Snippets** collection are all examples of **ISESnippet** objects.</span></span> <span data-ttu-id="9d4e8-106">Самый простой способ создать фрагмент кода — использовать командлет [New-IseSnippet&#91;PSITPro5_ISE&#93;](https://technet.microsoft.com/library/0a6339a3-2683-4a8e-8929-90ad9a95c3e0).</span><span class="sxs-lookup"><span data-stu-id="9d4e8-106">The easiest way to create a snippet is to use the [New-IseSnippet&#91;PSITPro5_ISE&#93;](https://technet.microsoft.com/library/0a6339a3-2683-4a8e-8929-90ad9a95c3e0) cmdlet.</span></span>

## <a name="properties"></a><span data-ttu-id="9d4e8-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="9d4e8-107">Properties</span></span>

### <a name="author"></a><span data-ttu-id="9d4e8-108">Дизайнер</span><span class="sxs-lookup"><span data-stu-id="9d4e8-108">Author</span></span>

<span data-ttu-id="9d4e8-109">Поддерживается в интегрированной среде сценариев Windows PowerShell 3.0 и более поздних версия и отсутствует в более ранних версиях.</span><span class="sxs-lookup"><span data-stu-id="9d4e8-109">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

<span data-ttu-id="9d4e8-110">Свойство только для чтения, которое получает имя автора фрагмента.</span><span class="sxs-lookup"><span data-stu-id="9d4e8-110">The read-only property that gets the name of the author of the snippet.</span></span>

```powershell
# Get the author of the first snippet item
$psISE.CurrentPowerShellTab.Snippets.Item(0).Author
```

### <a name="codefragment"></a><span data-ttu-id="9d4e8-111">CodeFragment</span><span class="sxs-lookup"><span data-stu-id="9d4e8-111">CodeFragment</span></span>

<span data-ttu-id="9d4e8-112">Поддерживается в интегрированной среде сценариев Windows PowerShell 3.0 и более поздних версия и отсутствует в более ранних версиях.</span><span class="sxs-lookup"><span data-stu-id="9d4e8-112">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

<span data-ttu-id="9d4e8-113">Свойство только для чтения, которое получает фрагмент кода, вставляемый в редактор.</span><span class="sxs-lookup"><span data-stu-id="9d4e8-113">The read-only property that gets the code fragment to be inserted into the editor.</span></span>

```powershell
# Get the code fragment associated with the first snippet item.
$psISE.CurrentPowerShellTab.Snippets.Item(0).CodeFragment
```

### <a name="shortcut"></a><span data-ttu-id="9d4e8-114">Установленное напрямую доверие</span><span class="sxs-lookup"><span data-stu-id="9d4e8-114">Shortcut</span></span>

<span data-ttu-id="9d4e8-115">Поддерживается в интегрированной среде сценариев Windows PowerShell 3.0 и более поздних версия и отсутствует в более ранних версиях.</span><span class="sxs-lookup"><span data-stu-id="9d4e8-115">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

<span data-ttu-id="9d4e8-116">Свойство только для чтения, которое получает сочетания клавиш Windows для пункта меню.</span><span class="sxs-lookup"><span data-stu-id="9d4e8-116">The read-only property that gets the Windows keyboard shortcut for the menu item.</span></span>

```powershell
# Get the shortcut for the first submenu item.
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Clear()
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Add('_Process', {Get-Process}, 'Alt+P')
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus[0].Shortcut
```

## <a name="see-also"></a><span data-ttu-id="9d4e8-117">См. также</span><span class="sxs-lookup"><span data-stu-id="9d4e8-117">See Also</span></span>

- [<span data-ttu-id="9d4e8-118">Объект ISESnippetCollection</span><span class="sxs-lookup"><span data-stu-id="9d4e8-118">The ISESnippetCollection Object</span></span>](The-ISESnippetCollection-Object.md)
- [<span data-ttu-id="9d4e8-119">Назначение объектной модели скриптов интегрированной среды скриптов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9d4e8-119">Purpose of the Windows PowerShell ISE Scripting Object Model</span></span>](purpose-of-the-windows-powershell-ise-scripting-object-model.md)
- [<span data-ttu-id="9d4e8-120">Иерархия объектной модели интегрированной среды скриптов</span><span class="sxs-lookup"><span data-stu-id="9d4e8-120">The ISE Object Model Hierarchy</span></span>](The-ISE-Object-Model-Hierarchy.md)
