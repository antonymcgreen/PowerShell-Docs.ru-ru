---
ms.date: 06/05/2017
keywords: powershell,командлет
title: Объект ISEFile
ms.assetid: 1c6d91f3-c556-42a2-a017-79b6b7b4b7db
ms.openlocfilehash: 24549720b8bc35435882533b0eb138de432ede65
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 12/14/2018
ms.locfileid: "53403011"
---
# <a name="the-isefile-object"></a><span data-ttu-id="31b31-103">Объект ISEFile</span><span class="sxs-lookup"><span data-stu-id="31b31-103">The ISEFile Object</span></span>

<span data-ttu-id="31b31-104">Объект **ISEFile** представляет файл в интегрированной среде скриптов (ISE) Windows PowerShell®.</span><span class="sxs-lookup"><span data-stu-id="31b31-104">An **ISEFile** object represents a file in Windows PowerShell® Integrated Scripting Environment (ISE).</span></span> <span data-ttu-id="31b31-105">Он является экземпляром класса Microsoft.PowerShell.Host.ISE.ISEFile.</span><span class="sxs-lookup"><span data-stu-id="31b31-105">It is an instance of the Microsoft.PowerShell.Host.ISE.ISEFile class.</span></span> <span data-ttu-id="31b31-106">В этом разделе перечислены его члены (методы и свойства).</span><span class="sxs-lookup"><span data-stu-id="31b31-106">This topic lists its member methods and member properties.</span></span> <span data-ttu-id="31b31-107">Объект **$PsISE.CurrentFile** и все файлы в коллекции "Файлы" на вкладке PowerShell являются экземплярами класса Microsoft.PowerShell.Host.ISE.ISEFile.</span><span class="sxs-lookup"><span data-stu-id="31b31-107">The **$psISE.CurrentFile** and the files in the Files collection in a PowerShell tab are all instances of the Microsoft.PowerShell.Host.ISE.ISEFile class.</span></span>

## <a name="methods"></a><span data-ttu-id="31b31-108">Методы</span><span class="sxs-lookup"><span data-stu-id="31b31-108">Methods</span></span>

### <a name="save-saveencoding-"></a><span data-ttu-id="31b31-109">Save\( \[saveEncoding\] \)</span><span class="sxs-lookup"><span data-stu-id="31b31-109">Save\( \[saveEncoding\] \)</span></span>

<span data-ttu-id="31b31-110">Поддерживается в интегрированной среде сценариев Windows PowerShell 2.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="31b31-110">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="31b31-111">Сохраняет файл на диске.</span><span class="sxs-lookup"><span data-stu-id="31b31-111">Saves the file to disk.</span></span>

<span data-ttu-id="31b31-112">**\[saveEncoding\]**  — необязательный параметр кодировки символов [System.Text.Encoding](https://msdn.microsoft.com/library/system.text.encoding.aspx), используемый для сохраненного файла.</span><span class="sxs-lookup"><span data-stu-id="31b31-112">**\[saveEncoding\]** - optional [System.Text.Encoding](https://msdn.microsoft.com/library/system.text.encoding.aspx) An optional character encoding parameter to be used for the saved file.</span></span> <span data-ttu-id="31b31-113">Значение по умолчанию — **UTF8**.</span><span class="sxs-lookup"><span data-stu-id="31b31-113">The default value is **UTF8**.</span></span>

### <a name="exceptions"></a><span data-ttu-id="31b31-114">Исключения</span><span class="sxs-lookup"><span data-stu-id="31b31-114">Exceptions</span></span>

- <span data-ttu-id="31b31-115">**System.IO.IOException**: Не удалось сохранить файл.</span><span class="sxs-lookup"><span data-stu-id="31b31-115">**System.IO.IOException**: The file could not be saved.</span></span>

```powershell
# Save the file using the default encoding (UTF8)
$psISE.CurrentFile.Save()

# Save the file as ASCII.
$psISE.CurrentFile.Save([System.Text.Encoding]::ASCII)

# Gets the current encoding.
$myfile = $psISE.CurrentFile
$myfile.Encoding
```

### <a name="saveasfilename-saveencoding"></a><span data-ttu-id="31b31-116">SaveAs\(filename, \[saveEncoding\]\)</span><span class="sxs-lookup"><span data-stu-id="31b31-116">SaveAs\(filename, \[saveEncoding\]\)</span></span>

<span data-ttu-id="31b31-117">Поддерживается в интегрированной среде сценариев Windows PowerShell 2.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="31b31-117">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="31b31-118">Сохраняет файл с указанным именем файла и кодировкой.</span><span class="sxs-lookup"><span data-stu-id="31b31-118">Saves the file with the specified file name and encoding.</span></span>

<span data-ttu-id="31b31-119">**filename** — строка. Имя, используемое для сохранения файла.</span><span class="sxs-lookup"><span data-stu-id="31b31-119">**filename** - String The name to be used to save the file.</span></span>

<span data-ttu-id="31b31-120">**\[saveEncoding\]**  — необязательный параметр кодировки символов [System.Text.Encoding](https://msdn.microsoft.com/library/system.text.encoding.aspx), используемый для сохраненного файла.</span><span class="sxs-lookup"><span data-stu-id="31b31-120">**\[saveEncoding\]** - optional [System.Text.Encoding](https://msdn.microsoft.com/library/system.text.encoding.aspx) An optional character encoding parameter to be used for the saved file.</span></span> <span data-ttu-id="31b31-121">Значение по умолчанию — **UTF8**.</span><span class="sxs-lookup"><span data-stu-id="31b31-121">The default value is **UTF8**.</span></span>

### <a name="exceptions"></a><span data-ttu-id="31b31-122">Исключения</span><span class="sxs-lookup"><span data-stu-id="31b31-122">Exceptions</span></span>

- <span data-ttu-id="31b31-123">**System.ArgumentNullException**: **Filename** параметр имеет значение null.</span><span class="sxs-lookup"><span data-stu-id="31b31-123">**System.ArgumentNullException**: The **filename** parameter is null.</span></span>
- <span data-ttu-id="31b31-124">**System.ArgumentException**: **Filename** параметр пуст.</span><span class="sxs-lookup"><span data-stu-id="31b31-124">**System.ArgumentException**: The **filename** parameter is empty.</span></span>
- <span data-ttu-id="31b31-125">**System.IO.IOException**: Не удалось сохранить файл.</span><span class="sxs-lookup"><span data-stu-id="31b31-125">**System.IO.IOException**: The file could not be saved.</span></span>

```powershell
# Save the file with a full path and name.
$fullpath = "c:\temp\newname.txt"
$psISE.CurrentFile.SaveAs($fullPath)
# Save the file with a full path and name and explicitly as UTF8.
$psISE.CurrentFile.SaveAs($fullPath, [System.Text.Encoding]::UTF8)
```

## <a name="properties"></a><span data-ttu-id="31b31-126">Свойства</span><span class="sxs-lookup"><span data-stu-id="31b31-126">Properties</span></span>

### <a name="displayname"></a><span data-ttu-id="31b31-127">DisplayName</span><span class="sxs-lookup"><span data-stu-id="31b31-127">DisplayName</span></span>

<span data-ttu-id="31b31-128">Поддерживается в интегрированной среде сценариев Windows PowerShell 2.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="31b31-128">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="31b31-129">Свойство только для чтения, которое получает строку, содержащую отображаемое имя этого файла.</span><span class="sxs-lookup"><span data-stu-id="31b31-129">The read-only property that gets the string that contains the display name of this file.</span></span> <span data-ttu-id="31b31-130">Имя отображается на вкладке **Файл** в верхней части окна редактора.</span><span class="sxs-lookup"><span data-stu-id="31b31-130">The name is shown on the **File** tab at the top of the editor.</span></span> <span data-ttu-id="31b31-131">Наличие звездочки \(\*\) в конце имени указывает, что в файле есть изменения, которые не были сохранены.</span><span class="sxs-lookup"><span data-stu-id="31b31-131">The presence of an asterisk \(\*\) at the end of the name indicates that the file has changes that have not been saved.</span></span>

```powershell
# Shows the display name of the file.
$psISE.CurrentFile.DisplayName
```

### <a name="editor"></a><span data-ttu-id="31b31-132">Editor</span><span class="sxs-lookup"><span data-stu-id="31b31-132">Editor</span></span>

<span data-ttu-id="31b31-133">Поддерживается в интегрированной среде сценариев Windows PowerShell 2.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="31b31-133">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="31b31-134">Свойство только для чтения, которое получает [объект редактора](The-ISEEditor-Object.md), используемый для указанного файла.</span><span class="sxs-lookup"><span data-stu-id="31b31-134">The read-only property that gets the [editor object](The-ISEEditor-Object.md) that is used for the specified file.</span></span>

```powershell
# Gets the editor and the text.
$psISE.CurrentFile.Editor.Text
```

### <a name="encoding"></a><span data-ttu-id="31b31-135">Encoding</span><span class="sxs-lookup"><span data-stu-id="31b31-135">Encoding</span></span>

<span data-ttu-id="31b31-136">Поддерживается в интегрированной среде сценариев Windows PowerShell 2.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="31b31-136">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="31b31-137">Свойство только для чтения, которое получает исходную кодировку файла.</span><span class="sxs-lookup"><span data-stu-id="31b31-137">The read-only property that gets the original file encoding.</span></span> <span data-ttu-id="31b31-138">Это объект **System.Text.Encoding**.</span><span class="sxs-lookup"><span data-stu-id="31b31-138">This is a **System.Text.Encoding** object.</span></span>

```powershell
# Shows the encoding for the file.
$psISE.CurrentFile.Encoding
```

### <a name="fullpath"></a><span data-ttu-id="31b31-139">FullPath</span><span class="sxs-lookup"><span data-stu-id="31b31-139">FullPath</span></span>

<span data-ttu-id="31b31-140">Поддерживается в интегрированной среде сценариев Windows PowerShell 2.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="31b31-140">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="31b31-141">Свойство только для чтения, которое получает строку, указывающую полный путь к открытому файлу.</span><span class="sxs-lookup"><span data-stu-id="31b31-141">The read-only property that gets the string that specifies the full path of the opened file.</span></span>

```powershell
# Shows the full path for the file.
$psISE.CurrentFile.FullPath
```

### <a name="issaved"></a><span data-ttu-id="31b31-142">IsSaved</span><span class="sxs-lookup"><span data-stu-id="31b31-142">IsSaved</span></span>

<span data-ttu-id="31b31-143">Поддерживается в интегрированной среде сценариев Windows PowerShell 2.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="31b31-143">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="31b31-144">Логическое свойство только для чтения, которое возвращает значение **$true**, если файл был сохранен после последнего изменения.</span><span class="sxs-lookup"><span data-stu-id="31b31-144">The read-only Boolean property that returns **$true** if the file has been saved after it was last modified.</span></span>

```powershell
# Determines whether the file has been saved since it was last modified.
$myfile = $psISE.CurrentFile
$myfile.IsSaved
```

### <a name="isuntitled"></a><span data-ttu-id="31b31-145">IsUntitled</span><span class="sxs-lookup"><span data-stu-id="31b31-145">IsUntitled</span></span>

<span data-ttu-id="31b31-146">Поддерживается в интегрированной среде сценариев Windows PowerShell 2.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="31b31-146">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="31b31-147">Свойство только для чтения, которое возвращает значение **$true**, если для файла не задано имя.</span><span class="sxs-lookup"><span data-stu-id="31b31-147">The read-only property that returns **$true** if the file has never been given a title.</span></span>

```powershell
# Determines whether the file has never been given a title.
$psISE.CurrentFile.IsUntitled
$psISE.CurrentFile.SaveAs("temp.txt")
$psISE.CurrentFile.IsUntitled
```

## <a name="see-also"></a><span data-ttu-id="31b31-148">См. также</span><span class="sxs-lookup"><span data-stu-id="31b31-148">See Also</span></span>

- [<span data-ttu-id="31b31-149">Объект ISEFileCollection</span><span class="sxs-lookup"><span data-stu-id="31b31-149">The ISEFileCollectionObject</span></span>](The-ISEFileCollection-Object.md)
- [<span data-ttu-id="31b31-150">Назначение объектной модели скриптов интегрированной среды скриптов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="31b31-150">Purpose of the Windows PowerShell ISE Scripting Object Model</span></span>](Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [<span data-ttu-id="31b31-151">Иерархия объектной модели интегрированной среды скриптов</span><span class="sxs-lookup"><span data-stu-id="31b31-151">The ISE Object Model Hierarchy</span></span>](The-ISE-Object-Model-Hierarchy.md)