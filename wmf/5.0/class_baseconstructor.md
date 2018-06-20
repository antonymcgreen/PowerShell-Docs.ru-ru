---
ms.date: 06/12/2017
keywords: wmf,powershell,установка
ms.openlocfilehash: 9486fdbaeca66c83551564c76ce47482f77c36b9
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2018
ms.locfileid: "34225612"
---
# <a name="call-base-class-constructor"></a>Вызов конструктора базовых классов

Чтобы вызвать конструктор базовых классов из подкласса, используйте ключевое слово **base**:

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

Если базовый класс имеет конструктор по умолчанию (без параметров), явный вызов конструктора можно опустить:

```powershell
class C : B
{
    C([int]$c) {}
}
```
