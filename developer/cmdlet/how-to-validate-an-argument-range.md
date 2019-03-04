---
title: Способы проверки диапазона аргумент | Документация Майкрософт
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
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56859740"
---
# <a name="how-to-validate-an-argument-range"></a>Как проверить диапазон аргумента

В этом примере показано, как задать правило проверки, среда выполнения Windows PowerShell можно использовать для проверки минимальное и максимальное значения аргумента параметра перед выполнением командлета. Это правило проверки устанавливается путем объявления атрибута ValidateRange.

> [!NOTE]
> Дополнительные сведения о классе, который определяет этот атрибут, см. в разделе [System.Management.Automation.Validaterangeattribute](/dotnet/api/System.Management.Automation.ValidateRangeAttribute).

### <a name="to-validate-an-argument-range"></a>Для проверки диапазона аргументов

- Добавьте атрибут ValidateRange, как показано в следующем коде. В этом примере указывает диапазон 0 – 5 для `InputData` параметра.

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

Дополнительные сведения о том, как объявить этот атрибут, см. в разделе [объявление атрибута ValidateRange](./validaterange-attribute-declaration.md).

## <a name="see-also"></a>См. также

[Объявление атрибута ValidateRange](./validaterange-attribute-declaration.md)

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
