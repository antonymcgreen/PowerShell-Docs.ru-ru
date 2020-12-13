---
ms.date: 09/13/2016
ms.topic: reference
title: Объявление атрибута ValidateCount
description: Объявление атрибута ValidateCount
ms.openlocfilehash: 6acdd02a10ecc1bc2be0e6be88cf2f42a3673eb8
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92646265"
---
# <a name="validatecount-attribute-declaration"></a>Объявление атрибута ValidateCount

Атрибут Валидатекаунт указывает минимальное и максимальное число аргументов, допустимых для параметра командлета.

## <a name="syntax"></a>Синтаксис

```csharp
[ValidateCount(int minLength, int maxlength)]
```

#### <a name="parameters"></a>Параметры

`MinLength` ([System. Int32][]) обязательный. Указывает минимальное число аргументов.

`MaxLength`([System. Int32][]) обязательный. Указывает максимальное число аргументов.

## <a name="remarks"></a>Комментарии

- Дополнительные сведения об объявлении этого атрибута см. в разделе [проверка числа аргументов][].

- Если этот атрибут не вызывается, соответствующий параметр командлета может иметь любое количество аргументов.

- Среда выполнения Windows PowerShell выдает ошибку при следующих условиях:

  - `MinLength` `MaxLength` Параметры атрибута и не относятся к типу [System. Int32][].

  - Значение `MaxLength` параметра атрибута меньше значения `MinLength` параметра атрибута.

- Атрибут Валидатекаунт определяется классом [System. Management. Automation. валидатекаунтаттрибуте][] .

## <a name="see-also"></a>См. также:

[System. Management. Automation. Валидатекаунтаттрибуте][]

[Как проверить количество аргументов][]

[Запись командлета Windows PowerShell][]

[Как проверить количество аргументов]: how-to-validate-an-argument-count.md
[Запись командлета Windows PowerShell]: writing-a-windows-powershell-cmdlet.md

[System.Int32]: /dotnet/api/System.Int32
[System. Management. Automation. Валидатекаунтаттрибуте]: /dotnet/api/System.Management.Automation.ValidateCountAttribute
