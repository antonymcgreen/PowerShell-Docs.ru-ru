---
description: В этой статье объясняется, как создать настройку считывания входных данных PowerShell в командной строке консоли.
keywords: powershell,командлет
Locale: en-US
ms.date: 01/04/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_psconsolehostreadline?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_PSConsoleHostReadLine
ms.openlocfilehash: 49c3ce4099109fc721a13b61f390f564b8893a25
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93232489"
---
# <a name="about_psconsolehostreadline"></a>about_PSConsoleHostReadLine

## <a name="short-description"></a>КРАТКОЕ ОПИСАНИЕ
В этой статье объясняется, как создать настройку считывания входных данных PowerShell в командной строке консоли.

## <a name="long-description"></a>ПОДРОБНОЕ ОПИСАНИЕ

Начиная с Windows PowerShell 3,0 можно написать функцию с именем Псконсолехостреадлине, которая переопределяет способ обработки ввода в консоли по умолчанию.

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

По умолчанию PowerShell считывает входные данные из консоли, что называется режимом обработанные, в котором подсистема консоли Windows обрабатывает все нажатия клавиш, меню F7 и другие входные данные. При нажатии клавиши ВВОД или Tab PowerShell получает текст, который был введен до этого момента. Невозможно понять, что вы нажали Ctrl-R, CTRL-A, Ctrl-E или любые другие клавиши, прежде чем нажать клавишу ВВОД или TAB. В Windows PowerShell 3,0 функция Псконсолехостреадлине решает эту проблему. При определении функции с именем Псконсолехостреадлине на узле консоли PowerShell PowerShell вызывает эту функцию вместо механизма ввода "режима обработанные".

### <a name="see-also"></a>СМ. ТАКЖЕ

[about_Prompts](about_Prompts.md)
