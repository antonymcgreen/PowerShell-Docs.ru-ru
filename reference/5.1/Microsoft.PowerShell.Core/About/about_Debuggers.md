---
description: Описывает отладчик PowerShell.
keywords: powershell,командлет
Locale: en-US
ms.date: 08/06/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_debuggers?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Debuggers
ms.openlocfilehash: d3353a9c684091b17f496e15f1553c860d26e973
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93232434"
---
# <a name="about-debuggers"></a>О отладчиках

## <a name="short-description"></a>КРАТКОЕ ОПИСАНИЕ
Описывает отладчик PowerShell.

## <a name="long-description"></a>ПОДРОБНОЕ ОПИСАНИЕ

Отладка — это процесс проверки сценария во время его выполнения для обнаружения и исправления ошибок в инструкциях сценария. Отладчик PowerShell помогает исследовать и выявление ошибок и неэффективности в скриптах, функциях, командах, рабочих процессах PowerShell, конфигурациях PowerShell или в выражениях.

Начиная с PowerShell 5,0, отладчик PowerShell был обновлен для отладки скриптов, функций, рабочих процессов, команд, конфигураций или выражений, которые выполняются в консоли или интегрированной среде сценариев Windows PowerShell на удаленных компьютерах. Вы можете запустить `Enter-PSSession` Интерактивный удаленный сеанс PowerShell, в котором можно задать точки останова и выполнять отладку файлов сценариев и команд на удаленном компьютере. `Enter-PSSession` Обновлены функциональные возможности, которые позволяют повторно подключиться к и ввести отключенный сеанс, выполняющий сценарий или команду на удаленном компьютере. Если выполняемый скрипт достигает точки останова, ваш сеанс клиента автоматически запускает отладчик. Если отключенный сеанс, в котором выполняется скрипт, уже вызвал точку останова и остановлен в точке останова, `Enter-PSSession` автоматически запускает отладчик командной строки после повторного подключения к сеансу.

Отладчик PowerShell можно также использовать для отладки рабочих процессов PowerShell в консоли PowerShell или в интегрированной среде сценариев Windows PowerShell. Начиная с PowerShell 5,0 можно выполнять отладку в выполняющихся заданиях или процессах либо локально, либо удаленно.

Вы можете использовать функции отладчика PowerShell для проверки сценария, функции, команды, рабочего процесса или выражения PowerShell во время работы. Отладчик PowerShell включает набор командлетов, позволяющих задавать точки останова, управлять точками останова и просматривать стек вызовов.

## <a name="debugger-cmdlets"></a>Командлеты отладчика

Отладчик PowerShell включает следующий набор командлетов:

- `Set-PSBreakpoint`: Задает точки останова в строках, переменных и командах.
- `Get-PSBreakpoint`: Возвращает точки останова в текущем сеансе.
- `Disable-PSBreakpoint`: Отключает точки останова в текущем сеансе.
- `Enable-PSBreakpoint`: Повторное включение точек останова в текущем сеансе.
- `Remove-PSBreakpoint`: Удаляет точки останова из текущего сеанса.
- `Get-PSCallStack`: Отображает текущий стек вызовов.

## <a name="starting-and-stopping-the-debugger"></a>Запуск и остановка отладчика

Чтобы запустить отладчик, задайте одну или несколько точек останова. Затем запустите скрипт, команду или функцию, которые требуется отладить.

При достижении точки останова выполнение останавливается и управление передается отладчику.

Чтобы завершить работу отладчика, выполните сценарий, команду или функцию, пока она не будет завершена. Или введите `stop` или `t` .

### <a name="debugger-commands"></a>Команды отладчика

При использовании отладчика в консоли PowerShell используйте следующие команды для управления выполнением. В интегрированной среде сценариев Windows PowerShell используйте команды в меню Отладка.

Примечание. сведения об использовании отладчика в других ведущих приложениях см. в документации по ведущему приложению.

- `s`, `StepInto` : Выполняет следующий оператор, а затем останавливается.

- `v`, `StepOver` : Выполняет следующий оператор, но пропускает функции и вызовы. Пропущенные операторы выполняются, но в них отладчик не останавливается.

- `Ctrl+Break`(Разбейте все в ISE) на выполнение сценария в консоли PowerShell или ИНТЕГРИРОВАНной среде сценариев Windows PowerShell. Обратите <kbd>Ctrl</kbd>внимание, что + <kbd>разрыв</kbd> CTRL в Windows PowerShell 2,0, 3,0 и 4,0 закрывает программу. Прерывать все работает как с локальными, так и с удаленными интерактивными сценариями.

- `o`, `StepOut` : Действия из текущей функции; на один уровень вверх при вложении. Если в основном тексте, он переходит к концу или следующей точке останова. Пропущенные операторы выполняются, но в них отладчик не останавливается.

- `c`, `Continue` : Продолжит работу до завершения скрипта или до достижения следующей точки останова. Пропущенные операторы выполняются, но в них отладчик не останавливается.

- `l`, `List` : Отображает часть скрипта, который исполняется. По умолчанию отображается текущая строка, пять предыдущих строк и 10 последующих строк.
  Чтобы продолжить составление списка сценариев, нажмите клавишу ВВОД.

- `l <m>`, `List` : Отображает 16 строк сценария, начиная с номера строки, заданного параметром `<m>` .

- `l <m> <n>`, `List` : Отображает `<n>` строки скрипта, начиная с номера строки, заданного параметром `<m>` .

- `q`, `Stop` , `Exit` : Останавливает выполнение скрипта и завершает работу отладчика. Если выполняется отладка задания с помощью `Debug-Job` командлета, `Exit` команда отсоединяет отладчик и позволяет продолжить выполнение задания.

- `k`, `Get-PsCallStack` : Отображает текущий стек вызовов.

- `<Enter>`: Повторяет последнюю команду, если она была на шаге (-ов), Степовер (v) или List (l). В противном случае представляет действие отправки.

- `?`, `h` : Отображает справку по командам отладчика.

Чтобы выйти из отладчика, можно использовать команду «прекратить» (q).

Начиная с PowerShell 5,0 можно выполнить команду Exit, чтобы выйти из вложенного сеанса отладки, запущенного с помощью команды `Debug-Job` или `Debug-Runspace` .

С помощью этих команд отладчика можно выполнять сценарий, останавливаться на определенном этапе, проверять значения переменных и состояния системы и продолжать выполнение сценария до тех пор, пока не будет выявлена проблема.

Примечание. при переходе к оператору с оператором перенаправления, например ">", отладчик PowerShell выполняет шаг над всеми остальными инструкциями в скрипте.

Отображение значений переменных скрипта

В отладчике можно также вводить команды, отображать значения переменных, использовать командлеты и выполнять сценарии в командной строке.

Можно отобразить текущее значение всех переменных в отлаживаемом скрипте, за исключением следующих автоматических переменных:

```powershell
$_
$Args
$Input
$MyInvocation
$PSBoundParameters
```

При попытке отобразить значение любой из этих переменных отображается значение переменной из внутреннего конвейера отладчика, а не переменной в сценарии.

Чтобы отобразить значения этих переменных для отлаживаемого скрипта, в скрипте присвойте значение автоматически изменяемой переменной новой переменной. Затем можно отобразить значение новой переменной.

Например, примененная к объекту директива

```powershell
$scriptArgs = $Args
$scriptArgs
```

В примере в этом разделе значение `$MyInvocation` переменной переназначается следующим образом:

```powershell
$scriptname = $MyInvocation.MyCommand.Path
```

## <a name="the-debugger-environment"></a>Среда отладчика

При достижении точки останова вы вводите среду отладчика. Командная строка изменится так, чтобы она начиналась с "[DBG]:". При отладке рабочего процесса выводится запрос «[ВФДБГ]». Вы можете настроить запрос.

Дополнительные сведения о настройке командной строки см. в разделе [about_Prompts](about_prompts.md).

Кроме того, в некоторых ведущих приложениях, таких как консоль PowerShell (но не в интегрированной среде сценариев Windows PowerShell [ISE]), для отладки открывается вложенный запрос. Вложенные запросы можно обнаружить по повторяющимся символам "больше чем" (ASCII 62), которые отображаются в командной строке.

Например, в консоли PowerShell по умолчанию используется следующая строка отладки:

```
[DBG]: PS (get-location)>>>
```

Уровень вложенности можно найти с помощью `$NestedPromptLevel` автоматической переменной.

Кроме того, `$PSDebugContext` в локальной области определена автоматическая переменная,. Наличие переменной можно использовать `$PsDebugContext` для определения того, находится ли вы в отладчике.

Пример:

```powershell
if ($PSDebugContext) {"Debugging"} else {"Not Debugging"}
```

Значение переменной можно использовать `$PSDebugContext` в отладке.

```
[DBG]: PS>>> $PSDebugContext.InvocationInfo

Name   CommandLineParameters  UnboundArguments  Location
----   ---------------------  ----------------  --------
=      {}                     {}                C:\ps-test\vote.ps1 (1)
```

## <a name="debugging-and-scope"></a>Отладка и область

Переход в отладчик не влияет на область, в которой работает, но при достижении точки останова в скрипте вы переходите в область скрипта. Область скрипта является дочерней для области, в которой запущен отладчик.

Чтобы найти переменные и псевдонимы, определенные в области скрипта, используйте параметр scope `Get-Alias` `Get-Variable` командлета или.

Например, следующая команда получает переменные в локальной области (скрипт):

```powershell
Get-Variable -scope 0
```

Вы можете сократить команду следующим образом:

```powershell
gv -s 0
```

Это удобный способ просмотра только переменных, определенных в скрипте и определенных во время отладки.

Отладка в командной строке

При установке точки останова переменной или точки останова команды можно задать точку останова только в файле скрипта. Однако по умолчанию точка останова устанавливается для любого, который выполняется в текущем сеансе.

Например, если задать точку останова в `$name` переменной, отладчик остановится на любой `$name` переменной в любом скрипте, команде, функции, командлете или выражении, которое выполняется до отключения или удаления точки останова.

Это позволяет выполнять отладку скриптов в более реалистичном контексте, в котором они могут зависеть от функций, переменных и других сценариев в сеансе и в профиле пользователя.

Точки останова строки зависят от файлов скриптов, поэтому они задаются только в файлах скриптов.

## <a name="debugging-workflows"></a>Отладка рабочих процессов

Отладчик PowerShell 4,0 можно использовать для отладки рабочих процессов PowerShell либо в консоли PowerShell, либо в интегрированной среде сценариев Windows PowerShell. Существуют некоторые ограничения на отладку рабочих процессов с помощью отладчика PowerShell.

- Переменные рабочего процесса можно просмотреть в отладчике, но Установка переменных рабочего процесса из отладчика не поддерживается.
- Заполнение клавишей TAB при остановке в отладчике рабочих процессов недоступно.
- Отладка рабочих процессов работает только с синхронным запуском рабочих процессов из сценария PowerShell. Вы не можете отлаживать рабочие процессы, если они выполняются как задания (с параметром **AsJob** ).
- Другие вложенные сценарии отладки, такие как рабочий процесс, вызывающий другой рабочий процесс или рабочий процесс, вызывающий скрипт, не реализуются.

В следующем примере демонстрируется отладка рабочего процесса. Когда отладчик переходит к функции рабочего процесса, запрос отладчика изменится на "[ВФДБГ]".

```powershell
PS C:> Set-PSBreakpoint -Script C:\TestWFDemo1.ps1 -Line 8

ID Script           Line Command    Variable     Action
-- ------           ---- -------    --------     ------
0 TestWFDemo1.ps1   8

PS C:> C:\TestWFDemo1.ps1
Entering debug mode. Use h or ? for help.

Hit Line breakpoint on 'C:\TestWFDemo1.ps1:8'

At C:\TestWFDemo1.ps1:8 char:5
+     Write-Output -InputObject "Now writing output:"
# +!INCLUDE[]~~~~~

[WFDBG:localhost]: PS C:>> list

# 3:

4:  workflow SampleWorkflowTest
5:  {
6:      param ($MyOutput)
# 7:

8:*     Write-Output -InputObject "Now writing output:"
9:      Write-Output -Input $MyOutput
# 10:

11:      Write-Output -InputObject "Get PowerShell process:"
12:      Get-Process -Name powershell
# 13:

14:      Write-Output -InputObject "Workflow function complete."
15:  }
# 16:

17:  # Call workflow function
18:  SampleWorkflowTest -MyOutput "Hello"

[WFDBG:localhost]: PS C:>> $MyOutput
Hello
[WFDBG:localhost]: PS C:>> stepOver
Now writing output:
At C:\TestWFDemo1.ps1:9 char:5
+     Write-Output -Input $MyOutput
# +!INCLUDE[]~

[WFDBG:localhost]: PS C:>> list

4:  workflow SampleWorkflowTest
5:  {
6:      param ($MyOutput)
# 7:

8:      Write-Output -InputObject "Now writing output:"
9:*     Write-Output -Input $MyOutput
# 10:

11:      Write-Output -InputObject "Get PowerShell process:"
12:      Get-Process -Name powershell
# 13:

14:      Write-Output -InputObject "Workflow function complete."
15:  }
# 16:

17:  # Call workflow function
18:  SampleWorkflowTest -MyOutput "Hello"
# 19:


[WFDBG:localhost]: PS C:>> stepOver
Hello
At C:\TestWFDemo1.ps1:11 char:5
+     Write-Output -InputObject "Get PowerShell process:"
# +!INCLUDE[]~~~~~~~~~

[WFDBG:localhost]: PS C:>> stepOut
Get PowerShell process:

Handles  NPM(K)    PM(K)    WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----    ----- -----   ------     -- -----------
    433      35   106688   128392   726     2.67   7124 powershell
    499      44   134244   172096   787     2.79   7452 powershell

Workflow function complete.
```

## <a name="debugging-functions"></a>Функции отладки

При установке точки останова в функции, которая содержит `Begin` `Process` разделы, и `End` , отладчик прерывает выполнение в первой строке каждого раздела.

Пример:

```powershell
function test-cmdlet {
    begin {
        write-output "Begin"
    }
    process {
        write-output "Process"
    }
    end {
        write-output "End"
    }
}

C:\PS> Set-PSBreakpoint -command test-cmdlet

C:\PS> test-cmdlet

Begin
Entering debug mode. Use h or ? for help.

Hit Command breakpoint on 'prompt:test-cmdlet'

test-cmdlet

[DBG]: C:\PS> c
Process
Entering debug mode. Use h or ? for help.

Hit Command breakpoint on 'prompt:test-cmdlet'

test-cmdlet

[DBG]: C:\PS> c
End
Entering debug mode. Use h or ? for help.

Hit Command breakpoint on 'prompt:test-cmdlet'

test-cmdlet

# [DBG]: C:\PS>
```

## <a name="debugging-remote-scripts"></a>Отладка удаленных скриптов

Начиная с PowerShell 5,0 можно запустить отладчик PowerShell в удаленном сеансе, в консоли или в интегрированной среде сценариев Windows PowerShell.
`Enter-PSSession` были обновлены функциональные возможности для повторного подключения к и входа в отключенный сеанс, запущенный на удаленном компьютере, и в данный момент выполняется сценарий. Если выполняемый скрипт достигает точки останова, ваш сеанс клиента автоматически запускает отладчик.

Ниже приведен пример, в котором показано, как это работает, с точками останова, заданными в скрипте в строках 6, 11, 22 и 25. Обратите внимание, что в примере при запуске отладчика есть два идентифицирующих приглашения: имя компьютера, на котором выполняется сеанс, и запрос DBG, который позволяет убедиться в том, что вы работаете в режиме отладки.

```powershell
Enter-Pssession -Cn localhost
[localhost]: PS C:\psscripts> Set-PSBreakpoint .\ttest19.ps1 6,11,22,25

ID Script          Line     Command          Variable          Action
-- ------          ----     -------          --------          ------
0 ttest19.ps1          6
1 ttest19.ps1          11
2 ttest19.ps1          22
3 ttest19.ps1          25

[localhost]: PS C:\psscripts> .\ttest19.ps1
Hit Line breakpoint on 'C:\psscripts\ttest19.ps1:11'

At C:\psscripts\ttest19.ps1:11 char:1
+ $winRMName = "WinRM"
# + ~

[localhost]: [DBG]: PS C:\psscripts>> list

6:      1..5 | foreach { sleep 1; Write-Output "hello2day $_" }
7:  }
# 8:

9:  $count = 10
10:  $psName = "PowerShell"
11:* $winRMName = "WinRM"
12:  $myVar = 102
# 13:

14:  for ($i=0; $i -lt $count; $i++)
15:  {
16:      sleep 1
17:      Write-Output "Loop iteration is: $i"
18:      Write-Output "MyVar is $myVar"
# 19:

20:      hello2day
# 21:


[localhost]: [DBG]: PS C:\psscripts>> stepover
At C:\psscripts\ttest19.ps1:12 char:1
+ $myVar = 102
# + ~

[localhost]: [DBG]: PS C:\psscripts>> quit
[localhost]: PS C:\psscripts> Exit-PSSession
PS C:\psscripts>
```

## <a name="examples"></a>Примеры

Этот сценарий тестирования обнаруживает версию операционной системы и отображает сообщение, соответствующее системе. Он включает функцию, вызов функции и переменную.

Следующая команда отображает содержимое файла скрипта теста:

```powershell
PS C:\PS-test>  Get-Content test.ps1

function psversion {
  "PowerShell " + $PSVersionTable.PSVersion
  if ($PSVersionTable.PSVersion.Major -lt 6) {
    "Upgrade to PowerShell 6.0!"
  }
  else {
    "Have you run a background job today (start-job)?"
  }
}

$scriptName = $MyInvocation.MyCommand.Path
psversion
"Done $scriptName."
```

Для начала установите точку останова в определенном месте скрипта, например в строке, команде, переменной или функции.

Начните с создания точки останова строки в первой строке скрипта Test.ps1 в текущем каталоге.

```powershell
PS C:\ps-test> Set-PSBreakpoint -line 1 -script test.ps1
```

Данную команду можно сократить следующим образом:

```powershell
PS C:\ps-test> spb 1 -s test.ps1
```

Команда возвращает объект точки останова строки ( **System. Management. Automation. линебреакпоинт** ).

```
Column     : 0
Line       : 1
Action     :
Enabled    : True
HitCount   : 0
Id         : 0
Script     : C:\ps-test\test.ps1
ScriptName : C:\ps-test\test.ps1
```

Теперь запустите сценарий.

```powershell
PS C:\ps-test> .\test.ps1
```

Когда скрипт достигает первой точки останова, сообщение точки останова указывает на то, что отладчик активен. Он описывает точку останова и предварительный просмотр первой строки скрипта, которая является объявлением функции. Командная строка также изменится, указывая, что отладчик имеет элемент управления.

В строке предварительного просмотра содержится имя скрипта и номер строки предварительно просматриваемой команды.

```powershell
Entering debug mode. Use h or ? for help.

Hit Line breakpoint on 'C:\ps-test\test.ps1:1'

test.ps1:1   function psversion {
# DBG>
```

Используйте команды step, чтобы выполнить первый оператор в скрипте и просмотреть следующий оператор. Следующая инструкция использует `$MyInvocation` автоматическую переменную, чтобы установить значение `$scriptName` переменной в качестве пути и имени файла скрипта.

```powershell
DBG> s
test.ps1:11  $scriptName = $MyInvocation.MyCommand.Path
```

На этом этапе `$scriptName` переменная не заполняется, но можно проверить значение переменной, отображая ее значение. В этом случае используется значение `$null`.

```powershell
DBG> $scriptname
# DBG>
```

Используйте другие команды шага для выполнения текущей инструкции и предварительного просмотра следующей инструкции в скрипте. Следующий оператор вызывает функцию PsVersion.

```powershell
DBG> s
test.ps1:12  psversion
```

На этом этапе `$scriptName` переменная заполняется, но значение переменной проверяется путем отображения ее значения. В этом случае в качестве значения задается путь к скрипту.

```powershell
DBG> $scriptName
C:\ps-test\test.ps1
```

Используйте другую команду Step для выполнения вызова функции. Нажмите клавишу ВВОД или введите "s" для шага.

```powershell
DBG> s
test.ps1:2       "PowerShell " + $PSVersionTable.PSVersion
```

Сообщение отладки содержит предварительную версию инструкции в функции. Чтобы выполнить эту инструкцию и предварительно просмотреть следующий оператор в функции, можно использовать `Step` команду. Но в этом случае используйте команду шага (o). Она завершает выполнение функции (если она не достигает точки останова) и переходит к следующему оператору в скрипте.

```powershell
DBG> o
Windows PowerShell 2.0
Have you run a background job today (start-job)?
test.ps1:13  "Done $scriptName"
```

Так как мы работаем с последней инструкцией в сценарии, команды шаг, шаг с заходом и продолжить имеют одинаковый результат. В этом случае используйте шаг (o).

```powershell
Done C:\ps-test\test.ps1
PS C:\ps-test>
```

Команда Step by выполняет последнюю команду. Стандартная командная строка указывает, что отладчик завершил работу и вернул управление обработчику команд.

Теперь снова запустите отладчик. Прежде всего, чтобы удалить текущую точку останова, `Get-PsBreakpoint` Используйте `Remove-PsBreakpoint` командлеты и. (Если вы считаете, что вы можете повторно использовать точку останова, используйте `Disable-PsBreakpoint` командлет вместо `Remove-PsBreakpoint` .)

```powershell
PS C:\ps-test> Get-PSBreakpoint| Remove-PSBreakpoint
```

Данную команду можно сократить следующим образом:

```powershell
PS C:\ps-test> gbp | rbp
```

Или выполните команду, написав функцию, например следующую:

```powershell
function delbr { gbp | rbp }
```

Теперь создайте точку останова для `$scriptname` переменной.

```powershell
PS C:\ps-test> Set-PSBreakpoint -variable scriptname -script test.ps1
```

Вы можете сократить команду следующим образом:

```powershell
PS C:\ps-test> sbp -v scriptname -s test.ps1
```

Теперь запустите сценарий. Скрипт достигает точки останова переменной. Режимом по умолчанию является Write, поэтому выполнение останавливается непосредственно перед инструкцией, которая изменяет значение переменной.

```powershell
PS C:\ps-test> .\test.ps1
Hit Variable breakpoint on 'C:\ps-test\test.ps1:$scriptName'
(Write access)

test.ps1:11  $scriptName = $MyInvocation.MyCommand.Path
# DBG>
```

Отображает текущее значение `$scriptName` переменной, то есть `$null` .

```powershell
DBG> $scriptName
# DBG>
```

Используйте команды шага для выполнения инструкции, заполняющей переменную.
Затем отобразится новое значение `$scriptName` переменной.

```powershell
DBG> $scriptName
C:\ps-test\test.ps1
```powershell

Use a Step command (s) to preview the next statement in the script.

```powershell
DBG> s
test.ps1:12  psversion
```

Следующий оператор является вызовом функции PsVersion. Чтобы пропустить функцию, но по-прежнему выполнить ее, используйте команду Степовер (v). Если вы уже используете функцию Степовер, она не действует. Вызов функции отображается, но не выполняется.

```powershell
DBG> v
Windows PowerShell 2.0
Have you run a background job today (start-job)?
test.ps1:13  "Done $scriptName"
```

Команда Степовер выполняет функцию и просматривает следующий оператор в скрипте, который выводит последнюю строку.

Чтобы выйти из отладчика, используйте команду "прекратить" (t). Командная строка вернется в стандартную командную строку.

```powershell
C:\ps-test>
```

Чтобы удалить точки останова, используйте `Get-PsBreakpoint` `Remove-PsBreakpoint` командлеты и.

```powershell
PS C:\ps-test> Get-PSBreakpoint| Remove-PSBreakpoint
```

Создайте новую точку останова команды в функции PsVersion.

```powershell
PS C:\ps-test> Set-PSBreakpoint -command psversion -script test.ps1
```

Эту команду можно сократить, чтобы:

```powershell
PS C:\ps-test> sbp -c psversion -s test.ps1
```

Теперь запустите сценарий.

```powershell
PS C:\ps-test> .\test.ps1
Hit Command breakpoint on 'C:\ps-test\test.ps1:psversion'

test.ps1:12  psversion
# DBG>
```

Скрипт достигает точки останова при вызове функции. На этом этапе функция еще не вызывалась. Это дает возможность использовать параметр Action в, `Set-PSBreakpoint` чтобы задать условия для выполнения точки останова или выполнить подготовительные или диагностические задачи, такие как запуск журнала или вызов диагностического скрипта или сценария безопасности.

Чтобы задать действие, используйте команду Continue (c), чтобы выйти из скрипта, и `Remove-PsBreakpoint` команду, чтобы удалить текущую точку останова. (Точки останова доступны только для чтения, поэтому нельзя добавить действие в текущую точку останова.)

```powershell
DBG> c
Windows PowerShell 2.0
Have you run a background job today (start-job)?
Done C:\ps-test\test.ps1

PS C:\ps-test> Get-PSBreakpoint| Remove-PSBreakpoint
PS C:\ps-test>
```

Теперь создайте новую точку останова команды с действием. Следующая команда задает точку останова команды с действием, которое регистрирует значение `$scriptName` переменной при вызове функции. Поскольку ключевое слово Break не используется в действии, выполнение не останавливается. (Обратная кавычка (') — это символ продолжения строки.)

```powershell
PS C:\ps-test> Set-PSBreakpoint -command psversion -script test.ps1  `
-action { add-content "The value of `$scriptName is $scriptName." `
-path action.log}
```

Можно также добавить действия, задаваемые в качестве условий для точки останова. В следующей команде точка останова команды выполняется только в том случае, если для политики выполнения задано значение RemoteSigned, наиболее ограниченная политика, которая по-прежнему позволяет выполнять сценарии. (Обратная кавычка (') — это символ продолжения.)

```powershell
PS C:\ps-test> Set-PSBreakpoint -script test.ps1 -command psversion `
-action { if ((Get-ExecutionPolicy) -eq "RemoteSigned") { break }}
```

Ключевое слово Break в действии направляет отладчик для выполнения точки останова.
Можно также использовать ключевое слово Continue, чтобы направить отладчик для выполнения без нарушения. Так как ключевое слово default продолжает выполняться, необходимо указать Break, чтобы остановить выполнение.

Теперь запустите сценарий.

```powershell
PS C:\ps-test> .\test.ps1
Hit Command breakpoint on 'C:\ps-test\test.ps1:psversion'

test.ps1:12  psversion
```

Так как для политики выполнения задано значение **RemoteSigned** , выполнение останавливается при вызове функции.

На этом этапе может потребоваться проверить стек вызовов. Используйте `Get-PsCallStack` командлет или `Get-PsCallStack` команду отладчика (k). Следующая команда возвращает текущий стек вызовов.

```powershell
DBG> k
2: prompt
1: .\test.ps1: $args=[]
0: prompt: $args=[]
```

В этом примере демонстрируется лишь несколько способов использования отладчика PowerShell.

Чтобы получить дополнительные сведения о командлетах отладчика, введите следующую команду:

```powershell
help <cmdlet-name> -full
```

Например, введите:

```powershell
help Set-PSBreakpoint -full
```

## <a name="other-debugging-features-in-powershell"></a>Другие функции отладки в PowerShell

Помимо отладчика PowerShell, в PowerShell есть несколько других функций, которые можно использовать для отладки скриптов и функций.

- Интегрированная среда сценариев Windows PowerShell включает в себя интерактивный графический отладчик. Для получения дополнительных сведений запустите интегрированную среду сценариев Windows PowerShell и нажмите клавишу F1.

- `Set-PSDebug`Командлет предлагает самые базовые функции отладки скриптов, включая пошаговое выполнение и трассировку.

- Используйте `Set-StrictMode` командлет, чтобы обнаружить ссылки на неинициализированные переменные, ссылки на несуществующие свойства объекта и на недопустимый синтаксис функции.

- Добавьте в скрипт диагностические инструкции, например инструкции, отображающие значения переменных, инструкции, считывающие входные данные из командной строки, или инструкции, сообщающие о текущей инструкции. Используйте командлеты, которые содержат команду записи для этой задачи, например `Write-Host` ,, `Write-Debug` `Write-Warning` и `Write-Verbose` .

## <a name="see-also"></a>СМ. ТАКЖЕ

- [Disable-PSBreakpoint](xref:Microsoft.PowerShell.Utility.Disable-PSBreakpoint)
- [Enable-PSBreakpoint](xref:Microsoft.PowerShell.Utility.Enable-PSBreakpoint)
- [Get-PSBreakpoint](xref:Microsoft.PowerShell.Utility.Get-PSBreakpoint)
- [Get-PSCallStack](xref:Microsoft.PowerShell.Utility.Get-PSCallStack)
- [Remove-PSBreakpoint](xref:Microsoft.PowerShell.Utility.Remove-PSBreakpoint)
- [Set-PSBreakpoint](xref:Microsoft.PowerShell.Utility.Set-PSBreakpoint)
- [Write-Debug](xref:Microsoft.PowerShell.Utility.Write-Debug)
- [Write-Verbose](xref:Microsoft.PowerShell.Utility.Write-Verbose)
