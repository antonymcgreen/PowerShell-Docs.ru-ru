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
ms.openlocfilehash: a1a494534169b2da470286020dfacfa8e9084839
ms.sourcegitcommit: 17d798a041851382b406ed789097843faf37692d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2020
ms.locfileid: "83692326"
---
# <a name="validatelength-attribute-declaration"></a>Объявление атрибута ValidateLength

Атрибут Валидателенгс указывает минимальное и максимальное число символов для аргумента параметра командлета. Этот атрибут также может использоваться функциями Windows PowerShell.

## <a name="syntax"></a>Синтаксис

```csharp
[ValidateLength(int minLength, int maxlength)]
```

#### <a name="parameters"></a>Параметры

`MinLength`([System. Int32](/dotnet/api/System.Int32)) обязательный. Указывает минимальное допустимое число символов.

`MaxLength`([System. Int32](/dotnet/api/System.Int32)) обязательный. Указывает максимально допустимое число символов.

## <a name="remarks"></a>Комментарии

- Дополнительные сведения об объявлении этого атрибута см. в разделе [как объявлять правила проверки входных данных](./how-to-validate-parameter-input.md).

- Если этот атрибут не используется, соответствующий аргумент параметра может иметь любую длину.

- Среда выполнения Windows PowerShell выдает ошибку при следующих условиях:

  - Если значение `MaxLength` параметра атрибута меньше значения `MinLength` параметра атрибута.

  - Если `MaxLength` параметр атрибута имеет значение 0.

  - Если аргумент не является строкой.

- Атрибут Валидателенгс определяется классом [System. Management. Automation. валидателенгсаттрибуте](/dotnet/api/System.Management.Automation.ValidateLengthAttribute) .

## <a name="see-also"></a>См. также:

[System. Management. Automation. Валидателенгсаттрибуте](/dotnet/api/System.Management.Automation.ValidateLengthAttribute)

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
