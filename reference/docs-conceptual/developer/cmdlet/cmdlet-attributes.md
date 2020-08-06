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
# <a name="cmdlet-attributes"></a><span data-ttu-id="583e2-102">Атрибуты командлета</span><span class="sxs-lookup"><span data-stu-id="583e2-102">Cmdlet Attributes</span></span>

<span data-ttu-id="583e2-103">Windows PowerShell определяет несколько атрибутов, которые можно использовать для добавления в командлеты общих функциональных возможностей без реализации этих функций в собственном коде.</span><span class="sxs-lookup"><span data-stu-id="583e2-103">Windows PowerShell defines several attributes that you can use to add common functionality to your cmdlets without implementing that functionality within your own code.</span></span> <span data-ttu-id="583e2-104">Сюда входит атрибут командлета, определяющий класс Microsoft .NET Framework в качестве класса командлета, атрибут OutputType, указывающий типы .NET Framework, возвращаемые командлетом, атрибут параметра, определяющий открытые свойства в качестве параметров командлета, и многое другое.</span><span class="sxs-lookup"><span data-stu-id="583e2-104">This includes the Cmdlet attribute that identifies a Microsoft .NET Framework class as a cmdlet class, the OutputType attribute that specifies the .NET Framework types returned by the cmdlet, the Parameter attribute that identifies public properties as cmdlet parameters, and more.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="583e2-105">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="583e2-105">In This Section</span></span>

<span data-ttu-id="583e2-106">[Атрибуты в коде командлета](./attributes-in-cmdlet-code.md) Описывает преимущества использования атрибутов в коде командлета.</span><span class="sxs-lookup"><span data-stu-id="583e2-106">[Attributes in Cmdlet Code](./attributes-in-cmdlet-code.md) Describes the benefit of using attributes in cmdlet code.</span></span>

<span data-ttu-id="583e2-107">[Типы атрибутов](./attribute-types.md) Описывает различные атрибуты, которые можно снабдить классом командлета.</span><span class="sxs-lookup"><span data-stu-id="583e2-107">[Attribute Types](./attribute-types.md) Describes the different attributes that can decorate a cmdlet class.</span></span>

<span data-ttu-id="583e2-108">[Объявление атрибута Alias](./alias-attribute-declaration.md) Описывает, как определить псевдонимы для имени параметра командлета.</span><span class="sxs-lookup"><span data-stu-id="583e2-108">[Alias Attribute Declaration](./alias-attribute-declaration.md) Describes how to define aliases for a cmdlet parameter name.</span></span>

<span data-ttu-id="583e2-109">[Объявление атрибута командлета](./cmdlet-attribute-declaration.md) Описывает, как определить класс .NET Framework в качестве командлета.</span><span class="sxs-lookup"><span data-stu-id="583e2-109">[Cmdlet Attribute Declaration](./cmdlet-attribute-declaration.md) Describes how to define a .NET Framework class as a cmdlet.</span></span>

<span data-ttu-id="583e2-110">[Объявление атрибута учетных данных](./credential-attribute-declaration.md) Описывает, как добавить поддержку преобразования входных строк в объект [System. Management. Automation. PSCredential](/dotnet/api/System.Management.Automation.PSCredential) .</span><span class="sxs-lookup"><span data-stu-id="583e2-110">[Credential Attribute Declaration](./credential-attribute-declaration.md) Describes how to add support for converting string input into a [System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential) object.</span></span>

<span data-ttu-id="583e2-111">[Объявление атрибута OutputType](./outputtype-attribute-declaration.md) Описывает, как указать типы .NET Framework, возвращаемые командлетом.</span><span class="sxs-lookup"><span data-stu-id="583e2-111">[OutputType attribute Declaration](./outputtype-attribute-declaration.md) Describes how to specify the .NET Framework types returned by the cmdlet.</span></span>

<span data-ttu-id="583e2-112">[Объявление атрибута Parameter](./parameter-attribute-declaration.md) Описывает, как определить параметры командлета.</span><span class="sxs-lookup"><span data-stu-id="583e2-112">[Parameter Attribute Declaration](./parameter-attribute-declaration.md) Describes how to define the parameters of a cmdlet.</span></span>

<span data-ttu-id="583e2-113">[Объявление атрибута валидатекаунт](./validatecount-attribute-declaration.md) Описывает, как определить, сколько аргументов разрешено для параметра.</span><span class="sxs-lookup"><span data-stu-id="583e2-113">[ValidateCount Attribute Declaration](./validatecount-attribute-declaration.md) Describes how to define how many arguments are allowed for a parameter.</span></span>

<span data-ttu-id="583e2-114">[Объявление атрибута валидателенгс](./validatelength-attribute-declaration.md) Описывает, как определить длину аргумента параметра (в символах).</span><span class="sxs-lookup"><span data-stu-id="583e2-114">[ValidateLength Attribute Declaration](./validatelength-attribute-declaration.md) Describes how to define the length (in characters) of a parameter argument.</span></span>

<span data-ttu-id="583e2-115">[Объявление атрибута ValidatePattern](./validatepattern-attribute-declaration.md) Описывает, как определить допустимые шаблоны для аргумента параметра.</span><span class="sxs-lookup"><span data-stu-id="583e2-115">[ValidatePattern Attribute Declaration](./validatepattern-attribute-declaration.md) Describes how to define the valid patterns for a parameter argument.</span></span>

<span data-ttu-id="583e2-116">[Объявление атрибута валидатеранже](./validaterange-attribute-declaration.md) Описывает, как определить допустимый диапазон для аргумента параметра.</span><span class="sxs-lookup"><span data-stu-id="583e2-116">[ValidateRange Attribute Declaration](./validaterange-attribute-declaration.md) Describes how to define the valid range for a parameter argument.</span></span>

<span data-ttu-id="583e2-117">[Объявление атрибута "Validate](./validateset-attribute-declaration.md) " Описывает, как определить возможные значения для аргумента параметра.</span><span class="sxs-lookup"><span data-stu-id="583e2-117">[ValidateSet Attribute Declaration](./validateset-attribute-declaration.md) Describes how to define the possible values for a parameter argument.</span></span>

## <a name="reference"></a><span data-ttu-id="583e2-118">Справочник</span><span class="sxs-lookup"><span data-stu-id="583e2-118">Reference</span></span>

[<span data-ttu-id="583e2-119">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="583e2-119">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
