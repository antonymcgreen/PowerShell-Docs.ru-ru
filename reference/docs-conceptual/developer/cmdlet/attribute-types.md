---
title: Типы атрибутов | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9b1026ad-f072-4fca-8052-a2d8eb491c2a
caps.latest.revision: 6
ms.openlocfilehash: 52c75b3ca73706da39029d5b3ead52ff7197a5f1
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72364583"
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

### <a name="alias"></a>Alias

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

## <a name="see-also"></a>См. также:

[Пакет SDK для Windows PowerShell](../windows-powershell-reference.md)
