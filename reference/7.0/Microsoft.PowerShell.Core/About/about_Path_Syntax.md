---
description: Описывает полные и относительные форматы имен путей в PowerShell.
keywords: powershell,командлет
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_path_syntax?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Path_Syntax
ms.openlocfilehash: b58fdd62803bfb654c9c69acda390d63341aacd9
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93232218"
---
# <a name="about-path-syntax"></a><span data-ttu-id="6aa25-104">Сведения о синтаксисе пути</span><span class="sxs-lookup"><span data-stu-id="6aa25-104">About Path Syntax</span></span>

## <a name="short-description"></a><span data-ttu-id="6aa25-105">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="6aa25-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="6aa25-106">Описывает полные и относительные форматы имен путей в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6aa25-106">Describes the full and relative path name formats in  PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="6aa25-107">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="6aa25-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="6aa25-108">Все элементы в хранилище данных, доступные через поставщик PowerShell, могут быть однозначно идентифицированы по именам путей.</span><span class="sxs-lookup"><span data-stu-id="6aa25-108">All items in a data store accessible through a PowerShell provider can be uniquely identified by their path names.</span></span> <span data-ttu-id="6aa25-109">Имя пути — это сочетание имени элемента, контейнера и вложенных элементов, в которых находится элемент, и диска PowerShell, через который осуществляется доступ к контейнерам.</span><span class="sxs-lookup"><span data-stu-id="6aa25-109">A path name is a combination of the item name, the container and subcontainers in which the item is located, and the PowerShell drive through which the containers are accessed.</span></span>

<span data-ttu-id="6aa25-110">В PowerShell имена путей делятся на один из двух типов: полный и относительный.</span><span class="sxs-lookup"><span data-stu-id="6aa25-110">In PowerShell, path names are divided into one of two types: fully qualified and relative.</span></span> <span data-ttu-id="6aa25-111">Полное имя пути состоит из всех элементов, составляющих путь.</span><span class="sxs-lookup"><span data-stu-id="6aa25-111">A fully qualified path name consists of all elements that make up a path.</span></span> <span data-ttu-id="6aa25-112">Следующий синтаксис показывает элементы в полном имени пути:</span><span class="sxs-lookup"><span data-stu-id="6aa25-112">The following syntax shows the elements in a fully qualified path name:</span></span>

```powershell
[<provider>::]<drive>:[\<container>[\<subcontainer>...]]\<item>
```

<span data-ttu-id="6aa25-113">\<provider\>Заполнитель относится к поставщику PowerShell, с помощью которого вы обращаетесь к хранилищу данных.</span><span class="sxs-lookup"><span data-stu-id="6aa25-113">The \<provider\> placeholder refers to the PowerShell provider through which you access the data store.</span></span> <span data-ttu-id="6aa25-114">Например, Поставщик FileSystem позволяет получить доступ к файлам и каталогам на компьютере.</span><span class="sxs-lookup"><span data-stu-id="6aa25-114">For example, the FileSystem provider allows you to access the files and directories on your computer.</span></span> <span data-ttu-id="6aa25-115">Этот элемент синтаксиса является необязательным и никогда не нужен, так как имена дисков уникальны для всех поставщиков.</span><span class="sxs-lookup"><span data-stu-id="6aa25-115">This element of the syntax is optional and is never needed because the drive names are unique across all providers.</span></span>

<span data-ttu-id="6aa25-116">\<drive\>Заполнитель относится к диску PowerShell, который поддерживается определенным поставщиком PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6aa25-116">The \<drive\> placeholder refers to the PowerShell drive that is supported by a particular PowerShell provider.</span></span> <span data-ttu-id="6aa25-117">В случае с поставщиком FileSystem диски PowerShell сопоставляются с дисками Windows, настроенными в системе.</span><span class="sxs-lookup"><span data-stu-id="6aa25-117">In the case of the FileSystem provider, the PowerShell drives map to the Windows drives that are configured on your system.</span></span> <span data-ttu-id="6aa25-118">Например, если в системе есть диск A: и диск C:, то Поставщик FileSystem создает те же диски в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6aa25-118">For example, if your system includes an A: drive and a C: drive, the FileSystem provider creates the same drives in PowerShell.</span></span>

<span data-ttu-id="6aa25-119">После указания диска необходимо указать все контейнеры и подконтейнеры, содержащие этот элемент.</span><span class="sxs-lookup"><span data-stu-id="6aa25-119">After you have specified the drive, you must specify any containers and subcontainers that contain the item.</span></span> <span data-ttu-id="6aa25-120">Контейнеры должны быть указаны в иерархическом порядке, в котором они существуют в хранилище данных.</span><span class="sxs-lookup"><span data-stu-id="6aa25-120">The containers must be specified in the hierarchical order in which they exist in the data store.</span></span> <span data-ttu-id="6aa25-121">Иными словами, необходимо начать с родительского контейнера, потом дочернего контейнера в этом родительском контейнере и т. д.</span><span class="sxs-lookup"><span data-stu-id="6aa25-121">In other words, you must start with the parent container, then the child container in that parent container, and so on.</span></span> <span data-ttu-id="6aa25-122">Кроме того, каждому контейнеру должен предшествовать символ обратной косой черты.</span><span class="sxs-lookup"><span data-stu-id="6aa25-122">In addition, each container must be preceded by a backslash.</span></span> <span data-ttu-id="6aa25-123">(Обратите внимание, что PowerShell позволяет использовать косую черту для совместимости с другими оболочками PowerShell.)</span><span class="sxs-lookup"><span data-stu-id="6aa25-123">(Note that PowerShell allows you to use forward slashes for compatibility with other PowerShells.)</span></span>

<span data-ttu-id="6aa25-124">После указания контейнера и подконтейнеров необходимо указать имя элемента, перед которым следует обратная косая черта.</span><span class="sxs-lookup"><span data-stu-id="6aa25-124">After the container and subcontainers have been specified, you must provide the item name, preceded by a backslash.</span></span> <span data-ttu-id="6aa25-125">Например, полное имя пути для файла Shell.dll в каталоге C: \\ Windows \\ system32 выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="6aa25-125">For example, the fully qualified path name for the Shell.dll file in the C:\\Windows\\System32 directory is as follows:</span></span>

```powershell
C:\Windows\System32\Shell.dll
```

<span data-ttu-id="6aa25-126">В этом случае к диску, к которому обращаются контейнеры, относится диск C:, контейнер верхнего уровня — Windows, вложенная подсистема — system32 (расположенная в контейнере Windows), а элемент — Shell.dll.</span><span class="sxs-lookup"><span data-stu-id="6aa25-126">In this case, the drive through which the containers are accessed is the C: drive, the top-level container is Windows, the subcontainer is System32 (located within the Windows container), and the item is Shell.dll.</span></span>

<span data-ttu-id="6aa25-127">В некоторых ситуациях указывать полное имя пути не требуется, а вместо этого можно использовать относительный путь.</span><span class="sxs-lookup"><span data-stu-id="6aa25-127">In some situations, you do not need to specify a fully qualified path name and can instead use a relative path name.</span></span> <span data-ttu-id="6aa25-128">Относительное имя пути основано на текущем рабочем расположении.</span><span class="sxs-lookup"><span data-stu-id="6aa25-128">A relative path name is based on the current working location.</span></span> <span data-ttu-id="6aa25-129">PowerShell позволяет выявление элемента на основе его расположения относительно текущего рабочего расположения.</span><span class="sxs-lookup"><span data-stu-id="6aa25-129">PowerShell allows you to identify an item based on its location relative to the current working location.</span></span> <span data-ttu-id="6aa25-130">Можно указать относительные имена путей, используя специальные символы.</span><span class="sxs-lookup"><span data-stu-id="6aa25-130">You can specify relative path names by using special characters.</span></span> <span data-ttu-id="6aa25-131">В следующей таблице описывается каждый из этих символов и приводятся примеры относительных путей и полных имен путей.</span><span class="sxs-lookup"><span data-stu-id="6aa25-131">The following table describes each of these characters and provides examples of relative path names and fully qualified path names.</span></span> <span data-ttu-id="6aa25-132">Примеры в таблице основаны на текущем рабочем каталоге, для которого задано значение C:\Windows.</span><span class="sxs-lookup"><span data-stu-id="6aa25-132">The examples in the table are based on the current working directory being set to C:\Windows.</span></span>

|<span data-ttu-id="6aa25-133">Символ</span><span class="sxs-lookup"><span data-stu-id="6aa25-133">Symbol</span></span>|<span data-ttu-id="6aa25-134">Описание</span><span class="sxs-lookup"><span data-stu-id="6aa25-134">Description</span></span>               |<span data-ttu-id="6aa25-135">Относительный путь</span><span class="sxs-lookup"><span data-stu-id="6aa25-135">Relative path</span></span>    |<span data-ttu-id="6aa25-136">Полный путь.</span><span class="sxs-lookup"><span data-stu-id="6aa25-136">Full path</span></span>          |
|------|--------------------------|-----------------|-------------------|
|<span data-ttu-id="6aa25-137">.</span><span class="sxs-lookup"><span data-stu-id="6aa25-137">.</span></span>     |<span data-ttu-id="6aa25-138">Текущее расположение</span><span class="sxs-lookup"><span data-stu-id="6aa25-138">Current location</span></span>          |<span data-ttu-id="6aa25-139">.\\ Системой</span><span class="sxs-lookup"><span data-stu-id="6aa25-139">.\\System</span></span>        |<span data-ttu-id="6aa25-140">c: \\ \\ система Windows</span><span class="sxs-lookup"><span data-stu-id="6aa25-140">c:\\Windows\\System</span></span>|
|<span data-ttu-id="6aa25-141">..</span><span class="sxs-lookup"><span data-stu-id="6aa25-141">..</span></span>    |<span data-ttu-id="6aa25-142">Родительский элемент текущего расположения</span><span class="sxs-lookup"><span data-stu-id="6aa25-142">Parent of current location</span></span>|<span data-ttu-id="6aa25-143">..\\ Программные файлы</span><span class="sxs-lookup"><span data-stu-id="6aa25-143">..\\Program Files</span></span>|<span data-ttu-id="6aa25-144">c: \\ Program Files</span><span class="sxs-lookup"><span data-stu-id="6aa25-144">c:\\Program Files</span></span>  |
|\     |<span data-ttu-id="6aa25-145">Корень диска текущего</span><span class="sxs-lookup"><span data-stu-id="6aa25-145">Drive root of current</span></span>     |<span data-ttu-id="6aa25-146">\\Программные файлы</span><span class="sxs-lookup"><span data-stu-id="6aa25-146">\\Program Files</span></span>  |<span data-ttu-id="6aa25-147">c: \\ Program Files</span><span class="sxs-lookup"><span data-stu-id="6aa25-147">c:\\Program Files</span></span>  |
|      |<span data-ttu-id="6aa25-148">location</span><span class="sxs-lookup"><span data-stu-id="6aa25-148">location</span></span>                  |                 |                   |
|<span data-ttu-id="6aa25-149">None</span><span class="sxs-lookup"><span data-stu-id="6aa25-149">[none]</span></span>|<span data-ttu-id="6aa25-150">Специальные символы отсутствуют</span><span class="sxs-lookup"><span data-stu-id="6aa25-150">No special characters</span></span>     |<span data-ttu-id="6aa25-151">Система</span><span class="sxs-lookup"><span data-stu-id="6aa25-151">System</span></span>           |<span data-ttu-id="6aa25-152">c: \\ \\ система Windows</span><span class="sxs-lookup"><span data-stu-id="6aa25-152">c:\\Windows\\System</span></span>|

<span data-ttu-id="6aa25-153">При использовании имени пути в команде это имя вводится точно так же, как полное имя пути или его относительная часть.</span><span class="sxs-lookup"><span data-stu-id="6aa25-153">When using a path name in a command, you enter that name in the same way whether you use a fully qualified path name or a relative one.</span></span> <span data-ttu-id="6aa25-154">Например, предположим, что текущий рабочий каталог — C:\Windows</span><span class="sxs-lookup"><span data-stu-id="6aa25-154">For example, suppose that your current working directory is C:\Windows.</span></span> <span data-ttu-id="6aa25-155">Следующая Get-ChildItem команда извлекает все элементы в каталоге К:\течдокс:</span><span class="sxs-lookup"><span data-stu-id="6aa25-155">The following Get-ChildItem command retrieves all items in the C:\Techdocs directory:</span></span>

```powershell
Get-ChildItem \techdocs
```

<span data-ttu-id="6aa25-156">Обратная косая черта указывает, что следует использовать корневой диск текущего рабочего расположения.</span><span class="sxs-lookup"><span data-stu-id="6aa25-156">The backslash indicates that the drive root of the current working location should be used.</span></span> <span data-ttu-id="6aa25-157">Так как рабочий каталог имеет значение C: \\ Windows, корневым диском является диск c:.</span><span class="sxs-lookup"><span data-stu-id="6aa25-157">Because the working directory is C:\\Windows, the drive root is the C: drive.</span></span> <span data-ttu-id="6aa25-158">Так как каталог течдокс находится за пределами корневого каталога, необходимо указать только обратную косую черту.</span><span class="sxs-lookup"><span data-stu-id="6aa25-158">Because the techdocs directory is located off the root, you need to specify only the backslash.</span></span>

<span data-ttu-id="6aa25-159">Те же результаты можно получить с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="6aa25-159">You can achieve the same results by using the following command:</span></span>

```powershell
Get-ChildItem c:\techdocs
```

<span data-ttu-id="6aa25-160">Независимо от того, используется ли полное имя пути или имя относительного пути, имя пути важно не только потому, что он находит элемент, а также потому, что он однозначно определяет элемент, даже если этот элемент имеет то же имя, что и другой элемент в другом контейнере.</span><span class="sxs-lookup"><span data-stu-id="6aa25-160">Regardless of whether you use a fully qualified path name or a relative path name, a path name is important not only because it locates an item but also because it uniquely identifies the item even if that item shares the same name as another item in a different container.</span></span>

<span data-ttu-id="6aa25-161">Например, предположим, что у вас есть два файла, каждый из которых имеет имя Results.txt.</span><span class="sxs-lookup"><span data-stu-id="6aa25-161">For instance, suppose that you have two files that are each named Results.txt.</span></span>
<span data-ttu-id="6aa25-162">Первый файл находится в каталоге с именем C: \\ течдокс \\ Jan, а второй файл находится в каталоге с именем c: \\ течдокс \\ Фев. Путь к первому файлу (C: \\ течдокс \\ Jan \\Results.txt) и имя пути для второго файла (c: \\ течдокс \\ Фев \\Results.txt) позволяют четко различать два файла.</span><span class="sxs-lookup"><span data-stu-id="6aa25-162">The first file is in a directory named C:\\Techdocs\\Jan, and the second file is in a directory named C:\\Techdocs\\Feb. The path name for the first file (C:\\Techdocs\\Jan\\Results.txt) and the path name for the second file (C:\\Techdocs\\Feb\\Results.txt) allow you to clearly distinguish between the two files.</span></span>

## <a name="see-also"></a><span data-ttu-id="6aa25-163">СМ. ТАКЖЕ</span><span class="sxs-lookup"><span data-stu-id="6aa25-163">SEE ALSO</span></span>

[<span data-ttu-id="6aa25-164">about_Locations</span><span class="sxs-lookup"><span data-stu-id="6aa25-164">about_Locations</span></span>](about_Locations.md)