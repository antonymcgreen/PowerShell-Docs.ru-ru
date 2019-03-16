---
title: Как будет вызывать скрипты в командлет | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cc0bc6ce-48a5-4d9c-927e-636bca743e9f
caps.latest.revision: 9
ms.openlocfilehash: 7dcb8bc20ab56225764854f9dc6fdfd858ed7451
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2019
ms.locfileid: "58055790"
---
# <a name="how-to-invoke-scripts-within-a-cmdlet"></a>Как вызвать сценарий из командлета

В этом примере показано, как вызвать скрипт, который передается в командлет. Сценарий выполняется с помощью командлета, а его результаты возвращаются в командлет как коллекция [System.Management.Automation.PSObject](/dotnet/api/System.Management.Automation.PSObject) объектов.

## <a name="to-invoke-a-script-block"></a>Для вызова блок сценария

1. Команда проверяет, что блок сценария передан в командлет. Если передан блок сценария, команда вызывает блок скрипта с его нужными параметрами.

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

2. Затем, скрипт выполняется перебор Возвращенная коллекция [System.Management.Automation.PSObject](/dotnet/api/System.Management.Automation.PSObject) объектов и выполнить необходимые операции.

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
