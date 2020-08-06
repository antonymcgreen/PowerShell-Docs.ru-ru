---
title: Объявление атрибута Валидателенгс | Документация Майкрософт
ms.date: 09/13/2016
helpviewer_keywords:
- ValidateLength attribute, described
- attributes, ValidateLength
- ValidateLength attribute
ms.openlocfilehash: 7145dde55e79eeea6e3ceb91dfc1c93043a8857c
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786311"
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

## <a name="remarks"></a>Примечания

- Дополнительные сведения об объявлении этого атрибута см. в разделе [как объявлять правила проверки входных данных](./how-to-validate-parameter-input.md).

- Если этот атрибут не используется, соответствующий аргумент параметра может иметь любую длину.

- Среда выполнения Windows PowerShell выдает ошибку при следующих условиях:

  - Если значение `MaxLength` параметра атрибута меньше значения `MinLength` параметра атрибута.

  - Если `MaxLength` параметр атрибута имеет значение 0.

  - Если аргумент не является строкой.

- Атрибут Валидателенгс определяется классом [System. Management. Automation. валидателенгсаттрибуте](/dotnet/api/System.Management.Automation.ValidateLengthAttribute) .

## <a name="see-also"></a>См. также

[System. Management. Automation. Валидателенгсаттрибуте](/dotnet/api/System.Management.Automation.ValidateLengthAttribute)

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
