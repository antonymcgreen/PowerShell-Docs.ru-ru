---
title: Все, что вы хотели знать о ShouldProcess
description: ShouldProcess — важный компонент, который часто упускают из виду. Параметры WhatIf и Confirm упрощают добавление в функции.
ms.date: 05/23/2020
ms.custom: contributor-KevinMarquette
ms.openlocfilehash: 4f11ad84f5c89423fe56cfe438ed3cb1587ce59e
ms.sourcegitcommit: be1df0bf757d734975a9aa021727608a396059ee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2020
ms.locfileid: "96616052"
---
# <a name="everything-you-wanted-to-know-about-shouldprocess"></a>Все, что вы хотели знать о ShouldProcess

Некоторые возможности функций PowerShell значительно улучшают способ взаимодействия с ними пользователей.
Одна из таких важных возможностей, которую часто упускают из виду, — это поддержка параметров `-WhatIf` и `-Confirm`, которые можно легко добавить в функции. В этой статье мы подробно рассмотрим, как реализовать эту возможность.

> [!NOTE]
> [Оригинал][] этой статьи впервые был опубликован в блоге автора [@KevinMarquette][]. Команда разработчиков PowerShell благодарит Кевина за то, что он поделился с нами этим материалом. Читайте его блог — [PowerShellExplained.com][].

Это простая возможность, которую можно включить в функциях, чтобы подстраховать пользователей, если им это необходимо. Нет ничего страшнее, чем в первый раз использовать потенциально опасную команду. Совсем другое дело, если она запущена с параметром `-WhatIf`.

## <a name="commonparameters"></a>Общие параметры

Прежде чем мы рассмотрим реализацию этих [общих параметров][], я хочу вкратце рассказать о том, как они используются.

## <a name="using--whatif"></a>Использование параметра -WhatIf

Если команда поддерживает параметр `-WhatIf`, вы можете увидеть, что делает эта команда, не внося фактические изменения. Это хороший способ протестировать влияние команды, особенно перед выполнением каких-либо необратимых действий.

```powershell
PS C:\temp> Remove-Item -Path .\myfile1.txt -WhatIf
What if: Performing the operation "Remove File" on target "C:\Temp\myfile1.txt".
```

Если команда правильно реализует `ShouldProcess`, она должна отобразить все изменения, которые были бы внесены. Ниже приведен пример использования подстановочного знака для удаления нескольких файлов.

```powershell
PS C:\temp> Remove-Item -Path * -WhatIf
What if: Performing the operation "Remove File" on target "C:\Temp\myfile1.txt".
What if: Performing the operation "Remove File" on target "C:\Temp\myfile2.txt".
What if: Performing the operation "Remove File" on target "C:\Temp\importantfile.txt".
```

## <a name="using--confirm"></a>Использование параметра -Confirm

Команды, поддерживающие `-WhatIf`, также поддерживают `-Confirm`. Это дает возможность подтвердить действие перед его выполнением.

```powershell
PS C:\temp> Remove-Item .\myfile1.txt -Confirm

Confirm
Are you sure you want to perform this action?
Performing the operation "Remove File" on target "C:\Temp\myfile1.txt".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

В этом случае у вас есть несколько вариантов: продолжить выполнение, пропустить изменение или остановить выполнение скрипта. Эти параметры описаны в справке, которая вызывается при запросе из командной строки.

```Output
Y - Continue with only the next step of the operation.
A - Continue with all the steps of the operation.
N - Skip this operation and proceed with the next operation.
L - Skip this operation and all subsequent operations.
S - Pause the current pipeline and return to the command prompt. Type "exit" to resume the pipeline.
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

### <a name="localization"></a>Локализация

Этот запрос локализован в PowerShell, поэтому язык изменяется в зависимости от языка операционной системы. Это одна из автоматических возможностей PowerShell.

### <a name="switch-parameters"></a>Параметры-переключатели

Давайте вкратце рассмотрим способы передачи значения в параметр-переключатель. Основная причина, по которой я использую их для вызова, заключается в том, что зачастую вызываемые функции требуется передавать в значения параметров.

Первый подход — это использовать определенный синтаксис параметров, который применим для любых параметров, но в основном используется для параметров-переключателей. Чтобы присоединить значение к параметру, необходимо поставить двоеточие.

```powershell
Remove-Item -Path:* -WhatIf:$true
```

То же самое можно сделать и с переменной.

```powershell
$DoWhatIf = $true
Remove-Item -Path * -WhatIf:$DoWhatIf
```

Второй подход заключается в использовании хэш-таблицы для сплаттинга значения.

```powershell
$RemoveSplat = @{
    Path = '*'
    WhatIf = $true
}
Remove-Item @RemoveSplat
```

Если вы не знакомы с использованием хэш-таблиц или сплаттинга, то у меня есть другая статья на эту тему, в которой есть [все, что вы хотели узнать о хэш-таблицах][].

## <a name="supportsshouldprocess"></a>SupportsShouldProcess

Чтобы включить поддержку `-WhatIf` и `-Confirm`, для начала необходимо указать `SupportsShouldProcess` в `CmdletBinding` функции.

```powershell
function Test-ShouldProcess {
    [CmdletBinding(SupportsShouldProcess)]
    param()
    Remove-Item .\myfile1.txt
}
```

Указав `SupportsShouldProcess` таким образом, можно вызвать функцию с параметром `-WhatIf` (или `-Confirm`).

```powershell
PS> Test-ShouldProcess -WhatIf
What if: Performing the operation "Remove File" on target "C:\Temp\myfile1.txt".
```

Обратите внимание, что я не создаю параметр с именем `-WhatIf`. Он создается автоматически, если задать свойство `SupportsShouldProcess`. Если задать параметр `-WhatIf` для `Test-ShouldProcess`, некоторые из вызываемых объектов также выполняют обработку `-WhatIf`.

### <a name="trust-but-verify"></a>Доверяйте, но проверяйте

Полагаться на то, что все вызовы наследуют значение `-WhatIf`, довольно опасно. В остальных примерах я предполагаю, что это не так, и при вызове других команд буду задавать все параметры явно. Рекомендую и вам придерживаться того же подхода.

```powershell
function Test-ShouldProcess {
    [CmdletBinding(SupportsShouldProcess)]
    param()
    Remove-Item .\myfile1.txt -WhatIf:$WhatIfPreference
}
```

Позже, когда вы получите более полное представление об этих возможностях, я вернусь к этому вопросу и расскажу о различных тонкостях.

## <a name="pscmdletshouldprocess"></a>$PSCmdlet.ShouldProcess

Метод, который позволяет реализовать свойство `SupportsShouldProcess`, называется `$PSCmdlet.ShouldProcess`. Вы вызываете `$PSCmdlet.ShouldProcess(...)`, чтобы узнать, нужно ли обработать ту или иную логику, а остальное PowerShell выполняет автоматически. Давайте начнем с примера.

```powershell
function Test-ShouldProcess {
    [CmdletBinding(SupportsShouldProcess)]
    param()

    $file = Get-ChildItem './myfile1.txt'
    if($PSCmdlet.ShouldProcess($file.Name)){
        $file.Delete()
    }
}
```

Вызов `$PSCmdlet.ShouldProcess($file.name)` проверяет наличие параметра `-WhatIf` (и `-Confirm`) и обрабатывает его соответствующим образом. `-WhatIf` приводит к тому, что `ShouldProcess` выводит описание изменения и возвращает `$false`.

```powershell
PS> Test-ShouldProcess -WhatIf
What if: Performing the operation "Test-ShouldProcess" on target "myfile1.txt".
```

Вызов с `-Confirm` приводит к приостановке выполнения скрипта и отображению для пользователя вариантов продолжения. Он возвращает `$true`, если пользователь выбрал `Y`.

```powershell
PS> Test-ShouldProcess -Confirm
Confirm
Are you sure you want to perform this action?
Performing the operation "Test-ShouldProcess" on target "myfile1.txt".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

Замечательной особенностью метода `$PSCmdlet.ShouldProcess` является то, что он дублируется в подробных выходных данных. Я часто использую это при реализации `ShouldProcess`.

```powershell
PS> Test-ShouldProcess -Verbose
VERBOSE: Performing the operation "Test-ShouldProcess" on target "myfile1.txt".
```

### <a name="overloads"></a>Перегрузки

Для `$PSCmdlet.ShouldProcess` предусмотрено несколько различных перегрузок с разными параметрами для настройки вывода сообщений. Первая из них уже использовалась в приведенном выше примере. Давайте подробнее рассмотрим каждую из них.

```powershell
function Test-ShouldProcess {
    [CmdletBinding(SupportsShouldProcess)]
    param()

    if($PSCmdlet.ShouldProcess('TARGET')){
        # ...
    }
}
```

Эта выводит результат, включающий имя функции и целевой объект (значение параметра).

```powershell
What if: Performing the operation "Test-ShouldProcess" on target "TARGET".
```

Если указать второй параметр в качестве операции, вместо имени функции в сообщении будет использоваться значение операции.

```powershell
## $PSCmdlet.ShouldProcess('TARGET','OPERATION')
What if: Performing the operation "OPERATION" on target "TARGET".
```

Следующий вариант — указать три параметра для полной настройки сообщения. Если используются три параметра, первый из них является сообщением в целом. Два других параметра по-прежнему используются в выходных данных сообщения `-Confirm`.

```powershell
## $PSCmdlet.ShouldProcess('MESSAGE','TARGET','OPERATION')
What if: MESSAGE
```

### <a name="quick-parameter-reference"></a>Ссылка на параметр

Если вы читаете эту статью, только чтобы выяснить, какие параметры следует использовать, ниже приведен краткий справочник со сведениями о том, как параметры изменяют сообщение в различных сценариях `-WhatIf`.

```powershell
## $PSCmdlet.ShouldProcess('TARGET')
What if: Performing the operation "FUNCTION_NAME" on target "TARGET".

## $PSCmdlet.ShouldProcess('TARGET','OPERATION')
What if: Performing the operation "OPERATION" on target "TARGET".

## $PSCmdlet.ShouldProcess('MESSAGE','TARGET','OPERATION')
What if: MESSAGE
```

Я обычно использую метод с двумя параметрами.

### <a name="shouldprocessreason"></a>ShouldProcessReason

Существует также четвертая перегрузка. Она сложнее, чем друге, и позволяет получить причину выполнения `ShouldProcess`. Я добавляю ее здесь для полноты картины, так как вместо этого можно просто проверить, действительно ли значение `$WhatIfPreference` равно `$true`.

```powershell
$reason = ''
if($PSCmdlet.ShouldProcess('MESSAGE','TARGET','OPERATION',[ref]$reason)){
    Write-Output "Some Action"
}
$reason
```

Переменную `$reason` необходимо передать в четвертый параметр в виде ссылочной переменной с `[ref]`. `ShouldProcess` заполняет `$reason` значением `None` или `WhatIf`. Я бы не назвал это полезной возможностью, так что у меня нет причин ее использовать.

### <a name="where-to-place-it"></a>Место размещения

Метод `ShouldProcess` используется, чтобы сделать скрипты безопаснее. Поэтому его можно использовать при внесении изменений в скрипты. Я предпочитаю размещать вызов `$PSCmdlet.ShouldProcess` как можно ближе к изменению.

```powershell
## general logic and variable work
if ($PSCmdlet.ShouldProcess('TARGET','OPERATION')){
    # Change goes here
}
```

Если я обрабатываю коллекцию элементов, я вызываю этот метод для каждого элемента. Поэтому вызов помещается внутри цикла foreach.

```powershell
foreach ($node in $collection){
    # general logic and variable work
    if ($PSCmdlet.ShouldProcess($node,'OPERATION')){
        # Change goes here
    }
}
```

Причина, по которой я располагаю `ShouldProcess` в непосредственной близости от этого изменения, заключается в том, что мне нужно обеспечить выполнение как можно большей части кода при заданном параметре `-WhatIf`. Я хочу, чтобы по возможности выполнялась установка и проверка. Тогда пользователь увидит эти ошибки.

Я также хотел бы использовать этот код в тестах Pester, которые проверяют мои проекты. Если у меня есть фрагмент логики, который трудно макетировать в Pester, я зачастую помещаю его в метод `ShouldProcess` и вызываю его в своих тестах с параметром `-WhatIf`. Лучше протестировать часть кода, чем не тестировать его вообще.

### <a name="whatifpreference"></a>$WhatIfPreference

Первая привилегированная переменная — `$WhatIfPreference`. По умолчанию ее значение `$false`. Если задать для нее значение `$true`, функция выполняется так, как если бы вы указали `-WhatIf`. Если задать это в сеансе, все команды будут выполняться с параметром `-WhatIf`.

При вызове функции с параметром `-WhatIf` значение `$WhatIfPreference` становится равным `$true` в области действия функции.

## <a name="confirmimpact"></a>ConfirmImpact

Большинство моих примеров касаются `-WhatIf`, но все это также работает и при использовании `-Confirm` для отправки запроса пользователю. Для аргумента `ConfirmImpact` функции можно задать значение high, и тогда она будет выводить запрос пользователю, как если бы была вызвана с параметром `-Confirm`.

```powershell
function Test-ShouldProcess {
    [CmdletBinding(
        SupportsShouldProcess,
        ConfirmImpact = 'High'
    )]
    param()

    if ($PSCmdlet.ShouldProcess('TARGET')){
        Write-Output "Some Action"
    }
}
```

Этот вызов `Test-ShouldProcess` выполняет действие `-Confirm` из-за значения `High`.

```powershell
PS> Test-ShouldProcess

Confirm
Are you sure you want to perform this action?
Performing the operation "Test-ShouldProcess" on target "TARGET".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): y
Some Action
```

Очевидная проблема заключается в том, что теперь ее сложнее использовать в других скриптах без запроса пользователя. В этом случае можно передать `$false` в `-Confirm`, чтобы подавить запрос.

```powershell
PS> Test-ShouldProcess -Confirm:$false
Some Action
```

Я расскажу, как добавить поддержку `-Force` в одном из следующих разделов.

### <a name="confirmpreference"></a>$ConfirmPreference

`$ConfirmPreference` — это автоматическая переменная, определяющая, когда `ConfirmImpact` запрашивает подтверждение выполнения. Ниже приведены возможные значения для `$ConfirmPreference` и `ConfirmImpact`.

- `High`
- `Medium`
- `Low`
- `None`

С помощью этих значений можно указать различные уровни влияния для каждой функции. Если заданное для `$ConfirmPreference` значение выше, чем значение `ConfirmImpact`, запрос на подтверждение выполнения не выводится.

По умолчанию для `$ConfirmPreference` задано значение `High`, а для `ConfirmImpact` — значение `Medium`. Если вы хотите, чтобы функция автоматически запрашивала подтверждение пользователя, задайте для аргумента `ConfirmImpact` значение `High`. В противном случае задайте для него значение `Medium`, если команда выполняет необратимое действие, и `Low`, если она всегда безопасна для выполнения в рабочей среде. Если задать для него значение `none`, запрос на подтверждение не выводится, даже если задан параметр `-Confirm` (но поддержка `-WhatIf` по-прежнему предоставляется).

В случае вызова функции с параметром `-Confirm` значение `$ConfirmPreference` становится равным `Low` в области действия функции.

### <a name="suppressing-nested-confirm-prompts"></a>Подавление вложенных запросов на подтверждение

Вызываемые функции могут получать значение `$ConfirmPreference`. Это может привести к ситуации, когда вы добавляете запрос на подтверждение, но при этом вызываемая функция также запрашивает его у пользователя.

Я обычно предпочитаю использовать `-Confirm:$false` для вызываемых команд после того, как запрос уже обработан.

```powershell
function Test-ShouldProcess {
    [CmdletBinding(SupportsShouldProcess)]
    param()

    $file = Get-ChildItem './myfile1.txt'
    if($PSCmdlet.ShouldProcess($file.Name)){
        Remove-Item -Path $file.FullName -Confirm:$false
    }
}
```

Таким образом, мы снова возвращаемся к предыдущему предупреждению. Есть ряд особенностей, от которых зависит, в каких ситуациях `-WhatIf` не передается в функцию и в каких ситуациях `-Confirm` передается в функцию. Обещаю вернуться к этому вопросу позже.

## <a name="pscmdletshouldcontinue"></a>$PSCmdlet.ShouldContinue

Если вам требуется более жесткий контроль, чем обеспечивает `ShouldProcess`, можно запустить запрос непосредственно с помощью `ShouldContinue`. `ShouldContinue` пропускает `$ConfirmPreference`, `ConfirmImpact`, `-Confirm`, `$WhatIfPreference` и `-WhatIf`, так как запрос выводится при каждом выполнении.

`ShouldProcess` и `ShouldContinue` можно легко перепутать. Я обычно помню, что нужно использовать `ShouldProcess`, поскольку параметр в `CmdletBinding` называется `SupportsShouldProcess`.
Практически во всех сценариях следует использовать `ShouldProcess`. Именно поэтому я сначала рассматривал именно этот метод.

Давайте посмотрим на метод `ShouldContinue` в действии.

```powershell
function Test-ShouldContinue {
    [CmdletBinding()]
    param()

    if($PSCmdlet.ShouldContinue('TARGET','OPERATION')){
        Write-Output "Some Action"
    }
}
```

В данном случае мы получаем простой запрос с несколькими вариантами.

```powershell
Test-ShouldContinue

Second
TARGET
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):
```

Основная проблема использования `ShouldContinue` заключается в том, что пользователь в таком случае должен работать в интерактивном режиме, потому что для него всегда отображется запрос. Вам всегда следует создавать такие средства, которые могут использоваться другими скриптами. Для этого используется реализация `-Force`. Я вернусь к этой идее позже.

### <a name="yes-to-all"></a>Да для всех

Для `ShouldProcess` этот вариант обрабатывается автоматически, но для `ShouldContinue` необходимо выполнить еще несколько действий. Существует вторая перегрузка метода, в которую необходимо передать несколько значений по ссылке для управления логикой.

```powershell
function Test-ShouldContinue {
    [CmdletBinding()]
    param()

    $collection = 1..5
    $yesToAll = $false
    $noToAll = $false

    foreach($target in $collection) {

        $continue = $PSCmdlet.ShouldContinue(
                "TARGET_$target",
                'OPERATION',
                [ref]$yesToAll,
                [ref]$noToAll
            )

        if ($continue){
            Write-Output "Some Action [$target]"
        }
    }
}
```

Я добавил цикл `foreach` и коллекцию, чтобы показать их в действии. Я извлек вызов `ShouldContinue` из инструкции `if`, чтобы упростить чтение. Вызов метода с четырьмя параметрами — далеко не самый лучший подход, но я постарался сделать его как можно более понятным.

## <a name="implementing--force"></a>Реализация -Force

`ShouldProcess` и `ShouldContinue` должны реализовывать `-Force` различными способами. Хитрость таких реализаций заключается в том, что метод `ShouldProcess` всегда должен выполняться, а `ShouldContinue` не должен выполняться, если указано `-Force`.

### <a name="shouldprocess--force"></a>Параметр -Force метода ShouldProcess

Если задать для `ConfirmImpact` значение `high`, первое, что попытаются сделать пользователи, — это подавить его запрос с помощью `-Force`. Во всяком случае, это первое, что делаю я.

```powershell
Test-ShouldProcess -Force
Error: Test-ShouldProcess: A parameter cannot be found that matches parameter name 'force'.
```

Если вы припомните раздел `ConfirmImpact`, то поймете, что им на самом деле нужно вызвать его следующим образом.

```powershell
Test-ShouldProcess -Confirm:$false
```

Не все понимают, что это действительно необходимо сделать и что `-Force` не подавляет `ShouldContinue`.
Поэтому для нормальной работы пользователей мы должны реализовать `-Force`. Взгляните на этот полный пример.

```powershell
function Test-ShouldProcess {
    [CmdletBinding(
        SupportsShouldProcess,
        ConfirmImpact = 'High'
    )]
    param(
        [Switch]$Force
    )

    if ($Force){
        $ConfirmPreference = 'None'
    }

    if ($PSCmdlet.ShouldProcess('TARGET')){
        Write-Output "Some Action"
    }
}
```

Мы добавим собственный переключатель `-Force` в качестве параметра. Параметр `-Confirm` автоматически добавляется при использовании `SupportsShouldProcess` в `CmdletBinding`.

```powershell
[CmdletBinding(
    SupportsShouldProcess,
    ConfirmImpact = 'High'
)]
param(
    [Switch]$Force
)
```

Здесь основное внимание следует уделить логике `-Force`.

```powershell
if ($Force){
    $ConfirmPreference = 'None'
}
```

Если пользователь задает `-Force`, необходимо отключить запрос на подтверждение, если не указан параметр `-Confirm`. Это позволит пользователю принудительно вносить изменения, но ему по-прежнему придется их подтверждать. Затем мы зададим `$ConfirmPreference` в локальной области. Теперь с помощью параметра `-Force` можно временно присвоить `$ConfirmPreference` значение none, отключив запрос на подтверждение.

```powershell
if ($Force -or $PSCmdlet.ShouldProcess('TARGET')){
        Write-Output "Some Action"
    }
```

Если указать как `-Force`, так и `-WhatIf`, приоритет будет у `-WhatIf`. При таком подходе обработка `-WhatIf` сохраняется, так как `ShouldProcess` выполняется всегда.

Не добавляйте проверку для значения `$Force` в инструкции `if` с помощью метода `ShouldProcess`. Это неподходящий вариант для данного конкретного сценария, несмотря на то, что я продемонстрирую его в следующем разделе, посвященном `ShouldContinue`.

### <a name="shouldcontinue--force"></a>Параметр -Force метода ShouldContinue

Это правильный способ реализации `-Force` с `ShouldContinue`.

```powershell
function Test-ShouldContinue {
    [CmdletBinding()]
    param(
        [Switch]$Force
    )

    if($Force -or $PSCmdlet.ShouldContinue('TARGET','OPERATION')){
        Write-Output "Some Action"
    }
}
```

Если поместить переменную `$Force` слева от оператора `-or`, она вычисляется первой. При такой записи выполнение инструкции `if` упрощается. Если значение `$force` равно `$true`, `ShouldContinue` не выполняется.

```powershell
PS> Test-ShouldContinue -Force
Some Action
```

В этом сценарии не нужно беспокоиться о параметрах `-Confirm` и `-WhatIf`, так как они не поддерживаются `ShouldContinue`. Именно поэтому с данным методом следует работать иначе, чем с `ShouldProcess`.

## <a name="scope-issues"></a>Проблемы с областью действия

Предполагается, что при использовании параметров `-WhatIf` и `-Confirm` они применяются ко всем элементам внутри функции и всему, что она вызывает. Для этого они задают значение `$true` для параметра `$WhatIfPreference` или значение `Low` для параметра `$ConfirmPreference` в локальной области функции. При вызове другой функции эти значения используются для вызова метода `ShouldProcess`.

Фактически в большинстве случаев такой подход работает надлежащим образом. Каждый раз, когда вы вызываете встроенный командлет или функцию в той же области, все работает так, как нужно. Этот подход также работает при вызове скрипта или функции в модуле скрипта из консоли.

Однако есть одна особая ситуация, когда он не срабатывает. Возникает она, когда скрипт или модуль скрипта вызывает функцию в другом модуле скрипта. Может показаться, что это не такая уж проблема, однако следует отметить, что большинство модулей, создаваемых в коллекции PSGallery или извлекаемых из нее, являются модулями скриптов.

Основная проблема заключается в том, что модули скриптов не наследуют значения `$WhatIfPreference` или `$ConfirmPreference` (и некоторых других) при вызове из функций в других модулях скриптов.

Чтобы подвести итоги, сформулируем общее правило: данный подход работает правильно для двоичных модулей, но при работе и с модулями скриптов полагаться на него не следует. Если вы не уверены, проверьте его работу или просто считайте, что он работает неправильно.

Лично мне кажется, что это очень опасно, так как создает ситуацию, когда вы добавляете поддержку `-WhatIf` в несколько модулей, которые работают верно по отдельности, но при вызове друг из друга начинают функционировать неправильно.

Сейчас ведутся работы по устранению этой проблемы согласно RFC на GitHub. Дополнительные сведения см. в обсуждении [распространения настроек выполнения за пределы области действия модуля скрипта][RFC].

## <a name="in-closing"></a>Заключение

Мне нужно узнать, как использовать `ShouldProcess` всякий раз, когда это необходимо. Мне пришлось потратить много времени, чтобы научиться отличать `ShouldProcess` от `ShouldContinue`. Мне почти всегда нужно искать данные о том, какие параметры следует использовать. Поэтому не беспокойтесь, если вы все еще путаете их время от времени. Эта статья будет всегда у вас под рукой. Уверен, что я сам буду часто к ней обращаться.

Если вам понравилась эта публикация, поделитесь со мной своими идеями в Twitter по приведенной ниже ссылке. Мне всегда приятно общаться с людьми, которым были полезны мои материалы.

<!-- link references -->
[Оригинал]: https://powershellexplained.com/2020-03-15-Powershell-shouldprocess-whatif-confirm-shouldcontinue-everything/
[powershellexplained.com]: https://powershellexplained.com/
[@KevinMarquette]: https://twitter.com/KevinMarquette
[общих параметров]: /powershell/module/microsoft.powershell.core/about/about_commonparameters
[все, что вы хотели узнать о хэш-таблицах]: everything-about-hashtable.md
[RFC]: https://github.com/PowerShell/PowerShell-RFC/pull/221#issuecomment-592954839
