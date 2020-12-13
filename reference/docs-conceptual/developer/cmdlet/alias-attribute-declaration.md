---
ms.date: 09/13/2016
ms.topic: reference
title: Объявление атрибута псевдонима
description: Объявление атрибута псевдонима
ms.openlocfilehash: f2fe49578da2c795643b1f80fa44deefe1dbff09
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92668309"
---
# <a name="alias-attribute-declaration"></a>Объявление атрибута псевдонима

Атрибут Alias позволяет пользователю указать различные имена для параметра командлета. Псевдонимы можно использовать для предоставления сочетаний клавиш для имени параметра или для предоставления различных имен, подходящих для различных сценариев.

## <a name="syntax"></a>Синтаксис

```csharp
[Alias(aliasNames)]
```

#### <a name="parameters"></a>Параметры

`aliasName` (String []) Обязательно. Задает набор разделенных запятыми имен псевдонимов для параметра командлета.

## <a name="remarks"></a>Комментарии

- Атрибут Alias используется с атрибутом Parameter при указании параметра командлета. Дополнительные сведения об объявлении этих атрибутов см. в разделе [как объявлять параметры командлета](./how-to-declare-cmdlet-parameters.md).

- Каждое имя псевдонима должно быть уникальным в пределах командлета. Windows PowerShell не проверяет наличие повторяющихся имен псевдонимов.

- Атрибут Alias используется один раз для каждого параметра в командлете.

- Атрибут Alias определяется классом [System. Management. Automation. алиасаттрибуте](/dotnet/api/System.Management.Automation.AliasAttribute) .

## <a name="see-also"></a>См. также:

[Псевдонимы параметров](./parameter-aliases.md)

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
