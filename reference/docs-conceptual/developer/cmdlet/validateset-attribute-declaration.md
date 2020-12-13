---
ms.date: 09/13/2016
ms.topic: reference
title: Объявление атрибута ValidateSet
description: Объявление атрибута ValidateSet
ms.openlocfilehash: 7894d00561366ada492911e8147acbd8d3454a55
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92660463"
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

`ValidValues` ([System. String](/dotnet/api/System.String)) обязательный. Указывает допустимые значения элементов параметров. В следующем примере показано, как указать один элемент или несколько элементов.

```csharp
[ValidateSetAttribute("Steve")]
[ValidateSetAttribute("Steve","Mary")]
```

`IgnoreCase` ([System. Boolean](/dotnet/api/System.Boolean)) необязательный именованный параметр. Значение по умолчанию, равное `true` , указывает, что регистр игнорируется. Значение `false` делает командлет с учетом регистра.

## <a name="remarks"></a>Комментарии

- Этот атрибут можно использовать только один раз для каждого параметра.

- Если значение параметра является массивом, каждый элемент массива должен соответствовать элементу набора атрибутов.

- Атрибут Валидатесетаттрибуте определяется классом [System. Management. Automation. валидатесетаттрибуте](/dotnet/api/System.Management.Automation.ValidateSetAttribute) .

## <a name="see-also"></a>См. также:

[System. Management. Automation. Валидатесетаттрибуте](/dotnet/api/System.Management.Automation.ValidateSetAttribute)

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
