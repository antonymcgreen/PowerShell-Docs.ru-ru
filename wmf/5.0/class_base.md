---
ms.date: 06/12/2017
keywords: wmf,powershell,установка
ms.openlocfilehash: 8b3ebd22e03bf9bdd5f26965137a1b1ce9f47c3e
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62058783"
---
# <a name="declare-base-class"></a><span data-ttu-id="a713f-102">Объявление базового класса</span><span class="sxs-lookup"><span data-stu-id="a713f-102">Declare Base Class</span></span>
<span data-ttu-id="a713f-103">Класс можно объявить Windows PowerShell в качестве базового типа для другого класса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a713f-103">You can declare a Windows PowerShell class as a base type for another Windows PowerShell class.</span></span>

```powershell
class bar
{
   [int]foo()
       {
           return 100500
       }
}

class baz : bar {}

[baz]::new().foo() # return 100500
```

<span data-ttu-id="a713f-104">Кроме того, можно использовать существующие типы .NET Framework в качестве базовых классов:</span><span class="sxs-lookup"><span data-stu-id="a713f-104">You can also use existing .NET Framework types as base classes:</span></span>

```powershell
class MyIntList : system.collections.generic.list[int]
{

}

$list = [MyIntList]::new()

$list.Add(100)

$list[0] # return 100
```
