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
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72364413"
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

## <a name="see-also"></a>См. также:

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
