---
title: Создание XML-файла HelpInfo | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3971ce1f-271c-4938-a9d3-47ff3aaf7219
caps.latest.revision: 9
ms.openlocfilehash: 7df9764fd573b75f285fec592448a550e481bea3
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72367323"
---
# <a name="how-to-create-a-helpinfo-xml-file"></a><span data-ttu-id="b8560-102">Как создать XML-файл HelpInfo</span><span class="sxs-lookup"><span data-stu-id="b8560-102">How to Create a HelpInfo XML File</span></span>

<span data-ttu-id="b8560-103">В этом разделе объясняется, как создать и заполнить файл справочной информации, который обычно называется XML-файлом HelpInfo, для функции обновляемой справки Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b8560-103">This topics in this section explains how to create and populate a help information file, commonly known as a "HelpInfo XML file," for the Windows PowerShell Updatable Help feature.</span></span>

## <a name="helpinfo-xml-file-overview"></a><span data-ttu-id="b8560-104">Обзор XML-файла HelpInfo</span><span class="sxs-lookup"><span data-stu-id="b8560-104">HelpInfo XML File Overview</span></span>

<span data-ttu-id="b8560-105">XML-файл HelpInfo является основным источником сведений об обновляемой справке для модуля.</span><span class="sxs-lookup"><span data-stu-id="b8560-105">The HelpInfo XML file is the primary source of information about Updatable Help for the module.</span></span> <span data-ttu-id="b8560-106">Он включает расположение файлов справки для модулей, Поддерживаемые языки и региональные параметры пользовательского интерфейса, а также номера версий, с помощью которых обновляемая Справка определяет, есть ли у пользователя самые новые файлы справки.</span><span class="sxs-lookup"><span data-stu-id="b8560-106">It includes the location of the help files for the modules, the supported UI cultures, and the version numbers that Updatable Help uses to determine whether the user has the newest help files.</span></span>

<span data-ttu-id="b8560-107">Каждый модуль имеет только один XML-файл HelpInfo, даже если модуль содержит несколько файлов справки для нескольких языков и региональных параметров пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="b8560-107">Each module has just one HelpInfo XML file, even if the module includes multiple help files for multiple UI cultures.</span></span> <span data-ttu-id="b8560-108">Автор модуля создает XML-файл HelpInfo и помещает его в расположение в Интернете, указанное ключом **HelpInfoUri** в манифесте модуля.</span><span class="sxs-lookup"><span data-stu-id="b8560-108">The module author creates the HelpInfo XML file and places it in the Internet location that is specified by the **HelpInfoUri** key in the module manifest.</span></span> <span data-ttu-id="b8560-109">Когда файлы справки модуля обновляются и передаются, автор модуля обновляет XML-файл HelpInfo и заменяет исходный XML-файл HelpInfo новой версией.</span><span class="sxs-lookup"><span data-stu-id="b8560-109">When the module help files are updated and uploaded, the module author updates the HelpInfo XML file and replaces the original HelpInfo XML file with the new version.</span></span>

<span data-ttu-id="b8560-110">Очень важно, чтобы XML-файл HelpInfo был тщательно сохранен.</span><span class="sxs-lookup"><span data-stu-id="b8560-110">It is critical that the HelpInfo XML file is carefully maintained.</span></span> <span data-ttu-id="b8560-111">Если вы передаете новые файлы, но не забудьте увеличить номера версий, обновляемая Справка не будет скачивать новые файлы на компьютеры пользователей.</span><span class="sxs-lookup"><span data-stu-id="b8560-111">If you upload new files, but forget to increment the version numbers, Updatable Help will not download the new files to users' computers.</span></span> <span data-ttu-id="b8560-112">Если добавить файлы справки для нового языка и региональных параметров пользовательского интерфейса, но не обновлять XML-файл HelpInfo или поместить его в нужное расположение, обновляемая Справка не будет скачивать новые файлы.</span><span class="sxs-lookup"><span data-stu-id="b8560-112">if you add help files for a new UI culture, but don't update the HelpInfo XML file or place it in the correct location, Updatable Help will not download the new files.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="b8560-113">Содержание раздела</span><span class="sxs-lookup"><span data-stu-id="b8560-113">In this section</span></span>

<span data-ttu-id="b8560-114">Этот раздел содержит следующие темы.</span><span class="sxs-lookup"><span data-stu-id="b8560-114">This section includes the following topics.</span></span>

- [<span data-ttu-id="b8560-115">Схема XML HelpInfo</span><span class="sxs-lookup"><span data-stu-id="b8560-115">HelpInfo XML Schema</span></span>](./helpinfo-xml-schema.md)

- [<span data-ttu-id="b8560-116">Пример XML-файла HelpInfo</span><span class="sxs-lookup"><span data-stu-id="b8560-116">HelpInfo XML Sample File</span></span>](./helpinfo-xml-sample-file.md)

- [<span data-ttu-id="b8560-117">Как присвоить имя XML-файла HelpInfo</span><span class="sxs-lookup"><span data-stu-id="b8560-117">How to Name a HelpInfo XML File</span></span>](./how-to-name-a-helpinfo-xml-file.md)

- [<span data-ttu-id="b8560-118">Как задать номера версий XML HelpInfo</span><span class="sxs-lookup"><span data-stu-id="b8560-118">How to Set HelpInfo XML Version Numbers</span></span>](./how-to-set-helpinfo-xml-version-numbers.md)

## <a name="see-also"></a><span data-ttu-id="b8560-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="b8560-119">See Also</span></span>

[<span data-ttu-id="b8560-120">Поддержка обновляемой справки</span><span class="sxs-lookup"><span data-stu-id="b8560-120">Supporting Updatable Help</span></span>](./supporting-updatable-help.md)