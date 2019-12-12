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
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72369963"
---
# <a name="cmdlet-attributes"></a>Атрибуты командлета

Windows PowerShell определяет несколько атрибутов, которые можно использовать для добавления в командлеты общих функциональных возможностей без реализации этих функций в собственном коде. Сюда входит атрибут командлета, определяющий класс Microsoft .NET Framework в качестве класса командлета, атрибут OutputType, указывающий типы .NET Framework, возвращаемые командлетом, атрибут Parameter, определяющий открытые свойства в качестве командлета. параметры и многое другое.

## <a name="in-this-section"></a>Содержание

[Атрибуты в коде командлета](./attributes-in-cmdlet-code.md) Описывает преимущества использования атрибутов в коде командлета.

[Типы атрибутов](./attribute-types.md) Описывает различные атрибуты, которые можно снабдить классом командлета.

[Объявление атрибута Alias](./alias-attribute-declaration.md) Описывает, как определить псевдонимы для имени параметра командлета.

[Объявление атрибута командлета](./cmdlet-attribute-declaration.md) Описывает, как определить класс .NET Framework в качестве командлета.

[Объявление атрибута учетных данных](./credential-attribute-declaration.md) Описывает, как добавить поддержку преобразования входных строк в объект [System. Management. Automation. PSCredential](/dotnet/api/System.Management.Automation.PSCredential) .

[Объявление атрибута OutputType](./outputtype-attribute-declaration.md) Описывает, как указать типы .NET Framework, возвращаемые командлетом.

[Объявление атрибута Parameter](./parameter-attribute-declaration.md) Описывает, как определить параметры командлета.

[Объявление атрибута валидатекаунт](./validatecount-attribute-declaration.md) Описывает, как определить, сколько аргументов разрешено для параметра.

[Объявление атрибута валидателенгс](./validatelength-attribute-declaration.md) Описывает, как определить длину аргумента параметра (в символах).

[Объявление атрибута ValidatePattern](./validatepattern-attribute-declaration.md) Описывает, как определить допустимые шаблоны для аргумента параметра.

[Объявление атрибута валидатеранже](./validaterange-attribute-declaration.md) Описывает, как определить допустимый диапазон для аргумента параметра.

[Объявление атрибута "Validate](./validateset-attribute-declaration.md) " Описывает, как определить возможные значения для аргумента параметра.

## <a name="reference"></a>Ссылка

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
