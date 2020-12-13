---
ms.date: 09/13/2016
ms.topic: reference
title: Как создать XML-файл HelpInfo
description: Как создать XML-файл HelpInfo
ms.openlocfilehash: d5a24306aa6488fdefad0b7b1ea9e2978a93a7b5
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92647712"
---
# <a name="how-to-create-a-helpinfo-xml-file"></a><span data-ttu-id="6f304-103">Как создать XML-файл HelpInfo</span><span class="sxs-lookup"><span data-stu-id="6f304-103">How to Create a HelpInfo XML File</span></span>

<span data-ttu-id="6f304-104">В этом разделе объясняется, как создать и заполнить файл справочной информации, который обычно называется XML-файлом HelpInfo, для функции обновляемой справки PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6f304-104">This topics in this section explains how to create and populate a help information file, commonly known as a "HelpInfo XML file," for the PowerShell Updatable Help feature.</span></span>

## <a name="helpinfo-xml-file-overview"></a><span data-ttu-id="6f304-105">Обзор XML-файла HelpInfo</span><span class="sxs-lookup"><span data-stu-id="6f304-105">HelpInfo XML File Overview</span></span>

<span data-ttu-id="6f304-106">XML-файл HelpInfo является основным источником сведений об обновляемой справке для модуля.</span><span class="sxs-lookup"><span data-stu-id="6f304-106">The HelpInfo XML file is the primary source of information about Updatable Help for the module.</span></span> <span data-ttu-id="6f304-107">Он включает расположение файлов справки для модулей, Поддерживаемые языки и региональные параметры пользовательского интерфейса, а также номера версий, с помощью которых обновляемая Справка определяет, есть ли у пользователя самые новые файлы справки.</span><span class="sxs-lookup"><span data-stu-id="6f304-107">It includes the location of the help files for the modules, the supported UI cultures, and the version numbers that Updatable Help uses to determine whether the user has the newest help files.</span></span>

<span data-ttu-id="6f304-108">Каждый модуль имеет только один XML-файл HelpInfo, даже если модуль содержит несколько файлов справки для нескольких языков и региональных параметров пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="6f304-108">Each module has just one HelpInfo XML file, even if the module includes multiple help files for multiple UI cultures.</span></span> <span data-ttu-id="6f304-109">Автор модуля создает XML-файл HelpInfo и помещает его в расположение в Интернете, указанное ключом **HelpInfoUri** в манифесте модуля.</span><span class="sxs-lookup"><span data-stu-id="6f304-109">The module author creates the HelpInfo XML file and places it in the internet location that is specified by the **HelpInfoUri** key in the module manifest.</span></span> <span data-ttu-id="6f304-110">Когда файлы справки модуля обновляются и передаются, автор модуля обновляет XML-файл HelpInfo и заменяет исходный XML-файл HelpInfo новой версией.</span><span class="sxs-lookup"><span data-stu-id="6f304-110">When the module help files are updated and uploaded, the module author updates the HelpInfo XML file and replaces the original HelpInfo XML file with the new version.</span></span>

<span data-ttu-id="6f304-111">Очень важно, чтобы XML-файл HelpInfo был тщательно сохранен.</span><span class="sxs-lookup"><span data-stu-id="6f304-111">It is critical that the HelpInfo XML file is carefully maintained.</span></span> <span data-ttu-id="6f304-112">Если вы передаете новые файлы, но не забудьте увеличить номера версий, обновляемая Справка не будет скачивать новые файлы на компьютеры пользователей.</span><span class="sxs-lookup"><span data-stu-id="6f304-112">If you upload new files, but forget to increment the version numbers, Updatable Help will not download the new files to users' computers.</span></span> <span data-ttu-id="6f304-113">Если добавить файлы справки для нового языка и региональных параметров пользовательского интерфейса, но не обновлять XML-файл HelpInfo или поместить его в нужное расположение, обновляемая Справка не будет скачивать новые файлы.</span><span class="sxs-lookup"><span data-stu-id="6f304-113">if you add help files for a new UI culture, but don't update the HelpInfo XML file or place it in the correct location, Updatable Help will not download the new files.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="6f304-114">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="6f304-114">In this section</span></span>

<span data-ttu-id="6f304-115">Этот раздел содержит следующие темы.</span><span class="sxs-lookup"><span data-stu-id="6f304-115">This section includes the following topics.</span></span>

- [<span data-ttu-id="6f304-116">Схема XML-файла HelpInfo</span><span class="sxs-lookup"><span data-stu-id="6f304-116">HelpInfo XML Schema</span></span>](./helpinfo-xml-schema.md)

- [<span data-ttu-id="6f304-117">Пример XML-файла HelpInfo</span><span class="sxs-lookup"><span data-stu-id="6f304-117">HelpInfo XML Sample File</span></span>](./helpinfo-xml-sample-file.md)

- [<span data-ttu-id="6f304-118">Как назвать XML-файл HelpInfo</span><span class="sxs-lookup"><span data-stu-id="6f304-118">How to Name a HelpInfo XML File</span></span>](./how-to-name-a-helpinfo-xml-file.md)

- [<span data-ttu-id="6f304-119">Как задать номера версий XML-файла HelpInfo</span><span class="sxs-lookup"><span data-stu-id="6f304-119">How to Set HelpInfo XML Version Numbers</span></span>](./how-to-set-helpinfo-xml-version-numbers.md)

## <a name="see-also"></a><span data-ttu-id="6f304-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="6f304-120">See Also</span></span>

[<span data-ttu-id="6f304-121">Поддержка обновляемой справки</span><span class="sxs-lookup"><span data-stu-id="6f304-121">Supporting Updatable Help</span></span>](./supporting-updatable-help.md)
