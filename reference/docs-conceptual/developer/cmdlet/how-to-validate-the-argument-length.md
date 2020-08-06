---
title: Проверка длины аргумента | Документация Майкрософт
ms.date: 09/13/2016
helpviewer_keywords:
- ValidateLength attribute, example
ms.openlocfilehash: aa0545def6d9628f6b41090a425f0c5af25f6ad7
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784084"
---
# <a name="how-to-validate-the-argument-length"></a>Как проверить длину аргумента

В этом примере показано, как задать правило проверки, которое среда выполнения Windows PowerShell может использовать для проверки числа символов (длины) аргумента параметра перед выполнением командлета. Это правило проверки задается путем объявления атрибута Валидателенгс.

> [!NOTE]
> Дополнительные сведения о классе, который определяет этот атрибут, см. в разделе [System. Management. Automation. валидателенгсаттрибуте](/dotnet/api/System.Management.Automation.ValidateLengthAttribute).

## <a name="to-validate-the-argument-length"></a>Проверка длины аргумента

- Добавьте атрибут Validate, как показано в следующем коде. В этом примере указывается, что длина аргумента должна иметь длину от 0 до 10 символов.

    ```csharp
    [ValidateLength(0, 10)]
    [Parameter(Position = 0, Mandatory = true)]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

Дополнительные сведения об объявлении этого атрибута см. в разделе [объявление атрибута валидателенгс](./validatelength-attribute-declaration.md).

## <a name="see-also"></a>См. также

[Объявление атрибута ValidateLength](./validatelength-attribute-declaration.md)

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
