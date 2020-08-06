---
title: Создание файла форматирования (.format.ps1XML) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: abdbd4e15b0c4cb1dafcde087d24ed5792c86c3d
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781262"
---
# <a name="how-to-create-a-formatting-file-formatps1xml"></a><span data-ttu-id="faa77-102">Как создать файл форматирования (.format.ps1xml)</span><span class="sxs-lookup"><span data-stu-id="faa77-102">How to Create a Formatting File (.format.ps1xml)</span></span>

<span data-ttu-id="faa77-103">В этом разделе описывается создание файла форматирования (.format.ps1XML).</span><span class="sxs-lookup"><span data-stu-id="faa77-103">This topic describes how to create a formatting file (.format.ps1xml).</span></span>

> [!NOTE]
> <span data-ttu-id="faa77-104">Можно также создать файл форматирования, сделав копию одного из файлов, предоставляемых Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="faa77-104">You can also create a formatting file by making a copy of one of the files provided by Windows PowerShell.</span></span> <span data-ttu-id="faa77-105">При создании копии существующего файла удалите имеющуюся цифровую подпись и добавьте собственную сигнатуру в новый файл.</span><span class="sxs-lookup"><span data-stu-id="faa77-105">If you make a copy of an existing file, delete the existing digital signature, and add your own signature to the new file.</span></span>

### <a name="to-create-a-formatps1xml-file"></a><span data-ttu-id="faa77-106">Создание .format.ps1XML-файла.</span><span class="sxs-lookup"><span data-stu-id="faa77-106">To create a .format.ps1xml file.</span></span>

1. <span data-ttu-id="faa77-107">Создайте текстовый файл (. txt) с помощью текстового редактора, например Блокнота.</span><span class="sxs-lookup"><span data-stu-id="faa77-107">Create a text file (.txt) using a text editor such as Notepad.</span></span>

2. <span data-ttu-id="faa77-108">Скопируйте следующие строки в файл форматирования.</span><span class="sxs-lookup"><span data-stu-id="faa77-108">Copy the following lines into the formatting file.</span></span>

   ```xml
   <?xml version="1.0" encoding="utf-8" ?>
   <Configuration>
   <ViewDefinitions>
   </ViewDefinitions>
   </Configuration>
   ```

   - <span data-ttu-id="faa77-109">`<Configuration></Configuration>`Теги определяют корневой `Configuration` узел.</span><span class="sxs-lookup"><span data-stu-id="faa77-109">The `<Configuration></Configuration>` tags define the root `Configuration` node.</span></span> <span data-ttu-id="faa77-110">Все дополнительные XML-теги будут заключены в этот узел.</span><span class="sxs-lookup"><span data-stu-id="faa77-110">All additional XML tags will be enclosed within this node.</span></span>

   - <span data-ttu-id="faa77-111">`<ViewDefinitions></ViewDefinitions>`Теги определяют `ViewDefinitions` узел.</span><span class="sxs-lookup"><span data-stu-id="faa77-111">The `<ViewDefinitions></ViewDefinitions>` tags define the `ViewDefinitions` node.</span></span> <span data-ttu-id="faa77-112">Все представления определяются в этом узле.</span><span class="sxs-lookup"><span data-stu-id="faa77-112">All views are defined within this node.</span></span>

3. <span data-ttu-id="faa77-113">Сохраните файл в папку установки Windows PowerShell, в папку модуля или во вложенную папку папки Module.</span><span class="sxs-lookup"><span data-stu-id="faa77-113">Save the file to the Windows PowerShell installation folder, to your module folder, or to a subfolder of the module folder.</span></span> <span data-ttu-id="faa77-114">При сохранении файла используйте следующий формат имени: `MyFile.format.ps1xml` .</span><span class="sxs-lookup"><span data-stu-id="faa77-114">Use the following name format when you save the file:  `MyFile.format.ps1xml`.</span></span> <span data-ttu-id="faa77-115">Файлы форматирования должны использовать `.format.ps1xml` расширение.</span><span class="sxs-lookup"><span data-stu-id="faa77-115">Formatting files must use the `.format.ps1xml` extension.</span></span>

   <span data-ttu-id="faa77-116">Теперь все готово к добавлению представлений в файл форматирования.</span><span class="sxs-lookup"><span data-stu-id="faa77-116">You are now ready to add views to the formatting file.</span></span> <span data-ttu-id="faa77-117">Количество представлений, которые могут быть определены в файле форматирования, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="faa77-117">There is no limit to the number of views that can be defined in a formatting file.</span></span> <span data-ttu-id="faa77-118">Можно добавить одно представление для каждого объекта, несколько представлений для одного и того же объекта или одно представление, используемое несколькими объектами.</span><span class="sxs-lookup"><span data-stu-id="faa77-118">You can add a single view for each object, multiple views for the same object, or a single view that is used by multiple objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="faa77-119">См. также</span><span class="sxs-lookup"><span data-stu-id="faa77-119">See Also</span></span>

[<span data-ttu-id="faa77-120">Создание файла форматирования и типов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="faa77-120">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
