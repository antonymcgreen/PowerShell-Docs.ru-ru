---
title: Как обновить файлы справки
ms.date: 09/12/2016
ms.openlocfilehash: 80f7c8865729515de98648765fa36ce540e00162
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/22/2020
ms.locfileid: "86892954"
---
# <a name="how-to-update-help-files"></a><span data-ttu-id="b1540-102">Как обновить файлы справки</span><span class="sxs-lookup"><span data-stu-id="b1540-102">How to Update Help Files</span></span>

<span data-ttu-id="b1540-103">В этом разделе объясняется, как обновить файлы справки для модуля, поддерживающего обновляемую справку.</span><span class="sxs-lookup"><span data-stu-id="b1540-103">This topic explains how to update help files for a module that supports Updatable Help.</span></span>

## <a name="updating-help-files"></a><span data-ttu-id="b1540-104">Обновление файлов справки</span><span class="sxs-lookup"><span data-stu-id="b1540-104">Updating Help Files</span></span>

<span data-ttu-id="b1540-105">Существует множество причин для обновления файлов справки, например исправления ошибок, уточнения концепции, ответа на часто задаваемые вопросы, добавления новых файлов или добавления новых и лучших примеров.</span><span class="sxs-lookup"><span data-stu-id="b1540-105">There are many reasons to update help files, such as correcting errors, clarifying a concept, answering a frequently-asked question, adding new files, or adding new and better examples.</span></span>

<span data-ttu-id="b1540-106">Чтобы обновить файл справки, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="b1540-106">To update a help file:</span></span>

1. <span data-ttu-id="b1540-107">Измените файлы.</span><span class="sxs-lookup"><span data-stu-id="b1540-107">Change the files.</span></span>
1. <span data-ttu-id="b1540-108">Перевод файлов в другие языки и региональные параметры пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="b1540-108">Translate the files into other UI cultures.</span></span>
1. <span data-ttu-id="b1540-109">Собирайте все файлы справки (новые, измененные и неизмененные) для модуля в каждом языке и региональных параметрах пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="b1540-109">Collect all help files (new, changed, and unchanged) for the module in each UI culture.</span></span>
1. <span data-ttu-id="b1540-110">Проверьте файлы по схеме XML.</span><span class="sxs-lookup"><span data-stu-id="b1540-110">Validate the files against the XML schema.</span></span>
1. <span data-ttu-id="b1540-111">Перестройте CAB-файлы для каждого языка и региональных параметров пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="b1540-111">Rebuild the CAB files for each UI culture.</span></span>
1. <span data-ttu-id="b1540-112">В XML-файле HelpInfo Увеличьте номер версии файла CAB для каждого языка и региональных параметров пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="b1540-112">In the HelpInfo XML file, increment the version numbers of the CAB file for each UI culture.</span></span>
1. <span data-ttu-id="b1540-113">Передайте новые файлы CAB в расположение, указанное значением элемента **хелпконтентури** в XML-файле HelpInfo.</span><span class="sxs-lookup"><span data-stu-id="b1540-113">Upload the new CAB files to the location that is specified by the value of the **HelpContentUri** element in the HelpInfo XML file.</span></span> <span data-ttu-id="b1540-114">Замените старые CAB-файлы новыми CAB-файлами.</span><span class="sxs-lookup"><span data-stu-id="b1540-114">Replace the older CAB files with the new CAB files.</span></span>
1. <span data-ttu-id="b1540-115">Передайте обновленный XML-файл HelpInfo в расположение, указанное ключом **HelpInfoUri** в манифесте модуля.</span><span class="sxs-lookup"><span data-stu-id="b1540-115">Upload the updated HelpInfo XML file to the location that is specified by the **HelpInfoUri** key in the module manifest.</span></span> <span data-ttu-id="b1540-116">Замените старый XML-файл HelpInfo новым файлом.</span><span class="sxs-lookup"><span data-stu-id="b1540-116">Replace the older HelpInfo XML file with the new file.</span></span>
