---
description: Описывает, как получить доступ к элементам из рабочего расположения в PowerShell.
keywords: powershell,командлет
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_locations?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Locations
ms.openlocfilehash: 56af758f06e365eb070786e50d8f8309d8f608fd
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93230890"
---
# <a name="about_locations"></a><span data-ttu-id="0a20b-104">about_Locations</span><span class="sxs-lookup"><span data-stu-id="0a20b-104">about_Locations</span></span>

## <a name="short-description"></a><span data-ttu-id="0a20b-105">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="0a20b-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="0a20b-106">Описывает, как получить доступ к элементам из рабочего расположения в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0a20b-106">Describes how to access items from the working location in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="0a20b-107">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="0a20b-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="0a20b-108">Текущее рабочее расположение является расположением по умолчанию, в которое указывает команда.</span><span class="sxs-lookup"><span data-stu-id="0a20b-108">The current working location is the default location to which commands point.</span></span>
<span data-ttu-id="0a20b-109">Иными словами, это расположение, используемое PowerShell, если не указан явный путь к элементу или расположению, на которое влияет команда.</span><span class="sxs-lookup"><span data-stu-id="0a20b-109">In other words, this is the location that PowerShell uses if you do not supply an explicit path to the item or location that is affected by the command.</span></span> <span data-ttu-id="0a20b-110">В большинстве случаев текущее рабочее расположение — это диск, к которому обращается поставщик файловой системы PowerShell, и в некоторых случаях каталог на этом диске.</span><span class="sxs-lookup"><span data-stu-id="0a20b-110">In most cases, the current working location is a drive accessed through the PowerShell FileSystem provider and, in some cases, a directory on that drive.</span></span>
<span data-ttu-id="0a20b-111">Например, вы можете задать для текущего рабочего расположения следующее расположение:</span><span class="sxs-lookup"><span data-stu-id="0a20b-111">For example, you might set your current working location to the following location:</span></span>

```powershell
C:\Program Files\Windows PowerShell
```

<span data-ttu-id="0a20b-112">В результате все команды обрабатываются из этого расположения, если только не предоставлен явно другой путь.</span><span class="sxs-lookup"><span data-stu-id="0a20b-112">As a result, all commands are processed from this location unless another path is explicitly provided.</span></span>

<span data-ttu-id="0a20b-113">PowerShell поддерживает текущее рабочее расположение для каждого диска, даже если этот диск не является текущим.</span><span class="sxs-lookup"><span data-stu-id="0a20b-113">PowerShell maintains the current working location for each drive even when the drive is not the current drive.</span></span> <span data-ttu-id="0a20b-114">Это позволяет получить доступ к элементам из текущего рабочего расположения, обратившись только к диску другого расположения.</span><span class="sxs-lookup"><span data-stu-id="0a20b-114">This allows you to access items from the current working location by referring only to the drive of another location.</span></span>
<span data-ttu-id="0a20b-115">Например, предположим, что текущее рабочее расположение — C: \\ Windows.</span><span class="sxs-lookup"><span data-stu-id="0a20b-115">For example, suppose that your current working location is C:\\Windows.</span></span> <span data-ttu-id="0a20b-116">Теперь предположим, что вы используете следующую команду, чтобы изменить текущее рабочее расположение на диск HKLM:.</span><span class="sxs-lookup"><span data-stu-id="0a20b-116">Now, suppose you use the following command to change your current working location to the HKLM: drive:</span></span>

```powershell
Set-Location HKLM:
```

<span data-ttu-id="0a20b-117">Несмотря на то что текущее расположение теперь является диском реестра, вы по-прежнему можете обращаться к элементам в каталоге C: \\ Windows, просто используя диск c:, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="0a20b-117">Although your current location is now the registry drive, you can still access items in the C:\\Windows directory simply by using the C: drive, as shown in the following example:</span></span>

```powershell
Get-ChildItem C:
```

<span data-ttu-id="0a20b-118">PowerShell запоминает, что текущим рабочим расположением для этого диска является каталог Windows, поэтому он извлекает элементы из этого каталога.</span><span class="sxs-lookup"><span data-stu-id="0a20b-118">PowerShell remembers that your current working location for that drive is the Windows directory, so it retrieves items from that directory.</span></span> <span data-ttu-id="0a20b-119">Результаты будут такими же, если вы выполнили следующую команду:</span><span class="sxs-lookup"><span data-stu-id="0a20b-119">The results would be the same if you ran the following command:</span></span>

```powershell
Get-ChildItem C:\Windows
```

<span data-ttu-id="0a20b-120">В PowerShell для определения текущего рабочего расположения можно использовать команду Get-Location, а для установки текущего рабочего расположения можно использовать команду Set-Location.</span><span class="sxs-lookup"><span data-stu-id="0a20b-120">In PowerShell, you can use the Get-Location command to determine the current working location, and you can use the Set-Location command to set the current working location.</span></span> <span data-ttu-id="0a20b-121">Например, следующая команда устанавливает текущее рабочее расположение в каталог Windows диска C:.</span><span class="sxs-lookup"><span data-stu-id="0a20b-121">For example, the following command sets the current working location to the Windows directory of the C: drive:</span></span>

```powershell
Set-Location c:\windows
```

<span data-ttu-id="0a20b-122">После задания текущего рабочего расположения можно по-прежнему обращаться к элементам с других дисков, просто включив в команду имя диска (за которым следует двоеточие), как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="0a20b-122">After you set the current working location, you can still access items from other drives simply by including the drive name (followed by a colon) in the command, as shown in the following example:</span></span>

```powershell
Get-ChildItem HKLM:\software
```

<span data-ttu-id="0a20b-123">Пример команды извлекает список элементов в контейнере программного обеспечения куста локального компьютера HKEY в реестре.</span><span class="sxs-lookup"><span data-stu-id="0a20b-123">The example command retrieves a list of items in the Software container of the HKEY Local Machine hive in the registry.</span></span>

<span data-ttu-id="0a20b-124">PowerShell также позволяет использовать специальные символы для представления текущего рабочего расположения и его родительского расположения.</span><span class="sxs-lookup"><span data-stu-id="0a20b-124">PowerShell also allows you to use special characters to represent the current working location and its parent location.</span></span> <span data-ttu-id="0a20b-125">Для представления текущего рабочего расположения используйте одну точку.</span><span class="sxs-lookup"><span data-stu-id="0a20b-125">To represent the current working location, use a single period.</span></span> <span data-ttu-id="0a20b-126">Для представления родителя текущего рабочего расположения используйте две точки.</span><span class="sxs-lookup"><span data-stu-id="0a20b-126">To represent the parent of the current working location, use two periods.</span></span> <span data-ttu-id="0a20b-127">Например, следующий параметр указывает подкаталог System в текущем рабочем расположении:</span><span class="sxs-lookup"><span data-stu-id="0a20b-127">For example, the following specifies the System subdirectory in the current working location:</span></span>

```powershell
Get-ChildItem .\system
```

<span data-ttu-id="0a20b-128">Если текущее рабочее расположение — C: \\ Windows, эта команда возвращает список всех элементов в c: \\ Windows \\ System.</span><span class="sxs-lookup"><span data-stu-id="0a20b-128">If the current working location is C:\\Windows, this command returns a list of all the items in C:\\Windows\\System.</span></span> <span data-ttu-id="0a20b-129">Однако при использовании двух точек используется родительский каталог текущего рабочего каталога, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="0a20b-129">However, if you use two periods, the parent directory of the current working directory is used, as shown in the following example:</span></span>

```powershell
Get-ChildItem ..\"program files"
```

<span data-ttu-id="0a20b-130">В этом случае PowerShell обрабатывает две точки как диск C:, поэтому команда извлекает все элементы в каталоге C: \\ Program Files.</span><span class="sxs-lookup"><span data-stu-id="0a20b-130">In this case, PowerShell treats the two periods as the C: drive, so the command retrieves all the items in the C:\\Program Files directory.</span></span>

<span data-ttu-id="0a20b-131">Путь, начинающийся с косой черты, определяет путь из корня текущего диска.</span><span class="sxs-lookup"><span data-stu-id="0a20b-131">A path beginning with a slash identifies a path from the root of the current drive.</span></span> <span data-ttu-id="0a20b-132">Например, если текущее рабочее расположение — C: \\ Program Files \\ PowerShell, корневая папка диска — C. Поэтому следующая команда выводит список всех элементов в каталоге C: \\ Windows:</span><span class="sxs-lookup"><span data-stu-id="0a20b-132">For example, if your current working location is C:\\Program Files\\PowerShell, the root of your drive is C. Therefore, the following command lists all items in the C:\\Windows directory:</span></span>

```powershell
Get-ChildItem \windows
```

<span data-ttu-id="0a20b-133">Если не указать путь, начинающийся с имени диска, косой черты или точки при указании имени контейнера или элемента, предполагается, что контейнер или элемент находится в текущем рабочем расположении.</span><span class="sxs-lookup"><span data-stu-id="0a20b-133">If you do not specify a path beginning with a drive name, slash, or period when supplying the name of a container or item, the container or item is assumed to be located in the current working location.</span></span> <span data-ttu-id="0a20b-134">Например, если текущее рабочее расположение — C: \\ Windows, следующая команда возвращает все элементы в \\ \\ системном каталоге C: Windows:</span><span class="sxs-lookup"><span data-stu-id="0a20b-134">For example, if your current working location is C:\\Windows, the following command returns all the items in the C:\\Windows\\System directory:</span></span>

```powershell
Get-ChildItem system
```

<span data-ttu-id="0a20b-135">Если указать имя файла, а не имя каталога, PowerShell возвращает сведения об этом файле (предполагается, что файл находится в текущем рабочем расположении).</span><span class="sxs-lookup"><span data-stu-id="0a20b-135">If you specify a file name rather than a directory name, PowerShell returns details about that file (assuming that file is located in the current working location).</span></span>

## <a name="see-also"></a><span data-ttu-id="0a20b-136">СМ. ТАКЖЕ</span><span class="sxs-lookup"><span data-stu-id="0a20b-136">SEE ALSO</span></span>

[<span data-ttu-id="0a20b-137">Set-Location</span><span class="sxs-lookup"><span data-stu-id="0a20b-137">Set-Location</span></span>](xref:Microsoft.PowerShell.Management.Set-Location)

[<span data-ttu-id="0a20b-138">about_Providers</span><span class="sxs-lookup"><span data-stu-id="0a20b-138">about_Providers</span></span>](about_Providers.md)

[<span data-ttu-id="0a20b-139">about_Path_Syntax</span><span class="sxs-lookup"><span data-stu-id="0a20b-139">about_Path_Syntax</span></span>](about_Path_Syntax.md)

