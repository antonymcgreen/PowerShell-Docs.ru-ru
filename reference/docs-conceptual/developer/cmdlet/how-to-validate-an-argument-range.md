---
ms.date: 09/13/2016
ms.topic: reference
title: Как проверить диапазон аргумента
description: Как проверить диапазон аргумента
ms.openlocfilehash: 1c1c53d43350a38beb2193200de3bd6b689366a4
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666932"
---
# <a name="how-to-validate-an-argument-range"></a>Как проверить диапазон аргумента

В этом примере показано, как указать правило проверки, которое среда выполнения Windows PowerShell может использовать для проверки минимального и максимального значений аргумента параметра перед выполнением командлета. Это правило проверки задается путем объявления атрибута Валидатеранже.

> [!NOTE]
> Дополнительные сведения о классе, который определяет этот атрибут, см. в разделе [System. Management. Automation. валидатеранжеаттрибуте](/dotnet/api/System.Management.Automation.ValidateRangeAttribute).

### <a name="to-validate-an-argument-range"></a>Проверка диапазона аргументов

- Добавьте атрибут Валидатеранже, как показано в следующем коде. В этом примере в качестве параметра указывается диапазон от 0 до 5 `InputData` .

    ```csharp
    [ValidateRange(0, 5)]
    [Parameter(Position = 0, Mandatory = true)]
    public int InputData
    {
      get { return inputData; }
      set { inputData = value; }
    }
    private int inputData;
    ```

Дополнительные сведения об объявлении этого атрибута см. в разделе [объявление атрибута валидатеранже](./validaterange-attribute-declaration.md).

## <a name="see-also"></a>См. также:

[Объявление атрибута ValidateRange](./validaterange-attribute-declaration.md)

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
