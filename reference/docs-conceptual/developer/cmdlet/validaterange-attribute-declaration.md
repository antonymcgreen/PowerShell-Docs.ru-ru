---
title: Объявление атрибута Валидатеранже | Документация Майкрософт
ms.date: 09/13/2016
helpviewer_keywords:
- ValidateRange, described
- ValidateRange attribute
- attributes, ValidateRange
ms.openlocfilehash: 9aeaa6f03c170389ff61a058b505dbcf74df6958
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787790"
---
# <a name="validaterange-attribute-declaration"></a>Объявление атрибута ValidateRange

Атрибут Валидатеранже задает минимальное и максимальное значения (диапазон) для аргумента параметра командлета. Этот атрибут также может использоваться функциями Windows PowerShell.

## <a name="syntax"></a>Синтаксис

```csharp
[ValidateRange(object minRange, object maxRange)]
```

#### <a name="parameters"></a>Параметры

`MinRange`Требуется ([System. Object](/dotnet/api/system.object)). Указывает минимальное допустимое значение.

`MaxRange`Требуется ([System. Object](/dotnet/api/system.object)). Указывает максимально допустимое значение.

## <a name="remarks"></a>Примечания

- Среда выполнения Windows PowerShell создает ошибку создания, если значение `MinRange` параметра больше значения `MaxRange` параметра.

- Среда выполнения Windows PowerShell выдает ошибку проверки при выполнении следующих условий.

  - , Если значение аргумента меньше `MinRange` ограничения или превышает его `MaxRange` .

  - Если аргумент имеет тип, отличный от типа `MinRange` и `MaxRange` параметров.

- Атрибут Валидатеранже определяется классом [System. Management. Automation. валидатеранжеаттрибуте](/dotnet/api/System.Management.Automation.ValidateRangeAttribute) .

## <a name="see-also"></a>См. также

[System. Management. Automation. Валидатеранжеаттрибуте](/dotnet/api/System.Management.Automation.ValidateRangeAttribute)

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
