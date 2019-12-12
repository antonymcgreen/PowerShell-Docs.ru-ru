---
title: Как вызывать скрипты в командлете | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cc0bc6ce-48a5-4d9c-927e-636bca743e9f
caps.latest.revision: 9
ms.openlocfilehash: 7dcb8bc20ab56225764854f9dc6fdfd858ed7451
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72364413"
---
# <a name="how-to-invoke-scripts-within-a-cmdlet"></a><span data-ttu-id="1c790-102">Как вызвать сценарий из командлета</span><span class="sxs-lookup"><span data-stu-id="1c790-102">How to Invoke Scripts Within a Cmdlet</span></span>

<span data-ttu-id="1c790-103">В этом примере показано, как вызвать скрипт, передаваемый в командлет.</span><span class="sxs-lookup"><span data-stu-id="1c790-103">This example shows how to invoke a script that is supplied to a cmdlet.</span></span> <span data-ttu-id="1c790-104">Скрипт выполняется командлетом, и его результаты возвращаются в командлет в виде коллекции объектов [System. Management. Automation. PSObject](/dotnet/api/System.Management.Automation.PSObject) .</span><span class="sxs-lookup"><span data-stu-id="1c790-104">The script is executed by the cmdlet, and its results are returned to the cmdlet as a collection of [System.Management.Automation.PSObject](/dotnet/api/System.Management.Automation.PSObject) objects.</span></span>

## <a name="to-invoke-a-script-block"></a><span data-ttu-id="1c790-105">Вызов блока сценария</span><span class="sxs-lookup"><span data-stu-id="1c790-105">To invoke a script block</span></span>

1. <span data-ttu-id="1c790-106">Команда проверяет, был ли указан блок скрипта для командлета.</span><span class="sxs-lookup"><span data-stu-id="1c790-106">The command verifies that a script block was supplied to the cmdlet.</span></span> <span data-ttu-id="1c790-107">Если указан блок сценария, команда вызывает блок сценария с необходимыми параметрами.</span><span class="sxs-lookup"><span data-stu-id="1c790-107">If a script block was supplied, the command invokes the script block with its required parameters.</span></span>

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

2. <span data-ttu-id="1c790-108">Затем сценарий выполняет итерацию по возвращенной коллекции объектов [System. Management. Automation. PSObject](/dotnet/api/System.Management.Automation.PSObject) и выполняет необходимые операции.</span><span class="sxs-lookup"><span data-stu-id="1c790-108">Then, the script iterates through the returned collection of [System.Management.Automation.PSObject](/dotnet/api/System.Management.Automation.PSObject) objects and perform the necessary operations.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="1c790-109">См. также:</span><span class="sxs-lookup"><span data-stu-id="1c790-109">See Also</span></span>

[<span data-ttu-id="1c790-110">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1c790-110">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
