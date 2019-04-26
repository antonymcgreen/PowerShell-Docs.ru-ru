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
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62068694"
---
# <a name="attributes-in-cmdlet-code"></a><span data-ttu-id="45104-102">Атрибуты в коде командлета</span><span class="sxs-lookup"><span data-stu-id="45104-102">Attributes in Cmdlet Code</span></span>

<span data-ttu-id="45104-103">Чтобы использовать функциональные возможности, предоставляемые Windows PowerShell, классов и открытые свойства, определенные в коде командлета оформляются с использованием атрибутов.</span><span class="sxs-lookup"><span data-stu-id="45104-103">To use the common functionality provided by Windows PowerShell, the classes and public properties defined in the cmdlet code are decorated with attributes.</span></span> <span data-ttu-id="45104-104">Например, следующее определение класса использует атрибут командлета для идентификации класс Microsoft .NET Framework, в котором **Get-Proc** командлет реализован.</span><span class="sxs-lookup"><span data-stu-id="45104-104">For example, the following class definition uses the Cmdlet attribute to identify the Microsoft .NET Framework class in which the **Get-Proc** cmdlet is implemented.</span></span> <span data-ttu-id="45104-105">(Этот командлет используется в качестве примера в этом документе он аналогичен `Get-Process` командлет, предоставляемые Windows PowerShell.)</span><span class="sxs-lookup"><span data-stu-id="45104-105">(This cmdlet is used as an example in this document, and is similar to the `Get-Process` cmdlet provided by Windows PowerShell.)</span></span>

```csharp
[Cmdlet(VerbsCommon.Get, "Proc")]
public class GetProcCommand : Cmdlet
```

<span data-ttu-id="45104-106">Эти атрибуты считаются метаданных, так как их реализация отличается от реализации код командлета.</span><span class="sxs-lookup"><span data-stu-id="45104-106">These attributes are considered metadata because their implementation is separate from the implementation of the cmdlet code.</span></span> <span data-ttu-id="45104-107">Когда среда выполнения Windows PowerShell выполняет командлет, он распознает атрибуты и затем выполняет соответствующие действия для каждого атрибута.</span><span class="sxs-lookup"><span data-stu-id="45104-107">When the Windows PowerShell runtime runs the cmdlet, it recognizes the attributes and then performs the appropriate action for each attribute.</span></span>

<span data-ttu-id="45104-108">Несмотря на то, что может потребоваться реализовать собственную версию функции, предоставляемые эти атрибуты, проектирования хороший командлет использует эти общие функциональные возможности.</span><span class="sxs-lookup"><span data-stu-id="45104-108">Although you might want to implement your own version of the functionality provided by these attributes, a good cmdlet design uses these common functionalities.</span></span>

<span data-ttu-id="45104-109">Дополнительные сведения о различных атрибутов, которые могут быть объявлены в командлеты, см. в разделе [типы атрибутов](./attribute-types.md).</span><span class="sxs-lookup"><span data-stu-id="45104-109">For more information about the different attributes that can be declared in your cmdlets, see [Attribute Types](./attribute-types.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="45104-110">См. также</span><span class="sxs-lookup"><span data-stu-id="45104-110">See Also</span></span>

[<span data-ttu-id="45104-111">Типы атрибутов</span><span class="sxs-lookup"><span data-stu-id="45104-111">Attribute Types</span></span>](./attribute-types.md)

[<span data-ttu-id="45104-112">Запись командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="45104-112">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
