---
title: Типы атрибутов | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 96fdd38ba10eb748ab0762f0c910463dd472494d
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87782384"
---
# <a name="attribute-types"></a>Типы атрибутов

Атрибуты командлета могут быть сгруппированы по функциональным возможностям.
В следующих разделах описываются доступные атрибуты и описываются действия, выполняемые средой выполнения при вызове атрибута.

## <a name="cmdlet-attributes"></a>Атрибуты командлета

### <a name="cmdlet"></a>Командлет

Идентифицирует класс .NET Framework в качестве командлета.
Это обязательный базовый атрибут.
Дополнительные сведения см. в разделе [объявление атрибута командлета](./cmdlet-attribute-declaration.md).

## <a name="parameter-attributes"></a>Атрибуты параметра

### <a name="parameter"></a>Параметр

Определяет открытое свойство в классе командлета как параметр командлета.
Дополнительные сведения см. в разделе [объявление атрибута Parameter](./parameter-attribute-declaration.md).

### <a name="alias"></a>Псевдоним

Указывает один или несколько псевдонимов для параметра.
Дополнительные сведения см. в разделе [объявление атрибута Alias](./alias-attribute-declaration.md).

## <a name="argument-validation-attributes"></a>Атрибуты проверки аргументов

### <a name="validatecount"></a>валидатекаунт

Указывает минимальное и максимальное число аргументов, допустимых для параметра командлета.
Дополнительные сведения см. в разделе [объявление атрибута валидатекаунт](./validatecount-attribute-declaration.md).

### <a name="validatelength"></a>валидателенгс

Указывает минимальное и максимальное число символов для аргумента параметра командлета.
Дополнительные сведения см. в разделе [объявление атрибута валидателенгс](./validatelength-attribute-declaration.md).

### <a name="validatepattern"></a>ValidatePattern

Указывает шаблон регулярного выражения, которому должен соответствовать аргумент параметра командлета.
Дополнительные сведения см. в разделе [объявление атрибута ValidatePattern](./validatepattern-attribute-declaration.md).

### <a name="validaterange"></a>валидатеранже

Указывает минимальное и максимальное значения для аргумента параметра командлета.
Дополнительные сведения см. в разделе [объявление атрибута валидатеранже](./validaterange-attribute-declaration.md).

### <a name="validateset"></a>ValidateSet

Задает набор допустимых значений для аргумента параметра командлета.
Дополнительные сведения см. в разделе [объявление атрибута "Validate](./validateset-attribute-declaration.md)".

## <a name="see-also"></a>См. также

[Пакет SDK для Windows PowerShell](../windows-powershell-reference.md)
