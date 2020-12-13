---
ms.date: 09/13/2016
ms.topic: reference
title: Как вызвать сценарий из командлета
description: Как вызвать сценарий из командлета
ms.openlocfilehash: f4a43a1e1240854e57deac5721e1e070c1a45a51
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667034"
---
# <a name="how-to-invoke-scripts-within-a-cmdlet"></a><span data-ttu-id="7b1b5-103">Как вызвать сценарий из командлета</span><span class="sxs-lookup"><span data-stu-id="7b1b5-103">How to Invoke Scripts Within a Cmdlet</span></span>

<span data-ttu-id="7b1b5-104">В этом примере показано, как вызвать скрипт, передаваемый в командлет.</span><span class="sxs-lookup"><span data-stu-id="7b1b5-104">This example shows how to invoke a script that is supplied to a cmdlet.</span></span> <span data-ttu-id="7b1b5-105">Скрипт выполняется командлетом, и его результаты возвращаются в командлет в виде коллекции объектов [System. Management. Automation. PSObject](/dotnet/api/System.Management.Automation.PSObject) .</span><span class="sxs-lookup"><span data-stu-id="7b1b5-105">The script is executed by the cmdlet, and its results are returned to the cmdlet as a collection of [System.Management.Automation.PSObject](/dotnet/api/System.Management.Automation.PSObject) objects.</span></span>

## <a name="to-invoke-a-script-block"></a><span data-ttu-id="7b1b5-106">Вызов блока сценария</span><span class="sxs-lookup"><span data-stu-id="7b1b5-106">To invoke a script block</span></span>

1. <span data-ttu-id="7b1b5-107">Команда проверяет, был ли указан блок скрипта для командлета.</span><span class="sxs-lookup"><span data-stu-id="7b1b5-107">The command verifies that a script block was supplied to the cmdlet.</span></span> <span data-ttu-id="7b1b5-108">Если указан блок сценария, команда вызывает блок сценария с необходимыми параметрами.</span><span class="sxs-lookup"><span data-stu-id="7b1b5-108">If a script block was supplied, the command invokes the script block with its required parameters.</span></span>

    ```csharp
    if (script != null)
    {
      WriteDebug("Executing script block.");

      // Invoke the script block with the required arguments.
      Collection<PSObject> PSObjects =
                     script.Invoke(
                                   line,
                                   simpleMatch,
                                   caseSensitive
                                  );
    ```

2. <span data-ttu-id="7b1b5-109">Затем сценарий выполняет итерацию по возвращенной коллекции объектов [System. Management. Automation. PSObject](/dotnet/api/System.Management.Automation.PSObject) и выполняет необходимые операции.</span><span class="sxs-lookup"><span data-stu-id="7b1b5-109">Then, the script iterates through the returned collection of [System.Management.Automation.PSObject](/dotnet/api/System.Management.Automation.PSObject) objects and perform the necessary operations.</span></span>

    ```c
    foreach (PSObject psObject in psObjects)
    {
      if (LanguagePrimitives.IsTrue(psObject))
      {
        result = new MatchInfo();
        result.Line = line;
        result.IgnoreCase = !caseSensitive;

        break;
      }
    }

    ```

## <a name="see-also"></a><span data-ttu-id="7b1b5-110">См. также</span><span class="sxs-lookup"><span data-stu-id="7b1b5-110">See Also</span></span>

[<span data-ttu-id="7b1b5-111">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7b1b5-111">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
