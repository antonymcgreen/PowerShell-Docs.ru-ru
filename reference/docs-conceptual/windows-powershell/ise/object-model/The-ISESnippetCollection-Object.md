---
ms.date: 12/31/2019
keywords: powershell,командлет
title: Объект ISESnippetCollection
ms.openlocfilehash: 6cdc43dd1d82e94f66122d7f7b313c02e755fed7
ms.sourcegitcommit: 2aec310ad0c0b048400cb56f6fa64c1e554c812a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/23/2020
ms.locfileid: "83808580"
---
# <a name="the-isesnippetcollection-object"></a><span data-ttu-id="67e9a-103">Объект ISESnippetCollection</span><span class="sxs-lookup"><span data-stu-id="67e9a-103">The ISESnippetCollection Object</span></span>

<span data-ttu-id="67e9a-104">Объект **ISESnippetCollection** — это коллекция объектов **ISESnippet**.</span><span class="sxs-lookup"><span data-stu-id="67e9a-104">The **ISESnippetCollection** object is a collection of **ISESnippet** objects.</span></span> <span data-ttu-id="67e9a-105">Коллекция файлов, с которой связан объект **PowerShellTab**, является членом этого класса.</span><span class="sxs-lookup"><span data-stu-id="67e9a-105">The files collection that is associated with a **PowerShellTab** object is a member of this class.</span></span> <span data-ttu-id="67e9a-106">Примером является коллекция `$psISE.CurrentPowerShellTab.Files`.</span><span class="sxs-lookup"><span data-stu-id="67e9a-106">An example is the `$psISE.CurrentPowerShellTab.Files` collection.</span></span>

## <a name="methods"></a><span data-ttu-id="67e9a-107">Методы</span><span class="sxs-lookup"><span data-stu-id="67e9a-107">Methods</span></span>

### <a name="load-filepathname-"></a><span data-ttu-id="67e9a-108">Load\( FilePathName \)</span><span class="sxs-lookup"><span data-stu-id="67e9a-108">Load\( FilePathName \)</span></span>

<span data-ttu-id="67e9a-109">Поддерживается в интегрированной среде сценариев Windows PowerShell 3.0 и более поздних версия и отсутствует в более ранних версиях.</span><span class="sxs-lookup"><span data-stu-id="67e9a-109">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

<span data-ttu-id="67e9a-110">Скачивает файл `.snippets.ps1xml`, содержащий определяемые пользователем фрагменты кода.</span><span class="sxs-lookup"><span data-stu-id="67e9a-110">Loads a `.snippets.ps1xml` file that contains user-defined snippets.</span></span> <span data-ttu-id="67e9a-111">Для создания фрагментов кода проще всего использовать командлет `New-IseSnippet`, который автоматически сохраняет фрагменты в папке профиля, чтобы загружать их при каждом запуске интегрированной среды сценариев Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="67e9a-111">The easiest way to create snippets is to use the `New-IseSnippet` cmdlet, which automatically stores them in your profile folder so that they are loaded every time that you start Windows PowerShell ISE.</span></span>

<span data-ttu-id="67e9a-112">**FilePathName** — строка. Путь к файлу с расширением SNIPPETS.PS1XML и его имя. В нем содержатся определения фрагментов.</span><span class="sxs-lookup"><span data-stu-id="67e9a-112">**FilePathName** - String The path and file name to a .snippets.ps1xml file that contains snippet definitions.</span></span>

```powershell
# Loads a custom snippet file into the current PowerShell tab.
$SnipFile = Join-Path ( Split-Path $profile) 'Snippets\MySnips.snippets.ps1xml' $psISE.CurrentPowerShellTab.Snippets.Add($SnipPath)
```

## <a name="see-also"></a><span data-ttu-id="67e9a-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="67e9a-113">See Also</span></span>

- [<span data-ttu-id="67e9a-114">Объект ISESnippet</span><span class="sxs-lookup"><span data-stu-id="67e9a-114">The ISESnippetObject</span></span>](The-ISESnippetObject.md)
- [<span data-ttu-id="67e9a-115">Назначение объектной модели скриптов интегрированной среды скриптов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="67e9a-115">Purpose of the Windows PowerShell ISE Scripting Object Model</span></span>](Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [<span data-ttu-id="67e9a-116">Иерархия объектной модели интегрированной среды скриптов</span><span class="sxs-lookup"><span data-stu-id="67e9a-116">The ISE Object Model Hierarchy</span></span>](The-ISE-Object-Model-Hierarchy.md)