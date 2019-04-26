---
title: Как создать XML-файл HelpInfo | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3971ce1f-271c-4938-a9d3-47ff3aaf7219
caps.latest.revision: 9
ms.openlocfilehash: 7df9764fd573b75f285fec592448a550e481bea3
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62082419"
---
# <a name="how-to-create-a-helpinfo-xml-file"></a><span data-ttu-id="47138-102">Как создать XML-файл HelpInfo</span><span class="sxs-lookup"><span data-stu-id="47138-102">How to Create a HelpInfo XML File</span></span>

<span data-ttu-id="47138-103">В этом разделе, в этом разделе объясняется, как создать и заполнить файл сведений о справке, известную как «HelpInfo XML файла» для функцию обновляемой справки Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="47138-103">This topics in this section explains how to create and populate a help information file, commonly known as a "HelpInfo XML file," for the Windows PowerShell Updatable Help feature.</span></span>

## <a name="helpinfo-xml-file-overview"></a><span data-ttu-id="47138-104">Общие сведения о файле HelpInfo XML</span><span class="sxs-lookup"><span data-stu-id="47138-104">HelpInfo XML File Overview</span></span>

<span data-ttu-id="47138-105">XML-файл HelpInfo является основным источником информации об обновляемой справке для модуля.</span><span class="sxs-lookup"><span data-stu-id="47138-105">The HelpInfo XML file is the primary source of information about Updatable Help for the module.</span></span> <span data-ttu-id="47138-106">Он включает расположение файлов справки для модулей, поддерживаемых языков и региональных параметров пользовательского интерфейса и номера версий, обновляемую справку для определения, имеет ли пользователь новейшие файлы справки.</span><span class="sxs-lookup"><span data-stu-id="47138-106">It includes the location of the help files for the modules, the supported UI cultures, and the version numbers that Updatable Help uses to determine whether the user has the newest help files.</span></span>

<span data-ttu-id="47138-107">Каждый модуль имеет только один XML-файл HelpInfo, даже если модуль содержит несколько файлов справки для нескольких языков и региональных параметров пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="47138-107">Each module has just one HelpInfo XML file, even if the module includes multiple help files for multiple UI cultures.</span></span> <span data-ttu-id="47138-108">Создает XML-файл HelpInfo автора модуля и помещает ее в расположения в Интернете, задаваемый **HelpInfoUri** ключа в манифесте модуля.</span><span class="sxs-lookup"><span data-stu-id="47138-108">The module author creates the HelpInfo XML file and places it in the Internet location that is specified by the **HelpInfoUri** key in the module manifest.</span></span> <span data-ttu-id="47138-109">Если файлы справки для модуля обновления, чтобы загружены, автора модуля обновляет файл HelpInfo XML и заменяет исходный файл HelpInfo XML с новой версией.</span><span class="sxs-lookup"><span data-stu-id="47138-109">When the module help files are updated and uploaded, the module author updates the HelpInfo XML file and replaces the original HelpInfo XML file with the new version.</span></span>

<span data-ttu-id="47138-110">Крайне важно, что XML-файл HelpInfo тщательно сохранится.</span><span class="sxs-lookup"><span data-stu-id="47138-110">It is critical that the HelpInfo XML file is carefully maintained.</span></span> <span data-ttu-id="47138-111">Если загрузить новые файлы, но забыть номера версий, обновляемой справки не будет загружать новые файлы на компьютеры пользователей.</span><span class="sxs-lookup"><span data-stu-id="47138-111">If you upload new files, but forget to increment the version numbers, Updatable Help will not download the new files to users' computers.</span></span> <span data-ttu-id="47138-112">При добавлении файлы справки для нового пользовательского языка и региональных параметров, но не обновить файл HelpInfo XML или поместить его в нужное место, обновляемую справку, не скачивают новые файлы.</span><span class="sxs-lookup"><span data-stu-id="47138-112">if you add help files for a new UI culture, but don't update the HelpInfo XML file or place it in the correct location, Updatable Help will not download the new files.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="47138-113">Содержание раздела</span><span class="sxs-lookup"><span data-stu-id="47138-113">In this section</span></span>

<span data-ttu-id="47138-114">Этот раздел содержит следующие темы.</span><span class="sxs-lookup"><span data-stu-id="47138-114">This section includes the following topics.</span></span>

- [<span data-ttu-id="47138-115">HelpInfo XML-схемы</span><span class="sxs-lookup"><span data-stu-id="47138-115">HelpInfo XML Schema</span></span>](./helpinfo-xml-schema.md)

- [<span data-ttu-id="47138-116">Пример файла HelpInfo XML</span><span class="sxs-lookup"><span data-stu-id="47138-116">HelpInfo XML Sample File</span></span>](./helpinfo-xml-sample-file.md)

- [<span data-ttu-id="47138-117">Принципы присвоения имен XML-файл HelpInfo</span><span class="sxs-lookup"><span data-stu-id="47138-117">How to Name a HelpInfo XML File</span></span>](./how-to-name-a-helpinfo-xml-file.md)

- [<span data-ttu-id="47138-118">Как задать номера версий HelpInfo XML</span><span class="sxs-lookup"><span data-stu-id="47138-118">How to Set HelpInfo XML Version Numbers</span></span>](./how-to-set-helpinfo-xml-version-numbers.md)

## <a name="see-also"></a><span data-ttu-id="47138-119">См. также</span><span class="sxs-lookup"><span data-stu-id="47138-119">See Also</span></span>

[<span data-ttu-id="47138-120">Поддержка обновляемой справки</span><span class="sxs-lookup"><span data-stu-id="47138-120">Supporting Updatable Help</span></span>](./supporting-updatable-help.md)