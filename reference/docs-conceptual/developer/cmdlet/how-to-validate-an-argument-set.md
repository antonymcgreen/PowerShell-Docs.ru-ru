---
ms.date: 09/13/2016
ms.topic: reference
title: Как проверить набор аргументов
description: Как проверить набор аргументов
ms.openlocfilehash: 50ec0a48277893584d896e14ad6aa843682a28cc
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92650368"
---
# <a name="how-to-validate-an-argument-set"></a>Как проверить набор аргументов

В этом примере показано, как задать правило проверки, которое среда выполнения Windows PowerShell может использовать для проверки аргумента параметра перед выполнением командлета. Это правило проверки предоставляет набор допустимых значений аргумента параметра.

> [!NOTE]
> Дополнительные сведения о классе, который определяет этот атрибут, см. в разделе [System. Management. Automation. валидатесетаттрибуте](/dotnet/api/System.Management.Automation.ValidateSetAttribute).

## <a name="to-validate-an-argument-set"></a>Проверка набора аргументов

- Добавьте атрибут "Validate", как показано в следующем коде. В этом примере указывается набор из трех возможных значений для `UserName` параметра.

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

[Объявление атрибута ValidateSet](./validateset-attribute-declaration.md)

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
