---
title: Объявление атрибута "Validate" | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- attributes, ValidateSet
- ValidateSet attribute, described
- ValidateSet attribute
ms.assetid: 4a6f97ab-45b2-4f3d-84d4-30acf8e074d0
caps.latest.revision: 12
ms.openlocfilehash: b036f39cd01ffe4b4ce7db9627cb6da0d5327190
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72364283"
---
# <a name="validateset-attribute-declaration"></a>Объявление атрибута ValidateSet

Атрибут Валидатесетаттрибуте задает набор возможных значений для аргумента параметра командлета. Этот атрибут также может использоваться функциями Windows PowerShell.

Если этот атрибут указан, среда выполнения Windows PowerShell определяет, соответствует ли переданный аргумент параметру командлета элементу в указанном наборе элементов. Командлет выполняется, только если аргумент параметра соответствует элементу в наборе. Если совпадений не найдено, среда выполнения Windows PowerShell выдает ошибку.

## <a name="syntax"></a>Синтаксис

```csharp
[ValidateSetAttribute(params string[] validValues)]
[ValidateSetAttribute(params string[] validValues, Named Parameters)]
```

#### <a name="parameters"></a>Параметры

требуется `ValidValues` ([System. String](/dotnet/api/System.String)). Указывает допустимые значения элементов параметров. В следующем примере показано, как указать один элемент или несколько элементов.

```csharp
[ValidateSetAttribute("Steve")]
[ValidateSetAttribute("Steve","Mary")]
```

`IgnoreCase` ([System. Boolean](/dotnet/api/System.Boolean)) необязательный именованный параметр. Значение по умолчанию `true` указывает, что регистр игнорируется. Значение `false` делает командлет с учетом регистра.

## <a name="remarks"></a>Замечания

- Этот атрибут можно использовать только один раз для каждого параметра.

- Если значение параметра является массивом, каждый элемент массива должен соответствовать элементу набора атрибутов.

- Атрибут Валидатесетаттрибуте определяется классом [System. Management. Automation. валидатесетаттрибуте](/dotnet/api/System.Management.Automation.ValidateSetAttribute) .

## <a name="see-also"></a>См. также:

[System. Management. Automation. Валидатесетаттрибуте](/dotnet/api/System.Management.Automation.ValidateSetAttribute)

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
