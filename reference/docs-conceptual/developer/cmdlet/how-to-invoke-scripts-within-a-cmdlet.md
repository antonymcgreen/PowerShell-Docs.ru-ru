---
title: Как вызывать скрипты в командлете | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 248ad7e2e35fe53682836d094a391023007fa0b7
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784135"
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
