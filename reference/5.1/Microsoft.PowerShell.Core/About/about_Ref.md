---
description: Описывает создание и использование переменной ссылочного типа. Можно использовать переменные ссылочного типа, чтобы позволить функции изменять значение передаваемой ей переменной.
keywords: powershell,командлет
Locale: en-US
ms.date: 08/24/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_ref?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Ref
ms.openlocfilehash: 3d1ae1fd53e7b4e845c8df76e1826c45b32c9c72
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231966"
---
# <a name="about-ref"></a>О ссылке

## <a name="short-description"></a>Краткое описание

Описывает создание и использование переменной ссылочного типа. Можно использовать переменные ссылочного типа, чтобы позволить функции изменять значение передаваемой ей переменной.

## <a name="long-description"></a>Подробное описание

Переменные можно передавать в функции *по ссылке* или *по значению*.

При передаче переменной *по значению* передается копия данных.

В следующем примере функция изменяет значение переданной переменной. В PowerShell целочисленные типы являются типами значений, поэтому они передаются по значению.
Таким образом, значение `$var` не изменяется вне области действия функции.

```powershell
Function Test($data)
{
    $data = 3
}

$var = 10
Test -data $var
$var
```

```output
10
```

В следующем примере переменная, содержащая, `Hashtable` передается в функцию. `Hashtable` объект является типом объекта, поэтому по умолчанию он передается в функцию *по ссылке*.

При передаче переменной *по ссылке* функция может изменить данные, и это изменение сохраняется после выполнения функции.

```powershell
Function Test($data)
{
    $data.Test = "New Text"
}

$var = @{}
Test -data $var
$var
```

```output
Name                           Value
----                           -----
Test                           New Text
```

Функция добавляет новую пару "ключ-значение", которая сохраняется вне области действия функции.

### <a name="writing-functions-to-accept-reference-parameters"></a>Написание функций для принятия ссылочных параметров

Можно создать код для функций, чтобы использовать в качестве ссылки параметр, независимо от типа передаваемых данных. Для этого необходимо указать тип параметров в виде `System.Management.Automation.PSReference` или `[ref]` .

При использовании ссылок необходимо использовать `Value` свойство `System.Management.Automation.PSReference` типа для доступа к данным.

```powershell
Function Test([ref]$data)
{
    $data.Value = 3
}
```

Чтобы передать переменную в параметр, для которого требуется ссылка, необходимо ввести в качестве ссылки приведение переменной.

> [!NOTE]
> Требуются квадратные скобки и скобки.

```powershell
$var = 10
Test -data ([ref]$var)
$var
```

```output
3
```

### <a name="passing-references-to-net-methods"></a>Передача ссылок в методы .NET

Некоторые методы .NET могут потребовать передачи переменной в качестве ссылки. Если в определении метода используются ключевые слова `in` , `out` или `ref` для параметра, он принимает ссылку.

```powershell
[int] | Get-Member -Static -Name TryParse
```

```output
Name     MemberType Definition
----     ---------- ----------
TryParse Method     static bool TryParse(string s, [ref] int result)
```

`TryParse`Метод пытается выполнить синтаксический анализ строки в виде целого числа. Если метод завершается успешно, возвращается значение `$true` , а результат сохраняется в переменной, передаваемой **по ссылке**.

```
PS> $number = 0
PS> [int]::TryParse("15", ([ref]$number))
True
PS> $number
15
```

### <a name="references-and-scopes"></a>Ссылки и области

Ссылки позволяют изменять значение переменной в родительской области внутри дочерней области.

```powershell
# Create a value type variable.
$i = 0
# Create a reference type variable.
$iRef = [ref]0
# Invoke a scriptblock to attempt to change both values.
&{$i++;$iRef.Value++}
# Output the results.
"`$i = $i;`$iRef = $($iRef.Value)"
```

```output
$i = 0;$iRef = 1
```

Была изменена только переменная ссылочного типа.

## <a name="see-also"></a>См. также статью

[about_Variables](about_Variables.md)

[about_Environment_Variables](about_Environment_Variables.md)

[about_Functions](about_Functions.md)

[about_Script_Blocks](about_Script_Blocks.md)

[about_Scopes](about_scopes.md)
