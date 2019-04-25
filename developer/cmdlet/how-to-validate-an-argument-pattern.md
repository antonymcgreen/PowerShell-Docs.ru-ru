---
title: Как проверить шаблон аргумент | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ValidatePattern attribute, example
ms.assetid: 7ff76d4c-443a-4887-9ff8-241225f0aeec
caps.latest.revision: 9
ms.openlocfilehash: 5efc1210328c76e57a31d93b9eb52de114816c3c
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62067779"
---
# <a name="how-to-validate-an-argument-pattern"></a>Как проверить шаблон аргумента

В этом примере показано, как задать правило проверки, среда выполнения Windows PowerShell можно использовать для проверки комбинация символов аргумента параметра перед выполнением командлета. Это правило проверки устанавливается путем объявления атрибута ValidatePattern.

> [!NOTE]
> Дополнительные сведения о классе, который определяет этот атрибут, см. в разделе [System.Management.Automation.Validatepatternattribute](/dotnet/api/System.Management.Automation.ValidatePatternAttribute).

## <a name="to-validate-an-argument-pattern"></a>Чтобы проверить шаблон аргумент

- Добавьте атрибут проверки, как показано в следующем коде. В этом примере определяет шаблон из четырех цифр, где каждая цифра имеет значение от 0 до 9.

    ```csharp
    [ValidatePattern("[0-9][0-9][0-9][0-9]")]
    [Parameter(Position = 0, Mandatory = true)]
    public int InputData
    {
      get { return inputData; }
      set { inputData = value; }
    }

    private int inputData;
    ```

Дополнительные сведения о том, как объявить этот атрибут, см. в разделе [объявление атрибута ValidatePattern](./validatepattern-attribute-declaration.md).

## <a name="see-also"></a>См. также

[Объявление атрибута ValidatePattern](./validatepattern-attribute-declaration.md)

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
