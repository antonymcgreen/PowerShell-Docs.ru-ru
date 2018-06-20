---
ms.date: 06/12/2017
keywords: wmf,powershell,установка
ms.openlocfilehash: 116f79a95126d0a1c579a95ec99eb5d8b75cc1e0
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2018
ms.locfileid: "34225493"
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
