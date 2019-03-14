---
title: Объявление атрибута ValidateCount | Документация Майкрософт
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
ms.openlocfilehash: 4e0be34b6f7a56dcf02a4381de4d2a5d08db14df
ms.sourcegitcommit: 5990f04b8042ef2d8e571bec6d5b051e64c9921c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2019
ms.locfileid: "57794453"
---
# <a name="validatecount-attribute-declaration"></a>Объявление атрибута ValidateCount

Атрибут ValidateCount указывает минимальное и максимальное число аргументов для параметра командлета.

## <a name="syntax"></a>Синтаксис

```csharp
[ValidateCount(int minLength, int maxlength)]
```

#### <a name="parameters"></a>Параметры

`MinLength` ([System.Int32](/dotnet/api/System.Int32)) требуется. Указывает минимальное число аргументов.

`MaxLength`([System.Int32](/dotnet/api/System.Int32)) требуется. Указывает максимальное количество аргументов.

## <a name="remarks"></a>Замечания

- Дополнительные сведения о том, как объявить этот атрибут, см. в разделе [как объявить правила проверки входных данных](http://msdn.microsoft.com/en-us/544c2100-62ba-4be4-b2a2-cc0d4e4fc45b).

- Если этот атрибут не вызывается, соответствующего параметра командлета может иметь любое количество аргументов.

- Среда выполнения Windows PowerShell выдает ошибку при следующих условиях:

    - `MinLength` И `MaxLength` атрибут параметры не имеют тип [System.Int32](/dotnet/api/System.Int32).

    - Значение `MaxLength` параметр атрибута меньше, чем значение `MinLength` параметр атрибута.

- Атрибут ValidateCount определяется [System.Management.Automation.Validatecount](/dotnet/api/System.Management.Automation.ValidateCount) класса.

## <a name="see-also"></a>См. также

[System.Management.Automation.Validatecount](/dotnet/api/System.Management.Automation.ValidateCount)

[Как объявить правила проверки входных данных](http://msdn.microsoft.com/en-us/544c2100-62ba-4be4-b2a2-cc0d4e4fc45b)

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
