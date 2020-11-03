---
description: В этой статье объясняется, как создать настройку считывания входных данных PowerShell в командной строке консоли.
keywords: powershell,командлет
Locale: en-US
ms.date: 01/04/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_psconsolehostreadline?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_PSConsoleHostReadLine
ms.openlocfilehash: 3c5f629471ce2a4315e3e90f2baec86dfda1506b
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2020
ms.locfileid: "93233138"
---
# <a name="about_psconsolehostreadline"></a><span data-ttu-id="752c3-104">about_PSConsoleHostReadLine</span><span class="sxs-lookup"><span data-stu-id="752c3-104">about_PSConsoleHostReadLine</span></span>

## <a name="short-description"></a><span data-ttu-id="752c3-105">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="752c3-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="752c3-106">В этой статье объясняется, как создать настройку считывания входных данных PowerShell в командной строке консоли.</span><span class="sxs-lookup"><span data-stu-id="752c3-106">Explains how to create a customize how PowerShell reads input at the console prompt.</span></span>

## <a name="long-description"></a><span data-ttu-id="752c3-107">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="752c3-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="752c3-108">Начиная с Windows PowerShell v3 можно написать функцию с именем Псконсолехостреадлине, которая переопределяет способ обработки входных данных консоли по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="752c3-108">Starting in Windows PowerShell V3, you can write a function named PSConsoleHostReadLine that overrides the default way that console input is processed.</span></span>

### <a name="examples"></a><span data-ttu-id="752c3-109">Примеры</span><span class="sxs-lookup"><span data-stu-id="752c3-109">EXAMPLES</span></span>

<span data-ttu-id="752c3-110">В следующем примере запускается блокнот и получается ввод из текстового файла, создаваемого пользователем:</span><span class="sxs-lookup"><span data-stu-id="752c3-110">The following example launches Notepad and gets input from a text File that the user creates:</span></span>

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

### <a name="remarks"></a><span data-ttu-id="752c3-111">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="752c3-111">REMARKS</span></span>

<span data-ttu-id="752c3-112">По умолчанию PowerShell считывает входные данные из консоли, что называется режимом обработанные, в котором подсистема консоли Windows обрабатывает все нажатия клавиш, меню F7 и другие входные данные.</span><span class="sxs-lookup"><span data-stu-id="752c3-112">By default, PowerShell reads input from the console in what is known as "Cooked Mode" -- in which the Windows console subsystem handles all the keypresses, F7 menus, and other input.</span></span> <span data-ttu-id="752c3-113">При нажатии клавиши ВВОД или Tab Windows PowerShell получает текст, который был введен до этого момента.</span><span class="sxs-lookup"><span data-stu-id="752c3-113">When you press Enter or Tab, Windows PowerShell gets the text that you have typed up to that point.</span></span> <span data-ttu-id="752c3-114">Невозможно понять, что вы нажали Ctrl-R, CTRL-A, Ctrl-E или любые другие клавиши, прежде чем нажать клавишу ВВОД или TAB. В Windows PowerShell версии 3 функция Псконсолехостреадлине решает эту проблему.</span><span class="sxs-lookup"><span data-stu-id="752c3-114">There is no way for it to know that you pressed Ctrl-R, Ctrl-A, Ctrl-E, or any other keys before pressing Enter or Tab. In Windows PowerShell version 3, the PSConsoleHostReadLine function solves this issue.</span></span> <span data-ttu-id="752c3-115">При определении функции с именем Псконсолехостреадлине в узле консоли Windows PowerShell Windows PowerShell вызывает эту функцию вместо механизма ввода "режима обработанные".</span><span class="sxs-lookup"><span data-stu-id="752c3-115">When you define a function named PSConsoleHostReadline in the Windows PowerShell console host, Windows PowerShell calls that function instead of the "Cooked Mode" input mechanism.</span></span>

### <a name="see-also"></a><span data-ttu-id="752c3-116">СМ. ТАКЖЕ</span><span class="sxs-lookup"><span data-stu-id="752c3-116">SEE ALSO</span></span>

[<span data-ttu-id="752c3-117">about_Prompts</span><span class="sxs-lookup"><span data-stu-id="752c3-117">about_Prompts</span></span>](about_Prompts.md)
