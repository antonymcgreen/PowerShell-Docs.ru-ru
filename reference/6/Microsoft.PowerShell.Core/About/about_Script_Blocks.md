---
description: Определяет, что такое блок скрипта, и объясняет, как использовать блоки сценариев на языке программирования PowerShell.
keywords: powershell,командлет
Locale: en-US
ms.date: 04/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_script_blocks?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Script_Blocks
ms.openlocfilehash: dc3ee050399e92506cabed370e95d03c65652953
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231265"
---
# <a name="about-script-blocks"></a>О блоках скриптов

## <a name="short-description"></a>Краткое описание

Определяет, что такое блок скрипта, и объясняет, как использовать блоки сценариев на языке программирования PowerShell.

## <a name="long-description"></a>Подробное описание

В языке программирования PowerShell блок скрипта представляет собой коллекцию инструкций или выражений, которые можно использовать как единый блок.
Блок сценария может принимать аргументы и возвращать значения.

Синтаксический блок скрипта — это список операторов в фигурных скобках, как показано в следующем синтаксисе:

```
{<statement list>}
```

Блок скрипта возвращает выходные данные всех команд в блоке скрипта либо как один объект, либо как массив.

Также можно указать возвращаемое значение с помощью `return` ключевого слова. `return`Ключевое слово не влияет на другие выходные данные, возвращаемые блоком скрипта, и не подавляет их. Однако `return` ключевое слово завершает блок сценария в этой строке. Дополнительные сведения см. в разделе [about_Return](about_Return.md).

Как и функции, блок скрипта может включать параметры. Используйте ключевое слово Param для присвоения именованных параметров, как показано в следующем синтаксисе:

```
{
Param([type]$Parameter1 [,[type]$Parameter2])
<statement list>
}
```

> [!NOTE]
> В блоке сценария, в отличие от функции, нельзя указывать параметры за пределами фигурных скобок.

Как и функции, блоки скриптов могут содержать `DynamicParam` `Begin` `Process` Ключевые слова,, и `End` . Дополнительные сведения см. в разделе [about_Functions](about_Functions.md) и [about_Functions_Advanced](about_Functions_Advanced.md).

## <a name="using-script-blocks"></a>Использование блоков сценариев

Блок скрипта — это экземпляр Microsoft .NET типа платформы `System.Management.Automation.ScriptBlock` . Команды могут иметь значения параметров блока сценария. Например, `Invoke-Command` командлет имеет `ScriptBlock` параметр, который принимает значение блока сценария, как показано в следующем примере:

```powershell
Invoke-Command -ScriptBlock { Get-Process }
```

```Output
Handles  NPM(K)    PM(K)     WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----     ----- -----   ------     -- -----------
999          28    39100     45020   262    15.88   1844 communicator
721          28    32696     36536   222    20.84   4028 explorer
...
```

`Invoke-Command` также может выполнять блоки скриптов с блоками параметров.
Параметры присваиваются по положению с помощью параметра **ArgumentList** .

```powershell
Invoke-Command -ScriptBlock { param($p1, $p2)
"p1: $p1"
"p2: $p2"
} -ArgumentList "First", "Second"
```

```Output
p1: First
p2: Second
```

Блок скрипта в предыдущем примере использует `param` ключевое слово для создания параметров `$p1` и `$p2` . Строка "First" привязывается к первому параметру ( `$p1` ), а "Second" — к ( `$p2` ).

Дополнительные сведения о поведении **ArgumentList** см. в разделе [about_Splatting](about_Splatting.md#splatting-with-arrays).

Переменные можно использовать для хранения и выполнения блоков сценариев. В приведенном ниже примере блок скрипта сохраняется в переменной и передается в `Invoke-Command` .

```powershell
$a = { Get-Service BITS }
Invoke-Command -ScriptBlock $a
```

```Output
Status   Name               DisplayName
------   ----               -----------
Running  BITS               Background Intelligent Transfer Ser...
```

Оператор Call — это еще один способ выполнения блоков сценариев, хранящихся в переменной.
Как и `Invoke-Command` оператор Call, выполняет блок скрипта в дочерней области. Оператор Call может упростить использование параметров с блоками скриптов.

```powershell
$a ={ param($p1, $p2)
"p1: $p1"
"p2: $p2"
}
&$a -p2 "First" -p1 "Second"
```

```Output
p1: Second
p2: First
```

Выходные данные из блоков скрипта можно сохранить в переменной с помощью присваивания.

```
PS>  $a = { 1 + 1}
PS>  $b = &$a
PS>  $b
2
```

```
PS>  $a = { 1 + 1}
PS>  $b = Invoke-Command $a
PS>  $b
2
```

Дополнительные сведения о операторе Call см. в разделе [about_Operators](about_Operators.md).

## <a name="using-delay-bind-script-blocks-with-parameters"></a>Использование блоков скриптов с отложенной привязкой с параметрами

Типизированный параметр, который принимает входные данные конвейера ( `by Value` ) или ( `by PropertyName` ), позволяет использовать блоки скриптов с **отложенной привязкой** для параметра.
В блоке скрипта **с отложенной привязкой** можно ссылаться на перенаправленный объект, используя переменную конвейера `$_` .

```powershell
# Renames config.log to old_config.log
dir config.log | Rename-Item -NewName {"old_" + $_.Name}
```

В более сложных командлетах блоки скриптов с отложенной привязкой позволяют повторно использовать один из переданных объектов для заполнения других параметров.

Примечания к блокам скриптов **отложенной привязки** в качестве параметров:

- Необходимо явно указать все имена параметров, используемые с блоками скриптов **отложенной привязки** .
- Параметр не должен быть нетипизированным, а тип параметра не может быть `[scriptblock]` или `[object]` .
- Если используется блок скрипта **отложенной привязки** без предоставления входных данных конвейера, возникает ошибка.

  ```powershell
  Rename-Item -NewName {$_.Name + ".old"}
  ```

  ```Output
  Rename-Item : Cannot evaluate parameter 'NewName' because its argument is
  specified as a script block and there is no input. A script block cannot
  be evaluated without input.
  At line:1 char:23
  +  Rename-Item -NewName {$_.Name + ".old"}
  +                       ~~~~~~~~~~~~~~~~~~
      + CategoryInfo          : MetadataError: (:) [Rename-Item],
        ParameterBindingException
      + FullyQualifiedErrorId : ScriptBlockArgumentNoInput,
        Microsoft.PowerShell.Commands.RenameItemCommand
  ```

## <a name="see-also"></a>См. также:

[about_Functions](about_Functions.md)

[about_Functions_Advanced](about_Functions_Advanced.md)

[about_Operators](about_Operators.md)
