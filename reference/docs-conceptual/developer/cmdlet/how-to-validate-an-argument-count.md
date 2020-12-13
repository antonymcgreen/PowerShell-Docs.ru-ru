---
ms.date: 09/13/2016
ms.topic: reference
title: Как проверить количество аргументов
description: Как проверить количество аргументов
ms.openlocfilehash: 46a32d61138fb50bceea98171f76749c9d96734d
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666949"
---
# <a name="how-to-validate-an-argument-count"></a>Как проверить количество аргументов

В этом примере показано, как задать правило проверки, которое может использовать среда выполнения Windows PowerShell для проверки числа аргументов (счетчика), принимаемых параметром перед выполнением командлета. Это правило проверки задается путем объявления атрибута Валидатекаунт.

> [!NOTE]
> Дополнительные сведения о классе, который определяет этот атрибут, см. в разделе [System. Management. Automation. валидатекаунтаттрибуте](/dotnet/api/System.Management.Automation.ValidateCountAttribute).

## <a name="to-validate-an-argument-count"></a>Проверка числа аргументов

- Добавьте атрибут Validate, как показано в следующем коде. В этом примере указывается, что параметр принимает один аргумент или не больше трех аргументов.

    ```csharp
    [ValidateCount(1, 3)]
    [Parameter(Position = 0, Mandatory = true)]
    public string[] UserNames
    {
      get { return userNames; }
      set { userNames = value; }
    }

    private string[] userNames;
    ```

Дополнительные сведения об объявлении этого атрибута см. в разделе [объявление атрибута валидатекаунт](./validatecount-attribute-declaration.md).

## <a name="see-also"></a>См. также:

[Объявление атрибута ValidateCount](./validatecount-attribute-declaration.md)

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
