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
ms.sourcegitcommit: 2aec310ad0c0b048400cb56f6fa64c1e554c812a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/23/2020
ms.locfileid: "83811333"
---
# <a name="how-to-create-a-windows-powershell-snap-in"></a><span data-ttu-id="b1eb0-102">Как создать оснастку Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b1eb0-102">How to Create a Windows PowerShell Snap-in</span></span>

<span data-ttu-id="b1eb0-103">Оснастка Windows PowerShell предоставляет механизм для регистрации наборов командлетов и другого поставщика Windows PowerShell с оболочкой, тем самым расширяя функциональные возможности оболочки.</span><span class="sxs-lookup"><span data-stu-id="b1eb0-103">A Windows PowerShell snap-in provides a mechanism for registering sets of cmdlets and another Windows PowerShell provider with the shell, thus extending the functionality of the shell.</span></span> <span data-ttu-id="b1eb0-104">Оснастка Windows PowerShell может зарегистрировать все командлеты и поставщики в одной сборке или зарегистрировать конкретный список командлетов и поставщиков.</span><span class="sxs-lookup"><span data-stu-id="b1eb0-104">A Windows PowerShell snap-in can register all the cmdlets and providers in a single assembly, or it can register a specific list of cmdlets and providers.</span></span>

<span data-ttu-id="b1eb0-105">Сборки оснастки должны быть установлены в защищенном каталоге так же, как и в других операционных системах.</span><span class="sxs-lookup"><span data-stu-id="b1eb0-105">Snap-in assemblies should be installed in a protected directory, just as they would be with other operating systems.</span></span> <span data-ttu-id="b1eb0-106">В противном случае злонамеренные пользователи могут заменить сборку на небезопасный код.</span><span class="sxs-lookup"><span data-stu-id="b1eb0-106">Otherwise, malicious users can replace an assembly with unsafe code.</span></span>

## <a name="windows-powershell-snap-in-classes"></a><span data-ttu-id="b1eb0-107">Классы оснастки Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b1eb0-107">Windows PowerShell Snap-in Classes</span></span>

<span data-ttu-id="b1eb0-108">Все классы оснастки Windows PowerShell являются производными от классов [System. Management. Automation. PSSnapin](/dotnet/api/System.Management.Automation.PSSnapIn) или [System. Management. Automation. кустомпсснапин](/dotnet/api/System.Management.Automation.CustomPSSnapIn) .</span><span class="sxs-lookup"><span data-stu-id="b1eb0-108">All Windows PowerShell snap-in classes derive from the [System.Management.Automation.PSSnapIn](/dotnet/api/System.Management.Automation.PSSnapIn) or [System.Management.Automation.Custompssnapin](/dotnet/api/System.Management.Automation.CustomPSSnapIn) classes.</span></span>

## <a name="examples"></a><span data-ttu-id="b1eb0-109">Примеры</span><span class="sxs-lookup"><span data-stu-id="b1eb0-109">Examples</span></span>

<span data-ttu-id="b1eb0-110">Создание [оснастки Windows PowerShell](./writing-a-windows-powershell-snap-in.md). в этом примере показано, как создать оснастку, которая будет использоваться для регистрации всех командлетов и поставщиков в сборке.</span><span class="sxs-lookup"><span data-stu-id="b1eb0-110">[Writing a Windows PowerShell Snap-in](./writing-a-windows-powershell-snap-in.md): This example shows how to create a snap-in that is used to register all the cmdlets and providers in an assembly.</span></span>

<span data-ttu-id="b1eb0-111">[Написание пользовательской оснастки Windows PowerShell. в](./writing-a-custom-windows-powershell-snap-in.md)этом примере показано, как создать пользовательскую оснастку, которая будет использоваться для регистрации определенного набора командлетов и поставщиков, которые могут существовать или отсутствовать в одной сборке.</span><span class="sxs-lookup"><span data-stu-id="b1eb0-111">[Writing a Custom Windows PowerShell Snap-in](./writing-a-custom-windows-powershell-snap-in.md): This example shows how to create a custom snap-in that is used to register a specific set of cmdlets and providers that might or might not exist in a single assembly.</span></span>

## <a name="see-also"></a><span data-ttu-id="b1eb0-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="b1eb0-112">See Also</span></span>

[<span data-ttu-id="b1eb0-113">System. Management. Automation. PSSnapIn</span><span class="sxs-lookup"><span data-stu-id="b1eb0-113">System.Management.Automation.PSSnapIn</span></span>](/dotnet/api/System.Management.Automation.PSSnapIn)

[<span data-ttu-id="b1eb0-114">System. Management. Automation. Кустомпсснапин</span><span class="sxs-lookup"><span data-stu-id="b1eb0-114">System.Management.Automation.Custompssnapin</span></span>](/dotnet/api/System.Management.Automation.CustomPSSnapIn)

[<span data-ttu-id="b1eb0-115">Регистрация командлетов</span><span class="sxs-lookup"><span data-stu-id="b1eb0-115">Registering Cmdlets</span></span>](./registering-cmdlets.md)

[<span data-ttu-id="b1eb0-116">Пакет SDK оболочки Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b1eb0-116">Windows PowerShell Shell SDK</span></span>](../windows-powershell-reference.md)
