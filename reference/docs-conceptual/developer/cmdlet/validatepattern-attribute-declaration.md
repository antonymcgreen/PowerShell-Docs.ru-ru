---
ms.date: 09/13/2016
ms.topic: reference
title: Объявление атрибута ValidatePattern
description: Объявление атрибута ValidatePattern
ms.openlocfilehash: 364f63d2c52563eaefe64bcbb2bbae511bccb074
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92646173"
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

`RegexString` ([System. String](/dotnet/api/System.String)) обязательный. Задает регулярное выражение, которое проверяет аргумент параметра.

Параметры ([System. Text. RegularExpressions. RegexOptions](/dotnet/api/System.Text.RegularExpressions.RegexOptions)) необязательный именованный параметр. Задает побитовое сочетание флагов [System. Text. RegularExpressions. RegexOptions](/dotnet/api/System.Text.RegularExpressions.RegexOptions) , задающих параметры регулярных выражений.

## <a name="remarks"></a>Комментарии

- Этот атрибут можно использовать только один раз для каждого параметра.

- `Option`Для дальнейшего определения шаблона можно использовать параметр атрибута. Например, можно сделать шаблон чувствительным к регистру.

- Если этот атрибут применяется к коллекции, каждый элемент в коллекции должен соответствовать шаблону.

- Атрибут ValidatePattern определяется классом [System. Management. Automation. валидатепаттернаттрибуте](/dotnet/api/System.Management.Automation.ValidatePatternAttribute) .

## <a name="see-also"></a>См. также:

[System. Management. Automation. Валидатепаттернаттрибуте](/dotnet/api/System.Management.Automation.ValidatePatternAttribute)

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
