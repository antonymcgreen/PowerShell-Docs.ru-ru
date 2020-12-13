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
# <a name="how-to-invoke-scripts-within-a-cmdlet"></a>Как вызвать сценарий из командлета

В этом примере показано, как вызвать скрипт, передаваемый в командлет. Скрипт выполняется командлетом, и его результаты возвращаются в командлет в виде коллекции объектов [System. Management. Automation. PSObject](/dotnet/api/System.Management.Automation.PSObject) .

## <a name="to-invoke-a-script-block"></a>Вызов блока сценария

1. Команда проверяет, был ли указан блок скрипта для командлета. Если указан блок сценария, команда вызывает блок сценария с необходимыми параметрами.

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

2. Затем сценарий выполняет итерацию по возвращенной коллекции объектов [System. Management. Automation. PSObject](/dotnet/api/System.Management.Automation.PSObject) и выполняет необходимые операции.

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

## <a name="see-also"></a>См. также

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
