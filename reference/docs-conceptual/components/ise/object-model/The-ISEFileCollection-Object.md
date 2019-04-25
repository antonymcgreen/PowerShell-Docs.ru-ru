---
ms.date: 06/05/2017
keywords: powershell,командлет
title: Объект ISEFileCollection
ms.assetid: 0f86a427-ea38-4bce-85f8-06c98d30d508
ms.openlocfilehash: eb4b2784820cbe51f662fd2fd945d8760ef9dbff
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62086754"
---
# <a name="the-isefilecollection-object"></a><span data-ttu-id="23ebb-103">Объект ISEFileCollection</span><span class="sxs-lookup"><span data-stu-id="23ebb-103">The ISEFileCollection Object</span></span>

<span data-ttu-id="23ebb-104">Объект **ISEFileCollection**  — это коллекция объектов **ISEFile**.</span><span class="sxs-lookup"><span data-stu-id="23ebb-104">The **ISEFileCollection** object is a collection of **ISEFile** objects.</span></span> <span data-ttu-id="23ebb-105">Примером является коллекция $psISE.CurrentPowerShellTab.Files.</span><span class="sxs-lookup"><span data-stu-id="23ebb-105">An example is the $psISE.CurrentPowerShellTab.Files collection.</span></span>

## <a name="methods"></a><span data-ttu-id="23ebb-106">Методы</span><span class="sxs-lookup"><span data-stu-id="23ebb-106">Methods</span></span>

### <a name="add-fullpath-"></a><span data-ttu-id="23ebb-107">Add\( \[fullPath\] \)</span><span class="sxs-lookup"><span data-stu-id="23ebb-107">Add\( \[fullPath\] \)</span></span>

<span data-ttu-id="23ebb-108">Поддерживается в интегрированной среде сценариев Windows PowerShell 2.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="23ebb-108">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="23ebb-109">Создает и возвращает новый файл без имени и добавляет его в коллекцию.</span><span class="sxs-lookup"><span data-stu-id="23ebb-109">Creates and returns a new untitled file and adds it to the collection.</span></span> <span data-ttu-id="23ebb-110">Свойство **IsUntitled** созданного файла имеет значение **$true**.</span><span class="sxs-lookup"><span data-stu-id="23ebb-110">The **IsUntitled** property of the newly created file is **$true**.</span></span>

<span data-ttu-id="23ebb-111">**\[fullPath\]**  — необязательная строка. Полный путь к файлу.</span><span class="sxs-lookup"><span data-stu-id="23ebb-111">**\[fullPath\]** - Optional string The fully specified path of the file.</span></span> <span data-ttu-id="23ebb-112">Исключение возникает, если включен параметр **fullPath** и относительный путь или если вместо полного пути используется имя файла.</span><span class="sxs-lookup"><span data-stu-id="23ebb-112">An exception is generated if you include the **fullPath** parameter and a relative path, or if you use a file name instead of the full path.</span></span>

```powershell
# Adds a new untitled file to the collection of files in the current PowerShell tab.
$newFile = $psISE.CurrentPowerShellTab.Files.Add()

# Adds a file specified by its full path to the collection of files in the current PowerShell tab.
$psISE.CurrentPowerShellTab.Files.Add("$pshome\Examples\profile.ps1")
```

### <a name="remove-file-force-"></a><span data-ttu-id="23ebb-113">Remove\( File, \[Force\] \)</span><span class="sxs-lookup"><span data-stu-id="23ebb-113">Remove\( File, \[Force\] \)</span></span>

<span data-ttu-id="23ebb-114">Поддерживается в интегрированной среде сценариев Windows PowerShell 2.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="23ebb-114">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="23ebb-115">Удаляет указанный файл из текущей вкладки PowerShell.</span><span class="sxs-lookup"><span data-stu-id="23ebb-115">Removes a specified file from the current PowerShell tab.</span></span>

<span data-ttu-id="23ebb-116">**File** — строка. Файл ISEFile, удаляемый из коллекции.</span><span class="sxs-lookup"><span data-stu-id="23ebb-116">**File** - String The ISEFile file that you want to remove from the collection.</span></span> <span data-ttu-id="23ebb-117">Если файл не был сохранен, этот метод создает исключение.</span><span class="sxs-lookup"><span data-stu-id="23ebb-117">If the file has not been saved, this method throws an exception.</span></span> <span data-ttu-id="23ebb-118">Используйте параметр **Force** для принудительного удаления несохраненного файла.</span><span class="sxs-lookup"><span data-stu-id="23ebb-118">Use the **Force** switch parameter to force the removal of an unsaved file.</span></span>

<span data-ttu-id="23ebb-119">**\[Force\]**  — необязательное логическое значение. Если задано значение **$true**, предоставляет разрешение на удаление файла, даже если он не был сохранен с момента последнего использования.</span><span class="sxs-lookup"><span data-stu-id="23ebb-119">**\[Force\]** - optional Boolean If set to **$true**, grants permission to remove the file even if it has not been saved after last use.</span></span> <span data-ttu-id="23ebb-120">Значение по умолчанию — **$false**.</span><span class="sxs-lookup"><span data-stu-id="23ebb-120">The default is **$false**.</span></span>

```powershell
# Removes the first opened file from the file collection associated with the current PowerShell tab.
# If the file has not yet been saved, then an exception is generated.
$firstfile = $psISE.CurrentPowerShellTab.Files[0]
$psISE.CurrentPowerShellTab.Files.Remove($firstfile)

# Removes the first opened file from the file collection associated with the current PowerShell tab, even if it has not been saved.
$firstfile = $psISE.CurrentPowerShellTab.Files[0]
$psISE.CurrentPowerShellTab.Files.Remove($firstfile, $true)
```

### <a name="setselectedfile-selectedfile-"></a><span data-ttu-id="23ebb-121">SetSelectedFile\( selectedFile \)</span><span class="sxs-lookup"><span data-stu-id="23ebb-121">SetSelectedFile\( selectedFile \)</span></span>

<span data-ttu-id="23ebb-122">Поддерживается в интегрированной среде сценариев Windows PowerShell 2.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="23ebb-122">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="23ebb-123">Выбирает файл, который задается параметром **selectedFile**.</span><span class="sxs-lookup"><span data-stu-id="23ebb-123">Selects the file that is specified by the **selectedFile** parameter.</span></span>

<span data-ttu-id="23ebb-124">**selectedFile** — Microsoft.PowerShell.Host.ISE.ISEFile. Выбираемый файл ISEFile.</span><span class="sxs-lookup"><span data-stu-id="23ebb-124">**selectedFile** - Microsoft.PowerShell.Host.ISE.ISEFile The ISEFile file that you want to select.</span></span>

```powershell
# Selects the specified file.
$firstfile = $psISE.CurrentPowerShellTab.Files[0]
$psISE.CurrentPowerShellTab.Files.SetSelectedFile($firstfile)
```

## <a name="see-also"></a><span data-ttu-id="23ebb-125">См. также</span><span class="sxs-lookup"><span data-stu-id="23ebb-125">See Also</span></span>

- [<span data-ttu-id="23ebb-126">Объект ISEFile</span><span class="sxs-lookup"><span data-stu-id="23ebb-126">The ISEFile Object</span></span>](The-ISEFile-Object.md)
- [<span data-ttu-id="23ebb-127">Назначение объектной модели скриптов интегрированной среды скриптов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="23ebb-127">Purpose of the Windows PowerShell ISE Scripting Object Model</span></span>](Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [<span data-ttu-id="23ebb-128">Иерархия объектной модели интегрированной среды скриптов</span><span class="sxs-lookup"><span data-stu-id="23ebb-128">The ISE Object Model Hierarchy</span></span>](The-ISE-Object-Model-Hierarchy.md)