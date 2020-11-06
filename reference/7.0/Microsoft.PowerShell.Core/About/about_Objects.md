---
description: Содержит ценные сведения об объектах в PowerShell.
keywords: powershell,командлет
Locale: en-US
ms.date: 11/30/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_objects?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Objects
ms.openlocfilehash: b845dc8b55a19bb642c194398b0c9f5f13d24cb3
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93232497"
---
# <a name="about-objects"></a><span data-ttu-id="2e218-104">Об объектах</span><span class="sxs-lookup"><span data-stu-id="2e218-104">About Objects</span></span>

## <a name="short-description"></a><span data-ttu-id="2e218-105">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="2e218-105">Short Description</span></span>
<span data-ttu-id="2e218-106">Содержит ценные сведения об объектах в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2e218-106">Provides essential information about objects in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="2e218-107">Полное описание</span><span class="sxs-lookup"><span data-stu-id="2e218-107">Long Description</span></span>

<span data-ttu-id="2e218-108">Каждое действие, выполняемое в PowerShell, выполняется в контексте объектов.</span><span class="sxs-lookup"><span data-stu-id="2e218-108">Every action you take in PowerShell occurs within the context of objects.</span></span> <span data-ttu-id="2e218-109">По мере перемещения данных от одной команды к другой она перемещается как один или несколько идентифицируемых объектов.</span><span class="sxs-lookup"><span data-stu-id="2e218-109">As data moves from one command to the next, it moves as one or more identifiable objects.</span></span> <span data-ttu-id="2e218-110">Затем объект представляет собой коллекцию данных, представляющих элемент.</span><span class="sxs-lookup"><span data-stu-id="2e218-110">An object, then, is a collection of data that represents an item.</span></span> <span data-ttu-id="2e218-111">Объект состоит из трех типов данных: типа объектов, его методов и свойств.</span><span class="sxs-lookup"><span data-stu-id="2e218-111">An object is made up of three types of data: the objects type, its methods, and its properties.</span></span>

## <a name="types-methods-and-properties"></a><span data-ttu-id="2e218-112">Типы, методы и свойства</span><span class="sxs-lookup"><span data-stu-id="2e218-112">Types, Methods, and Properties</span></span>

<span data-ttu-id="2e218-113">Тип объекта указывает на тип объекта.</span><span class="sxs-lookup"><span data-stu-id="2e218-113">The object type tells what kind of object it is.</span></span> <span data-ttu-id="2e218-114">Например, объект, представляющий файл, является объектом FileInfo.</span><span class="sxs-lookup"><span data-stu-id="2e218-114">For example, an object that represents a file is a FileInfo object.</span></span>

<span data-ttu-id="2e218-115">Методы объекта — это действия, которые можно выполнять над объектом.</span><span class="sxs-lookup"><span data-stu-id="2e218-115">The object methods are actions that you can perform on the object.</span></span>
<span data-ttu-id="2e218-116">Например, объекты FileInfo имеют метод CopyTo, который можно использовать для копирования файла.</span><span class="sxs-lookup"><span data-stu-id="2e218-116">For example, FileInfo objects have a CopyTo method that you can use to copy the file.</span></span>

<span data-ttu-id="2e218-117">Свойства объекта хранят сведения об объекте.</span><span class="sxs-lookup"><span data-stu-id="2e218-117">Object properties store information about the object.</span></span> <span data-ttu-id="2e218-118">Например, объекты FileInfo имеют свойство LastWriteTime, которое хранит дату и время последнего обращения к файлу.</span><span class="sxs-lookup"><span data-stu-id="2e218-118">For example, FileInfo objects have a LastWriteTime property that stores the date and time that the file was most recently accessed.</span></span>

<span data-ttu-id="2e218-119">При работе с объектами можно использовать их методы и свойства в командах для выполнения действий и управления данными.</span><span class="sxs-lookup"><span data-stu-id="2e218-119">When working with objects, you can use their methods and properties in commands to take action and manage data.</span></span>

## <a name="objects-in-pipelines"></a><span data-ttu-id="2e218-120">Объекты в конвейерах</span><span class="sxs-lookup"><span data-stu-id="2e218-120">Objects in Pipelines</span></span>

<span data-ttu-id="2e218-121">Когда команды объединяются в конвейере, они передают данные друг другу как объекты.</span><span class="sxs-lookup"><span data-stu-id="2e218-121">When commands are combined in a pipeline, they pass information to each other as objects.</span></span> <span data-ttu-id="2e218-122">При выполнении первой команды она отправляет один или несколько объектов в конвейер во вторую команду.</span><span class="sxs-lookup"><span data-stu-id="2e218-122">When the first command runs, it sends one or more objects down the pipeline to the second command.</span></span> <span data-ttu-id="2e218-123">Вторая команда получает объекты из первой команды, обрабатывает объекты, а затем передает новые или измененные объекты в следующую команду в конвейере.</span><span class="sxs-lookup"><span data-stu-id="2e218-123">The second command receives the objects from the first command, processes the objects, and then passes new or revised objects to the next command in the pipeline.</span></span>
<span data-ttu-id="2e218-124">Это остается до тех пор, пока не будут выполнены все команды в конвейере.</span><span class="sxs-lookup"><span data-stu-id="2e218-124">This continues until all commands in the pipeline run.</span></span>

<span data-ttu-id="2e218-125">В следующем примере показано, как передаются объекты из одной команды в следующую:</span><span class="sxs-lookup"><span data-stu-id="2e218-125">The following example demonstrates how objects are passed from one command to the next:</span></span>

```powershell
Get-ChildItem C: | where { $_.PsIsContainer -eq $false } | Format-List
```

<span data-ttu-id="2e218-126">Первая команда `Get-ChildItem C:` возвращает файл или объект каталога для каждого элемента в корневом каталоге файловой системы.</span><span class="sxs-lookup"><span data-stu-id="2e218-126">The first command `Get-ChildItem C:` returns a file or directory object for each item in the root directory of the file system.</span></span> <span data-ttu-id="2e218-127">Объекты File и Directory передаются по конвейеру во вторую команду.</span><span class="sxs-lookup"><span data-stu-id="2e218-127">The file and directory objects are passed down the pipeline to the second command.</span></span>

<span data-ttu-id="2e218-128">Вторая команда `where { $_.PsIsContainer -eq $false }` использует свойство PSIsContainer всех объектов файловой системы для выбора только тех файлов, которые имеют значение false ( \$ false) в свойстве PSIsContainer.</span><span class="sxs-lookup"><span data-stu-id="2e218-128">The second command `where { $_.PsIsContainer -eq $false }` uses the PsIsContainer property of all file system objects to select only files, which have a value of False (\$false) in their PsIsContainer property.</span></span> <span data-ttu-id="2e218-129">Папки, которые являются контейнерами и, таким словами, имеют значение true ( \$ true) в свойстве PSIsContainer, не выбираются.</span><span class="sxs-lookup"><span data-stu-id="2e218-129">Folders, which are containers and, thus, have a value of True (\$true) in their PsIsContainer property, are not selected.</span></span>

<span data-ttu-id="2e218-130">Вторая команда передает только файловые объекты в третью команду `Format-List` , которая отображает объекты файлов в списке.</span><span class="sxs-lookup"><span data-stu-id="2e218-130">The second command passes only the file objects to the third command `Format-List`, which displays the file objects in a list.</span></span>

## <a name="see-also"></a><span data-ttu-id="2e218-131">См. также:</span><span class="sxs-lookup"><span data-stu-id="2e218-131">See Also</span></span>

[<span data-ttu-id="2e218-132">about_Methods</span><span class="sxs-lookup"><span data-stu-id="2e218-132">about_Methods</span></span>](about_Methods.md)

[<span data-ttu-id="2e218-133">about_Object_Creation</span><span class="sxs-lookup"><span data-stu-id="2e218-133">about_Object_Creation</span></span>](about_Object_Creation.md)

[<span data-ttu-id="2e218-134">about_Properties</span><span class="sxs-lookup"><span data-stu-id="2e218-134">about_Properties</span></span>](about_Properties.md)

[<span data-ttu-id="2e218-135">about_Pipelines</span><span class="sxs-lookup"><span data-stu-id="2e218-135">about_Pipelines</span></span>](about_Pipelines.md)

[<span data-ttu-id="2e218-136">Get-Member</span><span class="sxs-lookup"><span data-stu-id="2e218-136">Get-Member</span></span>](xref:Microsoft.PowerShell.Utility.Get-Member)