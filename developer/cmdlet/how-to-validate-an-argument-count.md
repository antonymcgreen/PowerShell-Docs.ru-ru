---
title: Как проверить количество аргументов | Документация Майкрософт
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
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62067813"
---
# <a name="how-to-validate-an-argument-count"></a>Как проверить количество аргументов

В этом примере показано, как задать правило проверки, среда выполнения Windows PowerShell можно использовать для проверки число аргументов (число), которая принимает параметр перед выполнением командлета. Это правило проверки устанавливается путем объявления атрибута ValidateCount.

> [!NOTE]
> Дополнительные сведения о классе, который определяет этот атрибут, см. в разделе [System.Management.Automation.Validatecountattribute](/dotnet/api/System.Management.Automation.ValidateCountAttribute).

## <a name="to-validate-an-argument-count"></a>Чтобы проверить количество аргументов

- Добавьте атрибут проверки, как показано в следующем коде. В этом примере указывает, что параметр принимает один аргумент или до трех аргументов.

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

Дополнительные сведения о том, как объявить этот атрибут, см. в разделе [объявление атрибута ValidateCount](./validatecount-attribute-declaration.md).

## <a name="see-also"></a>См. также

[Объявление атрибута ValidateCount](./validatecount-attribute-declaration.md)

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
