---
ms.date: 12/31/2019
keywords: powershell,командлет
title: Объект ISEFile
ms.openlocfilehash: 1069e46aa586b8df2050129194a909b90f77b745
ms.sourcegitcommit: 2aec310ad0c0b048400cb56f6fa64c1e554c812a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/23/2020
ms.locfileid: "83809890"
---
# <a name="the-isefile-object"></a><span data-ttu-id="a556c-103">Объект ISEFile</span><span class="sxs-lookup"><span data-stu-id="a556c-103">The ISEFile Object</span></span>

<span data-ttu-id="a556c-104">Объект **ISEFile** представляет файл в интегрированной среде скриптов (ISE) Windows PowerShell®.</span><span class="sxs-lookup"><span data-stu-id="a556c-104">An **ISEFile** object represents a file in Windows PowerShell® Integrated Scripting Environment (ISE).</span></span> <span data-ttu-id="a556c-105">Он является экземпляром класса **Microsoft.PowerShell.Host.ISE.ISEFile**.</span><span class="sxs-lookup"><span data-stu-id="a556c-105">It is an instance of the **Microsoft.PowerShell.Host.ISE.ISEFile** class.</span></span> <span data-ttu-id="a556c-106">В этом разделе перечислены его члены (методы и свойства).</span><span class="sxs-lookup"><span data-stu-id="a556c-106">This topic lists its member methods and member properties.</span></span> <span data-ttu-id="a556c-107">Объект `$psISE.CurrentFile` и все файлы в коллекции "Файлы" на вкладке PowerShell являются экземплярами класса \*\***Microsoft.PowerShell.Host.ISE.ISEFile**.</span><span class="sxs-lookup"><span data-stu-id="a556c-107">The `$psISE.CurrentFile` and the files in the Files collection in a PowerShell tab are all instances of the \*\*\*\*Microsoft.PowerShell.Host.ISE.ISEFile\*\* class.</span></span>

## <a name="methods"></a><span data-ttu-id="a556c-108">Методы</span><span class="sxs-lookup"><span data-stu-id="a556c-108">Methods</span></span>

### <a name="save-saveencoding-"></a><span data-ttu-id="a556c-109">Save\( \[saveEncoding\] \)</span><span class="sxs-lookup"><span data-stu-id="a556c-109">Save\( \[saveEncoding\] \)</span></span>

<span data-ttu-id="a556c-110">Поддерживается в интегрированной среде сценариев Windows PowerShell 2.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="a556c-110">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="a556c-111">Сохраняет файл на диске.</span><span class="sxs-lookup"><span data-stu-id="a556c-111">Saves the file to disk.</span></span>

<span data-ttu-id="a556c-112">**\[saveEncoding\]**  — необязательный параметр кодировки символов [System.Text.Encoding](https://msdn.microsoft.com/library/system.text.encoding.aspx), используемый для сохраненного файла.</span><span class="sxs-lookup"><span data-stu-id="a556c-112">**\[saveEncoding\]** - optional [System.Text.Encoding](https://msdn.microsoft.com/library/system.text.encoding.aspx) An optional character encoding parameter to be used for the saved file.</span></span> <span data-ttu-id="a556c-113">Значение по умолчанию — **UTF8**.</span><span class="sxs-lookup"><span data-stu-id="a556c-113">The default value is **UTF8**.</span></span>

### <a name="exceptions"></a><span data-ttu-id="a556c-114">Исключения</span><span class="sxs-lookup"><span data-stu-id="a556c-114">Exceptions</span></span>

- <span data-ttu-id="a556c-115">**System.IO.IOException**: не удалось сохранить файл.</span><span class="sxs-lookup"><span data-stu-id="a556c-115">**System.IO.IOException**: The file could not be saved.</span></span>

```powershell
# Save the file using the default encoding (UTF8)
$psISE.CurrentFile.Save()

# Save the file as ASCII.
$psISE.CurrentFile.Save([System.Text.Encoding]::ASCII)

# Gets the current encoding.
$myfile = $psISE.CurrentFile
$myfile.Encoding
```

### <a name="saveasfilename-saveencoding"></a><span data-ttu-id="a556c-116">SaveAs\(filename, \[saveEncoding\]\)</span><span class="sxs-lookup"><span data-stu-id="a556c-116">SaveAs\(filename, \[saveEncoding\]\)</span></span>

<span data-ttu-id="a556c-117">Поддерживается в интегрированной среде сценариев Windows PowerShell 2.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="a556c-117">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="a556c-118">Сохраняет файл с указанным именем файла и кодировкой.</span><span class="sxs-lookup"><span data-stu-id="a556c-118">Saves the file with the specified file name and encoding.</span></span>

<span data-ttu-id="a556c-119">**filename** — строка. Имя, используемое для сохранения файла.</span><span class="sxs-lookup"><span data-stu-id="a556c-119">**filename** - String The name to be used to save the file.</span></span>

<span data-ttu-id="a556c-120">**\[saveEncoding\]**  — необязательный параметр кодировки символов [System.Text.Encoding](https://msdn.microsoft.com/library/system.text.encoding.aspx), используемый для сохраненного файла.</span><span class="sxs-lookup"><span data-stu-id="a556c-120">**\[saveEncoding\]** - optional [System.Text.Encoding](https://msdn.microsoft.com/library/system.text.encoding.aspx) An optional character encoding parameter to be used for the saved file.</span></span> <span data-ttu-id="a556c-121">Значение по умолчанию — **UTF8**.</span><span class="sxs-lookup"><span data-stu-id="a556c-121">The default value is **UTF8**.</span></span>

### <a name="exceptions"></a><span data-ttu-id="a556c-122">Исключения</span><span class="sxs-lookup"><span data-stu-id="a556c-122">Exceptions</span></span>

- <span data-ttu-id="a556c-123">**System.ArgumentNullException**: параметр **filename** имеет значение NULL.</span><span class="sxs-lookup"><span data-stu-id="a556c-123">**System.ArgumentNullException**: The **filename** parameter is null.</span></span>
- <span data-ttu-id="a556c-124">**System.ArgumentException**: параметр **filename** пуст.</span><span class="sxs-lookup"><span data-stu-id="a556c-124">**System.ArgumentException**: The **filename** parameter is empty.</span></span>
- <span data-ttu-id="a556c-125">**System.IO.IOException**: не удалось сохранить файл.</span><span class="sxs-lookup"><span data-stu-id="a556c-125">**System.IO.IOException**: The file could not be saved.</span></span>

```powershell
# Save the file with a full path and name.
$fullpath = "c:\temp\newname.txt"
$psISE.CurrentFile.SaveAs($fullPath)
# Save the file with a full path and name and explicitly as UTF8.
$psISE.CurrentFile.SaveAs($fullPath, [System.Text.Encoding]::UTF8)
```

## <a name="properties"></a><span data-ttu-id="a556c-126">Свойства</span><span class="sxs-lookup"><span data-stu-id="a556c-126">Properties</span></span>

### <a name="displayname"></a><span data-ttu-id="a556c-127">DisplayName</span><span class="sxs-lookup"><span data-stu-id="a556c-127">DisplayName</span></span>

<span data-ttu-id="a556c-128">Поддерживается в интегрированной среде сценариев Windows PowerShell 2.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="a556c-128">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="a556c-129">Свойство только для чтения, которое получает строку, содержащую отображаемое имя этого файла.</span><span class="sxs-lookup"><span data-stu-id="a556c-129">The read-only property that gets the string that contains the display name of this file.</span></span> <span data-ttu-id="a556c-130">Имя отображается на вкладке **Файл** в верхней части окна редактора.</span><span class="sxs-lookup"><span data-stu-id="a556c-130">The name is shown on the **File** tab at the top of the editor.</span></span> <span data-ttu-id="a556c-131">Наличие звездочки (`(*)`) в конце имени указывает, что файл содержит изменения, которые не были сохранены.</span><span class="sxs-lookup"><span data-stu-id="a556c-131">The presence of an asterisk `(*)` at the end of the name indicates that the file has changes that have not been saved.</span></span>

```powershell
# Shows the display name of the file.
$psISE.CurrentFile.DisplayName
```

### <a name="editor"></a><span data-ttu-id="a556c-132">Редактор</span><span class="sxs-lookup"><span data-stu-id="a556c-132">Editor</span></span>

<span data-ttu-id="a556c-133">Поддерживается в интегрированной среде сценариев Windows PowerShell 2.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="a556c-133">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="a556c-134">Свойство только для чтения, которое получает [объект редактора](The-ISEEditor-Object.md), используемый для указанного файла.</span><span class="sxs-lookup"><span data-stu-id="a556c-134">The read-only property that gets the [editor object](The-ISEEditor-Object.md) that is used for the specified file.</span></span>

```powershell
# Gets the editor and the text.
$psISE.CurrentFile.Editor.Text
```

### <a name="encoding"></a><span data-ttu-id="a556c-135">Кодирование</span><span class="sxs-lookup"><span data-stu-id="a556c-135">Encoding</span></span>

<span data-ttu-id="a556c-136">Поддерживается в интегрированной среде сценариев Windows PowerShell 2.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="a556c-136">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="a556c-137">Свойство только для чтения, которое получает исходную кодировку файла.</span><span class="sxs-lookup"><span data-stu-id="a556c-137">The read-only property that gets the original file encoding.</span></span> <span data-ttu-id="a556c-138">Это объект **System.Text.Encoding**.</span><span class="sxs-lookup"><span data-stu-id="a556c-138">This is a **System.Text.Encoding** object.</span></span>

```powershell
# Shows the encoding for the file.
$psISE.CurrentFile.Encoding
```

### <a name="fullpath"></a><span data-ttu-id="a556c-139">FullPath</span><span class="sxs-lookup"><span data-stu-id="a556c-139">FullPath</span></span>

<span data-ttu-id="a556c-140">Поддерживается в интегрированной среде сценариев Windows PowerShell 2.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="a556c-140">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="a556c-141">Свойство только для чтения, которое получает строку, указывающую полный путь к открытому файлу.</span><span class="sxs-lookup"><span data-stu-id="a556c-141">The read-only property that gets the string that specifies the full path of the opened file.</span></span>

```powershell
# Shows the full path for the file.
$psISE.CurrentFile.FullPath
```

### <a name="issaved"></a><span data-ttu-id="a556c-142">IsSaved</span><span class="sxs-lookup"><span data-stu-id="a556c-142">IsSaved</span></span>

<span data-ttu-id="a556c-143">Поддерживается в интегрированной среде сценариев Windows PowerShell 2.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="a556c-143">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="a556c-144">Логическое свойство только для чтения, которое возвращает значение `$true`, если файл был сохранен после последнего изменения.</span><span class="sxs-lookup"><span data-stu-id="a556c-144">The read-only Boolean property that returns `$true` if the file has been saved after it was last modified.</span></span>

```powershell
# Determines whether the file has been saved since it was last modified.
$myfile = $psISE.CurrentFile
$myfile.IsSaved
```

### <a name="isuntitled"></a><span data-ttu-id="a556c-145">IsUntitled</span><span class="sxs-lookup"><span data-stu-id="a556c-145">IsUntitled</span></span>

<span data-ttu-id="a556c-146">Поддерживается в интегрированной среде сценариев Windows PowerShell 2.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="a556c-146">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="a556c-147">Свойство только для чтения, которое возвращает значение `$true`, если для файла не задано имя.</span><span class="sxs-lookup"><span data-stu-id="a556c-147">The read-only property that returns `$true` if the file has never been given a title.</span></span>

```powershell
# Determines whether the file has never been given a title.
$psISE.CurrentFile.IsUntitled
$psISE.CurrentFile.SaveAs("temp.txt")
$psISE.CurrentFile.IsUntitled
```

## <a name="see-also"></a><span data-ttu-id="a556c-148">См. также:</span><span class="sxs-lookup"><span data-stu-id="a556c-148">See Also</span></span>

- [<span data-ttu-id="a556c-149">Объект ISEFileCollection</span><span class="sxs-lookup"><span data-stu-id="a556c-149">The ISEFileCollectionObject</span></span>](The-ISEFileCollection-Object.md)
- [<span data-ttu-id="a556c-150">Назначение объектной модели скриптов интегрированной среды скриптов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a556c-150">Purpose of the Windows PowerShell ISE Scripting Object Model</span></span>](Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [<span data-ttu-id="a556c-151">Иерархия объектной модели интегрированной среды скриптов</span><span class="sxs-lookup"><span data-stu-id="a556c-151">The ISE Object Model Hierarchy</span></span>](The-ISE-Object-Model-Hierarchy.md)
