---
title: Объявление атрибута ValidateRange | Документация Майкрософт
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
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56857040"
---
# <a name="validaterange-attribute-declaration"></a>Объявление атрибута ValidateRange

Атрибут ValidateRange указывает минимальное и максимальное значения (диапазона) для аргумента параметра в командлет. Этот атрибут также может использоваться функциями Windows PowerShell.

## <a name="syntax"></a>Синтаксис

```csharp
[ValidateRange(object minRange, object maxRange)]
```

#### <a name="parameters"></a>Параметры

`MinRange` ([System.Object](/dotnet/api/system.object)) требуется. Задает минимальное допустимое значение.

`MaxRange` ([System.Object](/dotnet/api/system.object)) требуется. Указывает максимально допустимое значение.

## <a name="remarks"></a>Замечания

- Среда выполнения Windows PowerShell создает ошибку построения при значение `MinRange` параметр больше, чем значение `MaxRange` параметра.

- Среда выполнения Windows PowerShell создает ошибку проверки при следующих условиях:

    - Если значение аргумента равно меньше, чем `MinRange` ограничение или больше, чем `MaxRange` ограничение.

    - Когда аргумент не имеет тот же тип, что `MinRange` и `MaxRange` параметров.

- Атрибут ValidateRange определяется [System.Management.Automation.Validaterangeattribute](/dotnet/api/System.Management.Automation.ValidateRangeAttribute) класса.

## <a name="see-also"></a>См. также

[System.Management.Automation.Validaterangeattribute](/dotnet/api/System.Management.Automation.ValidateRangeAttribute)

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
