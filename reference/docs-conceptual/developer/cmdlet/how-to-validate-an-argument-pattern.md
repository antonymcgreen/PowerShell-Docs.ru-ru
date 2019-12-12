---
title: Проверка шаблона аргумента | Документация Майкрософт
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
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72365563"
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
