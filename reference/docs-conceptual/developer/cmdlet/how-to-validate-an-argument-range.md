---
title: Проверка диапазона аргументов | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ValidateRange attribute, example
ms.assetid: 3cba3ab7-c3b6-4d17-aa17-88377496551b
caps.latest.revision: 9
ms.openlocfilehash: a39e34d1f1c333185f09b4a934819e1368d29a48
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72365523"
---
# <a name="how-to-validate-an-argument-range"></a>Как проверить диапазон аргумента

В этом примере показано, как указать правило проверки, которое среда выполнения Windows PowerShell может использовать для проверки минимального и максимального значений аргумента параметра перед выполнением командлета. Это правило проверки задается путем объявления атрибута Валидатеранже.

> [!NOTE]
> Дополнительные сведения о классе, который определяет этот атрибут, см. в разделе [System. Management. Automation. валидатеранжеаттрибуте](/dotnet/api/System.Management.Automation.ValidateRangeAttribute).

### <a name="to-validate-an-argument-range"></a>Проверка диапазона аргументов

- Добавьте атрибут Валидатеранже, как показано в следующем коде. В этом примере указывается диапазон от 0 до 5 для параметра `InputData`.

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

[Объявление атрибута Валидатеранже](./validaterange-attribute-declaration.md)

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
