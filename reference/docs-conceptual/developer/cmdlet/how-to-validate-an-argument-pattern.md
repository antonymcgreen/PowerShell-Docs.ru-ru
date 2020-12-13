---
ms.date: 09/13/2016
ms.topic: reference
title: Как проверить шаблон аргумента
description: Как проверить шаблон аргумента
ms.openlocfilehash: ab5777c918a53c0a3900f87c52e7f14f9cb9b726
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666915"
---
# <a name="how-to-validate-an-argument-pattern"></a>Как проверить шаблон аргумента

В этом примере показано, как задать правило проверки, которое среда выполнения Windows PowerShell может использовать для проверки шаблона символов аргумента параметра перед выполнением командлета. Это правило проверки задается путем объявления атрибута ValidatePattern.

> [!NOTE]
> Дополнительные сведения о классе, который определяет этот атрибут, см. в разделе [System. Management. Automation. валидатепаттернаттрибуте](/dotnet/api/System.Management.Automation.ValidatePatternAttribute).

## <a name="to-validate-an-argument-pattern"></a>Проверка шаблона аргумента

- Добавьте атрибут Validate, как показано в следующем коде. В этом примере указывается шаблон из четырех цифр, где каждая цифра имеет значение от 0 до 9.

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

Дополнительные сведения об объявлении этого атрибута см. в разделе [объявление атрибута ValidatePattern](./validatepattern-attribute-declaration.md).

## <a name="see-also"></a>См. также:

[Объявление атрибута ValidatePattern](./validatepattern-attribute-declaration.md)

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
