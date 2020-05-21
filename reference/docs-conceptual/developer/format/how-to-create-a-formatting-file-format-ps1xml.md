---
title: Создание файла форматирования (. Format. ps1xml) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eb568878-f63e-4561-98e2-16ee2ac7559d
caps.latest.revision: 8
ms.openlocfilehash: 7a578dd63a53562f992b2970573258b8676e2a52
ms.sourcegitcommit: 17d798a041851382b406ed789097843faf37692d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2020
ms.locfileid: "83692274"
---
# <a name="how-to-create-a-formatting-file-formatps1xml"></a><span data-ttu-id="20e6a-102">Как создать файл форматирования (.format.ps1xml)</span><span class="sxs-lookup"><span data-stu-id="20e6a-102">How to Create a Formatting File (.format.ps1xml)</span></span>

<span data-ttu-id="20e6a-103">В этом разделе описывается создание файла форматирования (Format. ps1xml).</span><span class="sxs-lookup"><span data-stu-id="20e6a-103">This topic describes how to create a formatting file (.format.ps1xml).</span></span>

> [!NOTE]
> <span data-ttu-id="20e6a-104">Можно также создать файл форматирования, сделав копию одного из файлов, предоставляемых Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="20e6a-104">You can also create a formatting file by making a copy of one of the files provided by Windows PowerShell.</span></span> <span data-ttu-id="20e6a-105">При создании копии существующего файла удалите имеющуюся цифровую подпись и добавьте собственную сигнатуру в новый файл.</span><span class="sxs-lookup"><span data-stu-id="20e6a-105">If you make a copy of an existing file, delete the existing digital signature, and add your own signature to the new file.</span></span>

### <a name="to-create-a-formatps1xml-file"></a><span data-ttu-id="20e6a-106">Для создания файла. Format. ps1xml.</span><span class="sxs-lookup"><span data-stu-id="20e6a-106">To create a .format.ps1xml file.</span></span>

1. <span data-ttu-id="20e6a-107">Создайте текстовый файл (. txt) с помощью текстового редактора, например Блокнота.</span><span class="sxs-lookup"><span data-stu-id="20e6a-107">Create a text file (.txt) using a text editor such as Notepad.</span></span>

2. <span data-ttu-id="20e6a-108">Скопируйте следующие строки в файл форматирования.</span><span class="sxs-lookup"><span data-stu-id="20e6a-108">Copy the following lines into the formatting file.</span></span>

   ```xml
   <?xml version="1.0" encoding="utf-8" ?>
   <Configuration>
   <ViewDefinitions>
   </ViewDefinitions>
   </Configuration>
   ```

   - <span data-ttu-id="20e6a-109">`<Configuration></Configuration>`Теги определяют корневой `Configuration` узел.</span><span class="sxs-lookup"><span data-stu-id="20e6a-109">The `<Configuration></Configuration>` tags define the root `Configuration` node.</span></span> <span data-ttu-id="20e6a-110">Все дополнительные XML-теги будут заключены в этот узел.</span><span class="sxs-lookup"><span data-stu-id="20e6a-110">All additional XML tags will be enclosed within this node.</span></span>

   - <span data-ttu-id="20e6a-111">`<ViewDefinitions></ViewDefinitions>`Теги определяют `ViewDefinitions` узел.</span><span class="sxs-lookup"><span data-stu-id="20e6a-111">The `<ViewDefinitions></ViewDefinitions>` tags define the `ViewDefinitions` node.</span></span> <span data-ttu-id="20e6a-112">Все представления определяются в этом узле.</span><span class="sxs-lookup"><span data-stu-id="20e6a-112">All views are defined within this node.</span></span>

3. <span data-ttu-id="20e6a-113">Сохраните файл в папку установки Windows PowerShell, в папку модуля или во вложенную папку папки Module.</span><span class="sxs-lookup"><span data-stu-id="20e6a-113">Save the file to the Windows PowerShell installation folder, to your module folder, or to a subfolder of the module folder.</span></span> <span data-ttu-id="20e6a-114">При сохранении файла используйте следующий формат имени: `MyFile.format.ps1xml` .</span><span class="sxs-lookup"><span data-stu-id="20e6a-114">Use the following name format when you save the file:  `MyFile.format.ps1xml`.</span></span> <span data-ttu-id="20e6a-115">Файлы форматирования должны использовать `.format.ps1xml` расширение.</span><span class="sxs-lookup"><span data-stu-id="20e6a-115">Formatting files must use the `.format.ps1xml` extension.</span></span>

   <span data-ttu-id="20e6a-116">Теперь все готово к добавлению представлений в файл форматирования.</span><span class="sxs-lookup"><span data-stu-id="20e6a-116">You are now ready to add views to the formatting file.</span></span> <span data-ttu-id="20e6a-117">Количество представлений, которые могут быть определены в файле форматирования, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="20e6a-117">There is no limit to the number of views that can be defined in a formatting file.</span></span> <span data-ttu-id="20e6a-118">Можно добавить одно представление для каждого объекта, несколько представлений для одного и того же объекта или одно представление, используемое несколькими объектами.</span><span class="sxs-lookup"><span data-stu-id="20e6a-118">You can add a single view for each object, multiple views for the same object, or a single view that is used by multiple objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="20e6a-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="20e6a-119">See Also</span></span>

[<span data-ttu-id="20e6a-120">Создание файла форматирования и типов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="20e6a-120">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
