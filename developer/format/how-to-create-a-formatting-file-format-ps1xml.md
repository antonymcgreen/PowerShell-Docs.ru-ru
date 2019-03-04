---
title: Как создать файл форматирования (. format.ps1xml) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eb568878-f63e-4561-98e2-16ee2ac7559d
caps.latest.revision: 8
ms.openlocfilehash: e97e9ddb1bf81ba66e5f3cedddd22e3a861ce228
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56862970"
---
# <a name="how-to-create-a-formatting-file-formatps1xml"></a><span data-ttu-id="746b6-102">Как создать файл форматирования (.format.ps1xml)</span><span class="sxs-lookup"><span data-stu-id="746b6-102">How to Create a Formatting File (.format.ps1xml)</span></span>

<span data-ttu-id="746b6-103">В этом разделе описывается, как создать файл форматирования (. format.ps1xml).</span><span class="sxs-lookup"><span data-stu-id="746b6-103">This topic describes how to create a formatting file (.format.ps1xml).</span></span>

> [!NOTE]
> <span data-ttu-id="746b6-104">Кроме того, можно создать файл форматирования путем копирования одного из файлов, предоставляемые Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="746b6-104">You can also create a formatting file by making a copy of one of the files provided by Windows PowerShell.</span></span> <span data-ttu-id="746b6-105">Если следует создать копию существующего файла, удалите существующие цифровой подписи и добавить свою собственную подпись в новый файл.</span><span class="sxs-lookup"><span data-stu-id="746b6-105">If you make a copy of an existing file, delete the existing digital signature, and add your own signature to the new file.</span></span>

### <a name="to-create-a-formatps1xml-file"></a><span data-ttu-id="746b6-106">Для создания. файле format.ps1xml.</span><span class="sxs-lookup"><span data-stu-id="746b6-106">To create a .format.ps1xml file.</span></span>

1. <span data-ttu-id="746b6-107">Создайте текстовый файл (.txt) с помощью текстового редактора, например в блокноте.</span><span class="sxs-lookup"><span data-stu-id="746b6-107">Create a text file (.txt) using a text editor such as Notepad.</span></span>

2. <span data-ttu-id="746b6-108">Скопируйте следующие строки в файле форматирования.</span><span class="sxs-lookup"><span data-stu-id="746b6-108">Copy the following lines into the formatting file.</span></span>

   ```xml
   <?xml version="1.0" encoding="utf-8" ?>
   <Configuration>
   <ViewDefinitions>
   </ViewDefinitions>
   </Configuration>
   ```

   - <span data-ttu-id="746b6-109">\<Конфигурации >\</Configuration > теги определяющие корневой `Configuration` узла.</span><span class="sxs-lookup"><span data-stu-id="746b6-109">The \<Configuration>\</Configuration> tags define the root `Configuration` node.</span></span> <span data-ttu-id="746b6-110">Все дополнительные теги XML будет заключаться в этот узел.</span><span class="sxs-lookup"><span data-stu-id="746b6-110">All additional XML tags will be enclosed within this node.</span></span>

   - <span data-ttu-id="746b6-111"><ViewDefinitions> </ViewDefinitions> Теги определяют `ViewDefinitions` узла.</span><span class="sxs-lookup"><span data-stu-id="746b6-111">The <ViewDefinitions></ViewDefinitions> tags define the `ViewDefinitions` node.</span></span> <span data-ttu-id="746b6-112">Все представления определяются в пределах этого узла.</span><span class="sxs-lookup"><span data-stu-id="746b6-112">All views are defined within this node.</span></span>

3. <span data-ttu-id="746b6-113">Сохраните файл в папку установки Windows PowerShell, в папку модуля или во вложенную папку папки модуля.</span><span class="sxs-lookup"><span data-stu-id="746b6-113">Save the file to the Windows PowerShell installation folder, to your module folder, or to a subfolder of the module folder.</span></span> <span data-ttu-id="746b6-114">При сохранении файла, используйте следующий формат имени: `MyFile.format.ps1xml`.</span><span class="sxs-lookup"><span data-stu-id="746b6-114">Use the following name format when you save the file:  `MyFile.format.ps1xml`.</span></span> <span data-ttu-id="746b6-115">Необходимо использовать файлы форматирования `.format.ps1xml` расширения.</span><span class="sxs-lookup"><span data-stu-id="746b6-115">Formatting files must use the `.format.ps1xml` extension.</span></span>

   <span data-ttu-id="746b6-116">Теперь вы готовы добавить представления в файле форматирования.</span><span class="sxs-lookup"><span data-stu-id="746b6-116">You are now ready to add views to the formatting file.</span></span> <span data-ttu-id="746b6-117">Нет ограничений на количество представлений, которые могут быть определены в файле форматирования.</span><span class="sxs-lookup"><span data-stu-id="746b6-117">There is no limit to the number of views that can be defined in a formatting file.</span></span> <span data-ttu-id="746b6-118">Можно добавить одно представление для каждого объекта, несколько представлений для одного объекта или одно представление, используется несколько объектов.</span><span class="sxs-lookup"><span data-stu-id="746b6-118">You can add a single view for each object, multiple views for the same object, or a single view that is used by multiple objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="746b6-119">См. также</span><span class="sxs-lookup"><span data-stu-id="746b6-119">See Also</span></span>

[<span data-ttu-id="746b6-120">Написание форматирования Windows PowerShell и типы файлов</span><span class="sxs-lookup"><span data-stu-id="746b6-120">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
