---
ms.date: 06/12/2017
keywords: wmf,powershell,установка
title: Поток информации
ms.openlocfilehash: 39cb3c36a70530b3ff9777edc74b88d276cbbb7c
ms.sourcegitcommit: 2aec310ad0c0b048400cb56f6fa64c1e554c812a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/23/2020
ms.locfileid: "83808930"
---
# <a name="information-stream"></a><span data-ttu-id="fe11d-103">Поток информации</span><span class="sxs-lookup"><span data-stu-id="fe11d-103">Information Stream</span></span>

<span data-ttu-id="fe11d-104">В PowerShell 5.0 добавлен новый поток **информации** для передачи структурированных данных между скриптом и его узлом.</span><span class="sxs-lookup"><span data-stu-id="fe11d-104">PowerShell 5.0 adds a new structured **Information** stream to transmit structured data between a script and its host.</span></span> <span data-ttu-id="fe11d-105">`Write-Host` также обновлен для передачи выходных данных в поток **информации**, где их можно собрать или отключить.</span><span class="sxs-lookup"><span data-stu-id="fe11d-105">`Write-Host` has also been updated to emit its output to the **Information** stream where you can now capture or silence it.</span></span> <span data-ttu-id="fe11d-106">Новый командлет `Write-Information`, используемый с общими параметрами **-InformationVariable** и **-InformationAction**, обладает повышенной гибкостью и расширенными возможностями.</span><span class="sxs-lookup"><span data-stu-id="fe11d-106">The new `Write-Information` cmdlet used with **InformationVariable** and **InformationAction** common parameters enables more flexibility and capability.</span></span>

<span data-ttu-id="fe11d-107">Следующая функция использует командлеты, которые используют преимущества нового потока **информации**.</span><span class="sxs-lookup"><span data-stu-id="fe11d-107">The following function uses cmdlets that take advantage of the new **Information** stream.</span></span>

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

<span data-ttu-id="fe11d-108">Ниже приведены примеры результатов выполнения этой функции.</span><span class="sxs-lookup"><span data-stu-id="fe11d-108">The following examples show the results of running this function.</span></span>

```powershell
$r = c:\temp\OutputGusher
```

```Output
Preparing to give you output!
=============================
I <3 Output
=============================

SCRIPT COMPLETE!!
```

<span data-ttu-id="fe11d-109">Переменная `$r` записала сведения о процессе в переменной скрипта `$p`.</span><span class="sxs-lookup"><span data-stu-id="fe11d-109">The `$r` variable has captured the process information in the script variable `$p`.</span></span>

```powershell
$r.Id
4008
```

<span data-ttu-id="fe11d-110">В отличие от командлета `Write-Host`, использование параметра **InformationVariable** метода `Write-Information` позволяет записывать выходные данные в переменной.</span><span class="sxs-lookup"><span data-stu-id="fe11d-110">Unlike the `Write-Host` cmdlet, using the **InformationVariable** parameter of `Write-Information` allows you to capture the output in a variable.</span></span> <span data-ttu-id="fe11d-111">С помощью **тега** можно создать отдельные каналы для сообщения, отправляемого в поток **информации**.</span><span class="sxs-lookup"><span data-stu-id="fe11d-111">Using the **Tag**, you can create separate channels for message sent to the **Information** stream.</span></span>

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

<span data-ttu-id="fe11d-112">При отправке сообщения в поток **информации** с тегом, это сообщение не отображается в ведущем приложении, но его можно получить с помощью имени тега.</span><span class="sxs-lookup"><span data-stu-id="fe11d-112">When you send a message to the **Information** stream with a tag, that message is not displayed in the host application but can be retrieved using the tag name.</span></span> <span data-ttu-id="fe11d-113">Пример:</span><span class="sxs-lookup"><span data-stu-id="fe11d-113">For example:</span></span>

```powershell
$iv | where Tags -eq 'LogHigh'
```

```Output
Some important logging information
```
