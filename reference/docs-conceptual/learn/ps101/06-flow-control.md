---
title: Управление потоком
description: PowerShell предоставляет методы создания циклов, принятия решений и логического управления потоком кода в скриптах.
ms.date: 06/02/2020
ms.custom: Contributor-mikefrobbins
ms.reviewer: mirobb
ms.openlocfilehash: 74595f8c6a5d4a49b05e72dd6bde1441fd2b464e
ms.sourcegitcommit: df5e6f032ee2d4b556d50406832732d2f7dc2502
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/14/2021
ms.locfileid: "99601475"
---
# <a name="chapter-6---flow-control"></a>Глава 6. Управление потоком

## <a name="scripting"></a>Написание сценариев

Когда вы переходите от написания однострочных элементов кода PowerShell к написанию сценариев, это может показаться намного сложнее, чем есть на самом деле. Сценарий — это всего лишь те же или похожие команды, которые вы можете запускать в интерактивном режиме в консоли PowerShell, если они не сохранены в виде файла `.PS1`. Существуют некоторые конструкции написания сценариев, которые вы можете использовать вместо командлета `ForEach-Object`, например цикл `foreach`. Эти различия могут ввести в заблуждение начинающих пользователей, особенно если они полагают, что `foreach` является конструкцией сценария и псевдонимом для командлета `ForEach-Object`.

## <a name="looping"></a>Выполнение цикла

Одно из основных преимуществ PowerShell состоит в следующем: если вы определили способ выполнения задачи для одного элемента, вы можете так же легко выполнить ее для нескольких сотен элементов. Достаточно пройтись в цикле по этим элементам, используя один из множества различных типов циклов в PowerShell.

### <a name="foreach-object"></a>ForEach-Object

`ForEach-Object` — это командлет для прохода по элементам в конвейере, например с помощью однострочных элементов кода PowerShell. `ForEach-Object` осуществляет потоковую передачу объектов по конвейеру.

Хотя параметр **Module** для `Get-Command` принимает несколько значений в виде строк, он осуществляет это только через входные данные конвейера по имени свойства или через входные данные параметра. В следующем сценарии, если мне нужно передать две строки по значению в `Get-Command` для использования с параметром **Module**, я буду использовать командлет `ForEach-Object`.

```powershell
'ActiveDirectory', 'SQLServer' |
   ForEach-Object {Get-Command -Module $_} |
     Group-Object -Property ModuleName -NoElement |
         Sort-Object -Property Count -Descending
```

```Output
Count Name
----- ----
  147 ActiveDirectory
   82 SqlServer
```

В предыдущем примере текущим объектом является `$_`. Начиная с PowerShell версии 3.0 `$PSItem` можно использовать вместо `$_`. Но я встречаюсь с тем, что самые опытные пользователи PowerShell все еще предпочитают использовать `$_`, так как он обеспечивает обратную и меньшую совместимость.

При использовании ключевого слова `foreach` вы должны сохранить все элементы в памяти, прежде чем по ним проходить, а это может быть нелегкой задачей, если не знать, с каким количеством элементов вы работаете.

```powershell
$ComputerName = 'DC01', 'WEB01'
foreach ($Computer in $ComputerName) {
  Get-ADComputer -Identity $Computer
}
```

```Output
DistinguishedName : CN=DC01,OU=Domain Controllers,DC=mikefrobbins,DC=com
DNSHostName       : dc01.mikefrobbins.com
Enabled           : True
Name              : DC01
ObjectClass       : computer
ObjectGUID        : c38da20c-a484-469d-ba4c-bab3fb71ae8e
SamAccountName    : DC01$
SID               : S-1-5-21-2989741381-570885089-3319121794-1001
UserPrincipalName :

DistinguishedName : CN=WEB01,CN=Computers,DC=mikefrobbins,DC=com
DNSHostName       : web01.mikefrobbins.com
Enabled           : True
Name              : WEB01
ObjectClass       : computer
ObjectGUID        : 33aa530e-1e31-40d8-8c78-76a18b673c33
SamAccountName    : WEB01$
SID               : S-1-5-21-2989741381-570885089-3319121794-1107
UserPrincipalName :
```

Цикл `foreach` или `ForEach-Object` нужно обязательно выполнить несколько раз, иначе вы получите сообщение об ошибке.

```powershell
Get-ADComputer -Identity 'DC01', 'WEB01'
```

```Output
Get-ADComputer : Cannot convert 'System.Object[]' to the type
'Microsoft.ActiveDirectory.Management.ADComputer' required by parameter 'Identity'.
Specified method is not supported.
At line:1 char:26
+ Get-ADComputer -Identity 'DC01', 'WEB01'
+                          ```````````````
    + CategoryInfo          : InvalidArgument: (:) [Get-ADComputer], ParameterBindingExc
   eption
    + FullyQualifiedErrorId : CannotConvertArgument,Microsoft.ActiveDirectory.Management
   .Commands.GetADComputer
```

В других случаях вы можете получить те же результаты, одновременно удаляя цикл. Чтобы разобраться с параметрами, сверьтесь со справкой по командлетам.

```powershell
'DC01', 'WEB01' | Get-ADComputer
```

```Output
DistinguishedName : CN=DC01,OU=Domain Controllers,DC=mikefrobbins,DC=com
DNSHostName       : dc01.mikefrobbins.com
Enabled           : True
Name              : DC01
ObjectClass       : computer
ObjectGUID        : c38da20c-a484-469d-ba4c-bab3fb71ae8e
SamAccountName    : DC01$
SID               : S-1-5-21-2989741381-570885089-3319121794-1001
UserPrincipalName :

DistinguishedName : CN=WEB01,CN=Computers,DC=mikefrobbins,DC=com
DNSHostName       : web01.mikefrobbins.com
Enabled           : True
Name              : WEB01
ObjectClass       : computer
ObjectGUID        : 33aa530e-1e31-40d8-8c78-76a18b673c33
SamAccountName    : WEB01$
SID               : S-1-5-21-2989741381-570885089-3319121794-1107
UserPrincipalName :
```

Как вы видите в предыдущих примерах, параметр **Identity** для `Get-ADComputer` принимает только одно значение, если оно предоставлено с помощью входных параметров, и при этом позволяет получить несколько элементов, если входные данные предоставляются через входные данные конвейера.

### <a name="for"></a>Для

Цикл `for` выполняет итерацию до тех пор, пока заданное условие имеет значение "Истина". Цикл `for` я использую редко, но все же использую.

```powershell
for ($i = 1; $i -lt 5; $i++) {
  Write-Output "Sleeping for $i seconds"
  Start-Sleep -Seconds $i
}
```

```Output
Sleeping for 1 seconds
Sleeping for 2 seconds
Sleeping for 3 seconds
Sleeping for 4 seconds
```

В предыдущем примере цикл будет повторяться четыре раза, начиная с числа 1, и продолжит выполняться до тех пор, пока переменная счетчика `$i` не составит значение менее 5. Этот цикл будет бездействовать в течение всего 10 секунд.

### <a name="do"></a>Как нужно

В PowerShell существуют два разных цикла `do`. Цикл `Do Until` выполняется до тех пор, пока заданное условие имеет значение "Ложь".

```powershell
$number = Get-Random -Minimum 1 -Maximum 10
do {
  $guess = Read-Host -Prompt "What's your guess?"
  if ($guess -lt $number) {
    Write-Output 'Too low!'
  }
  elseif ($guess -gt $number) {
    Write-Output 'Too high!'
  }
}
until ($guess -eq $number)
```

```Output
What's your guess?: 1
Too low!
What's your guess?: 2
Too low!
What's your guess?: 3
```

В предыдущем примере показана игра с цифрами, которая будет продолжаться до тех пор, пока значение, которое вы выдаете, не будет равняться тому же числу, которое было создано командлетом `Get-Random`.

Цикл `Do While` — полная противоположность. Он выполняется до тех пор, пока заданное условие не примет значение "Истина".

```powershell
$number = Get-Random -Minimum 1 -Maximum 10
do {
  $guess = Read-Host -Prompt "What's your guess?"
  if ($guess -lt $number) {
    Write-Output 'Too low!'
  } elseif ($guess -gt $number) {
    Write-Output 'Too high!'
  }
}
while ($guess -ne $number)
```

```Output
What's your guess?: 1
Too low!
What's your guess?: 2
Too low!
What's your guess?: 3
Too low!
What's your guess?: 4
```

Аналогичные результаты можно получить с помощью цикла `Do While`, изменив условие проверки на значение "Не равно".

Циклы `Do` всегда выполняются не менее одного раза, так как заданное условие вычисляется в конце цикла.

### <a name="while"></a>While

Цикл `Do While`, как и цикл `While`, выполняется до тех пор, пока заданное условие имеет значение "Истина". При этом различие состоит в том, что цикл `While` принимает условие в верхней части цикла перед выполнением любого кода. Поэтому этот цикл не выполняется, если условие принимает значение "Ложь".

```powershell
$date = Get-Date -Date 'November 22'
while ($date.DayOfWeek -ne 'Thursday') {
  $date = $date.AddDays(1)
}
Write-Output $date
```

```Output
Thursday, November 23, 2017 12:00:00 AM
```

В предыдущем примере вычисляется, на какой день недели приходится День благодарения в США. Этот день всегда приходится на четвертый четверг ноября. Поэтому цикл начинается с 22-го дня ноября и добавляет один день, когда день недели не равен четвергу. Если на 22-е число выпадает четверг, цикл не выполняется.

## <a name="break-continue-and-return"></a>Инструкции "Прервать", "Продолжить" и "Вернуть"

Инструкция `Break` используется для прерывания цикла. Кроме того, она часто используется с инструкцией `switch`.

```powershell
for ($i = 1; $i -lt 5; $i++) {
  Write-Output "Sleeping for $i seconds"
  Start-Sleep -Seconds $i
  break
}
```

```Output
Sleeping for 1 seconds
```

Инструкция `break`, показанная в предыдущем примере, приводит к выходу цикла в первой итерации.

Инструкция "Продолжить" позволяет перейти к следующей итерации цикла.

```powershell
while ($i -lt 5) {
  $i += 1
  if ($i -eq 3) {
    continue
  }
  Write-Output $i
}
```

```Output
1
2
4
5
```

В предыдущем примере выводятся числа 1, 2, 4 и 5. В нем исключается число 3 и выполняется переход к следующей итерации цикла. Инструкция `break`, как и `continue`, прерывает цикл, только если это не текущая итерация. Затем процесс переходит к следующей итерации, а не к прерыванию и остановке цикла.

Инструкция "Вернуть" позволяет выйти из существующей области.

```powershell
$number = 1..10
foreach ($n in $number) {
  if ($n -ge 4) {
    Return $n
  }
}
```

```Output
4
```

Заметьте, что в предыдущем примере при возврате выводится первый результат, а затем выполняется выход из цикла. Более подробное описание инструкции о результатах можно найти в одной из моих статей блога. [The PowerShell return keyword][]

## <a name="summary"></a>Сводка

В этой главе вы узнали о разных типах циклов, существующих в PowerShell.

## <a name="review"></a>Просмотр

1. Чем отличается командлет `ForEach-Object` от конструкции сценариев foreach?
1. В чем основное преимущество использования цикла While от цикла Do while или Do Until?
1. Как различаются инструкции "Прервать" и "Продолжить"?

## <a name="recommended-reading"></a>Рекомендуем прочесть

- [ForEach-Object][]
- [about_ForEach][]
- [about_For][]
- [about_Do][]
- [about_While][]
- [about_Break][]
- [about_Continue][]
- [about_Return][]

<!-- link references -->
[ForEach-Object]: /powershell/module/microsoft.powershell.core/foreach-object
[about_ForEach]: /powershell/module/microsoft.powershell.core/about/about_foreach
[about_For]: /powershell/module/microsoft.powershell.core/about/about_for
[about_Do]: /powershell/module/microsoft.powershell.core/about/about_do
[about_While]: /powershell/module/microsoft.powershell.core/about/about_while
[about_Break]: /powershell/module/microsoft.powershell.core/about/about_break
[about_Continue]: /powershell/module/microsoft.powershell.core/about/about_continue
[about_Return]: /powershell/module/microsoft.powershell.core/about/about_return
[The PowerShell return keyword]: https://mikefrobbins.com/2015/07/23/the-powershell-return-keyword/
