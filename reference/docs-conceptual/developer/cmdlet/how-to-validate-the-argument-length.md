---
title: Проверка длины аргумента | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ValidateLength attribute, example
ms.assetid: d5ddaa6e-4904-46da-beb0-0295a8f38332
caps.latest.revision: 12
ms.openlocfilehash: 8a21675acd087df93f93c25952c78931255d60b3
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72365493"
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

## <a name="see-also"></a>См. также:

[Объявление атрибута Валидателенгс](./validatelength-attribute-declaration.md)

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
