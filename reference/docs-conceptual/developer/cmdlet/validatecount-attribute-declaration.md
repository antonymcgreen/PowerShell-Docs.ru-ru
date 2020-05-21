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
ms.openlocfilehash: 3cae95fab30a4abe4e544ed5cb7dadc9f4debf02
ms.sourcegitcommit: 17d798a041851382b406ed789097843faf37692d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2020
ms.locfileid: "83692378"
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
