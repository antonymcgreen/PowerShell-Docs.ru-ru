---
title: Обновление файлов справки | Документация Майкрософт
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 495869a6-080e-4401-9ddc-16edd2f86857
caps.latest.revision: 6
ms.openlocfilehash: 2c1fbd70aab1f65f33ea206b7ab1e2bd3dfd8c7a
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72367143"
---
# <a name="how-to-update-help-files"></a><span data-ttu-id="49fa7-102">Как обновить файлы справки</span><span class="sxs-lookup"><span data-stu-id="49fa7-102">How to Update Help Files</span></span>

<span data-ttu-id="49fa7-103">В этом разделе объясняется, как обновить файлы справки для модуля, поддерживающего обновляемую справку.</span><span class="sxs-lookup"><span data-stu-id="49fa7-103">This topic explains how to update help files for a module that supports Updatable Help.</span></span>

## <a name="updating-help-files"></a><span data-ttu-id="49fa7-104">Обновление файлов справки</span><span class="sxs-lookup"><span data-stu-id="49fa7-104">Updating Help Files</span></span>

<span data-ttu-id="49fa7-105">Существует множество причин для обновления файлов справки, например исправления ошибок, уточнения концепции, ответа на часто задаваемые вопросы, добавления новых файлов или добавления новых и лучших примеров.</span><span class="sxs-lookup"><span data-stu-id="49fa7-105">There are many reasons to update help files, such as correcting errors, clarifying a concept, answering a frequently-asked question, adding new files, or adding new and better examples.</span></span>

<span data-ttu-id="49fa7-106">Чтобы обновить файл справки, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="49fa7-106">To update a help file:</span></span>

1. <span data-ttu-id="49fa7-107">Измените файлы.</span><span class="sxs-lookup"><span data-stu-id="49fa7-107">Change the files.</span></span>

2. <span data-ttu-id="49fa7-108">Перевод файлов в другие языки и региональные параметры пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="49fa7-108">Translate the files into other UI cultures.</span></span>

3. <span data-ttu-id="49fa7-109">Собирайте все файлы справки (новые, измененные и неизмененные) для модуля в каждом языке и региональных параметрах пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="49fa7-109">Collect all help files (new, changed, and unchanged) for the module in each UI culture.</span></span>

4. <span data-ttu-id="49fa7-110">Проверьте файлы по схеме XML.</span><span class="sxs-lookup"><span data-stu-id="49fa7-110">Validate the files against the XML schema.</span></span>

5. <span data-ttu-id="49fa7-111">Перестройте CAB-файлы для каждого языка и региональных параметров пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="49fa7-111">Rebuild the CAB files for each UI culture.</span></span>

6. <span data-ttu-id="49fa7-112">В XML-файле HelpInfo Увеличьте номер версии файла CAB для каждого языка и региональных параметров пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="49fa7-112">In the HelpInfo XML file, increment the version numbers of the CAB file for each UI culture.</span></span>

7. <span data-ttu-id="49fa7-113">Передайте новые файлы CAB в расположение, указанное значением элемента **хелпконтентури** в XML-файле HelpInfo.</span><span class="sxs-lookup"><span data-stu-id="49fa7-113">Upload the new CAB files to the location that is specified by the value of the **HelpContentUri** element in the HelpInfo XML file.</span></span> <span data-ttu-id="49fa7-114">Замените старые CAB-файлы новыми CAB-файлами.</span><span class="sxs-lookup"><span data-stu-id="49fa7-114">Replace the older CAB files with the new CAB files.</span></span>

8. <span data-ttu-id="49fa7-115">Передайте обновленный XML-файл HelpInfo в расположение, указанное ключом **HelpInfoUri** в манифесте модуля.</span><span class="sxs-lookup"><span data-stu-id="49fa7-115">Upload the updated HelpInfo XML file to the location that is specified by the **HelpInfoUri** key in the module manifest.</span></span> <span data-ttu-id="49fa7-116">Замените старый XML-файл HelpInfo новым файлом.</span><span class="sxs-lookup"><span data-stu-id="49fa7-116">Replace the older HelpInfo XML file with the new file.</span></span>