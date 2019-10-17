---
title: Проверка обновляемой справки | Документация Майкрософт
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3e064048-2b94-4365-bdb7-f1ee7c0a7fd7
caps.latest.revision: 6
ms.openlocfilehash: cecc6c26ccaece06462ddd74b53534137fcf3037
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72367153"
---
# <a name="how-to-test-updatable-help"></a><span data-ttu-id="1b74f-102">Как проверить обновляемую справку</span><span class="sxs-lookup"><span data-stu-id="1b74f-102">How to Test Updatable Help</span></span>

<span data-ttu-id="1b74f-103">В этом разделе описываются подходы к тестированию обновляемой справки для модуля.</span><span class="sxs-lookup"><span data-stu-id="1b74f-103">This topic describes approaches to testing Updatable Help for a module.</span></span>

## <a name="using-verbose-to-detect-errors"></a><span data-ttu-id="1b74f-104">Использование verbose для обнаружения ошибок</span><span class="sxs-lookup"><span data-stu-id="1b74f-104">Using Verbose to Detect Errors</span></span>

<span data-ttu-id="1b74f-105">После отправки XML-файлов HelpInfo и CAB для модуля протестируйте файлы, выполнив команду [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) с параметром **verbose** .</span><span class="sxs-lookup"><span data-stu-id="1b74f-105">After uploading the HelpInfo XML file and CAB files for your module, test the files by running an [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) command with the **Verbose** parameter.</span></span> <span data-ttu-id="1b74f-106">Параметр **verbose** направляет `Update-Help` для получения сведений о критических шагах в действиях, от считывания ключа **HelpInfoUri** в манифесте модуля для проверки типов файлов в распакованном CAB-файле и поместив файлы в соответствующий язык. Каталог модуля.</span><span class="sxs-lookup"><span data-stu-id="1b74f-106">The **Verbose** parameter directs `Update-Help` to report the critical steps in its actions, from reading the **HelpInfoUri** key in the module manifest to validating the file types in the unpacked CAB file and placing the files in the language-specific module directory.</span></span>

<span data-ttu-id="1b74f-107">После разрешения всех подробных сообщений выполните команду `Update-Help` с параметром **Debug** .</span><span class="sxs-lookup"><span data-stu-id="1b74f-107">When all verbose messages are resolved, run an `Update-Help` command with the **Debug** parameter.</span></span> <span data-ttu-id="1b74f-108">Этот параметр должен обнаружить все оставшиеся проблемы с обновляемыми файлами справки.</span><span class="sxs-lookup"><span data-stu-id="1b74f-108">This parameter should detect any remaining problems with the Updatable Help files.</span></span>