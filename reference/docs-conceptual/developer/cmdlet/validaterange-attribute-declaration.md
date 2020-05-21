---
title: Объявление атрибута Валидатеранже | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ValidateRange, described
- ValidateRange attribute
- attributes, ValidateRange
ms.assetid: 1f8066e6-e5d3-4f4e-8948-a90af5dace82
caps.latest.revision: 11
ms.openlocfilehash: 560fa105ac3f93ae6334df0112f5290dfa20576c
ms.sourcegitcommit: 17d798a041851382b406ed789097843faf37692d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2020
ms.locfileid: "83692011"
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

## <a name="remarks"></a>Комментарии

- Среда выполнения Windows PowerShell создает ошибку создания, если значение `MinRange` параметра больше значения `MaxRange` параметра.

- Среда выполнения Windows PowerShell выдает ошибку проверки при выполнении следующих условий.

  - , Если значение аргумента меньше `MinRange` ограничения или превышает его `MaxRange` .

  - Если аргумент имеет тип, отличный от типа `MinRange` и `MaxRange` параметров.

- Атрибут Валидатеранже определяется классом [System. Management. Automation. валидатеранжеаттрибуте](/dotnet/api/System.Management.Automation.ValidateRangeAttribute) .

## <a name="see-also"></a>См. также:

[System. Management. Automation. Валидатеранжеаттрибуте](/dotnet/api/System.Management.Automation.ValidateRangeAttribute)

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
