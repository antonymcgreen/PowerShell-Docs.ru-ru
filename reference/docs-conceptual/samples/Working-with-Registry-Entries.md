---
ms.date: 06/05/2017
keywords: powershell,командлет
title: Работа с записями реестра
ms.assetid: fd254570-27ac-4cc9-81d4-011afd29b7dc
ms.openlocfilehash: 8483b6f98739697b24a13055dfffbc7b5bacc2cc
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "55681544"
---
# <a name="working-with-registry-entries"></a><span data-ttu-id="aee97-103">Работа с записями реестра</span><span class="sxs-lookup"><span data-stu-id="aee97-103">Working with Registry Entries</span></span>

<span data-ttu-id="aee97-104">Так как записи реестра являются свойствами разделов и их невозможно открыть напрямую, при работе с ними необходимо использовать немного другой подход.</span><span class="sxs-lookup"><span data-stu-id="aee97-104">Because registry entries are properties of keys and, as such, cannot be directly browsed, we need to take a slightly different approach when working with them.</span></span>

### <a name="listing-registry-entries"></a><span data-ttu-id="aee97-105">Создание списков записей реестра</span><span class="sxs-lookup"><span data-stu-id="aee97-105">Listing Registry Entries</span></span>

<span data-ttu-id="aee97-106">Существует несколько способов просмотра реестра.</span><span class="sxs-lookup"><span data-stu-id="aee97-106">There are many different ways to examine registry entries.</span></span> <span data-ttu-id="aee97-107">Самый простой — получить имена свойств, связанные с разделом.</span><span class="sxs-lookup"><span data-stu-id="aee97-107">The simplest way is to get the property names associated with a key.</span></span> <span data-ttu-id="aee97-108">Например, чтобы увидеть имена записей в разделе реестра `HKEY_LOCAL_MACHINE\Software\Microsoft\Windows\CurrentVersion`, используйте `Get-Item`.</span><span class="sxs-lookup"><span data-stu-id="aee97-108">For example, to see the names of the entries in the registry key `HKEY_LOCAL_MACHINE\Software\Microsoft\Windows\CurrentVersion`, use `Get-Item`.</span></span> <span data-ttu-id="aee97-109">Разделы реестра содержат свойство с универсальным именем Property, которое является списком записей реестра в разделе.</span><span class="sxs-lookup"><span data-stu-id="aee97-109">Registry keys have a property with the generic name of "Property" that is a list of registry entries in the key.</span></span>
<span data-ttu-id="aee97-110">Следующая команда выбирает свойство Property и расширяет элементы так, чтобы они отображались в списке:</span><span class="sxs-lookup"><span data-stu-id="aee97-110">The following command selects the Property property and expands the items so that they are displayed in a list:</span></span>

```powershell
Get-Item -Path Registry::HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion |
  Select-Object -ExpandProperty Property
```

```Output
DevicePath
MediaPathUnexpanded
ProgramFilesDir
CommonFilesDir
ProductId
```

<span data-ttu-id="aee97-111">Чтобы просмотреть записи реестра в более удобочитаемой форме, используйте `Get-ItemProperty`:</span><span class="sxs-lookup"><span data-stu-id="aee97-111">To view the registry entries in a more readable form, use `Get-ItemProperty`:</span></span>

```powershell
Get-ItemProperty -Path Registry::HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion
```

```Output
PSPath              : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\SO
                      FTWARE\Microsoft\Windows\CurrentVersion
PSParentPath        : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\SO
                      FTWARE\Microsoft\Windows
PSChildName         : CurrentVersion
PSDrive             : HKLM
PSProvider          : Microsoft.PowerShell.Core\Registry
DevicePath          : C:\WINDOWS\inf
MediaPathUnexpanded : C:\WINDOWS\Media
ProgramFilesDir     : C:\Program Files
CommonFilesDir      : C:\Program Files\Common Files
ProductId           : 76487-338-1167776-22465
WallPaperDir        : C:\WINDOWS\Web\Wallpaper
MediaPath           : C:\WINDOWS\Media
ProgramFilesPath    : C:\Program Files
PF_AccessoriesName  : Accessories
(default)           :
```

<span data-ttu-id="aee97-112">Все свойства Windows PowerShell раздела имеют префиксы PS, например **PSPath**, **PSParentPath**, **PSChildName** и **PSProvider**.</span><span class="sxs-lookup"><span data-stu-id="aee97-112">The Windows PowerShell-related properties for the key are all prefixed with "PS", such as **PSPath**, **PSParentPath**, **PSChildName**, and **PSProvider**.</span></span>

<span data-ttu-id="aee97-113">Для ссылки на текущее расположение можно использовать нотацию "`*.*`.".</span><span class="sxs-lookup"><span data-stu-id="aee97-113">You can use the `*.*` notation for referring to the current location.</span></span> <span data-ttu-id="aee97-114">Можно использовать `Set-Location` менять **CurrentVersion** контейнер реестра первого:</span><span class="sxs-lookup"><span data-stu-id="aee97-114">You can use `Set-Location` to change to the **CurrentVersion** registry container first:</span></span>

```powershell
Set-Location -Path Registry::HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion
```

<span data-ttu-id="aee97-115">Кроме того, можно использовать встроенный диск HKLM PSDrive с `Set-Location`:</span><span class="sxs-lookup"><span data-stu-id="aee97-115">Alternatively, you can use the built-in HKLM PSDrive with `Set-Location`:</span></span>

```powershell
Set-Location -Path hklm:\SOFTWARE\Microsoft\Windows\CurrentVersion
```

<span data-ttu-id="aee97-116">Затем можно использовать нотацию "`*.*`." для текущего расположения, чтобы перечислить свойства без указания полного пути:</span><span class="sxs-lookup"><span data-stu-id="aee97-116">You can then use the `*.*` notation for the current location to list the properties without specifying a full path:</span></span>

```powershell
Get-ItemProperty -Path .
```

```Output
...
DevicePath          : C:\WINDOWS\inf
MediaPathUnexpanded : C:\WINDOWS\Media
ProgramFilesDir     : C:\Program Files
...
```

<span data-ttu-id="aee97-117">Расширение пути работает так же, как и в файловой системе, поэтому в этом расположении можно получить **ItemProperty** листинг для `HKLM:\SOFTWARE\Microsoft\Windows\Help` с помощью `Get-ItemProperty -Path ..\Help`.</span><span class="sxs-lookup"><span data-stu-id="aee97-117">Path expansion works the same as it does within the file system, so from this location you can get the **ItemProperty** listing for `HKLM:\SOFTWARE\Microsoft\Windows\Help` by using `Get-ItemProperty -Path ..\Help`.</span></span>

### <a name="getting-a-single-registry-entry"></a><span data-ttu-id="aee97-118">Получение одной записи реестра</span><span class="sxs-lookup"><span data-stu-id="aee97-118">Getting a Single Registry Entry</span></span>

<span data-ttu-id="aee97-119">Если необходимо получить конкретную запись в разделе реестра, можно использовать один из нескольких возможных подходов.</span><span class="sxs-lookup"><span data-stu-id="aee97-119">If you want to retrieve a specific entry in a registry key, you can use one of several possible approaches.</span></span> <span data-ttu-id="aee97-120">Этот пример находит значение **DevicePath** в `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion`.</span><span class="sxs-lookup"><span data-stu-id="aee97-120">This example finds the value of **DevicePath** in `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion`.</span></span>

<span data-ttu-id="aee97-121">С помощью `Get-ItemProperty`, использовать **путь** параметр для указания имени ключа и **имя** параметр, чтобы указать имя **DevicePath** запись.</span><span class="sxs-lookup"><span data-stu-id="aee97-121">Using `Get-ItemProperty`, use the **Path** parameter to specify the name of the key, and the **Name** parameter to specify the name of the **DevicePath** entry.</span></span>

```powershell
Get-ItemProperty -Path HKLM:\Software\Microsoft\Windows\CurrentVersion -Name DevicePath
```

```Output
PSPath       : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\Software\
               Microsoft\Windows\CurrentVersion
PSParentPath : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\Software\
               Microsoft\Windows
PSChildName  : CurrentVersion
PSDrive      : HKLM
PSProvider   : Microsoft.PowerShell.Core\Registry
DevicePath   : C:\WINDOWS\inf
```

<span data-ttu-id="aee97-122">Эта команда возвращает стандартные свойства Windows PowerShell, а также свойство **DevicePath**.</span><span class="sxs-lookup"><span data-stu-id="aee97-122">This command returns the standard Windows PowerShell properties as well as the **DevicePath** property.</span></span>

> [!NOTE]
> <span data-ttu-id="aee97-123">Несмотря на то что `Get-ItemProperty` имеет **фильтра**, **Include**, и **исключить** параметры, они не может использоваться для фильтрации по имени свойства.</span><span class="sxs-lookup"><span data-stu-id="aee97-123">Although `Get-ItemProperty` has **Filter**, **Include**, and **Exclude** parameters, they cannot be used to filter by property name.</span></span> <span data-ttu-id="aee97-124">Эти параметры относятся к разделам реестра, пути к элементам и не к записям реестра.</span><span class="sxs-lookup"><span data-stu-id="aee97-124">These parameters refer to registry keys, which are item paths and not registry entries.</span></span> <span data-ttu-id="aee97-125">Записи реестра, которые являются свойствами элемента.</span><span class="sxs-lookup"><span data-stu-id="aee97-125">Registry entries which are item properties.</span></span>

<span data-ttu-id="aee97-126">Другой вариант — использовать средство командной строки Reg.exe.</span><span class="sxs-lookup"><span data-stu-id="aee97-126">Another option is to use the Reg.exe command line tool.</span></span> <span data-ttu-id="aee97-127">Для получения справки по reg.exe введите `reg.exe /?` в командной строке.</span><span class="sxs-lookup"><span data-stu-id="aee97-127">For help with reg.exe, type `reg.exe /?` at a command prompt.</span></span> <span data-ttu-id="aee97-128">Чтобы найти запись DevicePath, используйте reg.exe, как показано в следующей команде:</span><span class="sxs-lookup"><span data-stu-id="aee97-128">To find the DevicePath entry, use reg.exe as shown in the following command:</span></span>

```powershell
reg query HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion /v DevicePath
```

```Output
! REG.EXE VERSION 3.0

HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion
    DevicePath  REG_EXPAND_SZ   %SystemRoot%\inf
```

<span data-ttu-id="aee97-129">Также можно использовать объект **WshShell COM**, чтобы найти некоторые записи реестра, хотя этот метод не работает с большими двоичными данными или именами записей реестра, включающими такие символы, как "\\".</span><span class="sxs-lookup"><span data-stu-id="aee97-129">You can also use the **WshShell** COM object as well to find some registry entries, although this method does not work with large binary data or with registry entry names that include characters such as "\\").</span></span> <span data-ttu-id="aee97-130">Добавьте имя свойства с разделителем "\\" в путь элемента:</span><span class="sxs-lookup"><span data-stu-id="aee97-130">Append the property name to the item path with a \\ separator:</span></span>

```powershell
(New-Object -ComObject WScript.Shell).RegRead("HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\DevicePath")
```

```Output
%SystemRoot%\inf
```

### <a name="setting-a-single-registry-entry"></a><span data-ttu-id="aee97-131">Настройка одной записи реестра</span><span class="sxs-lookup"><span data-stu-id="aee97-131">Setting a Single Registry Entry</span></span>

<span data-ttu-id="aee97-132">Если вы хотите изменить определенную запись в раздел реестра, можно использовать один из нескольких возможных подходов.</span><span class="sxs-lookup"><span data-stu-id="aee97-132">If you want to change a specific entry in a registry key, you can use one of several possible approaches.</span></span> <span data-ttu-id="aee97-133">В этом примере изменяется **путь** запись в разделе `HKEY_CURRENT_USER\Environment`.</span><span class="sxs-lookup"><span data-stu-id="aee97-133">This example modifies the **Path** entry under `HKEY_CURRENT_USER\Environment`.</span></span> <span data-ttu-id="aee97-134">**Путь** запись указывает место для поиска исполняемых файлов.</span><span class="sxs-lookup"><span data-stu-id="aee97-134">The **Path** entry specifies where to find executable files.</span></span>

1. <span data-ttu-id="aee97-135">Получить текущее значение **путь** с использованием `Get-ItemProperty`.</span><span class="sxs-lookup"><span data-stu-id="aee97-135">Retrieve the current value of the **Path** entry using `Get-ItemProperty`.</span></span>
2. <span data-ttu-id="aee97-136">Добавить новое значение, отделив его с `;`.</span><span class="sxs-lookup"><span data-stu-id="aee97-136">Add the new value, separating it with a `;`.</span></span>
3. <span data-ttu-id="aee97-137">Используйте `Set-ItemProperty` с указанным ключом, именем записи и значение, чтобы изменить запись в реестр.</span><span class="sxs-lookup"><span data-stu-id="aee97-137">Use `Set-ItemProperty` with the specified key, entry name, and value to modify the registry entry.</span></span>

```powershell
$value = Get-ItemProperty -Path HKCU:\Environment -Name Path
$newpath = $value.Path += ";C:\src\bin\"
Set-ItemProperty -Path HKCU:\Environment -Name Path -Value $newpath
```

> [!NOTE]
> <span data-ttu-id="aee97-138">Несмотря на то что `Set-ItemProperty` имеет **фильтра**, **Include**, и **исключить** параметры, они не может использоваться для фильтрации по имени свойства.</span><span class="sxs-lookup"><span data-stu-id="aee97-138">Although `Set-ItemProperty` has **Filter**, **Include**, and **Exclude** parameters, they cannot be used to filter by property name.</span></span> <span data-ttu-id="aee97-139">Эти параметры относятся в разделам реестра (путям элементов), а не к записям реестра (свойствам элементов).</span><span class="sxs-lookup"><span data-stu-id="aee97-139">These parameters refer to registry keys—which are item paths—and not registry entries—which are item properties.</span></span>

<span data-ttu-id="aee97-140">Другой вариант — использовать средство командной строки Reg.exe.</span><span class="sxs-lookup"><span data-stu-id="aee97-140">Another option is to use the Reg.exe command line tool.</span></span> <span data-ttu-id="aee97-141">Для получения справки по reg.exe введите **reg.exe /?**.</span><span class="sxs-lookup"><span data-stu-id="aee97-141">For help with reg.exe, type **reg.exe /?**</span></span>
<span data-ttu-id="aee97-142">в командной строке.</span><span class="sxs-lookup"><span data-stu-id="aee97-142">at a command prompt.</span></span>

<span data-ttu-id="aee97-143">В следующем примере изменяется **путь** записи путем удаления пути, добавленные в приведенном выше примере.</span><span class="sxs-lookup"><span data-stu-id="aee97-143">The following example changes the **Path** entry by removing the path added in the example above.</span></span>
<span data-ttu-id="aee97-144">`Get-ItemProperty` по-прежнему используется для получения текущего значения, чтобы избежать необходимости анализировать строки, возвращаемой `reg query`.</span><span class="sxs-lookup"><span data-stu-id="aee97-144">`Get-ItemProperty` is still used to retrieve the current value to avoid having to parse the string returned from `reg query`.</span></span> <span data-ttu-id="aee97-145">**Подстроки** и **LastIndexOf** методы используются для получения добавляемый путь последнего **путь** запись.</span><span class="sxs-lookup"><span data-stu-id="aee97-145">The **SubString** and **LastIndexOf** methods are used to retrieve the last path added to the **Path** entry.</span></span>

```powershell
$value = Get-ItemProperty -Path HKCU:\Environment -Name Path
$newpath = $value.Path.SubString(0, $value.Path.LastIndexOf(';'))
reg add HKCU\Environment /v Path /d $newpath /f
```

```Output
The operation completed successfully.
```

### <a name="creating-new-registry-entries"></a><span data-ttu-id="aee97-146">Создание новых записей реестра</span><span class="sxs-lookup"><span data-stu-id="aee97-146">Creating New Registry Entries</span></span>

<span data-ttu-id="aee97-147">Чтобы добавить новую запись с именем «PowerShellPath» **CurrentVersion** использования ключей, `New-ItemProperty` с путем к разделу, именем записи и значение записи.</span><span class="sxs-lookup"><span data-stu-id="aee97-147">To add a new entry named "PowerShellPath" to the **CurrentVersion** key, use `New-ItemProperty` with the path to the key, the entry name, and the value of the entry.</span></span> <span data-ttu-id="aee97-148">В этом примере использовано значение переменной Windows PowerShell `$PSHome`, которой хранится путь к каталогу установки для Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="aee97-148">For this example, we will take the value of the Windows PowerShell variable `$PSHome`, which stores the path to the installation directory for Windows PowerShell.</span></span>

<span data-ttu-id="aee97-149">Вы можете добавить новую запись в раздел с помощью следующей команды, и команда также вернет сведения о новой записи:</span><span class="sxs-lookup"><span data-stu-id="aee97-149">You can add the new entry to the key by using the following command, and the command also returns information about the new entry:</span></span>

```powershell
New-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion -Name PowerShellPath -PropertyType String -Value $PSHome
```

```Output
PSPath         : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion
PSParentPath   : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows
PSChildName    : CurrentVersion
PSDrive        : HKLM
PSProvider     : Microsoft.PowerShell.Core\Registry
PowerShellPath : C:\Program Files\Windows PowerShell\v1.0
```

<span data-ttu-id="aee97-150">Значение **PropertyType** должно быть именем элемента перечисления **Microsoft.Win32.RegistryValueKind** из следующей таблицы:</span><span class="sxs-lookup"><span data-stu-id="aee97-150">The **PropertyType** must be the name of a **Microsoft.Win32.RegistryValueKind** enumeration member from the following table:</span></span>

|<span data-ttu-id="aee97-151">Значение PropertyType</span><span class="sxs-lookup"><span data-stu-id="aee97-151">PropertyType Value</span></span>|<span data-ttu-id="aee97-152">Значение</span><span class="sxs-lookup"><span data-stu-id="aee97-152">Meaning</span></span>|
|----------------------|-----------|
|<span data-ttu-id="aee97-153">Двоичные данные</span><span class="sxs-lookup"><span data-stu-id="aee97-153">Binary</span></span>|<span data-ttu-id="aee97-154">Двоичные данные</span><span class="sxs-lookup"><span data-stu-id="aee97-154">Binary data</span></span>|
|<span data-ttu-id="aee97-155">DWord</span><span class="sxs-lookup"><span data-stu-id="aee97-155">DWord</span></span>|<span data-ttu-id="aee97-156">Число, которое является допустимым UInt32</span><span class="sxs-lookup"><span data-stu-id="aee97-156">A number that is a valid UInt32</span></span>|
|<span data-ttu-id="aee97-157">ExpandString</span><span class="sxs-lookup"><span data-stu-id="aee97-157">ExpandString</span></span>|<span data-ttu-id="aee97-158">Строка, которая может содержать динамически раскрывающиеся переменные среды</span><span class="sxs-lookup"><span data-stu-id="aee97-158">A string that can contain environment variables that are dynamically expanded</span></span>|
|<span data-ttu-id="aee97-159">MultiString</span><span class="sxs-lookup"><span data-stu-id="aee97-159">MultiString</span></span>|<span data-ttu-id="aee97-160">Многострочная строка</span><span class="sxs-lookup"><span data-stu-id="aee97-160">A multiline string</span></span>|
|<span data-ttu-id="aee97-161">Строка</span><span class="sxs-lookup"><span data-stu-id="aee97-161">String</span></span>|<span data-ttu-id="aee97-162">Любое строковое значение</span><span class="sxs-lookup"><span data-stu-id="aee97-162">Any string value</span></span>|
|<span data-ttu-id="aee97-163">QWord</span><span class="sxs-lookup"><span data-stu-id="aee97-163">QWord</span></span>|<span data-ttu-id="aee97-164">8 байтов двоичных данных</span><span class="sxs-lookup"><span data-stu-id="aee97-164">8 bytes of binary data</span></span>|

> [!NOTE]
> <span data-ttu-id="aee97-165">Запись реестра можно добавить в несколько расположений, указав массив значений для параметра **Path**:</span><span class="sxs-lookup"><span data-stu-id="aee97-165">You can add a registry entry to multiple locations by specifying an array of values for the **Path** parameter:</span></span>

```powershell
New-ItemProperty -Name PowerShellPath -PropertyType String -Value $PSHome `
  -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion, HKCU:\SOFTWARE\Microsoft\Windows\CurrentVersion
```

<span data-ttu-id="aee97-166">Кроме того, можно перезаписать существующие значение записи реестра, добавив **Force** параметра к любому `New-ItemProperty` команды.</span><span class="sxs-lookup"><span data-stu-id="aee97-166">You can also overwrite a pre-existing registry entry value by adding the **Force** parameter to any `New-ItemProperty` command.</span></span>

### <a name="renaming-registry-entries"></a><span data-ttu-id="aee97-167">Переименование записей реестра</span><span class="sxs-lookup"><span data-stu-id="aee97-167">Renaming Registry Entries</span></span>

<span data-ttu-id="aee97-168">Чтобы переименовать **PowerShellPath** записи в «PSHome», используйте `Rename-ItemProperty`:</span><span class="sxs-lookup"><span data-stu-id="aee97-168">To rename the **PowerShellPath** entry to "PSHome," use `Rename-ItemProperty`:</span></span>

```powershell
Rename-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion -Name PowerShellPath -NewName PSHome
```

<span data-ttu-id="aee97-169">Чтобы отобразить переименованное значение, добавьте параметр **PassThru** в команду.</span><span class="sxs-lookup"><span data-stu-id="aee97-169">To display the renamed value, add the **PassThru** parameter to the command.</span></span>

```powershell
Rename-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion -Name PowerShellPath -NewName PSHome -passthru
```

### <a name="deleting-registry-entries"></a><span data-ttu-id="aee97-170">Удаление записей реестра</span><span class="sxs-lookup"><span data-stu-id="aee97-170">Deleting Registry Entries</span></span>

<span data-ttu-id="aee97-171">Чтобы удалить записи реестра PSHome и PowerShellPath, используйте `Remove-ItemProperty`:</span><span class="sxs-lookup"><span data-stu-id="aee97-171">To delete both the PSHome and PowerShellPath registry entries, use `Remove-ItemProperty`:</span></span>

```powershell
Remove-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion -Name PSHome
Remove-ItemProperty -Path HKCU:\SOFTWARE\Microsoft\Windows\CurrentVersion -Name PowerShellPath
```
