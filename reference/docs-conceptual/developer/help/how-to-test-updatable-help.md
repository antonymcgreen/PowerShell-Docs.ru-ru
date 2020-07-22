---
title: Как проверить обновляемую справку
ms.date: 09/12/2016
ms.openlocfilehash: 0602349f853fddd0cadae545eaf0302c150e3a28
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/22/2020
ms.locfileid: "86892971"
---
# <a name="how-to-test-updatable-help"></a><span data-ttu-id="a5df0-102">Как проверить обновляемую справку</span><span class="sxs-lookup"><span data-stu-id="a5df0-102">How to Test Updatable Help</span></span>

<span data-ttu-id="a5df0-103">В этом разделе описываются подходы к тестированию обновляемой справки для модуля.</span><span class="sxs-lookup"><span data-stu-id="a5df0-103">This topic describes approaches to testing Updatable Help for a module.</span></span>

## <a name="using-verbose-to-detect-errors"></a><span data-ttu-id="a5df0-104">Использование verbose для обнаружения ошибок</span><span class="sxs-lookup"><span data-stu-id="a5df0-104">Using Verbose to Detect Errors</span></span>

<span data-ttu-id="a5df0-105">После отправки XML-файлов HelpInfo и CAB для модуля протестируйте файлы, выполнив команду [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) с параметром **verbose** .</span><span class="sxs-lookup"><span data-stu-id="a5df0-105">After uploading the HelpInfo XML file and CAB files for your module, test the files by running an [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) command with the **Verbose** parameter.</span></span> <span data-ttu-id="a5df0-106">Параметр **verbose** направляет сведения `Update-Help` о критических шагах в действиях, изчитав ключ **HelpInfoUri** в манифесте модуля, чтобы проверить типы файлов в распакованном CAB-файле и поместить файлы в каталог модуля, зависящего от языка.</span><span class="sxs-lookup"><span data-stu-id="a5df0-106">The **Verbose** parameter directs `Update-Help` to report the critical steps in its actions, from reading the **HelpInfoUri** key in the module manifest to validating the file types in the unpacked CAB file and placing the files in the language-specific module directory.</span></span>

<span data-ttu-id="a5df0-107">После разрешения всех подробных сообщений выполните `Update-Help` команду с параметром **Debug** .</span><span class="sxs-lookup"><span data-stu-id="a5df0-107">When all verbose messages are resolved, run an `Update-Help` command with the **Debug** parameter.</span></span>
<span data-ttu-id="a5df0-108">Этот параметр должен обнаружить все оставшиеся проблемы с обновляемыми файлами справки.</span><span class="sxs-lookup"><span data-stu-id="a5df0-108">This parameter should detect any remaining problems with the Updatable Help files.</span></span>
