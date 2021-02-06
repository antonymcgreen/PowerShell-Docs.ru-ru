---
description: Содержит ценные сведения об объектах в PowerShell.
Locale: en-US
ms.date: 11/30/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_objects?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Objects
ms.openlocfilehash: bfb66e72a74d20379123558b85047097dc801e9d
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603966"
---
# <a name="about-objects"></a><span data-ttu-id="0e883-103">Об объектах</span><span class="sxs-lookup"><span data-stu-id="0e883-103">About Objects</span></span>

## <a name="short-description"></a><span data-ttu-id="0e883-104">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="0e883-104">Short Description</span></span>
<span data-ttu-id="0e883-105">Содержит ценные сведения об объектах в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0e883-105">Provides essential information about objects in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="0e883-106">Полное описание</span><span class="sxs-lookup"><span data-stu-id="0e883-106">Long Description</span></span>

<span data-ttu-id="0e883-107">Каждое действие, выполняемое в PowerShell, выполняется в контексте объектов.</span><span class="sxs-lookup"><span data-stu-id="0e883-107">Every action you take in PowerShell occurs within the context of objects.</span></span> <span data-ttu-id="0e883-108">По мере перемещения данных от одной команды к другой она перемещается как один или несколько идентифицируемых объектов.</span><span class="sxs-lookup"><span data-stu-id="0e883-108">As data moves from one command to the next, it moves as one or more identifiable objects.</span></span> <span data-ttu-id="0e883-109">Затем объект представляет собой коллекцию данных, представляющих элемент.</span><span class="sxs-lookup"><span data-stu-id="0e883-109">An object, then, is a collection of data that represents an item.</span></span> <span data-ttu-id="0e883-110">Объект состоит из трех типов данных: типа объектов, его методов и свойств.</span><span class="sxs-lookup"><span data-stu-id="0e883-110">An object is made up of three types of data: the objects type, its methods, and its properties.</span></span>

## <a name="types-methods-and-properties"></a><span data-ttu-id="0e883-111">Типы, методы и свойства</span><span class="sxs-lookup"><span data-stu-id="0e883-111">Types, Methods, and Properties</span></span>

<span data-ttu-id="0e883-112">Тип объекта указывает на тип объекта.</span><span class="sxs-lookup"><span data-stu-id="0e883-112">The object type tells what kind of object it is.</span></span> <span data-ttu-id="0e883-113">Например, объект, представляющий файл, является объектом FileInfo.</span><span class="sxs-lookup"><span data-stu-id="0e883-113">For example, an object that represents a file is a FileInfo object.</span></span>

<span data-ttu-id="0e883-114">Методы объекта — это действия, которые можно выполнять над объектом.</span><span class="sxs-lookup"><span data-stu-id="0e883-114">The object methods are actions that you can perform on the object.</span></span>
<span data-ttu-id="0e883-115">Например, объекты FileInfo имеют метод CopyTo, который можно использовать для копирования файла.</span><span class="sxs-lookup"><span data-stu-id="0e883-115">For example, FileInfo objects have a CopyTo method that you can use to copy the file.</span></span>

<span data-ttu-id="0e883-116">Свойства объекта хранят сведения об объекте.</span><span class="sxs-lookup"><span data-stu-id="0e883-116">Object properties store information about the object.</span></span> <span data-ttu-id="0e883-117">Например, объекты FileInfo имеют свойство LastWriteTime, которое хранит дату и время последнего обращения к файлу.</span><span class="sxs-lookup"><span data-stu-id="0e883-117">For example, FileInfo objects have a LastWriteTime property that stores the date and time that the file was most recently accessed.</span></span>

<span data-ttu-id="0e883-118">При работе с объектами можно использовать их методы и свойства в командах для выполнения действий и управления данными.</span><span class="sxs-lookup"><span data-stu-id="0e883-118">When working with objects, you can use their methods and properties in commands to take action and manage data.</span></span>

## <a name="objects-in-pipelines"></a><span data-ttu-id="0e883-119">Объекты в конвейерах</span><span class="sxs-lookup"><span data-stu-id="0e883-119">Objects in Pipelines</span></span>

<span data-ttu-id="0e883-120">Когда команды объединяются в конвейере, они передают данные друг другу как объекты.</span><span class="sxs-lookup"><span data-stu-id="0e883-120">When commands are combined in a pipeline, they pass information to each other as objects.</span></span> <span data-ttu-id="0e883-121">При выполнении первой команды она отправляет один или несколько объектов в конвейер во вторую команду.</span><span class="sxs-lookup"><span data-stu-id="0e883-121">When the first command runs, it sends one or more objects down the pipeline to the second command.</span></span> <span data-ttu-id="0e883-122">Вторая команда получает объекты из первой команды, обрабатывает объекты, а затем передает новые или измененные объекты в следующую команду в конвейере.</span><span class="sxs-lookup"><span data-stu-id="0e883-122">The second command receives the objects from the first command, processes the objects, and then passes new or revised objects to the next command in the pipeline.</span></span>
<span data-ttu-id="0e883-123">Это остается до тех пор, пока не будут выполнены все команды в конвейере.</span><span class="sxs-lookup"><span data-stu-id="0e883-123">This continues until all commands in the pipeline run.</span></span>

<span data-ttu-id="0e883-124">В следующем примере показано, как передаются объекты из одной команды в следующую:</span><span class="sxs-lookup"><span data-stu-id="0e883-124">The following example demonstrates how objects are passed from one command to the next:</span></span>

```powershell
Get-ChildItem C: | where { $_.PsIsContainer -eq $false } | Format-List
```

<span data-ttu-id="0e883-125">Первая команда `Get-ChildItem C:` возвращает файл или объект каталога для каждого элемента в корневом каталоге файловой системы.</span><span class="sxs-lookup"><span data-stu-id="0e883-125">The first command `Get-ChildItem C:` returns a file or directory object for each item in the root directory of the file system.</span></span> <span data-ttu-id="0e883-126">Объекты File и Directory передаются по конвейеру во вторую команду.</span><span class="sxs-lookup"><span data-stu-id="0e883-126">The file and directory objects are passed down the pipeline to the second command.</span></span>

<span data-ttu-id="0e883-127">Вторая команда `where { $_.PsIsContainer -eq $false }` использует свойство PSIsContainer всех объектов файловой системы для выбора только тех файлов, которые имеют значение false ( \$ false) в свойстве PSIsContainer.</span><span class="sxs-lookup"><span data-stu-id="0e883-127">The second command `where { $_.PsIsContainer -eq $false }` uses the PsIsContainer property of all file system objects to select only files, which have a value of False (\$false) in their PsIsContainer property.</span></span> <span data-ttu-id="0e883-128">Папки, которые являются контейнерами и, таким словами, имеют значение true ( \$ true) в свойстве PSIsContainer, не выбираются.</span><span class="sxs-lookup"><span data-stu-id="0e883-128">Folders, which are containers and, thus, have a value of True (\$true) in their PsIsContainer property, are not selected.</span></span>

<span data-ttu-id="0e883-129">Вторая команда передает только файловые объекты в третью команду `Format-List` , которая отображает объекты файлов в списке.</span><span class="sxs-lookup"><span data-stu-id="0e883-129">The second command passes only the file objects to the third command `Format-List`, which displays the file objects in a list.</span></span>

## <a name="see-also"></a><span data-ttu-id="0e883-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="0e883-130">See Also</span></span>

[<span data-ttu-id="0e883-131">about_Methods</span><span class="sxs-lookup"><span data-stu-id="0e883-131">about_Methods</span></span>](about_Methods.md)

[<span data-ttu-id="0e883-132">about_Object_Creation</span><span class="sxs-lookup"><span data-stu-id="0e883-132">about_Object_Creation</span></span>](about_Object_Creation.md)

[<span data-ttu-id="0e883-133">about_Properties</span><span class="sxs-lookup"><span data-stu-id="0e883-133">about_Properties</span></span>](about_Properties.md)

[<span data-ttu-id="0e883-134">about_Pipelines</span><span class="sxs-lookup"><span data-stu-id="0e883-134">about_Pipelines</span></span>](about_Pipelines.md)

[<span data-ttu-id="0e883-135">Get-Member</span><span class="sxs-lookup"><span data-stu-id="0e883-135">Get-Member</span></span>](xref:Microsoft.PowerShell.Utility.Get-Member)

