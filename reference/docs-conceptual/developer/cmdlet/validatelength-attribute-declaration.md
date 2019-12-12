---
title: Объявление атрибута Валидателенгс | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ValidateLength attribute, described
- attributes, ValidateLength
- ValidateLength attribute
ms.assetid: 82fe3a35-a94b-4bc1-ad9e-dfc5f1e788b3
caps.latest.revision: 13
ms.openlocfilehash: a25fa2410fcc6803563573596af1bc99052c3ffa
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72369183"
---
# <a name="validatelength-attribute-declaration"></a>Объявление атрибута ValidateLength

Атрибут Валидателенгс указывает минимальное и максимальное число символов для аргумента параметра командлета. Этот атрибут также может использоваться функциями Windows PowerShell.

## <a name="syntax"></a>Синтаксис

```csharp
[ValidateLength(int minLength, int maxlength)]
```

#### <a name="parameters"></a>Параметры

требуется `MinLength` ([System. Int32](/dotnet/api/System.Int32)). Указывает минимальное допустимое число символов.

требуется `MaxLength` ([System. Int32](/dotnet/api/System.Int32)). Указывает максимально допустимое число символов.

## <a name="remarks"></a>Замечания

- Дополнительные сведения об объявлении этого атрибута см. в разделе [как объявлять правила проверки входных данных](./how-to-validate-parameter-input.md).

- Если этот атрибут не используется, соответствующий аргумент параметра может иметь любую длину.

- Среда выполнения Windows PowerShell выдает ошибку при следующих условиях:

    - Если значение параметра атрибута `MaxLength` меньше значения параметра атрибута `MinLength`.

    - Если параметр атрибута `MaxLength` имеет значение 0.

    - Если аргумент не является строкой.

- Атрибут Валидателенгс определяется классом [System. Management. Automation. валидателенгсаттрибуте](/dotnet/api/System.Management.Automation.ValidateLengthAttribute) .

## <a name="see-also"></a>См. также:

[System. Management. Automation. Валидателенгсаттрибуте](/dotnet/api/System.Management.Automation.ValidateLengthAttribute)

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
