---
ms.date: 06/05/2017
keywords: powershell,командлет
title: Объект ISESnippetCollection
ms.openlocfilehash: 6c392c08767fba004f63155d5a469777856a0b59
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "67030501"
---
# <a name="the-isesnippetcollection-object"></a><span data-ttu-id="731c1-103">Объект ISESnippetCollection</span><span class="sxs-lookup"><span data-stu-id="731c1-103">The ISESnippetCollection Object</span></span>

<span data-ttu-id="731c1-104">Объект **ISESnippetCollection** — это коллекция объектов **ISESnippet**.</span><span class="sxs-lookup"><span data-stu-id="731c1-104">The **ISESnippetCollection** object is a collection of **ISESnippet** objects.</span></span> <span data-ttu-id="731c1-105">Коллекция файлов, с которой связан объект **PowerShellTab**, является членом этого класса.</span><span class="sxs-lookup"><span data-stu-id="731c1-105">The files collection that is associated with a **PowerShellTab** object is a member of this class.</span></span> <span data-ttu-id="731c1-106">Примером является коллекция **$psISE.CurrentPowerShellTab.Files**.</span><span class="sxs-lookup"><span data-stu-id="731c1-106">An example is the **$psISE.CurrentPowerShellTab.Files** collection.</span></span>

## <a name="methods"></a><span data-ttu-id="731c1-107">Методы</span><span class="sxs-lookup"><span data-stu-id="731c1-107">Methods</span></span>

### <a name="load-filepathname-"></a><span data-ttu-id="731c1-108">Load\( FilePathName \)</span><span class="sxs-lookup"><span data-stu-id="731c1-108">Load\( FilePathName \)</span></span>

<span data-ttu-id="731c1-109">Поддерживается в интегрированной среде сценариев Windows PowerShell 3.0 и более поздних версия и отсутствует в более ранних версиях.</span><span class="sxs-lookup"><span data-stu-id="731c1-109">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

<span data-ttu-id="731c1-110">Загружает SNIPPETS.PS1XML-файл, содержащий определяемые пользователем фрагменты кода.</span><span class="sxs-lookup"><span data-stu-id="731c1-110">Loads a .snippets.ps1xml file that contains user-defined snippets.</span></span> <span data-ttu-id="731c1-111">Для создания фрагментов кода проще всего использовать командлет New-IseSnippet, который автоматически сохраняет фрагменты в папке профиля, чтобы загружать их при каждом запуске интегрированной среды сценариев Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="731c1-111">The easiest way to create snippets is to use the New-IseSnippet cmdlet, which automatically stores them in your profile folder so that they are loaded every time that you start Windows PowerShell ISE.</span></span>

<span data-ttu-id="731c1-112">**FilePathName** — строка. Путь к файлу с расширением SNIPPETS.PS1XML и его имя. В нем содержатся определения фрагментов.</span><span class="sxs-lookup"><span data-stu-id="731c1-112">**FilePathName** - String The path and file name to a .snippets.ps1xml file that contains snippet definitions.</span></span>

```powershell
# Loads a custom snippet file into the current PowerShell tab.
$SnipFile = Join-Path ( Split-Path $profile) 'Snippets\MySnips.snippets.ps1xml' $psISE.CurrentPowerShellTab.Snippets.Add($SnipPath)
```

## <a name="see-also"></a><span data-ttu-id="731c1-113">См. также</span><span class="sxs-lookup"><span data-stu-id="731c1-113">See Also</span></span>

- [<span data-ttu-id="731c1-114">Объект ISESnippet</span><span class="sxs-lookup"><span data-stu-id="731c1-114">The ISESnippetObject</span></span>](The-ISESnippetObject.md)
- [<span data-ttu-id="731c1-115">Назначение объектной модели скриптов интегрированной среды скриптов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="731c1-115">Purpose of the Windows PowerShell ISE Scripting Object Model</span></span>](Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [<span data-ttu-id="731c1-116">Иерархия объектной модели интегрированной среды скриптов</span><span class="sxs-lookup"><span data-stu-id="731c1-116">The ISE Object Model Hierarchy</span></span>](The-ISE-Object-Model-Hierarchy.md)
