---
title: Объявление атрибута ValidatePattern | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- attributes, ValidatePattern
- ValidatePattern attribute, described
- ValidatePattern attribute
ms.assetid: 87b811be-6d93-4e7d-b9d0-c567a19bb0ef
caps.latest.revision: 13
ms.openlocfilehash: 5edcb65a6fbe1cb2fe2d0efe3f763fb84628b049
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72369163"
---
# <a name="validatepattern-attribute-declaration"></a>Объявление атрибута ValidatePattern

Атрибут ValidatePattern указывает шаблон регулярного выражения, который проверяет аргумент параметра командлета. Этот атрибут также может использоваться функциями Windows PowerShell.

При вызове ValidatePattern в командлете среда выполнения Windows PowerShell преобразует аргумент параметра командлета в строку, а затем сравнивает эту строку с шаблоном, предоставленным атрибутом ValidatePattern. Командлет выполняется только в том случае, если преобразованное строковое представление аргумента соответствует указанному шаблону. Если они не совпадают, то среда выполнения Windows PowerShell выдает ошибку.

## <a name="syntax"></a>Синтаксис

```csharp
[ValidatePattern(string regexString)]
[ValidatePattern(string regexString, Named Parameters)]
```

#### <a name="parameters"></a>Параметры

требуется `RegexString` ([System. String](/dotnet/api/System.String)). Задает регулярное выражение, которое проверяет аргумент параметра.

Параметры ([System. Text. RegularExpressions. RegexOptions](/dotnet/api/System.Text.RegularExpressions.RegexOptions)) необязательный именованный параметр. Задает побитовое сочетание флагов [System. Text. RegularExpressions. RegexOptions](/dotnet/api/System.Text.RegularExpressions.RegexOptions) , задающих параметры регулярных выражений.

## <a name="remarks"></a>Замечания

- Этот атрибут можно использовать только один раз для каждого параметра.

- Чтобы дополнительно определить шаблон, можно использовать параметр `Option` атрибута. Например, можно сделать шаблон чувствительным к регистру.

- Если этот атрибут применяется к коллекции, каждый элемент в коллекции должен соответствовать шаблону.

- Атрибут ValidatePattern определяется классом [System. Management. Automation. валидатепаттернаттрибуте](/dotnet/api/System.Management.Automation.ValidatePatternAttribute) .

## <a name="see-also"></a>См. также:

[System. Management. Automation. Валидатепаттернаттрибуте](/dotnet/api/System.Management.Automation.ValidatePatternAttribute)

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
