---
title: Создание оснастки Windows PowerShell | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- snap-ins [PowerShell SDK], examples
ms.assetid: 71bd9b2c-5f2e-4aa8-b5fe-08c956540d37
caps.latest.revision: 10
ms.openlocfilehash: 43199544dc02ccae4b61053c30d6ed36576adfcf
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2019
ms.locfileid: "58055943"
---
# <a name="how-to-create-a-windows-powershell-snap-in"></a><span data-ttu-id="0517a-102">Как создать оснастку Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0517a-102">How to Create a Windows PowerShell Snap-in</span></span>

<span data-ttu-id="0517a-103">Оснастки Windows PowerShell предоставляет механизм для регистрации наборы командлетов и другого поставщика Windows PowerShell с оболочкой, расширяя таким образом функциональных возможностей оболочки.</span><span class="sxs-lookup"><span data-stu-id="0517a-103">A Windows PowerShell snap-in provides a mechanism for registering sets of cmdlets and another Windows PowerShell provider with the shell, thus extending the functionality of the shell.</span></span> <span data-ttu-id="0517a-104">Оснастки Windows PowerShell можно зарегистрировать все командлеты и поставщики в одной сборке, или для регистрации в определенный список командлетов и поставщиков.</span><span class="sxs-lookup"><span data-stu-id="0517a-104">A Windows PowerShell snap-in can register all the cmdlets and providers in a single assembly, or it can register a specific list of cmdlets and providers.</span></span>

<span data-ttu-id="0517a-105">Оснастка сборки должны быть установлены в защищенный каталог, так же, как они будут иметь с другими операционными системами.</span><span class="sxs-lookup"><span data-stu-id="0517a-105">Snap-in assemblies should be installed in a protected directory, just as they would be with other operating systems.</span></span> <span data-ttu-id="0517a-106">В противном случае пользователи-злоумышленники можно заменить сборку небезопасного кода.</span><span class="sxs-lookup"><span data-stu-id="0517a-106">Otherwise, malicious users can replace an assembly with unsafe code.</span></span>

## <a name="windows-powershell-snap-in-classes"></a><span data-ttu-id="0517a-107">Windows PowerShell Snap-in классы</span><span class="sxs-lookup"><span data-stu-id="0517a-107">Windows PowerShell Snap-in Classes</span></span>

<span data-ttu-id="0517a-108">Все классы оснастки Windows PowerShell являются производными от [System.Management.Automation.PSSnapIn](/dotnet/api/System.Management.Automation.PSSnapIn) или [System.Management.Automation.Custompssnapin](/dotnet/api/System.Management.Automation.CustomPSSnapIn) классы.</span><span class="sxs-lookup"><span data-stu-id="0517a-108">All Windows PowerShell snap-in classes derive from the [System.Management.Automation.PSSnapIn](/dotnet/api/System.Management.Automation.PSSnapIn) or [System.Management.Automation.Custompssnapin](/dotnet/api/System.Management.Automation.CustomPSSnapIn) classes.</span></span>

## <a name="examples"></a><span data-ttu-id="0517a-109">Примеры</span><span class="sxs-lookup"><span data-stu-id="0517a-109">Examples</span></span>

<span data-ttu-id="0517a-110">[Написание оснастки Windows PowerShell](./writing-a-windows-powershell-snap-in.md): В этом примере показано, как создать это оснастка, который позволяет зарегистрировать все командлеты и поставщики в сборке.</span><span class="sxs-lookup"><span data-stu-id="0517a-110">[Writing a Windows PowerShell Snap-in](./writing-a-windows-powershell-snap-in.md): This example shows how to create a snap-in that is used to register all the cmdlets and providers in an assembly.</span></span>

<span data-ttu-id="0517a-111">[Написание пользовательских Windows PowerShell – – оснастка](./writing-a-custom-windows-powershell-snap-in.md): В этом примере показано, как создать пользовательский оснастки, используемый для регистрации определенного набора командлетов и поставщиков, которые могут или не существовать в одной сборке.</span><span class="sxs-lookup"><span data-stu-id="0517a-111">[Writing a Custom Windows PowerShell Snap-in](./writing-a-custom-windows-powershell-snap-in.md): This example shows how to create a custom snap-in that is used to register a specific set of cmdlets and providers that might or might not exist in a single assembly.</span></span>

## <a name="see-also"></a><span data-ttu-id="0517a-112">См. также</span><span class="sxs-lookup"><span data-stu-id="0517a-112">See Also</span></span>

[<span data-ttu-id="0517a-113">System.Management.Automation.PSSnapIn</span><span class="sxs-lookup"><span data-stu-id="0517a-113">System.Management.Automation.PSSnapIn</span></span>](/dotnet/api/System.Management.Automation.PSSnapIn)

[<span data-ttu-id="0517a-114">System.Management.Automation.Custompssnapin</span><span class="sxs-lookup"><span data-stu-id="0517a-114">System.Management.Automation.Custompssnapin</span></span>](/dotnet/api/System.Management.Automation.CustomPSSnapIn)

[<span data-ttu-id="0517a-115">Регистрация командлетов</span><span class="sxs-lookup"><span data-stu-id="0517a-115">Registering Cmdlets</span></span>](./registering-cmdlets.md)

[<span data-ttu-id="0517a-116">Оболочка Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="0517a-116">Windows PowerShell Shell SDK</span></span>](../windows-powershell-reference.md)
