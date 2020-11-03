---
description: В этой статье объясняется, как создать настройку считывания входных данных PowerShell в командной строке консоли.
keywords: powershell,командлет
Locale: en-US
ms.date: 01/04/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_psconsolehostreadline?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_PSConsoleHostReadLine
ms.openlocfilehash: 59373f7a69f5a27411c9087bb666929321f654c0
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2020
ms.locfileid: "93232994"
---
# <a name="about_psconsolehostreadline"></a><span data-ttu-id="d1923-104">about_PSConsoleHostReadLine</span><span class="sxs-lookup"><span data-stu-id="d1923-104">about_PSConsoleHostReadLine</span></span>

## <a name="short-description"></a><span data-ttu-id="d1923-105">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="d1923-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="d1923-106">В этой статье объясняется, как создать настройку считывания входных данных PowerShell в командной строке консоли.</span><span class="sxs-lookup"><span data-stu-id="d1923-106">Explains how to create a customize how PowerShell reads input at the console prompt.</span></span>

## <a name="long-description"></a><span data-ttu-id="d1923-107">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="d1923-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="d1923-108">Начиная с Windows PowerShell 3,0 можно написать функцию с именем Псконсолехостреадлине, которая переопределяет способ обработки ввода в консоли по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d1923-108">Starting in Windows PowerShell 3.0, you can write a function named PSConsoleHostReadLine that overrides the default way that console input is processed.</span></span>

### <a name="examples"></a><span data-ttu-id="d1923-109">Примеры</span><span class="sxs-lookup"><span data-stu-id="d1923-109">EXAMPLES</span></span>

<span data-ttu-id="d1923-110">В следующем примере запускается блокнот и получается ввод из текстового файла, создаваемого пользователем:</span><span class="sxs-lookup"><span data-stu-id="d1923-110">The following example launches Notepad and gets input from a text File that the user creates:</span></span>

```powershell
function PSConsoleHostReadLine
{
  $inputFile = Join-Path $env:TEMP PSConsoleHostReadLine
  Set-Content $inputFile "PS > "

  # Notepad opens. Enter your command in it, save the file, and then exit.
  notepad $inputFile | Out-Null
  $userInput = Get-Content $inputFile
  $resultingCommand = $userInput.Replace("PS >", "")
  $resultingCommand
}
```

### <a name="remarks"></a><span data-ttu-id="d1923-111">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="d1923-111">REMARKS</span></span>

<span data-ttu-id="d1923-112">По умолчанию PowerShell считывает входные данные из консоли, что называется режимом обработанные, в котором подсистема консоли Windows обрабатывает все нажатия клавиш, меню F7 и другие входные данные.</span><span class="sxs-lookup"><span data-stu-id="d1923-112">By default, PowerShell reads input from the console in what is known as "Cooked Mode" -- in which the Windows console subsystem handles all the keypresses, F7 menus, and other input.</span></span> <span data-ttu-id="d1923-113">При нажатии клавиши ВВОД или Tab PowerShell получает текст, который был введен до этого момента.</span><span class="sxs-lookup"><span data-stu-id="d1923-113">When you press Enter or Tab, PowerShell gets the text that you have typed up to that point.</span></span> <span data-ttu-id="d1923-114">Невозможно понять, что вы нажали Ctrl-R, CTRL-A, Ctrl-E или любые другие клавиши, прежде чем нажать клавишу ВВОД или TAB. В Windows PowerShell 3,0 функция Псконсолехостреадлине решает эту проблему.</span><span class="sxs-lookup"><span data-stu-id="d1923-114">There is no way for it to know that you pressed Ctrl-R, Ctrl-A, Ctrl-E, or any other keys before pressing Enter or Tab. In Windows PowerShell 3.0, the PSConsoleHostReadLine function solves this issue.</span></span> <span data-ttu-id="d1923-115">При определении функции с именем Псконсолехостреадлине на узле консоли PowerShell PowerShell вызывает эту функцию вместо механизма ввода "режима обработанные".</span><span class="sxs-lookup"><span data-stu-id="d1923-115">When you define a function named PSConsoleHostReadline in the PowerShell console host, PowerShell calls that function instead of the "Cooked Mode" input mechanism.</span></span>

### <a name="see-also"></a><span data-ttu-id="d1923-116">СМ. ТАКЖЕ</span><span class="sxs-lookup"><span data-stu-id="d1923-116">SEE ALSO</span></span>

[<span data-ttu-id="d1923-117">about_Prompts</span><span class="sxs-lookup"><span data-stu-id="d1923-117">about_Prompts</span></span>](about_Prompts.md)
