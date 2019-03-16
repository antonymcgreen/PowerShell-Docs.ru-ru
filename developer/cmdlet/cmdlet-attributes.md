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
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2019
ms.locfileid: "58055178"
---
# <a name="cmdlet-attributes"></a><span data-ttu-id="820f1-102">Атрибуты командлета</span><span class="sxs-lookup"><span data-stu-id="820f1-102">Cmdlet Attributes</span></span>

<span data-ttu-id="820f1-103">Windows PowerShell определяет несколько атрибутов, которые позволяют добавлять функциональные возможности в командлеты без реализации этой функциональности в собственном коде.</span><span class="sxs-lookup"><span data-stu-id="820f1-103">Windows PowerShell defines several attributes that you can use to add common functionality to your cmdlets without implementing that functionality within your own code.</span></span> <span data-ttu-id="820f1-104">Это включает атрибут командлета, который определяет класс Microsoft .NET Framework как класс командлет атрибута OutputType, который указывает типы .NET Framework, возвращаемый командлетом, атрибут параметра, определяющего открытые свойства как командлет параметры и многое другое.</span><span class="sxs-lookup"><span data-stu-id="820f1-104">This includes the Cmdlet attribute that identifies a Microsoft .NET Framework class as a cmdlet class, the OutputType attribute that specifies the .NET Framework types returned by the cmdlet, the Parameter attribute that identifies public properties as cmdlet parameters, and more.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="820f1-105">Содержание</span><span class="sxs-lookup"><span data-stu-id="820f1-105">In This Section</span></span>

<span data-ttu-id="820f1-106">[Атрибуты в коде командлета](./attributes-in-cmdlet-code.md) описываются преимущества использования атрибутов в коде командлета.</span><span class="sxs-lookup"><span data-stu-id="820f1-106">[Attributes in Cmdlet Code](./attributes-in-cmdlet-code.md) Describes the benefit of using attributes in cmdlet code.</span></span>

<span data-ttu-id="820f1-107">[Типы атрибутов](./attribute-types.md) описаны различные атрибуты, которые может декорировать класс командлета.</span><span class="sxs-lookup"><span data-stu-id="820f1-107">[Attribute Types](./attribute-types.md) Describes the different attributes that can decorate a cmdlet class.</span></span>

<span data-ttu-id="820f1-108">[Объявление атрибута псевдоним](./alias-attribute-declaration.md) описывает способ определения псевдонимов по имени параметра командлета.</span><span class="sxs-lookup"><span data-stu-id="820f1-108">[Alias Attribute Declaration](./alias-attribute-declaration.md) Describes how to define aliases for a cmdlet parameter name.</span></span>

<span data-ttu-id="820f1-109">[Объявление атрибута командлет](./cmdlet-attribute-declaration.md) описывается, как определить класс .NET Framework как командлет.</span><span class="sxs-lookup"><span data-stu-id="820f1-109">[Cmdlet Attribute Declaration](./cmdlet-attribute-declaration.md) Describes how to define a .NET Framework class as a cmdlet.</span></span>

<span data-ttu-id="820f1-110">[Учетные данные объявление атрибута](./credential-attribute-declaration.md) описывается, как добавить поддержку для преобразования строкового ввода в [System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential) объекта.</span><span class="sxs-lookup"><span data-stu-id="820f1-110">[Credential Attribute Declaration](./credential-attribute-declaration.md) Describes how to add support for converting string input into a [System.Management.Automation.PSCredential](/dotnet/api/System.Management.Automation.PSCredential) object.</span></span>

<span data-ttu-id="820f1-111">[Атрибута OutputType объявление](./outputtype-attribute-declaration.md) описывается, как указать типы .NET Framework, возвращаемый командлетом.</span><span class="sxs-lookup"><span data-stu-id="820f1-111">[OutputType attribute Declaration](./outputtype-attribute-declaration.md) Describes how to specify the .NET Framework types returned by the cmdlet.</span></span>

<span data-ttu-id="820f1-112">[Объявление атрибута параметра](./parameter-attribute-declaration.md) описывается определение параметров командлета.</span><span class="sxs-lookup"><span data-stu-id="820f1-112">[Parameter Attribute Declaration](./parameter-attribute-declaration.md) Describes how to define the parameters of a cmdlet.</span></span>

<span data-ttu-id="820f1-113">[Объявление атрибута ValidateCount](./validatecount-attribute-declaration.md) описывается, как определить, сколько аргументы можно использовать для параметра.</span><span class="sxs-lookup"><span data-stu-id="820f1-113">[ValidateCount Attribute Declaration](./validatecount-attribute-declaration.md) Describes how to define how many arguments are allowed for a parameter.</span></span>

<span data-ttu-id="820f1-114">[Объявление атрибута ValidateLength](./validatelength-attribute-declaration.md) описывается, как определить длину (в символах) аргумент параметра.</span><span class="sxs-lookup"><span data-stu-id="820f1-114">[ValidateLength Attribute Declaration](./validatelength-attribute-declaration.md) Describes how to define the length (in characters) of a parameter argument.</span></span>

<span data-ttu-id="820f1-115">[Объявление атрибута ValidatePattern](./validatepattern-attribute-declaration.md) описывается определение допустимых шаблонов для аргумента параметра.</span><span class="sxs-lookup"><span data-stu-id="820f1-115">[ValidatePattern Attribute Declaration](./validatepattern-attribute-declaration.md) Describes how to define the valid patterns for a parameter argument.</span></span>

<span data-ttu-id="820f1-116">[Объявление атрибута ValidateRange](./validaterange-attribute-declaration.md) описывается определение допустимое значение для аргумента параметра.</span><span class="sxs-lookup"><span data-stu-id="820f1-116">[ValidateRange Attribute Declaration](./validaterange-attribute-declaration.md) Describes how to define the valid range for a parameter argument.</span></span>

<span data-ttu-id="820f1-117">[Объявление атрибута ValidateSet](./validateset-attribute-declaration.md) описывается, как определить возможные значения для аргумента параметра.</span><span class="sxs-lookup"><span data-stu-id="820f1-117">[ValidateSet Attribute Declaration](./validateset-attribute-declaration.md) Describes how to define the possible values for a parameter argument.</span></span>

## <a name="reference"></a><span data-ttu-id="820f1-118">Ссылка</span><span class="sxs-lookup"><span data-stu-id="820f1-118">Reference</span></span>

[<span data-ttu-id="820f1-119">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="820f1-119">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
