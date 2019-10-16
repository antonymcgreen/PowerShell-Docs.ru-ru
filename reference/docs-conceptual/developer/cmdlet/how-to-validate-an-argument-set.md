---
title: Проверка набора аргументов | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ValidateSet attribute, example
ms.assetid: 55f0f664-d2ad-4501-a3dc-9f7a27c8ab11
caps.latest.revision: 8
ms.openlocfilehash: 6d8b189ed6311efd5a7348ab1e58934e9bff12a3
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72365513"
---
# <a name="how-to-validate-an-argument-set"></a>Как проверить набор аргументов

В этом примере показано, как задать правило проверки, которое среда выполнения Windows PowerShell может использовать для проверки аргумента параметра перед выполнением командлета. Это правило проверки предоставляет набор допустимых значений аргумента параметра.

> [!NOTE]
> Дополнительные сведения о классе, который определяет этот атрибут, см. в разделе [System. Management. Automation. валидатесетаттрибуте](/dotnet/api/System.Management.Automation.ValidateSetAttribute).

## <a name="to-validate-an-argument-set"></a>Проверка набора аргументов

- Добавьте атрибут "Validate", как показано в следующем коде. В этом примере указывается набор из трех возможных значений для параметра `UserName`.

    ```csharp
    [ValidateSet("Steve", "Mary", "Carl", IgnoreCase = true)]
    [Parameter(Position = 0, Mandatory = true)]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }

    private string userName;
    ```

Дополнительные сведения об объявлении этого атрибута см. в разделе [Проверка объявления атрибута](./validateset-attribute-declaration.md).

## <a name="see-also"></a>См. также:

[System. Management. Automation. Валидатесетаттрибуте](/dotnet/api/System.Management.Automation.ValidateSetAttribute)

[Объявление атрибута "Validate"](./validateset-attribute-declaration.md)

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
