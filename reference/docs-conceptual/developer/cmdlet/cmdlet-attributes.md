---
ms.date: 09/13/2016
ms.topic: reference
title: Атрибуты командлета
description: Атрибуты командлета
ms.openlocfilehash: 6a106f33cb34c6c33b88a981815543bc9af4e4ba
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92653509"
---
# <a name="cmdlet-attributes"></a><span data-ttu-id="b3ada-103">Атрибуты командлета</span><span class="sxs-lookup"><span data-stu-id="b3ada-103">Cmdlet Attributes</span></span>

<span data-ttu-id="b3ada-104">Windows PowerShell определяет несколько атрибутов, которые можно использовать для добавления в командлеты общих функциональных возможностей без реализации этих функций в собственном коде.</span><span class="sxs-lookup"><span data-stu-id="b3ada-104">Windows PowerShell defines several attributes that you can use to add common functionality to your cmdlets without implementing that functionality within your own code.</span></span> <span data-ttu-id="b3ada-105">Сюда входит атрибут командлета, определяющий класс Microsoft .NET Framework в качестве класса командлета, атрибут OutputType, указывающий типы .NET Framework, возвращаемые командлетом, атрибут параметра, определяющий открытые свойства в качестве параметров командлета, и многое другое.</span><span class="sxs-lookup"><span data-stu-id="b3ada-105">This includes the Cmdlet attribute that identifies a Microsoft .NET Framework class as a cmdlet class, the OutputType attribute that specifies the .NET Framework types returned by the cmdlet, the Parameter attribute that identifies public properties as cmdlet parameters, and more.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="b3ada-106">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="b3ada-106">In This Section</span></span>

<span data-ttu-id="b3ada-107">[Атрибуты в коде командлета](./attributes-in-cmdlet-code.md) Описывает преимущества использования атрибутов в коде командлета.</span><span class="sxs-lookup"><span data-stu-id="b3ada-107">[Attributes in Cmdlet Code](./attributes-in-cmdlet-code.md) Describes the benefit of using attributes in cmdlet code.</span></span>

<span data-ttu-id="b3ada-108">[Типы атрибутов](./attribute-types.md) Описывает различные атрибуты, которые можно снабдить классом командлета.</span><span class="sxs-lookup"><span data-stu-id="b3ada-108">[Attribute Types](./attribute-types.md) Describes the different attributes that can decorate a cmdlet class.</span></span>

<span data-ttu-id="b3ada-109">[Объявление атрибута Alias](./alias-attribute-declaration.md) Описывает, как определить псевдонимы для имени параметра командлета.</span><span class="sxs-lookup"><span data-stu-id="b3ada-109">[Alias Attribute Declaration](./alias-attribute-declaration.md) Describes how to define aliases for a cmdlet parameter name.</span></span>

<span data-ttu-id="b3ada-110">[Объявление атрибута командлета](./cmdlet-attribute-declaration.md) Описывает, как определить класс .NET Framework в качестве командлета.</span><span class="sxs-lookup"><span data-stu-id="b3ada-110">[Cmdlet Attribute Declaration](./cmdlet-attribute-declaration.md) Describes how to define a .NET Framework class as a cmdlet.</span></span>

<span data-ttu-id="b3ada-111">[Объявление атрибута учетных данных](./credential-attribute-declaration.md) Описывает, как добавить поддержку преобразования входных строк в объект [System. Management. Automation. PSCredential](/dotnet/api/System.Management.Automation.PSCredential) .</span><span class="sxs-lookup"><span data-stu-id="b3ada-111">[Credential Attribute Declaration](./credential-attribute-declaration.md) Describes how to add support for converting string input into a [System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential) object.</span></span>

<span data-ttu-id="b3ada-112">[Объявление атрибута OutputType](./outputtype-attribute-declaration.md) Описывает, как указать типы .NET Framework, возвращаемые командлетом.</span><span class="sxs-lookup"><span data-stu-id="b3ada-112">[OutputType attribute Declaration](./outputtype-attribute-declaration.md) Describes how to specify the .NET Framework types returned by the cmdlet.</span></span>

<span data-ttu-id="b3ada-113">[Объявление атрибута Parameter](./parameter-attribute-declaration.md) Описывает, как определить параметры командлета.</span><span class="sxs-lookup"><span data-stu-id="b3ada-113">[Parameter Attribute Declaration](./parameter-attribute-declaration.md) Describes how to define the parameters of a cmdlet.</span></span>

<span data-ttu-id="b3ada-114">[Объявление атрибута валидатекаунт](./validatecount-attribute-declaration.md) Описывает, как определить, сколько аргументов разрешено для параметра.</span><span class="sxs-lookup"><span data-stu-id="b3ada-114">[ValidateCount Attribute Declaration](./validatecount-attribute-declaration.md) Describes how to define how many arguments are allowed for a parameter.</span></span>

<span data-ttu-id="b3ada-115">[Объявление атрибута валидателенгс](./validatelength-attribute-declaration.md) Описывает, как определить длину аргумента параметра (в символах).</span><span class="sxs-lookup"><span data-stu-id="b3ada-115">[ValidateLength Attribute Declaration](./validatelength-attribute-declaration.md) Describes how to define the length (in characters) of a parameter argument.</span></span>

<span data-ttu-id="b3ada-116">[Объявление атрибута ValidatePattern](./validatepattern-attribute-declaration.md) Описывает, как определить допустимые шаблоны для аргумента параметра.</span><span class="sxs-lookup"><span data-stu-id="b3ada-116">[ValidatePattern Attribute Declaration](./validatepattern-attribute-declaration.md) Describes how to define the valid patterns for a parameter argument.</span></span>

<span data-ttu-id="b3ada-117">[Объявление атрибута валидатеранже](./validaterange-attribute-declaration.md) Описывает, как определить допустимый диапазон для аргумента параметра.</span><span class="sxs-lookup"><span data-stu-id="b3ada-117">[ValidateRange Attribute Declaration](./validaterange-attribute-declaration.md) Describes how to define the valid range for a parameter argument.</span></span>

<span data-ttu-id="b3ada-118">[Объявление атрибута "Validate](./validateset-attribute-declaration.md) " Описывает, как определить возможные значения для аргумента параметра.</span><span class="sxs-lookup"><span data-stu-id="b3ada-118">[ValidateSet Attribute Declaration](./validateset-attribute-declaration.md) Describes how to define the possible values for a parameter argument.</span></span>

## <a name="reference"></a><span data-ttu-id="b3ada-119">Ссылка</span><span class="sxs-lookup"><span data-stu-id="b3ada-119">Reference</span></span>

[<span data-ttu-id="b3ada-120">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b3ada-120">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
