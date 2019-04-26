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
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62068665"
---
# <a name="attribute-types"></a>Типы атрибутов

Командлет атрибуты могут быть сгруппированы по функциональным возможностям.
В следующих разделах описываются доступные атрибуты и описывают, что исполняющая среда создает при вызове атрибута.

## <a name="cmdlet-attributes"></a>Атрибуты командлета

### <a name="cmdlet"></a>Командлет

Определяет класс .NET Framework как командлет.
Это обязательный базовый атрибут.
Дополнительные сведения см. в разделе [объявление атрибута командлет](./cmdlet-attribute-declaration.md).

## <a name="parameter-attributes"></a>Атрибуты параметра

### <a name="parameter"></a>Параметр

Определяет открытое свойство в классе командлета в виде параметра командлета.
Дополнительные сведения см. в разделе [объявление атрибута параметра](./parameter-attribute-declaration.md).

### <a name="alias"></a>Alias

Указывает один или несколько псевдонимов для параметра.
Дополнительные сведения см. в разделе [объявление атрибута псевдоним](./alias-attribute-declaration.md).

## <a name="argument-validation-attributes"></a>Атрибуты проверки аргументов

### <a name="validatecount"></a>ValidateCount

Указывает минимальное и максимальное число аргументов, которые разрешены для параметра командлета.
Дополнительные сведения см. в разделе [объявление атрибута ValidateCount](./validatecount-attribute-declaration.md).

### <a name="validatelength"></a>ValidateLength

Указывает минимальное и максимальное количество символов для аргумента параметра командлета.
Дополнительные сведения см. в разделе [объявление атрибута ValidateLength](./validatelength-attribute-declaration.md).

### <a name="validatepattern"></a>ValidatePattern

Указывает шаблон регулярного выражения, которое должно соответствовать аргумент параметра в командлет.
Дополнительные сведения см. в разделе [объявление атрибута ValidatePattern](./validatepattern-attribute-declaration.md).

### <a name="validaterange"></a>ValidateRange

Задает минимальное и максимальное значения для аргумента параметра командлета.
Дополнительные сведения см. в разделе [объявление атрибута ValidateRange](./validaterange-attribute-declaration.md).

### <a name="validateset"></a>ValidateSet

Задает набор допустимых значений для аргумента параметра в командлет.
Дополнительные сведения см. в разделе [объявление атрибута ValidateSet](./validateset-attribute-declaration.md).

## <a name="see-also"></a>См. также

[Пакет SDK для Windows PowerShell](../windows-powershell-reference.md)
