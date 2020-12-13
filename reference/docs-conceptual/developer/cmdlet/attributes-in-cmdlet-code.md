---
ms.date: 09/13/2016
ms.topic: reference
title: Атрибуты в коде командлета
description: Атрибуты в коде командлета
ms.openlocfilehash: 296bb8bcb06ef660e97dc792d1ecf596cc7c2930
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92653657"
---
# <a name="attributes-in-cmdlet-code"></a><span data-ttu-id="250bf-103">Атрибуты в коде командлета</span><span class="sxs-lookup"><span data-stu-id="250bf-103">Attributes in Cmdlet Code</span></span>

<span data-ttu-id="250bf-104">Для использования общих функциональных возможностей, предоставляемых Windows PowerShell, классы и общие свойства, определенные в коде командлета, оформляются с помощью атрибутов.</span><span class="sxs-lookup"><span data-stu-id="250bf-104">To use the common functionality provided by Windows PowerShell, the classes and public properties defined in the cmdlet code are decorated with attributes.</span></span> <span data-ttu-id="250bf-105">Например, следующее определение класса использует атрибут командлета для определения класса Microsoft .NET Framework, в котором реализован командлет **Get-proc** .</span><span class="sxs-lookup"><span data-stu-id="250bf-105">For example, the following class definition uses the Cmdlet attribute to identify the Microsoft .NET Framework class in which the **Get-Proc** cmdlet is implemented.</span></span> <span data-ttu-id="250bf-106">(Этот командлет используется в качестве примера в этом документе и аналогичен `Get-Process` командлету, предоставленному Windows PowerShell.)</span><span class="sxs-lookup"><span data-stu-id="250bf-106">(This cmdlet is used as an example in this document, and is similar to the `Get-Process` cmdlet provided by Windows PowerShell.)</span></span>

```csharp
[Cmdlet(VerbsCommon.Get, "Proc")]
public class GetProcCommand : Cmdlet
```

<span data-ttu-id="250bf-107">Эти атрибуты считаются метаданными, так как их реализация отличается от реализации кода командлета.</span><span class="sxs-lookup"><span data-stu-id="250bf-107">These attributes are considered metadata because their implementation is separate from the implementation of the cmdlet code.</span></span> <span data-ttu-id="250bf-108">Когда среда выполнения Windows PowerShell выполняет командлет, он распознает атрибуты, а затем выполняет соответствующее действие для каждого атрибута.</span><span class="sxs-lookup"><span data-stu-id="250bf-108">When the Windows PowerShell runtime runs the cmdlet, it recognizes the attributes and then performs the appropriate action for each attribute.</span></span>

<span data-ttu-id="250bf-109">Хотя может потребоваться реализовать собственную версию функциональности, предоставляемую этими атрибутами, хорошая разработка командлетов использует эти общие функциональные возможности.</span><span class="sxs-lookup"><span data-stu-id="250bf-109">Although you might want to implement your own version of the functionality provided by these attributes, a good cmdlet design uses these common functionalities.</span></span>

<span data-ttu-id="250bf-110">Дополнительные сведения о различных атрибутах, которые могут быть объявлены в командлетах, см. в разделе [типы атрибутов](./attribute-types.md).</span><span class="sxs-lookup"><span data-stu-id="250bf-110">For more information about the different attributes that can be declared in your cmdlets, see [Attribute Types](./attribute-types.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="250bf-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="250bf-111">See Also</span></span>

[<span data-ttu-id="250bf-112">Типы атрибутов</span><span class="sxs-lookup"><span data-stu-id="250bf-112">Attribute Types</span></span>](./attribute-types.md)

[<span data-ttu-id="250bf-113">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="250bf-113">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
