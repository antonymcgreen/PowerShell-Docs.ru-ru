---
ms.date: 09/13/2016
ms.topic: reference
title: Объявление атрибута ValidateLength
description: Объявление атрибута ValidateLength
ms.openlocfilehash: b35fe24c6fc44aaca6a39d819d6e3fc2d8a2cade
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92646182"
---
# <a name="validatelength-attribute-declaration"></a>Объявление атрибута ValidateLength

Атрибут Валидателенгс указывает минимальное и максимальное число символов для аргумента параметра командлета. Этот атрибут также может использоваться функциями Windows PowerShell.

## <a name="syntax"></a>Синтаксис

```csharp
[ValidateLength(int minLength, int maxlength)]
```

#### <a name="parameters"></a>Параметры

`MinLength` ([System. Int32](/dotnet/api/System.Int32)) обязательный. Указывает минимальное допустимое число символов.

`MaxLength` ([System. Int32](/dotnet/api/System.Int32)) обязательный. Указывает максимально допустимое число символов.

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
