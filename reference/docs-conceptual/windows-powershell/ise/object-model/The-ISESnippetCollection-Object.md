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
# <a name="the-isesnippetcollection-object"></a><span data-ttu-id="0e2ff-104">Объект ISESnippetCollection</span><span class="sxs-lookup"><span data-stu-id="0e2ff-104">The ISESnippetCollection Object</span></span>

<span data-ttu-id="0e2ff-105">Объект **ISESnippetCollection**  — это коллекция объектов **ISESnippet** .</span><span class="sxs-lookup"><span data-stu-id="0e2ff-105">The **ISESnippetCollection** object is a collection of **ISESnippet** objects.</span></span> <span data-ttu-id="0e2ff-106">Коллекция файлов, с которой связан объект **PowerShellTab** , является членом этого класса.</span><span class="sxs-lookup"><span data-stu-id="0e2ff-106">The files collection that is associated with a **PowerShellTab** object is a member of this class.</span></span> <span data-ttu-id="0e2ff-107">Примером является коллекция `$psISE.CurrentPowerShellTab.Files`.</span><span class="sxs-lookup"><span data-stu-id="0e2ff-107">An example is the `$psISE.CurrentPowerShellTab.Files` collection.</span></span>

## <a name="methods"></a><span data-ttu-id="0e2ff-108">Методы</span><span class="sxs-lookup"><span data-stu-id="0e2ff-108">Methods</span></span>

### <a name="load-filepathname-"></a><span data-ttu-id="0e2ff-109">Load\( FilePathName \)</span><span class="sxs-lookup"><span data-stu-id="0e2ff-109">Load\( FilePathName \)</span></span>

<span data-ttu-id="0e2ff-110">Поддерживается в интегрированной среде сценариев Windows PowerShell 3.0 и более поздних версия и отсутствует в более ранних версиях.</span><span class="sxs-lookup"><span data-stu-id="0e2ff-110">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

<span data-ttu-id="0e2ff-111">Скачивает файл `.snippets.ps1xml`, содержащий определяемые пользователем фрагменты кода.</span><span class="sxs-lookup"><span data-stu-id="0e2ff-111">Loads a `.snippets.ps1xml` file that contains user-defined snippets.</span></span> <span data-ttu-id="0e2ff-112">Для создания фрагментов кода проще всего использовать командлет `New-IseSnippet`, который автоматически сохраняет фрагменты в папке профиля, чтобы загружать их при каждом запуске интегрированной среды сценариев Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0e2ff-112">The easiest way to create snippets is to use the `New-IseSnippet` cmdlet, which automatically stores them in your profile folder so that they are loaded every time that you start Windows PowerShell ISE.</span></span>

<span data-ttu-id="0e2ff-113">**FilePathName**  — строка. Путь к файлу с расширением SNIPPETS.PS1XML и его имя. В нем содержатся определения фрагментов.</span><span class="sxs-lookup"><span data-stu-id="0e2ff-113">**FilePathName** - String The path and file name to a .snippets.ps1xml file that contains snippet definitions.</span></span>

```powershell
# Loads a custom snippet file into the current PowerShell tab.
$SnipFile = Join-Path ( Split-Path $profile) 'Snippets\MySnips.snippets.ps1xml' $psISE.CurrentPowerShellTab.Snippets.Add($SnipPath)
```

## <a name="see-also"></a><span data-ttu-id="0e2ff-114">См. также</span><span class="sxs-lookup"><span data-stu-id="0e2ff-114">See Also</span></span>

- [<span data-ttu-id="0e2ff-115">Объект ISESnippet</span><span class="sxs-lookup"><span data-stu-id="0e2ff-115">The ISESnippetObject</span></span>](The-ISESnippetObject.md)
- [<span data-ttu-id="0e2ff-116">Назначение объектной модели сценариев интегрированной среды сценариев Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0e2ff-116">Purpose of the Windows PowerShell ISE Scripting Object Model</span></span>](Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [<span data-ttu-id="0e2ff-117">Иерархия объектной модели интегрированной среды скриптов</span><span class="sxs-lookup"><span data-stu-id="0e2ff-117">The ISE Object Model Hierarchy</span></span>](The-ISE-Object-Model-Hierarchy.md)
