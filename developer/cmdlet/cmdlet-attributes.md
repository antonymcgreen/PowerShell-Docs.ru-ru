---
title: Атрибуты командлета | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- attributes [PowerShell SDK]
- attributes [PowerShell SDK], described
ms.assetid: d3f4f652-d929-4c27-9358-9baa390a094c
caps.latest.revision: 14
ms.openlocfilehash: 326cd408e86402974569fc76d5e473be5a56f0b6
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62068612"
---
# <a name="cmdlet-attributes"></a>Атрибуты командлета

Windows PowerShell определяет несколько атрибутов, которые позволяют добавлять функциональные возможности в командлеты без реализации этой функциональности в собственном коде. Это включает атрибут командлета, который определяет класс Microsoft .NET Framework как класс командлет атрибута OutputType, который указывает типы .NET Framework, возвращаемый командлетом, атрибут параметра, определяющего открытые свойства как командлет параметры и многое другое.

## <a name="in-this-section"></a>Содержание

[Атрибуты в коде командлета](./attributes-in-cmdlet-code.md) описываются преимущества использования атрибутов в коде командлета.

[Типы атрибутов](./attribute-types.md) описаны различные атрибуты, которые может декорировать класс командлета.

[Объявление атрибута псевдоним](./alias-attribute-declaration.md) описывает способ определения псевдонимов по имени параметра командлета.

[Объявление атрибута командлет](./cmdlet-attribute-declaration.md) описывается, как определить класс .NET Framework как командлет.

[Учетные данные объявление атрибута](./credential-attribute-declaration.md) описывается, как добавить поддержку для преобразования строкового ввода в [System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential) объекта.

[Атрибута OutputType объявление](./outputtype-attribute-declaration.md) описывается, как указать типы .NET Framework, возвращаемый командлетом.

[Объявление атрибута параметра](./parameter-attribute-declaration.md) описывается определение параметров командлета.

[Объявление атрибута ValidateCount](./validatecount-attribute-declaration.md) описывается, как определить, сколько аргументы можно использовать для параметра.

[Объявление атрибута ValidateLength](./validatelength-attribute-declaration.md) описывается, как определить длину (в символах) аргумент параметра.

[Объявление атрибута ValidatePattern](./validatepattern-attribute-declaration.md) описывается определение допустимых шаблонов для аргумента параметра.

[Объявление атрибута ValidateRange](./validaterange-attribute-declaration.md) описывается определение допустимое значение для аргумента параметра.

[Объявление атрибута ValidateSet](./validateset-attribute-declaration.md) описывается, как определить возможные значения для аргумента параметра.

## <a name="reference"></a>Ссылка

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
