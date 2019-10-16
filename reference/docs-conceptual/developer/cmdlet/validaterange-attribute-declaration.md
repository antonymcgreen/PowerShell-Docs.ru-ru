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
ms.openlocfilehash: 155a406b9855c435041fe175ac7d983a4b4eb8b7
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72369133"
---
# <a name="validaterange-attribute-declaration"></a>Объявление атрибута ValidateRange

Атрибут Валидатеранже задает минимальное и максимальное значения (диапазон) для аргумента параметра командлета. Этот атрибут также может использоваться функциями Windows PowerShell.

## <a name="syntax"></a>Синтаксис

```csharp
[ValidateRange(object minRange, object maxRange)]
```

#### <a name="parameters"></a>Параметры

требуется `MinRange` ([System. Object](/dotnet/api/system.object)). Указывает минимальное допустимое значение.

требуется `MaxRange` ([System. Object](/dotnet/api/system.object)). Указывает максимально допустимое значение.

## <a name="remarks"></a>Замечания

- Среда выполнения Windows PowerShell создает ошибку создания, если значение параметра `MinRange` больше значения параметра `MaxRange`.

- Среда выполнения Windows PowerShell выдает ошибку проверки при выполнении следующих условий.

    - Если значение аргумента меньше `MinRange` или больше ограничения `MaxRange`.

    - Если тип аргумента отличается от типа `MinRange` и параметров `MaxRange`.

- Атрибут Валидатеранже определяется классом [System. Management. Automation. валидатеранжеаттрибуте](/dotnet/api/System.Management.Automation.ValidateRangeAttribute) .

## <a name="see-also"></a>См. также:

[System. Management. Automation. Валидатеранжеаттрибуте](/dotnet/api/System.Management.Automation.ValidateRangeAttribute)

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
