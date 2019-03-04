---
title: Как обновить файлы справки | Документация Майкрософт
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 495869a6-080e-4401-9ddc-16edd2f86857
caps.latest.revision: 6
ms.openlocfilehash: 2c1fbd70aab1f65f33ea206b7ab1e2bd3dfd8c7a
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56855530"
---
# <a name="how-to-update-help-files"></a><span data-ttu-id="20837-102">Как обновить файлы справки</span><span class="sxs-lookup"><span data-stu-id="20837-102">How to Update Help Files</span></span>

<span data-ttu-id="20837-103">В этом разделе объясняется, как обновить файлы справки для модуля, который поддерживает обновляемую справку.</span><span class="sxs-lookup"><span data-stu-id="20837-103">This topic explains how to update help files for a module that supports Updatable Help.</span></span>

## <a name="updating-help-files"></a><span data-ttu-id="20837-104">Обновление файлов справки</span><span class="sxs-lookup"><span data-stu-id="20837-104">Updating Help Files</span></span>

<span data-ttu-id="20837-105">Существует множество причин для обновления файлов справки, такие как исправление ошибок, пояснение понятием, ответы на часто задаваемые вопросы, добавление новых файлов или новые и лучшие примеры.</span><span class="sxs-lookup"><span data-stu-id="20837-105">There are many reasons to update help files, such as correcting errors, clarifying a concept, answering a frequently-asked question, adding new files, or adding new and better examples.</span></span>

<span data-ttu-id="20837-106">Чтобы обновить файл справки:</span><span class="sxs-lookup"><span data-stu-id="20837-106">To update a help file:</span></span>

1. <span data-ttu-id="20837-107">Изменяет файлы.</span><span class="sxs-lookup"><span data-stu-id="20837-107">Change the files.</span></span>

2. <span data-ttu-id="20837-108">Преобразовать файлы в другие для языков и региональных параметров пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="20837-108">Translate the files into other UI cultures.</span></span>

3. <span data-ttu-id="20837-109">Соберите все файлы справки (новые, измененные и без изменений) для каждого языка пользовательского интерфейса в модуль.</span><span class="sxs-lookup"><span data-stu-id="20837-109">Collect all help files (new, changed, and unchanged) for the module in each UI culture.</span></span>

4. <span data-ttu-id="20837-110">Проверьте файлы, XML-схемы.</span><span class="sxs-lookup"><span data-stu-id="20837-110">Validate the files against the XML schema.</span></span>

5. <span data-ttu-id="20837-111">Перестройте CAB-файлы для каждого языка пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="20837-111">Rebuild the CAB files for each UI culture.</span></span>

6. <span data-ttu-id="20837-112">В файле HelpInfo XML обновлять номера версий CAB-файла для каждого языка пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="20837-112">In the HelpInfo XML file, increment the version numbers of the CAB file for each UI culture.</span></span>

7. <span data-ttu-id="20837-113">Отправка новых файлов CAB-ФАЙЛ в расположение, которое определяется по значению **HelpContentUri** в файле HelpInfo XML.</span><span class="sxs-lookup"><span data-stu-id="20837-113">Upload the new CAB files to the location that is specified by the value of the **HelpContentUri** element in the HelpInfo XML file.</span></span> <span data-ttu-id="20837-114">Замените старые версии файлов CAB-файла с новыми файлами CAB-файла.</span><span class="sxs-lookup"><span data-stu-id="20837-114">Replace the older CAB files with the new CAB files.</span></span>

8. <span data-ttu-id="20837-115">Отправьте обновленный файл HelpInfo XML в расположение, которое определяется **HelpInfoUri** ключа в манифесте модуля.</span><span class="sxs-lookup"><span data-stu-id="20837-115">Upload the updated HelpInfo XML file to the location that is specified by the **HelpInfoUri** key in the module manifest.</span></span> <span data-ttu-id="20837-116">Замените старые HelpInfo XML-файл с новым файлом.</span><span class="sxs-lookup"><span data-stu-id="20837-116">Replace the older HelpInfo XML file with the new file.</span></span>