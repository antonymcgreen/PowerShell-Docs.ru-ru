---
title: Способы тестирования обновляемой справки | Документация Майкрософт
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3e064048-2b94-4365-bdb7-f1ee7c0a7fd7
caps.latest.revision: 6
ms.openlocfilehash: f2f319a3cab4b4bd91e9b634dda57d58a6476b62
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56854740"
---
# <a name="how-to-test-updatable-help"></a><span data-ttu-id="a4547-102">Как проверить обновляемую справку</span><span class="sxs-lookup"><span data-stu-id="a4547-102">How to Test Updatable Help</span></span>

<span data-ttu-id="a4547-103">В этом разделе описаны подходы к тестированию обновляемую справку для модуля.</span><span class="sxs-lookup"><span data-stu-id="a4547-103">This topic describes approaches to testing Updatable Help for a module.</span></span>

## <a name="using-verbose-to-detect-errors"></a><span data-ttu-id="a4547-104">С помощью подробного для обнаружения ошибок</span><span class="sxs-lookup"><span data-stu-id="a4547-104">Using Verbose to Detect Errors</span></span>

<span data-ttu-id="a4547-105">После отправки XML-файл HelpInfo и CAB-файлы для вашего модуля, проверить файлы, запустив [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) с **Verbose** параметра.</span><span class="sxs-lookup"><span data-stu-id="a4547-105">After uploading the HelpInfo XML file and CAB files for your module, test the files by running an [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) command with the **Verbose** parameter.</span></span> <span data-ttu-id="a4547-106">**Verbose** параметр направляет `Update-Help` сообщить о важных этапов его действия, от чтения **HelpInfoUri** ключа в манифесте модуля к проверке типов файлов в распакованную CAB-файл и поместить файлы в каталоге модуля для конкретного языка.</span><span class="sxs-lookup"><span data-stu-id="a4547-106">The **Verbose** parameter directs `Update-Help` to report the critical steps in its actions, from reading the **HelpInfoUri** key in the module manifest to validating the file types in the unpacked CAB file and placing the files in the language-specific module directory.</span></span>
<span data-ttu-id="a4547-107">После отправки XML-файл HelpInfo и CAB-файлы для вашего модуля, проверить файлы, запустив [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) с **Verbose** параметра.</span><span class="sxs-lookup"><span data-stu-id="a4547-107">After uploading the HelpInfo XML file and CAB files for your module, test the files by running an [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) command with the **Verbose** parameter.</span></span> <span data-ttu-id="a4547-108">**Verbose** параметр направляет `Update-Help` сообщить о важных этапов его действия, от чтения **HelpInfoUri** ключа в манифесте модуля к проверке типов файлов в распакованную CAB-файл и поместить файлы в каталоге модуля для конкретного языка.</span><span class="sxs-lookup"><span data-stu-id="a4547-108">The **Verbose** parameter directs `Update-Help` to report the critical steps in its actions, from reading the **HelpInfoUri** key in the module manifest to validating the file types in the unpacked CAB file and placing the files in the language-specific module directory.</span></span>

<span data-ttu-id="a4547-109">При разрешении все подробные сообщения, запустите `Update-Help` с **Отладка** параметра.</span><span class="sxs-lookup"><span data-stu-id="a4547-109">When all verbose messages are resolved, run an `Update-Help` command with the **Debug** parameter.</span></span> <span data-ttu-id="a4547-110">Этот параметр определяет всех оставшихся проблем с обновляемых файлов справки.</span><span class="sxs-lookup"><span data-stu-id="a4547-110">This parameter should detect any remaining problems with the Updatable Help files.</span></span>