---
ms.date: 06/12/2017
keywords: wmf,powershell,установка
ms.openlocfilehash: 424e0b7a4d62fc35e5040a7e425950e887021d7e
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62085887"
---
# <a name="call-base-class-constructor"></a><span data-ttu-id="d7452-102">Вызов конструктора базовых классов</span><span class="sxs-lookup"><span data-stu-id="d7452-102">Call Base Class Constructor</span></span>

<span data-ttu-id="d7452-103">Чтобы вызвать конструктор базовых классов из подкласса, используйте ключевое слово **base**:</span><span class="sxs-lookup"><span data-stu-id="d7452-103">To call a base class constructor from a subclass, use the keyword **base**:</span></span>

```powershell
class A
{
    [int]$a

    A([int]$a)
    {
        $this.a = $a
    }
}

class B : A
{
    B() : base(103) {}
}

[B]::new().a # return 103
```

<span data-ttu-id="d7452-104">Если базовый класс имеет конструктор по умолчанию (без параметров), явный вызов конструктора можно опустить:</span><span class="sxs-lookup"><span data-stu-id="d7452-104">If a base class has a default (no parameter) constructor, you can omit an explicit constructor call:</span></span>

```powershell
class C : B
{
    C([int]$c) {}
}
```
