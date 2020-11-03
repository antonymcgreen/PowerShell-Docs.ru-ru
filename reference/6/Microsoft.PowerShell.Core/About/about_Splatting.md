---
description: Описывает, как использовать Сплаттинг для передачи параметров в команды в PowerShell.
keywords: powershell,командлет
Locale: en-US
ms.date: 04/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_splatting?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Splatting
ms.openlocfilehash: 7c479beffe7e424b7f880c81db7da3b4ec10d817
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231234"
---
# <a name="about-splatting"></a>О Сплаттинг

## <a name="short-description"></a>Краткое описание

Описывает, как использовать Сплаттинг для передачи параметров в команды в PowerShell.

## <a name="long-description"></a>Подробное описание

Сплаттинг — это метод передачи коллекции значений параметров в команду как единое целое. PowerShell связывает каждое значение в коллекции с параметром команды. Значения параметров сплаттед хранятся в именованных переменных Сплаттинг, которые выглядят как стандартные переменные, но начинаются с символа ( `@` ) вместо знака доллара ( `$` ). Символ at указывает PowerShell на передачу коллекции значений, а не одно значение.

Сплаттинг делает команды короче и проще в чтении. Можно повторно использовать значения сплаттинг в разных вызовах команд и использовать Сплаттинг для передачи значений параметров из `$PSBoundParameters` автоматической переменной в другие скрипты и функции.

Начиная с Windows PowerShell 3,0, можно также использовать Сплаттинг для представления всех параметров команды.

## <a name="syntax"></a>Синтаксис

```
<CommandName> <optional parameters> @<HashTable> <optional parameters>
<CommandName> <optional parameters> @<Array> <optional parameters>
```

Чтобы указать значения параметров для параметров позиционирования, в которых не требуются имена параметров, используйте синтаксис массива. Чтобы указать пары имен и значений параметров, используйте синтаксис хэш-таблицы. Значение сплаттед может находиться в любом месте в списке параметров.

При Сплаттинг не нужно использовать хэш-таблицу или массив для передачи всех параметров. Некоторые параметры можно передать с помощью Сплаттинг и передать другим по положению или имени параметра. Кроме того, можно со звездочкой несколько объектов в одной команде, чтобы для каждого параметра не передавалось больше одного значения.

## <a name="splatting-with-hash-tables"></a>Сплаттинг с хэш-таблицами

Используйте хэш-таблицу для со звездочкой пар имен и значений параметров. Этот формат можно использовать для всех типов параметров, включая параметры позиционирования и переключателя.
Позиционированные параметры должны быть назначены по имени.

В следующих примерах сравниваются две `Copy-Item` команды, которые копируют файл Test.txt в файл Test2.txt в том же каталоге.

В первом примере используется традиционный формат, в котором включены имена параметров.

```powershell
Copy-Item -Path "test.txt" -Destination "test2.txt" -WhatIf
```

Во втором примере используется хэш-таблица Сплаттинг. Первая команда создает хэш-таблицу пар "параметр-имя" и "параметр-значение" и сохраняет их в `$HashArguments` переменной. Вторая команда использует `$HashArguments` переменную в команде с параметром Сплаттинг. Символ "at" ( `@HashArguments` ) заменяет знак доллара ( `$HashArguments` ) в команде.

Чтобы указать значение параметра **WhatIf** , используйте `$True` или `$False` .

```powershell
$HashArguments = @{
  Path = "test.txt"
  Destination = "test2.txt"
  WhatIf = $true
}
Copy-Item @HashArguments
```

> [!NOTE]
> В первой команде символ at ( `@` ) указывает на хэш-таблицу, а не на значение сплаттед. Синтаксис для хэш-таблиц в PowerShell: `@{<name>=<value>; <name>=<value>; ...}`

## <a name="splatting-with-arrays"></a>Сплаттинг с массивами

Используйте массив, чтобы со звездочкой значения для параметров позиционирования, не требующих указания имен параметров. Значения должны быть в порядке порядкового номера в массиве.

В следующих примерах сравниваются две `Copy-Item` команды, которые копируют файл Test.txt в файл Test2.txt в том же каталоге.

В первом примере используется традиционный формат, в котором имена параметров опущены. Значения параметров отображаются в порядке расположения в команде.

```powershell
Copy-Item "test.txt" "test2.txt" -WhatIf
```

Во втором примере используется массив Сплаттинг. Первая команда создает массив значений параметров и сохраняет их в `$ArrayArguments` переменной. Значения находятся в порядке расположения в массиве. Вторая команда использует `$ArrayArguments` переменную в команде в Сплаттинг. Символ "at" ( `@ArrayArguments` ) заменяет знак доллара ( `$ArrayArguments` ) в команде.

```powershell
$ArrayArguments = "test.txt", "test2.txt"
Copy-Item @ArrayArguments -WhatIf
```

### <a name="using-the-argumentlist-parameter"></a>Использование параметра ArgumentList

Несколько командлетов имеют параметр **ArgumentList** , который используется для передачи значений параметров в блок сценария, выполняемый командлетом. Параметр **ArgumentList** принимает массив значений, передаваемых в блок скрипта. PowerShell эффективно использует Array Сплаттинг для привязки значений к параметрам блока script. Если при использовании **ArgumentList** необходимо передать массив как отдельный объект, привязанный к одному параметру, необходимо заключить массив в оболочку как единственный элемент другого массива.

В следующем примере имеется блок скрипта, который принимает один параметр, который является массивом строк.

```powershell
$array = 'Hello', 'World!'
Invoke-Command -ScriptBlock {
  param([string[]]$words) $words -join ' '
  } -ArgumentList $array
```

В этом примере `$array` блоку Script передается только первый элемент в.

```Output
Hello
```

```powershell
$array = 'Hello', 'World!'
Invoke-Command -ScriptBlock {
  param([string[]]$words) $words -join ' '
} -ArgumentList (,$array)
```

В этом примере `$array` переносится в массив, чтобы весь массив передавался в блок скрипта как один объект.

```Output
Hello World!
```

## <a name="examples"></a>Примеры

В этом примере показано, как повторно использовать значения сплаттед в различных командах. Команды в этом примере используют `Write-Host` командлет для записи сообщений в консоль главного приложения. Он использует Сплаттинг для указания цвета переднего плана и фона.

Чтобы изменить цвета всех команд, просто измените значение `$Colors` переменной.

Первая команда создает хэш-таблицу с именами и значениями параметров и сохраняет хэш-таблицу в `$Colors` переменной.

```powershell
$Colors = @{ForegroundColor = "black"; BackgroundColor = "white"}
```

Вторая и третья команды используют `$Colors` переменную для сплаттинг в `Write-Host` команде. Чтобы использовать `$Colors variable` , замените знак доллара ( `$Colors` ) на символ at ( `@Colors` ).

```powershell
#Write a message with the colors in $Colors
Write-Host "This is a test." @Colors

#Write second message with same colors. The position of splatted
#hash table does not matter.
Write-Host @Colors "This is another test."
```

В этом примере показано, как перенаправить свои параметры в другие команды с помощью Сплаттинг и `$PSBoundParameters` автоматической переменной.

`$PSBoundParameters`Автоматическая переменная — это объект словаря (System. Collections. Generic. Dictionary), содержащий все имена и значения параметров, которые используются при выполнении скрипта или функции.

В следующем примере мы используем `$PSBoundParameters` переменную для пересылки значений параметров, переданных в скрипт или функцию, в функцию `Test2` `Test1` . Оба вызова `Test1` функции `Test2` используют Сплаттинг.

```powershell
function Test1
{
    param($a, $b, $c)

    $a
    $b
    $c
}

function Test2
{
    param($a, $b, $c)

    #Call the Test1 function with $a, $b, and $c.
    Test1 @PsBoundParameters

    #Call the Test1 function with $b and $c, but not with $a
    $LimitedParameters = $PSBoundParameters
    $LimitedParameters.Remove("a") | Out-Null
    Test1 @LimitedParameters
}
```

```Output
Test2 -a 1 -b 2 -c 3
1
2
3
2
3
```

## <a name="splatting-command-parameters"></a>Параметры команды Сплаттинг

Сплаттинг можно использовать для представления параметров команды. Этот метод полезен при создании прокси-функции, то есть функции, которая вызывает другую команду. Эта функция появилась в Windows PowerShell 3,0.

Чтобы со звездочкой параметры команды, используйте `@Args` для представления параметров команды. Этот метод проще, чем перечислять параметры команды и работает без редакции, даже если параметры вызванной команды изменятся.

Эта функция использует `$Args` автоматическую переменную, которая содержит все значения неназначенных параметров.

Например, следующая функция вызывает `Get-Process` командлет. В этой функции `@Args` представляет все параметры `Get-Process` командлета.

```powershell
function Get-MyProcess { Get-Process @Args }
```

При использовании `Get-MyProcess` функции передаются все неназначенные параметры и значения параметров `@Args` , как показано в следующих командах.

```powershell
Get-MyProcess -Name PowerShell
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    463      46   225484     237196   719    15.86   3228 powershell
```

```powershell
Get-MyProcess -Name PowerShell_Ise -FileVersionInfo
```

```Output
ProductVersion   FileVersion      FileName
--------------   -----------      --------
6.2.9200.16384   6.2.9200.1638... C:\Windows\system32\WindowsPowerShell\...
```

Можно использовать `@Args` в функции, которая содержит явно объявленные параметры. Его можно использовать несколько раз в функции, но все введенные параметры передаются всем экземплярам `@Args` , как показано в следующем примере.

```powershell
function Get-MyCommand
{
    Param ([switch]$P, [switch]$C)
    if ($P) { Get-Process @Args }
    if ($C) { Get-Command @Args }
}

Get-MyCommand -P -C -Name PowerShell
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
408      28    75568      83176   620     1.33   1692 powershell

Path               : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.e
Extension          : .exe
Definition         : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.e
Visibility         : Public
OutputType         : {System.String}
Name               : powershell.exe
CommandType        : Application
ModuleName         :
Module             :
RemotingCapability : PowerShell
Parameters         :
ParameterSets      :
HelpUri            :
FileVersionInfo    : File:             C:\Windows\System32\WindowsPowerShell
                     \v1.0\powershell.exe
                     InternalName:     POWERSHELL
                     OriginalFilename: PowerShell.EXE.MUI
                     FileVersion:      10.0.14393.0 (rs1_release.160715-1616
                     FileDescription:  Windows PowerShell
                     Product:          Microsoft Windows Operating System
                     ProductVersion:   10.0.14393.0
                     Debug:            False
                     Patched:          False
                     PreRelease:       False
                     PrivateBuild:     False
                     SpecialBuild:     False
                     Language:         English (United States)
```

## <a name="notes"></a>Примечания

Если вы сделаете функцию в расширенной функции с помощью атрибутов **CmdletBinding** или **Parameter** , `$args` Автоматическая переменная больше не будет доступна в функции. Для расширенных функций требуется явное определение параметра.

Настройка требуемого состояния PowerShell (DSC) не была разработана для использования Сплаттинг.
Сплаттинг нельзя использовать для передачи значений в ресурс DSC. Дополнительные сведения см. в статье Гаел Колас " [псевдо-СПЛАТТИНГ DSC Resources](https://gaelcolas.com/2017/11/05/pseudo-splatting-dsc-resources/).

## <a name="see-also"></a>См. также статью

[about_Arrays](about_Arrays.md)

[about_Automatic_Variables](about_Automatic_Variables.md)

[about_Hash_Tables](about_Hash_Tables.md)

[about_Parameters](about_Parameters.md)
