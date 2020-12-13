---
ms.date: 09/12/2016
ms.topic: reference
title: Как проверить обновляемую справку
description: Как проверить обновляемую справку
ms.openlocfilehash: 47873089bfa1b918ea9970915e829a22aa7254c5
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667629"
---
# <a name="how-to-test-updatable-help"></a><span data-ttu-id="f8e9c-103">Как проверить обновляемую справку</span><span class="sxs-lookup"><span data-stu-id="f8e9c-103">How to Test Updatable Help</span></span>

<span data-ttu-id="f8e9c-104">В этом разделе описываются подходы к тестированию обновляемой справки для модуля.</span><span class="sxs-lookup"><span data-stu-id="f8e9c-104">This topic describes approaches to testing Updatable Help for a module.</span></span>

## <a name="using-verbose-to-detect-errors"></a><span data-ttu-id="f8e9c-105">Использование verbose для обнаружения ошибок</span><span class="sxs-lookup"><span data-stu-id="f8e9c-105">Using Verbose to Detect Errors</span></span>

<span data-ttu-id="f8e9c-106">После отправки XML-файлов HelpInfo и CAB для модуля протестируйте файлы, выполнив команду [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) с параметром **verbose** .</span><span class="sxs-lookup"><span data-stu-id="f8e9c-106">After uploading the HelpInfo XML file and CAB files for your module, test the files by running an [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) command with the **Verbose** parameter.</span></span> <span data-ttu-id="f8e9c-107">Параметр **verbose** направляет сведения `Update-Help` о критических шагах в действиях, изчитав ключ **HelpInfoUri** в манифесте модуля, чтобы проверить типы файлов в распакованном CAB-файле и поместить файлы в каталог модуля, зависящего от языка.</span><span class="sxs-lookup"><span data-stu-id="f8e9c-107">The **Verbose** parameter directs `Update-Help` to report the critical steps in its actions, from reading the **HelpInfoUri** key in the module manifest to validating the file types in the unpacked CAB file and placing the files in the language-specific module directory.</span></span>

<span data-ttu-id="f8e9c-108">После разрешения всех подробных сообщений выполните `Update-Help` команду с параметром **Debug** .</span><span class="sxs-lookup"><span data-stu-id="f8e9c-108">When all verbose messages are resolved, run an `Update-Help` command with the **Debug** parameter.</span></span>
<span data-ttu-id="f8e9c-109">Этот параметр должен обнаружить все оставшиеся проблемы с обновляемыми файлами справки.</span><span class="sxs-lookup"><span data-stu-id="f8e9c-109">This parameter should detect any remaining problems with the Updatable Help files.</span></span>
