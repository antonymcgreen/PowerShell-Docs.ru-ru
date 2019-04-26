---
title: Способы проверки длина аргумента | Документация Майкрософт
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
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62067722"
---
# <a name="how-to-validate-the-argument-length"></a>Как проверить длину аргумента

В этом примере показано, как задать правило проверки, среда выполнения Windows PowerShell можно использовать для проверки число символов (длина) аргумента параметра перед выполнением командлета. Это правило проверки устанавливается путем объявления атрибута ValidateLength.

> [!NOTE]
> Дополнительные сведения о классе, который определяет этот атрибут, см. в разделе [System.Management.Automation.Validatelengthattribute](/dotnet/api/System.Management.Automation.ValidateLengthAttribute).

## <a name="to-validate-the-argument-length"></a>Проверяемая длина аргумента

- Добавьте атрибут проверки, как показано в следующем коде. В этом примере указывает, что длина аргумента должно иметь длину 0 до 10 символов.

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

Дополнительные сведения о том, как объявить этот атрибут, см. в разделе [объявление атрибута ValidateLength](./validatelength-attribute-declaration.md).

## <a name="see-also"></a>См. также

[Объявление атрибута ValidateLength](./validatelength-attribute-declaration.md)

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
