---
ms.date: 06/12/2017
title: Поток информации
description: В PowerShell 5.0 добавлен новый поток **информации** для передачи структурированных данных между скриптом и его узлом.
ms.openlocfilehash: 818c99ce281f5ada596ff92cd7bafb8b7cacf709
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92646722"
---
# <a name="information-stream"></a>Поток информации

В PowerShell 5.0 добавлен новый поток **информации** для передачи структурированных данных между скриптом и его узлом. `Write-Host` также обновлен для передачи выходных данных в поток **информации** , где их можно собрать или отключить. Новый командлет `Write-Information`, используемый с общими параметрами **-InformationVariable** и **-InformationAction** , обладает повышенной гибкостью и расширенными возможностями.

Следующая функция использует командлеты, которые используют преимущества нового потока **информации** .

```powershell
function OutputGusher {
  [CmdletBinding()]
  param()
  Write-Host -ForegroundColor Green 'Preparing to give you output!'
  Write-Host '============================='
  Write-Host 'I ' -ForegroundColor White -NoNewline
  Write-Host '<3 ' -ForegroundColor Red -NoNewline
  Write-Host 'Output' -ForegroundColor White
  Write-Host '============================='

  $p = Get-Process -id $pid
  $p

  Write-Information $p -Tag Process
  Write-Information 'Some spammy logging information' -Tag LogLow
  Write-Information 'Some important logging information' -Tag LogHigh

  Write-Host
  Write-Host -ForegroundColor Green 'SCRIPT COMPLETE!!'
}
```

Ниже приведены примеры результатов выполнения этой функции.

```powershell
$r = OutputGusher
```

```Output
Preparing to give you output!
=============================
I <3 Output
=============================

SCRIPT COMPLETE!!
```

Переменная `$r` записала сведения о процессе в переменной скрипта `$p`.

```powershell
$r.Id
4008
```

В отличие от командлета `Write-Host`, использование параметра **InformationVariable** метода `Write-Information` позволяет записывать выходные данные в переменной. С помощью **тега** можно создать отдельные каналы для сообщения, отправляемого в поток **информации** .

```powershell
$r = OutputGusher -InformationVariable iv
$ivOutput = $iv | Group-Object -AsHash { $_.Tags[0] } -AsString
$ivOutput
```

```Output
Preparing to give you output!
=============================
I <3 Output
=============================
SCRIPT COMPLETE!!

Name                 Value
----                 -----
LogLow               {Some spammy logging information}
LogHigh              {Some important logging information}
Process              {System.Diagnostics.Process (powershell)}
PSHOST               {Preparing to give you output!, =============================, I , <3 ...}
```

При отправке сообщения в поток **информации** с тегом, это сообщение не отображается в ведущем приложении, но его можно получить с помощью имени тега. Пример:

```powershell
$iv | where Tags -eq 'LogHigh'
```

```Output
Some important logging information
```
