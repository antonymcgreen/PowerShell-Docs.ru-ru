---
ms.date: 09/13/2016
ms.topic: reference
title: Как создать файл форматирования (.format.ps1xml)
description: Как создать файл форматирования (.format.ps1xml)
ms.openlocfilehash: 5bbc1ba40bfccf13636abc0f0751938aa724b761
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651994"
---
# <a name="how-to-create-a-formatting-file-formatps1xml"></a><span data-ttu-id="57950-103">Как создать файл форматирования (.format.ps1xml)</span><span class="sxs-lookup"><span data-stu-id="57950-103">How to Create a Formatting File (.format.ps1xml)</span></span>

<span data-ttu-id="57950-104">В этом разделе описывается создание файла форматирования (.format.ps1XML).</span><span class="sxs-lookup"><span data-stu-id="57950-104">This topic describes how to create a formatting file (.format.ps1xml).</span></span>

> [!NOTE]
> <span data-ttu-id="57950-105">Можно также создать файл форматирования, сделав копию одного из файлов, предоставляемых Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="57950-105">You can also create a formatting file by making a copy of one of the files provided by Windows PowerShell.</span></span> <span data-ttu-id="57950-106">При создании копии существующего файла удалите имеющуюся цифровую подпись и добавьте собственную сигнатуру в новый файл.</span><span class="sxs-lookup"><span data-stu-id="57950-106">If you make a copy of an existing file, delete the existing digital signature, and add your own signature to the new file.</span></span>

### <a name="to-create-a-formatps1xml-file"></a><span data-ttu-id="57950-107">Создание .format.ps1XML-файла.</span><span class="sxs-lookup"><span data-stu-id="57950-107">To create a .format.ps1xml file.</span></span>

1. <span data-ttu-id="57950-108">Создайте текстовый файл (. txt) с помощью текстового редактора, например Блокнота.</span><span class="sxs-lookup"><span data-stu-id="57950-108">Create a text file (.txt) using a text editor such as Notepad.</span></span>

2. <span data-ttu-id="57950-109">Скопируйте следующие строки в файл форматирования.</span><span class="sxs-lookup"><span data-stu-id="57950-109">Copy the following lines into the formatting file.</span></span>

   ```xml
   <?xml version="1.0" encoding="utf-8" ?>
   <Configuration>
   <ViewDefinitions>
   </ViewDefinitions>
   </Configuration>
   ```

   - <span data-ttu-id="57950-110">`<Configuration></Configuration>`Теги определяют корневой `Configuration` узел.</span><span class="sxs-lookup"><span data-stu-id="57950-110">The `<Configuration></Configuration>` tags define the root `Configuration` node.</span></span> <span data-ttu-id="57950-111">Все дополнительные XML-теги будут заключены в этот узел.</span><span class="sxs-lookup"><span data-stu-id="57950-111">All additional XML tags will be enclosed within this node.</span></span>

   - <span data-ttu-id="57950-112">`<ViewDefinitions></ViewDefinitions>`Теги определяют `ViewDefinitions` узел.</span><span class="sxs-lookup"><span data-stu-id="57950-112">The `<ViewDefinitions></ViewDefinitions>` tags define the `ViewDefinitions` node.</span></span> <span data-ttu-id="57950-113">Все представления определяются в этом узле.</span><span class="sxs-lookup"><span data-stu-id="57950-113">All views are defined within this node.</span></span>

3. <span data-ttu-id="57950-114">Сохраните файл в папку установки Windows PowerShell, в папку модуля или во вложенную папку папки Module.</span><span class="sxs-lookup"><span data-stu-id="57950-114">Save the file to the Windows PowerShell installation folder, to your module folder, or to a subfolder of the module folder.</span></span> <span data-ttu-id="57950-115">При сохранении файла используйте следующий формат имени:  `MyFile.format.ps1xml` .</span><span class="sxs-lookup"><span data-stu-id="57950-115">Use the following name format when you save the file:  `MyFile.format.ps1xml`.</span></span> <span data-ttu-id="57950-116">Файлы форматирования должны использовать `.format.ps1xml` расширение.</span><span class="sxs-lookup"><span data-stu-id="57950-116">Formatting files must use the `.format.ps1xml` extension.</span></span>

   <span data-ttu-id="57950-117">Теперь все готово к добавлению представлений в файл форматирования.</span><span class="sxs-lookup"><span data-stu-id="57950-117">You are now ready to add views to the formatting file.</span></span> <span data-ttu-id="57950-118">Количество представлений, которые могут быть определены в файле форматирования, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="57950-118">There is no limit to the number of views that can be defined in a formatting file.</span></span> <span data-ttu-id="57950-119">Можно добавить одно представление для каждого объекта, несколько представлений для одного и того же объекта или одно представление, используемое несколькими объектами.</span><span class="sxs-lookup"><span data-stu-id="57950-119">You can add a single view for each object, multiple views for the same object, or a single view that is used by multiple objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="57950-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="57950-120">See Also</span></span>

[<span data-ttu-id="57950-121">Создание файла форматирования и типов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="57950-121">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
