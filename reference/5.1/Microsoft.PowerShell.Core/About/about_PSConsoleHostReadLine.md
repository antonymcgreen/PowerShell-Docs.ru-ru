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
# <a name="about_psconsolehostreadline"></a>about_PSConsoleHostReadLine

## <a name="short-description"></a>КРАТКОЕ ОПИСАНИЕ

В этой статье объясняется, как создать настройку считывания входных данных PowerShell в командной строке консоли.

## <a name="long-description"></a>ПОДРОБНОЕ ОПИСАНИЕ

Начиная с Windows PowerShell v3 можно написать функцию с именем Псконсолехостреадлине, которая переопределяет способ обработки входных данных консоли по умолчанию.

### <a name="examples"></a>Примеры

В следующем примере запускается блокнот и получается ввод из текстового файла, создаваемого пользователем:

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

### <a name="remarks"></a>ПРИМЕЧАНИЯ

По умолчанию PowerShell считывает входные данные из консоли, что называется режимом обработанные, в котором подсистема консоли Windows обрабатывает все нажатия клавиш, меню F7 и другие входные данные. При нажатии клавиши ВВОД или Tab Windows PowerShell получает текст, который был введен до этого момента. Невозможно понять, что вы нажали Ctrl-R, CTRL-A, Ctrl-E или любые другие клавиши, прежде чем нажать клавишу ВВОД или TAB. В Windows PowerShell версии 3 функция Псконсолехостреадлине решает эту проблему. При определении функции с именем Псконсолехостреадлине в узле консоли Windows PowerShell Windows PowerShell вызывает эту функцию вместо механизма ввода "режима обработанные".

### <a name="see-also"></a>СМ. ТАКЖЕ

[about_Prompts](about_Prompts.md)
