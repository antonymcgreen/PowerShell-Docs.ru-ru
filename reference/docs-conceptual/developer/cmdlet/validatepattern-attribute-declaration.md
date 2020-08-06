---
title: Объявление атрибута ValidatePattern | Документация Майкрософт
ms.date: 09/13/2016
helpviewer_keywords:
- attributes, ValidatePattern
- ValidatePattern attribute, described
- ValidatePattern attribute
ms.openlocfilehash: 713fa7a46a8eeefdbfd679a5e8436285fac085f8
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787807"
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

`RegexString`([System. String](/dotnet/api/System.String)) обязательный. Задает регулярное выражение, которое проверяет аргумент параметра.

Параметры ([System. Text. RegularExpressions. RegexOptions](/dotnet/api/System.Text.RegularExpressions.RegexOptions)) необязательный именованный параметр. Задает побитовое сочетание флагов [System. Text. RegularExpressions. RegexOptions](/dotnet/api/System.Text.RegularExpressions.RegexOptions) , задающих параметры регулярных выражений.

## <a name="remarks"></a>Примечания

- Этот атрибут можно использовать только один раз для каждого параметра.

- `Option`Для дальнейшего определения шаблона можно использовать параметр атрибута. Например, можно сделать шаблон чувствительным к регистру.

- Если этот атрибут применяется к коллекции, каждый элемент в коллекции должен соответствовать шаблону.

- Атрибут ValidatePattern определяется классом [System. Management. Automation. валидатепаттернаттрибуте](/dotnet/api/System.Management.Automation.ValidatePatternAttribute) .

## <a name="see-also"></a>См. также

[System. Management. Automation. Валидатепаттернаттрибуте](/dotnet/api/System.Management.Automation.ValidatePatternAttribute)

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
