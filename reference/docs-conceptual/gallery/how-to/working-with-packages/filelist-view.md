---
ms.date: 06/12/2017
contributor: JKeithB
keywords: коллекции,powershell,командлет,psgallery
title: Функция FileList в коллекции
ms.openlocfilehash: 5f372c943c73fa8e1014657394e40eaedef5d045
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "71328245"
---
# <a name="filelist-feature-in-the-gallery"></a><span data-ttu-id="d806b-103">Функция FileList в коллекции</span><span class="sxs-lookup"><span data-stu-id="d806b-103">FileList feature in the Gallery</span></span>

<span data-ttu-id="d806b-104">Вы можете просматривать содержимое всех пакетов, опубликованных в коллекции.</span><span class="sxs-lookup"><span data-stu-id="d806b-104">You are able to view the contents in all packages published in the gallery.</span></span>

<span data-ttu-id="d806b-105">Эта функция состоит из двух частей: отображение списка файлов пакета и содержимого поддерживаемых типов файлов.</span><span class="sxs-lookup"><span data-stu-id="d806b-105">This feature includes two parts: listing the files within the package, and displaying file contents for supported file types.</span></span> <span data-ttu-id="d806b-106">В настоящее время поддерживается отображение содержимого файлов со следующими расширениями: PS1, PSM1, PSD1, PS1XML, XML и TXT.</span><span class="sxs-lookup"><span data-stu-id="d806b-106">Currently we support displaying the contents of the following file extensions: .ps1, .psm1, .psd1, .ps1xml, .xml and .txt.</span></span> <span data-ttu-id="d806b-107">В следующих версиях будет добавлена поддержка дополнительных расширений.</span><span class="sxs-lookup"><span data-stu-id="d806b-107">We will be supporting more file extensions in the next releases.</span></span>

## <a name="where-to-find-filelist"></a><span data-ttu-id="d806b-108">Где находится FileList</span><span class="sxs-lookup"><span data-stu-id="d806b-108">Where to Find FileList</span></span>

<span data-ttu-id="d806b-109">На странице каждого отдельного пакета есть раздел FileList и ссылка **Показать**.</span><span class="sxs-lookup"><span data-stu-id="d806b-109">On each individual package page, you will be able to find FileList section and a **Show** link.</span></span> <span data-ttu-id="d806b-110">Щелкните ссылку "Показать". Откроется полный список элементов, содержащихся в пакете.</span><span class="sxs-lookup"><span data-stu-id="d806b-110">Click on the Show and you will find a complete list of items contained in the package.</span></span>

<span data-ttu-id="d806b-111">Каждый поддерживаемый тип файлов отображается как гиперссылка, щелкнув которую вы перейдете на новую страницу, где содержимое файла будет показано с выделением синтаксиса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d806b-111">Each supported file type is displayed as a hyperlink, and clicking it will take you to a new page with file contents displayed in PowerShell syntax highlighting.</span></span> <span data-ttu-id="d806b-112">Щелкнув заголовок или версию пакета, отображаемые в верхней части экрана, вы вернетесь на страницу сведений о пакете.</span><span class="sxs-lookup"><span data-stu-id="d806b-112">Clicking on the title or the version of the package, which is displayed at the top of the screen, will bring you back to package detail page.</span></span>
