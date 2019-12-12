---
title: Проверка числа аргументов | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ValidateCount attribute, example
ms.assetid: 4e6b6ac4-1003-4e7e-9d4a-9f1cf74fc4af
caps.latest.revision: 8
ms.openlocfilehash: b6ddb8185f21a65b2e3142ebb640962047e11763
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72365533"
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

[Объявление атрибута Валидатекаунт](./validatecount-attribute-declaration.md)

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
