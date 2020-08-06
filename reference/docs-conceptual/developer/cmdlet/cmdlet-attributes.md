---
title: Атрибуты командлета | Документация Майкрософт
ms.date: 09/13/2016
helpviewer_keywords:
- attributes [PowerShell SDK]
- attributes [PowerShell SDK], described
ms.openlocfilehash: f22c2882fbe5b2f51ca5ea218b921192b0a7d41f
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784526"
---
# <a name="cmdlet-attributes"></a>Атрибуты командлета

Windows PowerShell определяет несколько атрибутов, которые можно использовать для добавления в командлеты общих функциональных возможностей без реализации этих функций в собственном коде. Сюда входит атрибут командлета, определяющий класс Microsoft .NET Framework в качестве класса командлета, атрибут OutputType, указывающий типы .NET Framework, возвращаемые командлетом, атрибут параметра, определяющий открытые свойства в качестве параметров командлета, и многое другое.

## <a name="in-this-section"></a>В этом разделе

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

## <a name="reference"></a>Справочник

[Запись командлета Windows PowerShell](./writing-a-windows-powershell-cmdlet.md)
