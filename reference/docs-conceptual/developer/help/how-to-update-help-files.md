---
ms.date: 09/12/2016
ms.topic: reference
title: Как обновить файлы справки
description: Как обновить файлы справки
ms.openlocfilehash: 19bf501cf91b1eb5dabb334c2179953590b40232
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92649586"
---
# <a name="how-to-update-help-files"></a><span data-ttu-id="e4c05-103">Как обновить файлы справки</span><span class="sxs-lookup"><span data-stu-id="e4c05-103">How to Update Help Files</span></span>

<span data-ttu-id="e4c05-104">В этом разделе объясняется, как обновить файлы справки для модуля, поддерживающего обновляемую справку.</span><span class="sxs-lookup"><span data-stu-id="e4c05-104">This topic explains how to update help files for a module that supports Updatable Help.</span></span>

## <a name="updating-help-files"></a><span data-ttu-id="e4c05-105">Обновление файлов справки</span><span class="sxs-lookup"><span data-stu-id="e4c05-105">Updating Help Files</span></span>

<span data-ttu-id="e4c05-106">Существует множество причин для обновления файлов справки, например исправления ошибок, уточнения концепции, ответа на часто задаваемые вопросы, добавления новых файлов или добавления новых и лучших примеров.</span><span class="sxs-lookup"><span data-stu-id="e4c05-106">There are many reasons to update help files, such as correcting errors, clarifying a concept, answering a frequently-asked question, adding new files, or adding new and better examples.</span></span>

<span data-ttu-id="e4c05-107">Чтобы обновить файл справки, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="e4c05-107">To update a help file:</span></span>

1. <span data-ttu-id="e4c05-108">Измените файлы.</span><span class="sxs-lookup"><span data-stu-id="e4c05-108">Change the files.</span></span>
1. <span data-ttu-id="e4c05-109">Перевод файлов в другие языки и региональные параметры пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="e4c05-109">Translate the files into other UI cultures.</span></span>
1. <span data-ttu-id="e4c05-110">Собирайте все файлы справки (новые, измененные и неизмененные) для модуля в каждом языке и региональных параметрах пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="e4c05-110">Collect all help files (new, changed, and unchanged) for the module in each UI culture.</span></span>
1. <span data-ttu-id="e4c05-111">Проверьте файлы по схеме XML.</span><span class="sxs-lookup"><span data-stu-id="e4c05-111">Validate the files against the XML schema.</span></span>
1. <span data-ttu-id="e4c05-112">Перестройте CAB-файлы для каждого языка и региональных параметров пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="e4c05-112">Rebuild the CAB files for each UI culture.</span></span>
1. <span data-ttu-id="e4c05-113">В XML-файле HelpInfo Увеличьте номер версии файла CAB для каждого языка и региональных параметров пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="e4c05-113">In the HelpInfo XML file, increment the version numbers of the CAB file for each UI culture.</span></span>
1. <span data-ttu-id="e4c05-114">Передайте новые файлы CAB в расположение, указанное значением элемента **хелпконтентури** в XML-файле HelpInfo.</span><span class="sxs-lookup"><span data-stu-id="e4c05-114">Upload the new CAB files to the location that is specified by the value of the **HelpContentUri** element in the HelpInfo XML file.</span></span> <span data-ttu-id="e4c05-115">Замените старые CAB-файлы новыми CAB-файлами.</span><span class="sxs-lookup"><span data-stu-id="e4c05-115">Replace the older CAB files with the new CAB files.</span></span>
1. <span data-ttu-id="e4c05-116">Передайте обновленный XML-файл HelpInfo в расположение, указанное ключом **HelpInfoUri** в манифесте модуля.</span><span class="sxs-lookup"><span data-stu-id="e4c05-116">Upload the updated HelpInfo XML file to the location that is specified by the **HelpInfoUri** key in the module manifest.</span></span> <span data-ttu-id="e4c05-117">Замените старый XML-файл HelpInfo новым файлом.</span><span class="sxs-lookup"><span data-stu-id="e4c05-117">Replace the older HelpInfo XML file with the new file.</span></span>
