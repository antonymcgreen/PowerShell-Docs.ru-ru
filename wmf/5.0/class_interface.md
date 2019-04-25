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
# <a name="declare-implemented-interface"></a>Объявление реализованного интерфейса

Реализованные интерфейсы можно объявить после базовых типов или сразу после двоеточия (:), если базовый тип не указан. Все имена типов следует разделять запятыми. Это очень похоже на синтаксис C#.

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
