---
title: Как создать XML-файл HelpInfo
ms.date: 09/13/2016
ms.openlocfilehash: e395746e51309477bbcbff51b4591de3f73ce0db
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/22/2020
ms.locfileid: "86893311"
---
# <a name="how-to-create-a-helpinfo-xml-file"></a><span data-ttu-id="b6070-102">Как создать XML-файл HelpInfo</span><span class="sxs-lookup"><span data-stu-id="b6070-102">How to Create a HelpInfo XML File</span></span>

<span data-ttu-id="b6070-103">В этом разделе объясняется, как создать и заполнить файл справочной информации, который обычно называется XML-файлом HelpInfo, для функции обновляемой справки PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b6070-103">This topics in this section explains how to create and populate a help information file, commonly known as a "HelpInfo XML file," for the PowerShell Updatable Help feature.</span></span>

## <a name="helpinfo-xml-file-overview"></a><span data-ttu-id="b6070-104">Обзор XML-файла HelpInfo</span><span class="sxs-lookup"><span data-stu-id="b6070-104">HelpInfo XML File Overview</span></span>

<span data-ttu-id="b6070-105">XML-файл HelpInfo является основным источником сведений об обновляемой справке для модуля.</span><span class="sxs-lookup"><span data-stu-id="b6070-105">The HelpInfo XML file is the primary source of information about Updatable Help for the module.</span></span> <span data-ttu-id="b6070-106">Он включает расположение файлов справки для модулей, Поддерживаемые языки и региональные параметры пользовательского интерфейса, а также номера версий, с помощью которых обновляемая Справка определяет, есть ли у пользователя самые новые файлы справки.</span><span class="sxs-lookup"><span data-stu-id="b6070-106">It includes the location of the help files for the modules, the supported UI cultures, and the version numbers that Updatable Help uses to determine whether the user has the newest help files.</span></span>

<span data-ttu-id="b6070-107">Каждый модуль имеет только один XML-файл HelpInfo, даже если модуль содержит несколько файлов справки для нескольких языков и региональных параметров пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="b6070-107">Each module has just one HelpInfo XML file, even if the module includes multiple help files for multiple UI cultures.</span></span> <span data-ttu-id="b6070-108">Автор модуля создает XML-файл HelpInfo и помещает его в расположение в Интернете, указанное ключом **HelpInfoUri** в манифесте модуля.</span><span class="sxs-lookup"><span data-stu-id="b6070-108">The module author creates the HelpInfo XML file and places it in the internet location that is specified by the **HelpInfoUri** key in the module manifest.</span></span> <span data-ttu-id="b6070-109">Когда файлы справки модуля обновляются и передаются, автор модуля обновляет XML-файл HelpInfo и заменяет исходный XML-файл HelpInfo новой версией.</span><span class="sxs-lookup"><span data-stu-id="b6070-109">When the module help files are updated and uploaded, the module author updates the HelpInfo XML file and replaces the original HelpInfo XML file with the new version.</span></span>

<span data-ttu-id="b6070-110">Очень важно, чтобы XML-файл HelpInfo был тщательно сохранен.</span><span class="sxs-lookup"><span data-stu-id="b6070-110">It is critical that the HelpInfo XML file is carefully maintained.</span></span> <span data-ttu-id="b6070-111">Если вы передаете новые файлы, но не забудьте увеличить номера версий, обновляемая Справка не будет скачивать новые файлы на компьютеры пользователей.</span><span class="sxs-lookup"><span data-stu-id="b6070-111">If you upload new files, but forget to increment the version numbers, Updatable Help will not download the new files to users' computers.</span></span> <span data-ttu-id="b6070-112">Если добавить файлы справки для нового языка и региональных параметров пользовательского интерфейса, но не обновлять XML-файл HelpInfo или поместить его в нужное расположение, обновляемая Справка не будет скачивать новые файлы.</span><span class="sxs-lookup"><span data-stu-id="b6070-112">if you add help files for a new UI culture, but don't update the HelpInfo XML file or place it in the correct location, Updatable Help will not download the new files.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="b6070-113">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="b6070-113">In this section</span></span>

<span data-ttu-id="b6070-114">Этот раздел содержит следующие темы.</span><span class="sxs-lookup"><span data-stu-id="b6070-114">This section includes the following topics.</span></span>

- [<span data-ttu-id="b6070-115">Схема XML-файла HelpInfo</span><span class="sxs-lookup"><span data-stu-id="b6070-115">HelpInfo XML Schema</span></span>](./helpinfo-xml-schema.md)

- [<span data-ttu-id="b6070-116">Пример XML-файла HelpInfo</span><span class="sxs-lookup"><span data-stu-id="b6070-116">HelpInfo XML Sample File</span></span>](./helpinfo-xml-sample-file.md)

- [<span data-ttu-id="b6070-117">Как назвать XML-файл HelpInfo</span><span class="sxs-lookup"><span data-stu-id="b6070-117">How to Name a HelpInfo XML File</span></span>](./how-to-name-a-helpinfo-xml-file.md)

- [<span data-ttu-id="b6070-118">Как задать номера версий XML-файла HelpInfo</span><span class="sxs-lookup"><span data-stu-id="b6070-118">How to Set HelpInfo XML Version Numbers</span></span>](./how-to-set-helpinfo-xml-version-numbers.md)

## <a name="see-also"></a><span data-ttu-id="b6070-119">См. также</span><span class="sxs-lookup"><span data-stu-id="b6070-119">See Also</span></span>

[<span data-ttu-id="b6070-120">Поддержка обновляемой справки</span><span class="sxs-lookup"><span data-stu-id="b6070-120">Supporting Updatable Help</span></span>](./supporting-updatable-help.md)
