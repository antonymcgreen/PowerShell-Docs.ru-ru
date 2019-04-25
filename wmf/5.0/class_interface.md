---
ms.date: 06/12/2017
keywords: wmf,powershell,установка
ms.openlocfilehash: 4b593e9a1eca43ee7ad85fc921ae3c1d62722db9
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62085870"
---
# <a name="declare-implemented-interface"></a><span data-ttu-id="680ab-102">Объявление реализованного интерфейса</span><span class="sxs-lookup"><span data-stu-id="680ab-102">Declare Implemented Interface</span></span>

<span data-ttu-id="680ab-103">Реализованные интерфейсы можно объявить после базовых типов или сразу после двоеточия (:), если базовый тип не указан.</span><span class="sxs-lookup"><span data-stu-id="680ab-103">You can declare implemented interfaces after base types, or immediately after a colon (:), if there is no base type specified.</span></span> <span data-ttu-id="680ab-104">Все имена типов следует разделять запятыми.</span><span class="sxs-lookup"><span data-stu-id="680ab-104">Separate all type names by using commas.</span></span> <span data-ttu-id="680ab-105">Это очень похоже на синтаксис C#.</span><span class="sxs-lookup"><span data-stu-id="680ab-105">It’s very similar to C# syntax.</span></span>

```powershell
class MyComparable : system.IComparable
{
    [int] CompareTo([object] $obj)
    {
        return 0;
    }
}

class MyComparableBar : bar, system.IComparable
{
    [int] CompareTo([object] $obj)
    {
        return 0;
    }
}
```
