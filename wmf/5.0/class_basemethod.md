---
ms.date: 06/12/2017
keywords: wmf,powershell,установка
ms.openlocfilehash: 0e79127faf3f9bf6fe7d525db5bb946daf3b93e1
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62058630"
---
# <a name="call-base-class-method"></a><span data-ttu-id="25176-102">Вызов метода базового класса</span><span class="sxs-lookup"><span data-stu-id="25176-102">Call Base Class Method</span></span>

<span data-ttu-id="25176-103">Можно переопределить существующие методы в подклассах.</span><span class="sxs-lookup"><span data-stu-id="25176-103">You can override existing methods in subclasses.</span></span> <span data-ttu-id="25176-104">Для этого объявите методы, используя те же имя и сигнатуру:</span><span class="sxs-lookup"><span data-stu-id="25176-104">To do this, declare methods by using the same name and signature:</span></span>

```powershell
class baseClass
{
    [int]foo() {return 100500}
}

class childClass1 : baseClass
{
    [int]foo() {return 200600}
}

[childClass1]::new().foo() # return 200600
```

<span data-ttu-id="25176-105">Для вызова методов базового класса из переопределенных реализаций, выполните приведение к базовому классу ([baseClass]$this) при вызове:</span><span class="sxs-lookup"><span data-stu-id="25176-105">To call base class methods from overridden implementations, cast to the base class ([baseClass]$this) on invocation:</span></span>

```powershell
class childClass2 : baseClass
{
    [int]foo()
    {
        return 3 * ([baseClass]$this).foo()
    }
}

[childClass2]::new().foo() # return 301500
```

<span data-ttu-id="25176-106">Все методы PowerShell являются виртуальными.</span><span class="sxs-lookup"><span data-stu-id="25176-106">All PowerShell methods are virtual.</span></span> <span data-ttu-id="25176-107">Можно скрыть невиртуальные методы .NET в подклассе, используя тот же синтаксис, что и для переопределения: просто объявите методы, используя те же имя и сигнатуру:</span><span class="sxs-lookup"><span data-stu-id="25176-107">You can hide non-virtual .NET methods in a subclass by using the same syntax as you do for an override: just declare methods with same name and signature.</span></span>

```powershell
class MyIntList : system.collections.generic.list[int]
{
    # Add is final in system.collections.generic.list
    [void] Add([int]$arg)
    {
        ([system.collections.generic.list[int]]$this).Add($arg * 2)
    }
}

$list = [MyIntList]::new()
$list.Add(100)
$list[0] # return 200
```
