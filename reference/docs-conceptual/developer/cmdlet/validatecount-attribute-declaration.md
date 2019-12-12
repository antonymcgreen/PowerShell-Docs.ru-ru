---
title: Объявление атрибута Валидатекаунт | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- attributes, ValidateCount
- ValidateCount attribute, described
- ValidateCount attribute
ms.assetid: 516af1ef-2c2e-408d-84bc-865f5bccf761
caps.latest.revision: 11
ms.openlocfilehash: ffc45f6b80a2b7ed22f27d083d042b1de7f353f6
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72369233"
---
# <a name="validatecount-attribute-declaration"></a>Объявление атрибута ValidateCount

Атрибут Валидатекаунт указывает минимальное и максимальное число аргументов, допустимых для параметра командлета.

## <a name="syntax"></a>Синтаксис

```csharp
[ValidateCount(int minLength, int maxlength)]
```

#### <a name="parameters"></a>Параметры

требуется `MinLength` ([System.Int32][]). Указывает минимальное число аргументов.

требуется `MaxLength`([System.Int32][]). Указывает максимальное число аргументов.

## <a name="remarks"></a>Замечания

- Дополнительные сведения об объявлении этого атрибута см. в разделе [проверка числа аргументов][].

- Если этот атрибут не вызывается, соответствующий параметр командлета может иметь любое количество аргументов.

- Среда выполнения Windows PowerShell выдает ошибку при следующих условиях:

    - Параметры атрибута `MinLength` и `MaxLength` не относятся к типу [System.Int32][].

    - Значение параметра атрибута `MaxLength` меньше значения параметра атрибута `MinLength`.

- Атрибут Валидатекаунт определяется классом [System. Management. Automation. валидатекаунтаттрибуте][] .

## <a name="see-also"></a>См. также:

[System. Management. Automation. Валидатекаунтаттрибуте][]

[Проверка числа аргументов][]

[Запись командлета Windows PowerShell][]

[Проверка числа аргументов]: how-to-validate-an-argument-count.md
[Запись командлета Windows PowerShell]: writing-a-windows-powershell-cmdlet.md

[System.Int32]: /dotnet/api/System.Int32
[System. Management. Automation. Валидатекаунтаттрибуте]: /dotnet/api/System.Management.Automation.ValidateCountAttribute
