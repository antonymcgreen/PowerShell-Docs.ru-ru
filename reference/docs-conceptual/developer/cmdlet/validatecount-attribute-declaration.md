---
title: Объявление атрибута Валидатекаунт | Документация Майкрософт
ms.date: 09/13/2016
helpviewer_keywords:
- attributes, ValidateCount
- ValidateCount attribute, described
- ValidateCount attribute
ms.openlocfilehash: c013a354ee339bd14508fe30549673bc79d5c616
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786328"
---
# <a name="validatecount-attribute-declaration"></a>Объявление атрибута ValidateCount

Атрибут Валидатекаунт указывает минимальное и максимальное число аргументов, допустимых для параметра командлета.

## <a name="syntax"></a>Синтаксис

```csharp
[ValidateCount(int minLength, int maxlength)]
```

#### <a name="parameters"></a>Параметры

`MinLength`([System. Int32][]) обязательный. Указывает минимальное число аргументов.

`MaxLength`([System. Int32][]) обязательный. Указывает максимальное число аргументов.

## <a name="remarks"></a>Примечания

- Дополнительные сведения об объявлении этого атрибута см. в разделе [проверка числа аргументов][].

- Если этот атрибут не вызывается, соответствующий параметр командлета может иметь любое количество аргументов.

- Среда выполнения Windows PowerShell выдает ошибку при следующих условиях:

  - `MinLength` `MaxLength` Параметры атрибута и не относятся к типу [System. Int32][].

  - Значение `MaxLength` параметра атрибута меньше значения `MinLength` параметра атрибута.

- Атрибут Валидатекаунт определяется классом [System. Management. Automation. валидатекаунтаттрибуте][] .

## <a name="see-also"></a>См. также

[System. Management. Automation. Валидатекаунтаттрибуте][]

[Как проверить количество аргументов][]

[Запись командлета Windows PowerShell][]

[Как проверить количество аргументов]: how-to-validate-an-argument-count.md
[Запись командлета Windows PowerShell]: writing-a-windows-powershell-cmdlet.md

[System.Int32]: /dotnet/api/System.Int32
[System. Management. Automation. Валидатекаунтаттрибуте]: /dotnet/api/System.Management.Automation.ValidateCountAttribute
