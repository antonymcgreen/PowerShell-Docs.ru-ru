---
ms.date: 06/05/2017
keywords: powershell,командлет
title: Объект ISESnippetCollection
ms.openlocfilehash: 6c392c08767fba004f63155d5a469777856a0b59
ms.sourcegitcommit: a6f13c16a535acea279c0ddeca72f1f0d8a8ce4c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/12/2019
ms.locfileid: "67030501"
---
# <a name="the-isesnippetcollection-object"></a><span data-ttu-id="0bc39-103">Объект ISESnippetCollection</span><span class="sxs-lookup"><span data-stu-id="0bc39-103">The ISESnippetCollection Object</span></span>

<span data-ttu-id="0bc39-104">Объект **ISESnippetCollection** — это коллекция объектов **ISESnippet**.</span><span class="sxs-lookup"><span data-stu-id="0bc39-104">The **ISESnippetCollection** object is a collection of **ISESnippet** objects.</span></span> <span data-ttu-id="0bc39-105">Коллекция файлов, с которой связан объект **PowerShellTab**, является членом этого класса.</span><span class="sxs-lookup"><span data-stu-id="0bc39-105">The files collection that is associated with a **PowerShellTab** object is a member of this class.</span></span> <span data-ttu-id="0bc39-106">Примером является коллекция **$psISE.CurrentPowerShellTab.Files**.</span><span class="sxs-lookup"><span data-stu-id="0bc39-106">An example is the **$psISE.CurrentPowerShellTab.Files** collection.</span></span>

## <a name="methods"></a><span data-ttu-id="0bc39-107">Методы</span><span class="sxs-lookup"><span data-stu-id="0bc39-107">Methods</span></span>

### <a name="load-filepathname-"></a><span data-ttu-id="0bc39-108">Load\( FilePathName \)</span><span class="sxs-lookup"><span data-stu-id="0bc39-108">Load\( FilePathName \)</span></span>

<span data-ttu-id="0bc39-109">Поддерживается в интегрированной среде сценариев Windows PowerShell 3.0 и более поздних версия и отсутствует в более ранних версиях.</span><span class="sxs-lookup"><span data-stu-id="0bc39-109">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

<span data-ttu-id="0bc39-110">Загружает SNIPPETS.PS1XML-файл, содержащий определяемые пользователем фрагменты кода.</span><span class="sxs-lookup"><span data-stu-id="0bc39-110">Loads a .snippets.ps1xml file that contains user-defined snippets.</span></span> <span data-ttu-id="0bc39-111">Для создания фрагментов кода проще всего использовать командлет New-IseSnippet, который автоматически сохраняет фрагменты в папке профиля, чтобы загружать их при каждом запуске интегрированной среды сценариев Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0bc39-111">The easiest way to create snippets is to use the New-IseSnippet cmdlet, which automatically stores them in your profile folder so that they are loaded every time that you start Windows PowerShell ISE.</span></span>

<span data-ttu-id="0bc39-112">**FilePathName** — строка. Путь к файлу с расширением SNIPPETS.PS1XML и его имя. В нем содержатся определения фрагментов.</span><span class="sxs-lookup"><span data-stu-id="0bc39-112">**FilePathName** - String The path and file name to a .snippets.ps1xml file that contains snippet definitions.</span></span>

```powershell
# Loads a custom snippet file into the current PowerShell tab.
$SnipFile = Join-Path ( Split-Path $profile) 'Snippets\MySnips.snippets.ps1xml' $psISE.CurrentPowerShellTab.Snippets.Add($SnipPath)
```

## <a name="see-also"></a><span data-ttu-id="0bc39-113">См. также</span><span class="sxs-lookup"><span data-stu-id="0bc39-113">See Also</span></span>

- [<span data-ttu-id="0bc39-114">Объект ISESnippet</span><span class="sxs-lookup"><span data-stu-id="0bc39-114">The ISESnippetObject</span></span>](The-ISESnippetObject.md)
- [<span data-ttu-id="0bc39-115">Назначение объектной модели скриптов интегрированной среды скриптов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0bc39-115">Purpose of the Windows PowerShell ISE Scripting Object Model</span></span>](Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [<span data-ttu-id="0bc39-116">Иерархия объектной модели интегрированной среды скриптов</span><span class="sxs-lookup"><span data-stu-id="0bc39-116">The ISE Object Model Hierarchy</span></span>](The-ISE-Object-Model-Hierarchy.md)
