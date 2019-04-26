---
title: Как проверить набор аргументов | Документация Майкрософт
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
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62067725"
---
# <a name="how-to-validate-an-argument-set"></a>Как проверить набор аргументов

В этом примере показано, как задать правило проверки, среда выполнения Windows PowerShell можно использовать для проверки аргумент параметра перед выполнением командлета. Это правило проверки набор допустимых значений для параметра аргумента.

> [!NOTE]
> Дополнительные сведения о классе, который определяет этот атрибут, см. в разделе [System.Management.Automation.Validatesetattribute](/dotnet/api/System.Management.Automation.ValidateSetAttribute).

## <a name="to-validate-an-argument-set"></a>Чтобы проверить набор аргументов

- Добавьте атрибут ValidateSet, как показано в следующем коде. В этом примере задает набор из трех возможных значений для `UserName` параметра.

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

Дополнительные сведения о том, как объявить этот атрибут, см. в разделе [объявление атрибута ValidateSet](./validateset-attribute-declaration.md).

## <a name="see-also"></a>См. также

[System.Management.Automation.Validatesetattribute](/dotnet/api/System.Management.Automation.ValidateSetAttribute)

[Объявление атрибута ValidateSet](./validateset-attribute-declaration.md)

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
