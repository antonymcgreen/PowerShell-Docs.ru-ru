---
description: Описывает выход из текущей области действия, которая может быть функцией, скриптом или блоком скриптов.
keywords: powershell,командлет
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_return?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Return
ms.openlocfilehash: 3b1900d2d2f17c78c0f935bf86400af37fc7d9ec
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231278"
---
# <a name="about-return"></a>О возврате

## <a name="short-description"></a>Краткое описание

Описывает выход из текущей области действия, которая может быть функцией, скриптом или блоком скриптов.

## <a name="long-description"></a>Подробное описание

`return`Ключевое слово выполняет выход из функции, скрипта или блока скрипта. Он может использоваться для выхода из области в определенной точке, для возвращения значения или для указания на достижение конца области.

Пользователи, знакомые с языками, например C или C, \# могут использовать `return` ключевое слово, чтобы логика не выглядела явно.

В PowerShell результаты каждой инструкции возвращаются в виде выходных данных даже без оператора, содержащего `return` ключевое слово. Такие языки, как C или C \# , возвращают только значения или значения, заданные `return` ключевым словом.

> [!NOTE]
> Начиная с PowerShell 5,0, в PowerShell добавлен язык для определения классов с помощью формального синтаксиса.  В контексте класса PowerShell ничего не выводится из метода, за исключением того, что указывается `return` оператор. Дополнительные сведения о классах PowerShell можно узнать в [about_Classes](about_Classes.md).

### <a name="syntax"></a>Синтаксис

Синтаксис `return` ключевого слова выглядит следующим образом:

```
return [<expression>]
```

`return`Ключевое слово может располагаться отдельно, а за ним может следовать значение или выражение следующим образом:

```powershell
return
return $a
return (2 + $a)
```

### <a name="examples"></a>Примеры

В следующем примере `return` ключевое слово используется для выхода из функции в определенной точке, если выполняется условное выполнение. Нечетные числа не умножаются, так как `return` инструкция завершается до того, как эта инструкция может быть выполнена.

```powershell
function MultiplyEven
{
    param($number)

    if ($number % 2) { return "$number is not even" }
    $number * 2
}

1..10 | ForEach-Object {MultiplyEven -Number $_}
```

```output
1 is not even
4
3 is not even
8
5 is not even
12
7 is not even
16
9 is not even
20
```

В PowerShell значения могут возвращаться, даже если `return` ключевое слово не используется.
Возвращаются результаты каждой инструкции. Например, следующие инструкции возвращают значение `$a` переменной:

```powershell
$a
return
```

Следующая инструкция также возвращает значение `$a` :

```powershell
return $a
```

Следующий пример включает оператор, позволяющий пользователю понять, что функция выполняет вычисление:

```powershell
function calculation {
    param ($value)

    "Please wait. Working on calculation..."
    $value += 73
    return $value
}

$a = calculation 14
```

"Подождите. Работа с вычислениями... " строка не отображается. Вместо этого он присваивается `$a` переменной, как показано в следующем примере:

```
PS> $a
Please wait. Working on calculation...
87
```

И информационная строка, и результат вычисления возвращаются функцией и присваиваются `$a` переменной.

Если вы хотите отобразить сообщение в функции, начиная с PowerShell 5,0, можно использовать `Information` поток. Приведенный ниже код исправляет приведенный выше пример с помощью `Write-Information` командлета с `InformationAction` **продолжением** .

```powershell
function calculation {
    param ($value)

    Write-Information "Please wait. Working on calculation..." -InformationAction Continue
    $value += 73
    return $value
}

$a = calculation 14
```

```output
Please wait. Working on calculation...
C:\PS> $a
87
```

### <a name="return-values-and-the-pipeline"></a>Возвращаемые значения и конвейер

При возврате коллекции из блока скрипта или функции PowerShell автоматически выполняет откат элементов и передает их по одному за раз через конвейер. Это происходит из-за обработки PowerShell по одному времени. Дополнительные сведения см. в разделе [about_pipelines](about_pipelines.md).

Эта концепция показана в следующем примере функции, возвращающей массив чисел. Выходные данные функции передаются в командлет, `Measure-Object` который подсчитывает количество объектов в конвейере.

```powershell
function Test-Return
{
    $array = 1,2,3
    return $array
}
Test-Return | Measure-Object
```

```Output
Count    : 3
Average  :
Sum      :
Maximum  :
Minimum  :
Property :
```

Чтобы принудительно вернуть коллекцию в качестве одного объекта в конвейер, используйте один из следующих двух методов:

- Выражение унарного массива

  Используя унарное выражение, можно отправить возвращаемое значение вниз по конвейеру в виде одного объекта, как показано в следующем примере.

  ```powershell
  function Test-Return
  {
      $array = 1,2,3
      return (, $array)
  }
  Test-Return | Measure-Object
  ```

  ```Output
  Count    : 1
  Average  :
  Sum      :
  Maximum  :
  Minimum  :
  Property :
  ```

- `Write-Output` параметр WITH **GetEnumerator** .

  Можно также использовать `Write-Output` командлет с параметром **GetEnumerator** . В приведенном ниже примере `Measure-Object` командлет используется для подсчета объектов, отправленных в конвейер из примера функции с помощью `return` ключевого слова.

  ```powershell
  function Test-Return
  {
      $array = 1, 2, 3
      return Write-Output -NoEnumerate $array
  }

  Test-Return | Measure-Object
  ```

  ```Output
  Count    : 1
  Average  :
  Sum      :
  Maximum  :
  Minimum  :
  Property :
  ```

## <a name="see-also"></a>См. также статью

[about_Language_Keywords](about_Language_Keywords.md)

[about_Functions](about_Functions.md)

[about_Scopes](about_Scopes.md)

[about_Classes](about_Classes.md)

[Write-Information](xref:Microsoft.PowerShell.Utility.Write-Information)

[about_Script_Blocks](about_Script_Blocks.md)
