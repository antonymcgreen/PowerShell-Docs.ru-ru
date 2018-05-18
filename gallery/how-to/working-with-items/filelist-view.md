---
ms.date: 06/12/2017
contributor: JKeithB
ms.topic: conceptual
keywords: коллекции,powershell,командлет,psgallery
title: Функция FileList в коллекции
ms.openlocfilehash: d4d78d4eab89b0e3d48d18ed815d8f77327cc81d
ms.sourcegitcommit: e9ad4d85fd7eb72fb5bc37f6ca3ae1282ae3c6d7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/10/2018
---
# <a name="filelist-feature-in-the-gallery"></a><span data-ttu-id="f2400-103">Функция FileList в коллекции</span><span class="sxs-lookup"><span data-stu-id="f2400-103">FileList feature in the Gallery</span></span>

<span data-ttu-id="f2400-104">Вы можете просматривать содержимое всех элементов, опубликованных в коллекции.</span><span class="sxs-lookup"><span data-stu-id="f2400-104">You are able to view the contents in all items published in the gallery.</span></span>

<span data-ttu-id="f2400-105">Эта функция состоит из двух частей: отображение списка файлов элемента и содержимого поддерживаемых типов файлов.</span><span class="sxs-lookup"><span data-stu-id="f2400-105">This feature includes two parts: listing the files within the item, and displaying file contents for supported file types.</span></span> <span data-ttu-id="f2400-106">В настоящее время поддерживается отображение содержимого файлов со следующими расширениями: PS1, PSM1, PSD1, PS1XML, XML и TXT.</span><span class="sxs-lookup"><span data-stu-id="f2400-106">Currently we support displaying the contents of the following file extensions: .ps1, .psm1, .psd1, .ps1xml, .xml and .txt.</span></span> <span data-ttu-id="f2400-107">В следующих версиях будет добавлена поддержка дополнительных расширений.</span><span class="sxs-lookup"><span data-stu-id="f2400-107">We will be supporting more file extensions in the next releases.</span></span>

## <a name="where-to-find-filelist"></a><span data-ttu-id="f2400-108">Где находится FileList</span><span class="sxs-lookup"><span data-stu-id="f2400-108">Where to Find FileList</span></span>

<span data-ttu-id="f2400-109">На странице каждого отдельного элемента имеется раздел FileList и ссылка **Показать**.</span><span class="sxs-lookup"><span data-stu-id="f2400-109">On each individual item page, you will be able to find FileList section and a **Show** link.</span></span> <span data-ttu-id="f2400-110">Щелкните ссылку "Показать". Откроется полный список элементов, содержащихся в элементе.</span><span class="sxs-lookup"><span data-stu-id="f2400-110">Click on the Show and you will find a complete list of items contained in the item.</span></span>

<span data-ttu-id="f2400-111">Каждый поддерживаемый тип файлов отображается как гиперссылка, щелкнув которую вы перейдете на новую страницу, где содержимое файла будет показано с выделением синтаксиса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f2400-111">Each supported file type is displayed as a hyperlink, and clicking it will take you to a new page with file contents displayed in PowerShell syntax highlighting.</span></span> <span data-ttu-id="f2400-112">Щелкнув заголовок или версию элемента, отображаемые в верхней части экрана, вы вернетесь на страницу подробностей об элементе.</span><span class="sxs-lookup"><span data-stu-id="f2400-112">Clicking on the title or the version of the item, which is displayed at the top of the screen, will bring you back to item detail page.</span></span>