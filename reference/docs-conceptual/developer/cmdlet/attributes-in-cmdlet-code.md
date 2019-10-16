---
title: Атрибуты в коде командлета | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aea8d293-c45b-41eb-8385-548f7c9b280b
caps.latest.revision: 10
ms.openlocfilehash: 14505c4f7cc8490418ca463e3b81902f29d4f90b
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72370003"
---
# <a name="attributes-in-cmdlet-code"></a><span data-ttu-id="4d740-102">Атрибуты в коде командлета</span><span class="sxs-lookup"><span data-stu-id="4d740-102">Attributes in Cmdlet Code</span></span>

<span data-ttu-id="4d740-103">Для использования общих функциональных возможностей, предоставляемых Windows PowerShell, классы и общие свойства, определенные в коде командлета, оформляются с помощью атрибутов.</span><span class="sxs-lookup"><span data-stu-id="4d740-103">To use the common functionality provided by Windows PowerShell, the classes and public properties defined in the cmdlet code are decorated with attributes.</span></span> <span data-ttu-id="4d740-104">Например, следующее определение класса использует атрибут командлета для определения класса Microsoft .NET Framework, в котором реализован командлет **Get-proc** .</span><span class="sxs-lookup"><span data-stu-id="4d740-104">For example, the following class definition uses the Cmdlet attribute to identify the Microsoft .NET Framework class in which the **Get-Proc** cmdlet is implemented.</span></span> <span data-ttu-id="4d740-105">(Этот командлет используется в качестве примера в этом документе и аналогичен командлету `Get-Process`, предоставляемому Windows PowerShell.)</span><span class="sxs-lookup"><span data-stu-id="4d740-105">(This cmdlet is used as an example in this document, and is similar to the `Get-Process` cmdlet provided by Windows PowerShell.)</span></span>

```csharp
[Cmdlet(VerbsCommon.Get, "Proc")]
public class GetProcCommand : Cmdlet
```

<span data-ttu-id="4d740-106">Эти атрибуты считаются метаданными, так как их реализация отличается от реализации кода командлета.</span><span class="sxs-lookup"><span data-stu-id="4d740-106">These attributes are considered metadata because their implementation is separate from the implementation of the cmdlet code.</span></span> <span data-ttu-id="4d740-107">Когда среда выполнения Windows PowerShell выполняет командлет, он распознает атрибуты, а затем выполняет соответствующее действие для каждого атрибута.</span><span class="sxs-lookup"><span data-stu-id="4d740-107">When the Windows PowerShell runtime runs the cmdlet, it recognizes the attributes and then performs the appropriate action for each attribute.</span></span>

<span data-ttu-id="4d740-108">Хотя может потребоваться реализовать собственную версию функциональности, предоставляемую этими атрибутами, хорошая разработка командлетов использует эти общие функциональные возможности.</span><span class="sxs-lookup"><span data-stu-id="4d740-108">Although you might want to implement your own version of the functionality provided by these attributes, a good cmdlet design uses these common functionalities.</span></span>

<span data-ttu-id="4d740-109">Дополнительные сведения о различных атрибутах, которые могут быть объявлены в командлетах, см. в разделе [типы атрибутов](./attribute-types.md).</span><span class="sxs-lookup"><span data-stu-id="4d740-109">For more information about the different attributes that can be declared in your cmdlets, see [Attribute Types](./attribute-types.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4d740-110">См. также:</span><span class="sxs-lookup"><span data-stu-id="4d740-110">See Also</span></span>

[<span data-ttu-id="4d740-111">Типы атрибутов</span><span class="sxs-lookup"><span data-stu-id="4d740-111">Attribute Types</span></span>](./attribute-types.md)

[<span data-ttu-id="4d740-112">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4d740-112">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
