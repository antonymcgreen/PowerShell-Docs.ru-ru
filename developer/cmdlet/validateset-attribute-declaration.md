---
title: Объявление атрибута ValidateSet | Документация Майкрософт
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
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56861210"
---
# <a name="validateset-attribute-declaration"></a>Объявление атрибута ValidateSet

Атрибут ValidateSetAttribute указывает набор возможных значений для аргумента параметра командлета. Этот атрибут также может использоваться функциями Windows PowerShell.

Если этот атрибут указан, среда выполнения Windows PowerShell определяет, совпадает ли переданный аргумент для параметра командлета элемент в наборе предоставленный элемент. Командлет выполняется только в том случае, если аргумент параметра в соответствующий элемент в наборе. Если совпадений не найдено, возникает ошибка средой выполнения Windows PowerShell.

## <a name="syntax"></a>Синтаксис

```csharp
[ValidateSetAttribute(params string[] validValues)]
[ValidateSetAttribute(params string[] validValues, Named Parameters)]
```

#### <a name="parameters"></a>Параметры

`ValidValues` ([System.String](/dotnet/api/System.String)) требуется. Задает значения элемента допустимым параметром. Следующий пример демонстрирует задание один элемент или несколько элементов.

```csharp
[ValidateSetAttribute("Steve")]
[ValidateSetAttribute("Steve","Mary")]
```

`IgnoreCase` ([System.Boolean](/dotnet/api/System.Boolean)) необязательный именованный параметр. Значение по умолчанию `true` указывает, что регистр учитывается. Значение `false` делает командлет с учетом регистра.

## <a name="remarks"></a>Замечания

- Этот атрибут может использоваться только один раз на параметр.

- Если значение параметра представляет собой массив, каждый элемент массива должно соответствовать элемент набора атрибутов.

- Атрибут ValidateSetAttribute определяется [System.Management.Automation.Validatesetattribute](/dotnet/api/System.Management.Automation.ValidateSetAttribute) класса.

## <a name="see-also"></a>См. также

[System.Management.Automation.Validatesetattribute](/dotnet/api/System.Management.Automation.ValidateSetAttribute)

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
