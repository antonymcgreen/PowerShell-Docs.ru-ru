---
title: Функции
description: С помощью функций PowerShell можно создавать средства для многократного использования в сценариях.
ms.date: 06/02/2020
ms.custom: Contributor-mikefrobbins
ms.reviewer: mirobb
ms.openlocfilehash: e4734b556a78f67c54152dad93eada536dd1c928
ms.sourcegitcommit: df5e6f032ee2d4b556d50406832732d2f7dc2502
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/14/2021
ms.locfileid: "99600871"
---
# <a name="chapter-9---functions"></a>Глава 9. Функции

Если вы пишете однострочные коды и сценарии PowerShell, которые часто приходится изменять для применения в различных ситуациях, возможно, их стоит преобразовать в многократно используемую функцию.

По возможности я предпочитаю писать функции, потому что они больше ориентированы на работу со средствами. Я могу поместить функции в модуль сценария, отправить этот модуль в `$env:PSModulePath` и вызвать функции без необходимости физического определения их местонахождения. С помощью модуля PowerShellGet эти модули можно легко запрашивать в репозитории NuGet. PowerShellGet поставляется с PowerShell версии 5.0 и выше. Он доступен в виде отдельного скачиваемого файла для PowerShell версии 3.0 и более поздних версий.

Не нужно ничего усложнять. Будьте проще и выбирайте самый прямой путь для решения задач. Избегайте псевдонимов и позиционных параметров в любом многократно используемом коде. Отформатируйте код, чтобы сделать его удобочитаемым. Не указывайте значения прямо в коде — используйте параметры и переменные. Не пишите лишний код, даже если это ничему не повредит. Он усложнит ситуацию. При написании кода PowerShell очень важно обращать внимание на детали.

## <a name="naming"></a>Именование

При именовании функций в PowerShell используйте имя в [Регистр Pascal][] с утвержденным глаголом и существительным в единственном числе. Кроме того, перед существительным рекомендуется добавить префикс. Например: `<ApprovedVerb>-<Prefix><SingularNoun>`.

В PowerShell есть конкретный список утвержденных глаголов, которые можно получить, выполнив `Get-Verb`.

```powershell
Get-Verb | Sort-Object -Property Verb
```

```Output
Verb        Group
----        -----
Add         Common
Approve     Lifecycle
Assert      Lifecycle
Backup      Data
Block       Security
Checkpoint  Data
Clear       Common
Close       Common
Compare     Data
Complete    Lifecycle
Compress    Data
Confirm     Lifecycle
Connect     Communications
Convert     Data
ConvertFrom Data
ConvertTo   Data
Copy        Common
Debug       Diagnostic
Deny        Lifecycle
Disable     Lifecycle
Disconnect  Communications
Dismount    Data
Edit        Data
Enable      Lifecycle
Enter       Common
Exit        Common
Expand      Data
Export      Data
Find        Common
Format      Common
Get         Common
Grant       Security
Group       Data
Hide        Common
Import      Data
Initialize  Data
Install     Lifecycle
Invoke      Lifecycle
Join        Common
Limit       Data
Lock        Common
Measure     Diagnostic
Merge       Data
Mount       Data
Move        Common
New         Common
Open        Common
Optimize    Common
Out         Data
Ping        Diagnostic
Pop         Common
Protect     Security
Publish     Data
Push        Common
Read        Communications
Receive     Communications
Redo        Common
Register    Lifecycle
Remove      Common
Rename      Common
Repair      Diagnostic
Request     Lifecycle
Reset       Common
Resize      Common
Resolve     Diagnostic
Restart     Lifecycle
Restore     Data
Resume      Lifecycle
Revoke      Security
Save        Data
Search      Common
Select      Common
Send        Communications
Set         Common
Show        Common
Skip        Common
Split       Common
Start       Lifecycle
Step        Common
Stop        Lifecycle
Submit      Lifecycle
Suspend     Lifecycle
Switch      Common
Sync        Data
Test        Diagnostic
Trace       Diagnostic
Unblock     Security
Undo        Common
Uninstall   Lifecycle
Unlock      Common
Unprotect   Security
Unpublish   Data
Unregister  Lifecycle
Update      Data
Use         Other
Wait        Lifecycle
Watch       Common
Write       Communications
```

В предыдущем примере результаты отсортированы по столбцу **Verb**. Взглянув на столбец **Group**, вы получите представление о том, как эти глаголы используются. При добавлении функций в модуль важно выбрать утвержденную команду в PowerShell. Если будет выбран неутвержденный глагол, модуль создаст предупреждение во время загрузки. Из-за этого предупреждения ваши функции выглядят непрофессионально. Кроме того, неутвержденные глаголы ограничивают возможности обнаружения функций.

## <a name="a-simple-function"></a>Простая функция

Функция в PowerShell объявляется с помощью ключевого слова function, за которым следует имя функции, а затем — открывающая и закрывающая фигурные скобки. В этих скобках содержится код, который будет выполнять функция.

```powershell
function Get-Version {
    $PSVersionTable.PSVersion
}
```

Показан простой пример функции, возвращающей версию PowerShell.

```powershell
Get-Version
```

```Output
Major  Minor  Build  Revision
-----  -----  -----  --------
5      1      14393  693
```

Существует большая вероятность возникновения конфликта имен функций, названных примерно как `Get-Version`, и команд по умолчанию в PowerShell или команд, которые могут написать другие пользователи. Именно поэтому в целях предотвращения конфликтов имен рекомендуется добавлять префикс к части функции, выраженной существительным. В следующем примере используется префикс PS.

```powershell
function Get-PSVersion {
    $PSVersionTable.PSVersion
}
```

Эта функция идентична предыдущей, за исключением имени.

```powershell
Get-PSVersion
```

```Output
Major  Minor  Build  Revision
-----  -----  -----  --------
5      1      14393  693
```

Даже при добавлении префикса типа PS все равно есть большая вероятность конфликта имен. Обычно перед существительным в имени функции я указываю свои инициалы. Разработайте свой стандарт и придерживайтесь его.

```powershell
function Get-MrPSVersion {
    $PSVersionTable.PSVersion
}
```

Эта функция ничем не отличается от двух предыдущих, кроме использования более соответствующего имени для предотвращения конфликтов именования с другими командами PowerShell.

```powershell
Get-MrPSVersion
```

```Output
Major  Minor  Build  Revision
-----  -----  -----  --------
5      1      14393  693
```

Функции, загруженные в память, можно увидеть на PSDrive **Function**.

```powershell
Get-ChildItem -Path Function:\Get-*Version
```

```Output
CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Function        Get-Version
Function        Get-PSVersion
Function        Get-MrPSVersion
```

Чтобы удалить эти функции из текущего сеанса, необходимо удалить их из PSDrive **Function** или закрыть и повторно открыть PowerShell.

```powershell
Get-ChildItem -Path Function:\Get-*Version | Remove-Item
```

Убедитесь, что функции действительно удалены.

```powershell
Get-ChildItem -Path Function:\Get-*Version
```

Если функции были загружены в составе модуля, то, чтобы удалить их, можно выгрузить модуль.

```powershell
Remove-Module -Name <ModuleName>
```

Командлет `Remove-Module` удаляет модули из памяти в текущем сеансе PowerShell, но не удаляет их из системы или с диска.

## <a name="parameters"></a>Параметры

Не присваивайте значения статически! Используйте параметры и переменные. Когда дело доходит до именования параметров, по возможности используйте те же имена, что и у командлетов по умолчанию.

```powershell
function Test-MrParameter {

    param (
        $ComputerName
    )

    Write-Output $ComputerName

}
```

Почему в качестве имени параметра я использовал **ComputerName**, а не **Computer**, **ServerName** или **Host**? Потому что я хотел, чтобы мои функции были стандартизированы как стандартные командлеты.

Я создам функцию, которая будет запрашивать все команды в системе и возвращать количество команд с конкретными именами параметров.

```powershell
function Get-MrParameterCount {
    param (
        [string[]]$ParameterName
    )

    foreach ($Parameter in $ParameterName) {
        $Results = Get-Command -ParameterName $Parameter -ErrorAction SilentlyContinue

        [pscustomobject]@{
            ParameterName = $Parameter
            NumberOfCmdlets = $Results.Count
        }
    }
}
```

Как видно в приведенных ниже результатах, у 39 команд есть параметр **ComputerName**. Командлеты с такими параметрами, как **Computer**, **ServerName**, **Host** или **Machine**, не найдены.

```powershell
Get-MrParameterCount -ParameterName ComputerName, Computer, ServerName, Host, Machine
```

```Output
ParameterName NumberOfCmdlets
------------- ---------------
ComputerName               39
Computer                    0
ServerName                  0
Host                        0
Machine                     0
```

Кроме того, имена параметров рекомендуется указывать в том же регистре, что и имена командлетов по умолчанию. Используйте `ComputerName`, а не `computername`. В этом случае функции выглядят и работают как командлеты по умолчанию. Это очень удобно для пользователей, уже знакомых с PowerShell.

`param`Оператор позволяет определить один или несколько параметров. Определения параметров разделяются запятой ( `,` ). Дополнительные сведения см. в разделе [about_Functions_Advanced_Parameters][].

## <a name="advanced-functions"></a>Расширенные функции

Функцию в PowerShell можно легко преобразовать в расширенную. Одно из различий между функцией и расширенной функцией заключается в том, что расширенные функции имеют ряд общих параметров, которые добавляются в функцию автоматически. К этим общим параметрам относятся такие параметры, как **Verbose** и **Debug**.

Я начну с функции `Test-MrParameter`, которая использовалась в предыдущем разделе.

```powershell
function Test-MrParameter {

    param (
        $ComputerName
    )

    Write-Output $ComputerName

}
```

Хочу обратить ваше внимание на то, что функция `Test-MrParameter` не имеет общих параметров. Существует несколько различных способов просмотра общих параметров. Один из них — просмотр синтаксиса с помощью `Get-Command`.

```powershell
Get-Command -Name Test-MrParameter -Syntax
```

```Output
Test-MrParameter [[-ComputerName] <Object>]
```

Другой — детализация параметров с помощью `Get-Command`.

```powershell
(Get-Command -Name Test-MrParameter).Parameters.Keys
```

```Output
ComputerName
```

Добавьте `CmdletBinding`, чтобы преобразовать функцию в расширенную.

```powershell
function Test-MrCmdletBinding {

    [CmdletBinding()] #<<-- This turns a regular function into an advanced function
    param (
        $ComputerName
    )

    Write-Output $ComputerName

}
```

При добавлении `CmdletBinding` общие параметры добавляются автоматически. Для `CmdletBinding` требуется блок `param`, но блок `param` может быть пустым.

```powershell
Get-Command -Name Test-MrCmdletBinding -Syntax
```

```Output
Test-MrCmdletBinding [[-ComputerName] <Object>] [<CommonParameters>]
```

Если выполнить детализацию параметров с помощью `Get-Command`, можно увидеть имена параметров, включая общие параметры.

```powershell
(Get-Command -Name Test-MrCmdletBinding).Parameters.Keys
```

```Output
ComputerName
Verbose
Debug
ErrorAction
WarningAction
InformationAction
ErrorVariable
WarningVariable
InformationVariable
OutVariable
OutBuffer
PipelineVariable
```

## <a name="supportsshouldprocess"></a>SupportsShouldProcess

`SupportsShouldProcess` добавляет параметры **WhatIf** и **Confirm**. Они необходимы только для команд, которые вносят изменения.

```powershell
function Test-MrSupportsShouldProcess {

    [CmdletBinding(SupportsShouldProcess)]
    param (
        $ComputerName
    )

    Write-Output $ComputerName

}
```

Обратите внимание, что теперь появились параметры **WhatIf** и **Confirm**.

```powershell
Get-Command -Name Test-MrSupportsShouldProcess -Syntax
```

```Output
Test-MrSupportsShouldProcess [[-ComputerName] <Object>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

Опять же: с помощью `Get-Command` можно получить список фактических имен параметров, включая общие параметры и WhatIf и Confirm.

```powershell
(Get-Command -Name Test-MrSupportsShouldProcess).Parameters.Keys
```

```Output
ComputerName
Verbose
Debug
ErrorAction
WarningAction
InformationAction
ErrorVariable
WarningVariable
InformationVariable
OutVariable
OutBuffer
PipelineVariable
WhatIf
Confirm
```

## <a name="parameter-validation"></a>Проверка параметров

Входные данные следует проверять в самом начале. Для чего продолжать выполнение кода, если это невозможно сделать без допустимых входных данных?

Всегда вводите переменные, используемые для параметров (с указанием типа данных).

```powershell
function Test-MrParameterValidation {

    [CmdletBinding()]
    param (
        [string]$ComputerName
    )

    Write-Output $ComputerName

}
```

В предыдущем примере в качестве типа данных для параметра **ComputerName** указано **String**. Это означает, что допускается только одно имя компьютера. Если задается несколько имен компьютеров в виде списка с разделителями-запятыми, возникает ошибка.

```powershell
Test-MrParameterValidation -ComputerName Server01, Server02
```

```Output
Test-MrParameterValidation : Cannot process argument transformation on parameter
'ComputerName'. Cannot convert value to type System.String.
At line:1 char:42
+ Test-MrParameterValidation -ComputerName Server01, Server02
+
    + CategoryInfo          : InvalidData: (:) [Test-MrParameterValidation], ParameterBindingArg
     umentTransformationException
    + FullyQualifiedErrorId : ParameterArgumentTransformationError,Test-MrParameterValidation
```

Проблема с текущим определением заключается в том, что значение параметра **ComputerName** можно опустить, но оно требуется для успешного выполнения функции. Именно в таком случае будет полезен атрибут параметра `Mandatory`.

```powershell
function Test-MrParameterValidation {

    [CmdletBinding()]
    param (
        [Parameter(Mandatory)]
        [string]$ComputerName
    )

    Write-Output $ComputerName

}
```

В предыдущем примере используется синтаксис, совместимый с PowerShell версии 3.0 и более поздними.
Чтобы обеспечить совместимость функции с PowerShell версии 2.0 и более поздними, можно указать `[Parameter(Mandatory=$true)]`. Теперь, когда потребуется значение параметра **ComputerName**, которое пока не задано, функция выведет соответствующий запрос.

```powershell
Test-MrParameterValidation
```

```Output
cmdlet Test-MrParameterValidation at command pipeline position 1
Supply values for the following parameters:
ComputerName:
```

Чтобы разрешить несколько значений для параметра **ComputerName**, используйте тип данных **String**, но добавьте к нему открывающие и закрывающие квадратные скобки, позволяющие использовать массив строк.

```powershell
function Test-MrParameterValidation {

    [CmdletBinding()]
    param (
        [Parameter(Mandatory)]
        [string[]]$ComputerName
    )

    Write-Output $ComputerName

}
```

Возможно, вы захотите указать значение по умолчанию для параметра **ComputerName**, если это еще не сделано.
Проблема в том, что значения по умолчанию нельзя использовать с обязательными параметрами. Вместо этого потребуется атрибут проверки параметров `ValidateNotNullOrEmpty` со значением по умолчанию.

```powershell
function Test-MrParameterValidation {

    [CmdletBinding()]
    param (
        [ValidateNotNullOrEmpty()]
        [string[]]$ComputerName = $env:COMPUTERNAME
    )

    Write-Output $ComputerName

}
```

Даже при задании значения по умолчанию старайтесь не прибегать к статическим значениям. В предыдущем примере в качестве значения по умолчанию используется `$env:COMPUTERNAME`, которое автоматически преобразуется в имя локального компьютера, если значение не указано.

## <a name="verbose-output"></a>Подробные выходные данные

Несмотря на всю пользу встроенных комментариев, особенно при написании сложного кода, их никогда не увидят пользователи, если только не заглянут в сам код.

Функция, показанная в следующем примере, содержит встроенный комментарий в цикле `foreach`. Хотя этот конкретный комментарий может быть не так уж сложно обнаружить, представьте, что было бы, если бы функция включала сотни строк кода.

```powershell
function Test-MrVerboseOutput {

    [CmdletBinding()]
    param (
        [ValidateNotNullOrEmpty()]
        [string[]]$ComputerName = $env:COMPUTERNAME
    )

    foreach ($Computer in $ComputerName) {
        #Attempting to perform some action on $Computer <<-- Don't use
        #inline comments like this, use write verbose instead.
        Write-Output $Computer
    }

}
```

Лучшим вариантом является использование `Write-Verbose` вместо встроенных комментариев.

```powershell
function Test-MrVerboseOutput {

    [CmdletBinding()]
    param (
        [ValidateNotNullOrEmpty()]
        [string[]]$ComputerName = $env:COMPUTERNAME
    )

    foreach ($Computer in $ComputerName) {
        Write-Verbose -Message "Attempting to perform some action on $Computer"
        Write-Output $Computer
    }

}
```

Если функция вызывается без параметра **verbose**, подробные выходные данные отображаться не будут.

```powershell
Test-MrVerboseOutput -ComputerName Server01, Server02
```

При вызове функции с параметром **verbose** будут выведены подробные выходные данные.

```powershell
Test-MrVerboseOutput -ComputerName Server01, Server02 -Verbose
```

## <a name="pipeline-input"></a>Входные данные конвейера

Если требуется, чтобы функция принимала входные данные конвейера, необходимо написать дополнительный код. Как говорилось ранее в этой книге, команды могут принимать входные данные конвейера **по значению** (по типу) или **по имени свойства**. Вы можете писать свои функции так же, как машинные команды, чтобы они принимали один тип входных данных или оба.

Чтобы принимать входные данные конвейера **по значению**, укажите атрибут параметра `ValueFromPipeline` для этого конкретного параметра. Помните, что входные данные конвейера **по значению** можно принимать только от одного из каждого типа данных. Например, если есть два параметра, принимающих строковые входные данные, то только один из них может принимать входные данные конвейера **по значению**, так как, если это условие указано для обоих строковых параметров, входным данным конвейера будет неизвестно, к какому параметру следует выполнить привязку. Это еще одна причина, по которой я называю этот тип входных данных конвейера _по типу_ вместо **по значению**.

Входные данные конвейера поступают в один элемент за раз аналогично тому, как элементы обрабатываются в цикле `foreach`.
Если в качестве входных данных принимается массив, для обработки каждого из этих элементов требуется как минимум блок `process`. Если в качестве входных данных принимается только одно значение, блок `process` не требуется, но я по-прежнему рекомендую указывать его для обеспечения согласованности.

```powershell
function Test-MrPipelineInput {

    [CmdletBinding()]
    param (
        [Parameter(Mandatory,
                   ValueFromPipeline)]
        [string[]]$ComputerName
    )

    PROCESS {
        Write-Output $ComputerName
    }

}
```

Прием входных данных конвейера **по имени свойства** происходит аналогично, за исключением того, что указывается с помощью атрибута параметра `ValueFromPipelineByPropertyName` и может быть указан для любого числа параметров независимо от типа данных. Ключевом момент в том, что выходными данными команды, в которую передается параметр, должно быть имя свойства, совпадающее с именем параметра или псевдонимом параметра вашей функции.

```powershell
function Test-MrPipelineInput {

    [CmdletBinding()]
    param (
        [Parameter(Mandatory,
                   ValueFromPipelineByPropertyName)]
        [string[]]$ComputerName
    )

    PROCESS {
            Write-Output $ComputerName
    }

}
```

Блоки `BEGIN` и `END` являются необязательными. `BEGIN` указывается перед блоком `PROCESS` и используется для выполнения всех начальных задач до получения элементов из конвейера. Разобраться с этим очень важно. Переданные значения недоступны в блоке `BEGIN`. Блок `END` указывается после блока `PROCESS` и используется для очистки после обработки всех переданных элементов.

## <a name="error-handling"></a>Обработка ошибок

Функция, показанная в следующем примере, создает необработанное исключение, если не удается связаться с компьютером.

```powershell
function Test-MrErrorHandling {

    [CmdletBinding()]
    param (
        [Parameter(Mandatory,
                   ValueFromPipeline,
                   ValueFromPipelineByPropertyName)]
        [string[]]$ComputerName
    )

    PROCESS {
        foreach ($Computer in $ComputerName) {
            Test-WSMan -ComputerName $Computer
        }
    }

}
```

В PowerShell существует несколько различных способов обработки ошибок. Более современным является `Try/Catch`.

```powershell
function Test-MrErrorHandling {

    [CmdletBinding()]
    param (
        [Parameter(Mandatory,
                   ValueFromPipeline,
                   ValueFromPipelineByPropertyName)]
        [string[]]$ComputerName
    )

    PROCESS {
        foreach ($Computer in $ComputerName) {
            try {
                Test-WSMan -ComputerName $Computer
            }
            catch {
                Write-Warning -Message "Unable to connect to Computer: $Computer"
            }
        }
    }

}
```

Хотя функция, показанная в предыдущем примере, использует обработку ошибок, она также выдает необработанное исключение, так как команда не создает неустранимую ошибку. Разобраться с этим очень важно! Перехватываются только устранимые ошибки. Чтобы преобразовать неустранимую ошибку в устранимую, укажите параметр **ErrorAction** со значением **Stop**.

```powershell
function Test-MrErrorHandling {

    [CmdletBinding()]
    param (
        [Parameter(Mandatory,
                   ValueFromPipeline,
                   ValueFromPipelineByPropertyName)]
        [string[]]$ComputerName
    )

    PROCESS {
        foreach ($Computer in $ComputerName) {
            try {
                Test-WSMan -ComputerName $Computer -ErrorAction Stop
            }
            catch {
                Write-Warning -Message "Unable to connect to Computer: $Computer"
            }
        }
    }

}
```

Не изменяйте глобальную переменную `$ErrorActionPreference`, если в этом нет крайней необходимости. Если вы используете нечто вроде .NET непосредственно в функции PowerShell, параметр **ErrorAction** невозможно указать в самой команде. В этом случае может потребоваться изменить глобальную переменную `$ErrorActionPreference`, но, если вы измените ее, верните ее к исходному виду сразу же после того, как попробуете запустить команду.

## <a name="comment-based-help"></a>Справка на основе комментариев

В функции рекомендуется добавить справку на основе комментариев, чтобы пользователи, которым вы предоставляете доступ к функциям, могли знать, как их использовать.

```powershell
function Get-MrAutoStoppedService {

<#
.SYNOPSIS
    Returns a list of services that are set to start automatically, are not
    currently running, excluding the services that are set to delayed start.

.DESCRIPTION
    Get-MrAutoStoppedService is a function that returns a list of services from
    the specified remote computer(s) that are set to start automatically, are not
    currently running, and it excludes the services that are set to start automatically
    with a delayed startup.

.PARAMETER ComputerName
    The remote computer(s) to check the status of the services on.

.PARAMETER Credential
    Specifies a user account that has permission to perform this action. The default
    is the current user.

.EXAMPLE
     Get-MrAutoStoppedService -ComputerName 'Server1', 'Server2'

.EXAMPLE
     'Server1', 'Server2' | Get-MrAutoStoppedService

.EXAMPLE
     Get-MrAutoStoppedService -ComputerName 'Server1' -Credential (Get-Credential)

.INPUTS
    String

.OUTPUTS
    PSCustomObject

.NOTES
    Author:  Mike F Robbins
    Website: http://mikefrobbins.com
    Twitter: @mikefrobbins
#>

    [CmdletBinding()]
    param (

    )

    #Function Body

}
```

Добавленную справку на основе комментариев можно получить так же, как встроенные команды по умолчанию.

Весь синтаксис написания функции в PowerShell может показаться слишком объемным и перегруженным, особенно для тех, кто только начинает работу с этой оболочкой. Часто, если я не могу вспомнить какой-то синтаксис, я открываю вторую копию ISE на отдельном мониторе, просматриваю фрагмент "Cmdlet (расширенная функция) — Complete" и одновременно ввожу код для функции. В интегрированной среде сценариев PowerShell доступ к фрагментам кода можно получить с помощью сочетания клавиш <kbd>CTRL</kbd>+<kbd>J</kbd>.

## <a name="summary"></a>Сводка

В этой главе вы изучили основы написания функций в PowerShell, узнали, как преобразовать функцию в расширенную функцию, и ознакомились с некоторыми самыми важными моментами, которые следует учитывать при написании функций PowerShell, такими как проверка параметров, вывод подробных данных, входные данные конвейера, обработка ошибок и справка на основе комментариев.

## <a name="review"></a>Просмотр

1. Как получить список утвержденных глаголов в PowerShell?
1. Как преобразовать функцию PowerShell в расширенную функцию?
1. Когда следует добавлять параметры **WhatIf** и **Confirm** в функции PowerShell?
1. Как преобразовать неустранимую ошибку в устранимую?
1. Для чего нужно добавлять справку на основе комментариев к функциям?

## <a name="recommended-reading"></a>Рекомендуем прочесть

- [about_Functions][]
- [about_Functions_Advanced_Parameters][]
- [about_CommonParameters][]
- [about_Functions_CmdletBindingAttribute][]
- [about_Functions_Advanced][]
- [about_Try_Catch_Finally][]
- [about_Comment_Based_Help][]
- [Видео: создание инструментов PowerShell с помощью расширенных функций и модулей сценариев][]

<!-- link references -->
[about_Functions]: /powershell/module/microsoft.powershell.core/about/about_functions
[about_Functions_Advanced_Parameters]: /powershell/module/microsoft.powershell.core/about/about_functions_advanced_parameters
[about_CommonParameters]: /powershell/module/microsoft.powershell.core/about/about_commonparameters
[about_Functions_CmdletBindingAttribute]: /powershell/module/microsoft.powershell.core/about/about_functions_cmdletbindingattribute
[about_Functions_Advanced]: /powershell/module/microsoft.powershell.core/about/about_functions_advanced
[about_Try_Catch_Finally]: /powershell/module/microsoft.powershell.core/about/about_try_catch_finally
[about_Comment_Based_Help]: /powershell/module/microsoft.powershell.core/about/about_comment_based_help
[Видео: создание инструментов PowerShell с помощью расширенных функций и модулей сценариев]: https://mikefrobbins.com/2016/05/26/video-powershell-toolmaking-with-advanced-functions-and-script-modules/
[Регистр Pascal]: /dotnet/standard/design-guidelines/capitalization-conventions
