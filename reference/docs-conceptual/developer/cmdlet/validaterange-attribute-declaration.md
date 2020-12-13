---
ms.date: 09/13/2016
ms.topic: reference
title: Объявление атрибута ValidateRange
description: Объявление атрибута ValidateRange
ms.openlocfilehash: 1fec9d1bd36cd21b7f0f23bf6d72338d276dce91
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92660604"
---
# <a name="validaterange-attribute-declaration"></a>Объявление атрибута ValidateRange

Атрибут Валидатеранже задает минимальное и максимальное значения (диапазон) для аргумента параметра командлета. Этот атрибут также может использоваться функциями Windows PowerShell.

## <a name="syntax"></a>Синтаксис

```csharp
[ValidateRange(object minRange, object maxRange)]
```

#### <a name="parameters"></a>Параметры

`MinRange` Требуется ([System. Object](/dotnet/api/system.object)). Указывает минимальное допустимое значение.

`MaxRange` Требуется ([System. Object](/dotnet/api/system.object)). Указывает максимально допустимое значение.

## <a name="remarks"></a>Комментарии

- Среда выполнения Windows PowerShell создает ошибку создания, если значение `MinRange` параметра больше значения `MaxRange` параметра.

- Среда выполнения Windows PowerShell выдает ошибку проверки при выполнении следующих условий.

  - , Если значение аргумента меньше `MinRange` ограничения или превышает его `MaxRange` .

  - Если аргумент имеет тип, отличный от типа `MinRange` и `MaxRange` параметров.

- Атрибут Валидатеранже определяется классом [System. Management. Automation. валидатеранжеаттрибуте](/dotnet/api/System.Management.Automation.ValidateRangeAttribute) .

## <a name="see-also"></a>См. также:

[System. Management. Automation. Валидатеранжеаттрибуте](/dotnet/api/System.Management.Automation.ValidateRangeAttribute)

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
