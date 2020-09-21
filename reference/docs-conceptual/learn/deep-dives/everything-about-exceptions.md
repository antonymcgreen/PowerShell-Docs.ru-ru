---
title: Все, что вы хотели знать об исключениях
description: Обработка ошибок — это лишь часть процесса написания кода.
ms.date: 05/23/2020
ms.custom: contributor-KevinMarquette
ms.openlocfilehash: cd17ae6b5ded052c93923b648155a4dda8956b34
ms.sourcegitcommit: 94c39b0d36b948d3a62707ae8a3be00efe606434
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/11/2020
ms.locfileid: "90012567"
---
# <a name="everything-you-wanted-to-know-about-exceptions"></a>Все, что вы хотели знать об исключениях

Обработка ошибок — это лишь часть процесса написания кода. Зачастую можно проверить, выполняются ли условия для ожидаемого поведения. При возникновении непредвиденной ситуации необходимо переключиться на обработку исключений. Вы можете легко обрабатывать исключения, созданные кодом других разработчиков, или создавать собственные исключения, которые смогут обработать другие.

> [!NOTE]
> [Оригинал][] этой статьи впервые был опубликован в блоге автора [@KevinMarquette][]. Команда разработчиков PowerShell благодарит Кевина за то, что он поделился с нами этим материалом. Читайте его блог — [PowerShellExplained.com][].

## <a name="basic-terminology"></a>Базовая терминология

Прежде чем двигаться дальше, необходимо разобраться с основными терминами.

### <a name="exception"></a>Исключение

Исключение подобно событию, которое создается, когда не удается справиться с проблемой путем обычной обработки ошибок.
Примерами проблем, которые приводят к исключениям, могут служить попытки деления числа на ноль и нехватка памяти. Иногда автор кода, который вы используете, создает исключения для определенных проблем в случае их возникновения.

### <a name="throw-and-catch"></a>Throw и Catch

Когда происходит исключение, мы говорим, что оно вызвано. Чтобы обработать вызванное исключение, его необходимо перехватить. Если вызывается исключение, которое не перехватывается никакими объектами, выполнение скрипта прекращается.

### <a name="the-call-stack"></a>Стек вызовов

Стек вызовов — это список функций, которые вызывали друг друга. При вызове функции она добавляется в стек или вверх списка. При выходе из функции или возврате ею значения она удаляется из стека.

При вызове исключения выполняется проверка этого стека вызовов, чтобы обработчик исключений мог его перехватить.

### <a name="terminating-and-non-terminating-errors"></a>Неустранимые и устранимые ошибки

Исключение обычно является неустранимой ошибкой. Вызванное исключение либо перехватывается, либо завершает текущее выполнение. По умолчанию устранимая ошибка генерируется `Write-Error` и приводит к добавлению ошибки в выходной поток без вызова исключения.

Обращаю внимание на это потому, что `Write-Error` и другие устранимые ошибки не активируют `catch`.

### <a name="swallowing-an-exception"></a>Игнорирование исключения

Это ситуация, когда ошибка перехватывается только для того, чтобы ее подавить. Используйте эту возможность с осторожностью, поскольку это может существенно усложнить устранение неполадок.

## <a name="basic-command-syntax"></a>Основной синтаксис команды

Ниже приведен краткий обзор основного синтаксиса обработки исключений, используемого в PowerShell.

### <a name="throw"></a>Ключевое слово throw

Чтобы вызвать собственное событие исключения, воспользуйтесь ключевым словом `throw`.

```powershell
function Start-Something
{
    throw "Bad thing happened"
}
```

Это приведет к созданию исключения во время выполнения, которое является неустранимой ошибкой. Оно обрабатывается с помощью `catch` в вызывающей функции или приводит к выходу из скрипта с сообщением следующего вида.

```powershell
PS> Start-Something

Bad thing happened
At line:1 char:1
+ throw "Bad thing happened"
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : OperationStopped: (Bad thing happened:String) [], RuntimeException
    + FullyQualifiedErrorId : Bad thing happened
```

#### <a name="write-error--erroraction-stop"></a>Параметр -ErrorAction Stop командлета Write-Error

Я упоминал, что по умолчанию `Write-Error` не вызывает неустранимую ошибку. Если указать `-ErrorAction Stop`, `Write-Error` создаст неустранимую ошибку, которую можно обработать с помощью `catch`.

```powershell
Write-Error -Message "Houston, we have a problem." -ErrorAction Stop
```

Благодарю Ли Дейли за напоминание о том, что `-ErrorAction Stop` можно использовать таким образом.

#### <a name="cmdlet--erroraction-stop"></a>Параметр -ErrorAction Stop в командлете

Если указать `-ErrorAction Stop` в любой расширенной функции или командлете, все инструкции `Write-Error` будут преобразованы в неустранимые ошибки, которые приводят к остановке выполнения или могут быть обработаны с помощью `catch`.

```powershell
Start-Something -ErrorAction Stop
```

### <a name="trycatch"></a>Try и Catch

Принцип обработки исключений в PowerShell (и многих других языках) состоит в том, что сначала к разделу кода применяется `try`, а если происходит ошибка, к нему применяется `catch`. Приведем краткий пример.

```powershell
try
{
    Start-Something
}
catch
{
    Write-Output "Something threw an exception"
}

try
{
    Start-Something -ErrorAction Stop
}
catch
{
    Write-Output "Something threw an exception or used Write-Error"
}
```

Скрипт `catch` выполняется только в том случае, если произошла неустранимая ошибка. Если `try` выполняется правильно, `catch` пропускается.

### <a name="tryfinally"></a>Try и Finally

Иногда ошибку обрабатывать не требуется, но необходимо выполнить определенный код в зависимости от того, было ли создано исключение. Именно это и делает скрипт `finally`.

Взгляните на этот пример.

```powershell
$command = [System.Data.SqlClient.SqlCommand]::New(queryString, connection)
$command.Connection.Open()
$command.ExecuteNonQuery()
$command.Connection.Close()
```

Всякий раз, когда вы открываете ресурс или подключаетесь к нему, его следует закрыть. Если `ExecuteNonQuery()` вызывает исключение, соединение не закрывается. Вот тот же код в блоке `try/finally`.

```powershell
$command = [System.Data.SqlClient.SqlCommand]::New(queryString, connection)
try
{
    $command.Connection.Open()
    $command.ExecuteNonQuery()
}
finally
{
    $command.Connection.Close()
}
```

В этом примере соединение закрывается при возникновении ошибки. Оно также закрывается при отсутствии ошибок. При этом всякий раз выполняется скрипт `finally`.

Так как исключение не перехватывается, оно по-прежнему распространяет в стек вызовов.

### <a name="trycatchfinally"></a>Try, catch и finally

Вполне допустимо использовать `catch` и `finally` вместе. В большинстве случаев используется либо один, либо другой скрипт, но вам могут встретиться сценарии, в которых используются они оба.

## <a name="psitem"></a>$PSItem

Теперь, когда мы разобрались с основами, можно изучить вопрос подробнее.

В блоке `catch` существует автоматическая переменная (`$PSItem` или `$_`) типа `ErrorRecord`, содержащая сведения об исключении. Ниже приведен краткий обзор некоторых ключевых свойств.

В этих примерах для создания такого исключения я использовал недопустимый путь в `ReadAllText`.

```powershell
[System.IO.File]::ReadAllText( '\\test\no\filefound.log')
```

### <a name="psitemtostring"></a>PSItem.ToString()

Этот метод позволяет получить максимально понятное сообщение, которое можно использовать при ведении журнала и выводе общего результата. `ToString()` вызывается автоматически, если в строку помещена переменная `$PSItem`.

```powershell
catch
{
    Write-Output "Ran into an issue: $($PSItem.ToString())"
}

catch
{
    Write-Output "Ran into an issue: $PSItem"
}
```

### <a name="psiteminvocationinfo"></a>$PSItem.InvocationInfo

Это свойство содержит дополнительные сведения, собираемые PowerShell о функции или скрипте, которые вызвали исключение. Ниже приведено свойство `InvocationInfo` из примера созданного мною исключения.

```powershell
PS> $PSItem.InvocationInfo | Format-List *

MyCommand             : Get-Resource
BoundParameters       : {}
UnboundArguments      : {}
ScriptLineNumber      : 5
OffsetInLine          : 5
ScriptName            : C:\blog\throwerror.ps1
Line                  :     Get-Resource
PositionMessage       : At C:\blog\throwerror.ps1:5 char:5
                        +     Get-Resource
                        +     ~~~~~~~~~~~~
PSScriptRoot          : C:\blog
PSCommandPath         : C:\blog\throwerror.ps1
InvocationName        : Get-Resource
```

Здесь приведены важные сведения: имя `ScriptName`, строка кода `Line` и номер строки `ScriptLineNumber`, из которой инициирован вызов.

### <a name="psitemscriptstacktrace"></a>$PSItem.ScriptStackTrace

Это свойство показывает порядок вызовов функций, ведущих к коду, в котором создано исключение.

```powershell
PS> $PSItem.ScriptStackTrace
at Get-Resource, C:\blog\throwerror.ps1: line 13
at Start-Something, C:\blog\throwerror.ps1: line 5
at <ScriptBlock>, C:\blog\throwerror.ps1: line 18
```

Я выполняю вызовы функций в пределах одного скрипта, но таким же образом можно отслеживать функции при использовании нескольких скриптов.

### <a name="psitemexception"></a>$PSItem.Exception

Это, собственно, и есть вызванное исключение.

#### <a name="psitemexceptionmessage"></a>$PSItem.Exception.Message

Это общее сообщение, которое описывает исключение и служит хорошей отправной точкой при устранении неполадок. Для большинства исключений предусмотрены сообщения по умолчанию, но при необходимости их можно настроить по своему усмотрению.

```powershell
PS> $PSItem.Exception.Message

Exception calling "ReadAllText" with "1" argument(s): "The network path was not found."
```

Это еще одно сообщение, возвращаемое при вызове `$PSItem.ToString()`, если для `ErrorRecord` не задан другой его вариант.

#### <a name="psitemexceptioninnerexception"></a>$PSItem.Exception.InnerException

Исключения могут содержать внутренние исключения. Это часто случается, когда вызываемый код перехватывает одно исключение и вызывает другое. Исходное исключение помещается в новое исключение.

```powershell
PS> $PSItem.Exception.InnerExceptionMessage
The network path was not found.
```

Я вернусь к этому вопросу позже, когда буду рассказывать о повторном вызове исключений.

#### <a name="psitemexceptionstacktrace"></a>$PSItem.Exception.StackTrace

Это свойство `StackTrace` для исключения. Я продемонстрировал принцип работы свойства `ScriptStackTrace` выше, но это предназначено для вызовов управляемого кода.

```Output
at System.IO.FileStream.Init(String path, FileMode mode, FileAccess access, Int32 rights, Boolean
 useRights, FileShare share, Int32 bufferSize, FileOptions options, SECURITY_ATTRIBUTES secAttrs,
 String msgPath, Boolean bFromProxy, Boolean useLongPath, Boolean checkHost)
at System.IO.FileStream..ctor(String path, FileMode mode, FileAccess access, FileShare share, Int32
 bufferSize, FileOptions options, String msgPath, Boolean bFromProxy, Boolean useLongPath, Boolean
 checkHost)
at System.IO.StreamReader..ctor(String path, Encoding encoding, Boolean detectEncodingFromByteOrderMarks,
 Int32 bufferSize, Boolean checkHost)
at System.IO.File.InternalReadAllText(String path, Encoding encoding, Boolean checkHost)
at CallSite.Target(Closure , CallSite , Type , String )
```

Эта трассировка стека выполняется только в случае, если событие вызвано из управляемого кода. Я вызываю функцию .NET Framework напрямую, так что это все, что можно увидеть в этом примере. Как правило, трассировка стека просматривается, чтобы найти место остановки кода и начало системных вызовов.

## <a name="working-with-exceptions"></a>Работа с исключениями

Для работы с исключениями недостаточно базового синтаксиса и основных свойств.

### <a name="catching-typed-exceptions"></a>Перехват типизированных исключений

Исключения можно перехватывать избирательно. Исключения имеют тип, задав который можно перехватить только исключения определенного типа.

```powershell
try
{
    Start-Something -Path $path
}
catch [System.IO.FileNotFoundException]
{
    Write-Output "Could not find $path"
}
catch [System.IO.IOException]
{
        Write-Output "IO error with the file: $path"
}
```

Каждый блок `catch` проверяется на наличие исключения заданного типа, пока не будет найден тот, в котором оно создается.
Важно понимать, что исключения могут наследоваться от других исключений. В приведенном выше примере `FileNotFoundException` наследуется от `IOException`. Поэтому, если исключение `IOException` было первым, будет вызвано именно оно. Даже если совпадений несколько, вызывается только один блок catch.

При наличии исключения `System.IO.PathTooLongException` исключение `IOException` распознается как совпадение, но при наличии исключения `InsufficientMemoryException` перехватывать его нечем, поэтому оно распространится по стеку.

### <a name="catch-multiple-types-at-once"></a>Одновременный перехват нескольких типов

С помощью одной инструкции `catch` можно перехватывать несколько типов исключений одновременно.

```powershell
try
{
    Start-Something -Path $path -ErrorAction Stop
}
catch [System.IO.DirectoryNotFoundException],[System.IO.FileNotFoundException]
{
    Write-Output "The path or file was not found: [$path]"
}
catch [System.IO.IOException]
{
    Write-Output "IO error with the file: [$path]"
}
```

Благодарю `/u/Sheppard_Ra` за предложение добавить этот раздел.

### <a name="throwing-typed-exceptions"></a>Вызов типизированных исключений

В PowerShell можно вызывать типизированные исключения. Вместо вызова `throw` со строкой:

```powershell
throw "Could not find: $path"
```

используйте ускоритель исключений следующим образом:

```powershell
throw [System.IO.FileNotFoundException] "Could not find: $path"
```

Но в таком случае необходимо указать сообщение.

Можно также создать новый экземпляр исключения для вызова. При этом сообщение является необязательным, так как в системе предусмотрены сообщения по умолчанию для всех встроенных исключений.

```powershell
throw [System.IO.FileNotFoundException]::new()
throw [System.IO.FileNotFoundException]::new("Could not find path: $path")
```

Если вы не используете PowerShell 5.0 или более поздних версий, необходимо использовать устаревший подход с применением `New-Object`.

```powershell
throw (New-Object -TypeName System.IO.FileNotFoundException )
throw (New-Object -TypeName System.IO.FileNotFoundException -ArgumentList "Could not find path: $path")
```

Как упоминалось в предыдущем разделе, используя типизированное исключение, вы (или другие пользователи) можете перехватывать исключения по типу.

#### <a name="write-error--exception"></a>Параметр -Exception командлета Write-Error

Эти типизированные исключения можно добавить в `Write-Error` и при этом перехватывать исключения с помощью `catch` по их типу. Используйте командлет `Write-Error`, как показано в следующих примерах.

```powershell
# with normal message
Write-Error -Message "Could not find path: $path" -Exception ([System.IO.FileNotFoundException]::new()) -ErrorAction Stop

# With message inside new exception
Write-Error -Exception ([System.IO.FileNotFoundException]::new("Could not find path: $path")) -ErrorAction Stop

# Pre PS 5.0
Write-Error -Exception ([System.IO.FileNotFoundException]"Could not find path: $path") -ErrorAction Stop

Write-Error -Message "Could not find path: $path" -Exception ( New-Object -TypeName System.IO.FileNotFoundException ) -ErrorAction Stop
```

Теперь исключение можно перехватить следующим образом.

```powershell
catch [System.IO.FileNotFoundException]
{
    Write-Log $PSItem.ToString()
}
```

#### <a name="the-big-list-of-net-exceptions"></a>Большой список исключений .NET

В дополнение к этой публикации я (при помощи [Сообщество Reddit/r/PowerShell][]) составил основной список, который содержит сотни исключений .NET.

- [Большой список исключений .NET][]

Для начала я ищу в этом списке исключения, которые хорошо подходят для моей ситуации. Следует попытаться использовать исключения в базовом пространстве имен `System`.

### <a name="exceptions-are-objects"></a>Исключения как объекты

При использовании большого числа типизированных исключений следует помнить, что они являются объектами. Различные исключения имеют разные конструкторы и свойства. В документации [FileNotFoundException][] для `System.IO.FileNotFoundException` указано, что для этого исключения можно передать сообщение и путь к файлу.

```powershell
[System.IO.FileNotFoundException]::new("Could not find file", $path)
```

У него есть свойство `FileName`, которое предоставляет путь к этому файлу.

```powershell
catch [System.IO.FileNotFoundException]
{
    Write-Output $PSItem.Exception.FileName
}
```

Сведения о других конструкторах и свойствах объектов см. в документации по [Документация по .NET][].

### <a name="re-throwing-an-exception"></a>Повторный вызов исключения

Если блок `catch` используется только для вызова того же исключения с помощью `throw`, перехватывать его с помощью `catch` не стоит. Перехватывать с помощью `catch` следует только исключение, которое планируется обработать или использовать для выполнения какого-либо действия.

Бывают случаи, когда необходимо выполнить действие с исключением, но при этом вызывать его повторно, чтобы его можно было обработать на более низком уровне. Мы можем написать сообщение или записать проблему в журнал ближе к месту обнаружения, а обработать эту проблему на другом уровне стека.

```powershell
catch
{
    Write-Log $PSItem.ToString()
    throw $PSItem
}
```

Интересно, что `throw` можно вызвать из `catch`, и тогда текущее исключение будет вызвано повторно.

```powershell
catch
{
    Write-Log $PSItem.ToString()
    throw
}
```

Исключение создается повторно, чтобы сохранить исходные сведения о выполнении, например исходный скрипт и номер строки. Если на этом этапе вызывается новое исключение, оно скрывает первоначальное место его возникновения.

#### <a name="re-throwing-a-new-exception"></a>Повторный вызов нового исключения

Если вы перехватили исключение, но хотите вызвать другое, следует вложить исходное исключение в новое. Это позволяет объекту на более низком уровне стека получить к нему доступ как к `$PSItem.Exception.InnerException`.

```powershell
catch
{
    throw [System.MissingFieldException]::new('Could not access field',$PSItem.Exception)
}
```

#### <a name="pscmdletthrowterminatingerror"></a>$PSCmdlet.ThrowTerminatingError()

Единственное, что мне не нравится в использовании `throw` для необработанных исключений, заключается в том, что в качестве причины ошибки в сообщении об ошибке указывается инструкция `throw` и номер проблемной строки.

```Output
Unable to find the specified file.
At line:31 char:9
+         throw [System.IO.FileNotFoundException]::new()
+         ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : OperationStopped: (:) [], FileNotFoundException
    + FullyQualifiedErrorId : Unable to find the specified file.
```

Если сообщение об ошибке сообщает о том, что скрипт работает неправильно из-за вызова `throw` в строке 31, оно не подходит для отображения пользователям скрипта. Оно не сообщает им ничего полезного.

Декстер Дхами отметил, что для устранения этой проблемы я могу использовать `ThrowTerminatingError()`.

```powershell
$PSCmdlet.ThrowTerminatingError(
    [System.Management.Automation.ErrorRecord]::new(
        ([System.IO.FileNotFoundException]"Could not find $Path"),
        'My.ID',
        [System.Management.Automation.ErrorCategory]::OpenError,
        $MyObject
    )
)
```

Если предположить, что метод `ThrowTerminatingError()` вызван внутри функции с именем `Get-Resource`, сообщение об ошибке будет таким, как показано ниже.

```Output
Get-Resource : Could not find C:\Program Files (x86)\Reference
Assemblies\Microsoft\Framework\.NETPortable\v4.6\System.IO.xml
At line:6 char:5
+     Get-Resource -Path $Path
+     ~~~~~~~~~~~~
    + CategoryInfo          : OpenError: (:) [Get-Resource], FileNotFoundException
    + FullyQualifiedErrorId : My.ID,Get-Resource
```

Вы заметили, что в качестве источника проблемы в нем указана функция `Get-Resource`? Теперь пользователь узнает что-то полезное.

Так как значением `$PSItem` является `ErrorRecord`, можно таким же образом использовать `ThrowTerminatingError` для повторного вызова.

```powershell
catch
{
    $PSCmdlet.ThrowTerminatingError($PSItem)
}
```

При этом источник ошибки изменится на командлет, а внутренние данные о функции будут скрыты от его пользователей.

## <a name="try-can-create-terminating-errors"></a>Try как источник неустранимой ошибки

Кирк Манро указывает, что некоторые исключения являются неустранимыми ошибками только при выполнении внутри блока `try/catch`. В этом предоставленном им примере исключение во время выполнения вызывается вследствие деления на ноль.

```powershell
function Start-Something { 1/(1-1) }
```

Вызовем его теперь следующим образом, чтобы код содержал ошибку, но при этом выводилось сообщение.

```powershell
&{ Start-Something; Write-Output "We did it. Send Email" }
```

Однако если поместить этот же код в `try/catch`, то происходит нечто иное.

```powershell
try
{
    &{ Start-Something; Write-Output "We did it. Send Email" }
}
catch
{
    Write-Output "Notify Admin to fix error and send email"
}
```

Ошибка становится неустранимой, а первое сообщение не выводится. Не нравится мне в этом то, что при наличии такого кода в функции поведение становится другим, если использовать `try/catch`.

Сам я не сталкивался с такой проблемой, но это крайний случай, о котором следует помнить.

### <a name="pscmdletthrowterminatingerror-inside-trycatch"></a>Метод $PSCmdlet.ThrowTerminatingError() в try/catch

Одна из особенностей `$PSCmdlet.ThrowTerminatingError()` заключается в том, что в командлете этот метод вызывает неустранимую ошибку, но после выхода из него ошибка становится устранимой. Из-за этого тому, кто вызывает функцию, приходится решать, как следует обрабатывать такую ошибку. В этом случае можно превратить ее снова в неустранимую ошибку с помощью `-ErrorAction Stop` или воспользоваться вызовом из `try{...}catch{...}`.

### <a name="public-function-templates"></a>Шаблоны общих функций

В одной из последних бесед с Кирком Манро мы говорили о том, что он помещает каждый блок `begin`, `process` и `end` во всех своих расширенных функциях в блок `try{...}catch{...}`. В этих универсальных блоках catch у него есть одна строка с методом `$PSCmdlet.ThrowTerminatingError($PSItem)` для обработки всех исключений, вызываемых его функциями.

```powershell
function Start-Something
{
    [CmdletBinding()]
    param()

    process
    {
        try
        {
            ...
        }
        catch
        {
            $PSCmdlet.ThrowTerminatingError($PSItem)
        }
    }
}
```

Поскольку в его функциях все находится в операторе `try`, весь код работает единообразно. Это также позволяет выводить для пользователя понятные сообщения об ошибках, в которых скрыты данные о внутреннем коде.

## <a name="trap"></a>Ключевое слово trap

Я уделил много внимания особенностям блока `try/catch`. Однако прежде чем закрывать эту тему, нужно упомянуть об одной устаревшей функции.

Ключевое слово `trap` помещается в скрипт или функцию для перехвата всех исключений, возникающих в соответствующей области. При возникновении исключения выполняется код в ловушке `trap`, а затем продолжается выполнение стандартного кода. Если происходит несколько исключений, ловушка вызывается снова и снова.

```powershell
trap
{
    Write-Log $PSItem.ToString()
}

throw [System.Exception]::new('first')
throw [System.Exception]::new('second')
throw [System.Exception]::new('third')
```

Я лично никогда не применял этот подход. Однако, судя по скриптам администраторов и контроллеров, которые заносят в журнал абсолютно все исключения, а затем продолжают выполнение, могу сказать, что в нем есть своя польза.

## <a name="closing-remarks"></a>Заключительное слово

Добавление соответствующей обработки исключений в скрипты не только делает эти скрипты более стабильными, но и упрощает устранение таких исключений.

Я уделил так много внимания `throw`, так как это основное понятие, которым мы оперируем при обсуждении обработки исключений. В PowerShell также предоставляется командлет `Write-Error`, справляющийся со всеми ситуациями, в которых следовало бы использовать `throw`. Так что изложенное в этой статье вовсе не означает, что вам обязательно необходимо использовать `throw`.

Теперь, когда я подробно рассказал об обработке исключений, я собираюсь заняться вопросом использования `Write-Error -Stop` для создания ошибок в коде. Я также собираюсь воспользоваться советом Кирка и перейти на использование `ThrowTerminatingError` в качестве обработчика исключений для каждой функции.

<!-- link references -->
[powershellexplained.com]: https://powershellexplained.com/
[Оригинал]: https://powershellexplained.com/2017-04-10-Powershell-exceptions-everything-you-ever-wanted-to-know/
[@KevinMarquette]: https://twitter.com/KevinMarquette
[Сообщество Reddit/r/PowerShell]: https://www.reddit.com/r/PowerShell/comments/64866o/kevmar_all_net_46_exceptions_list_for_use_with/
[Большой список исключений .NET]: https://powershellexplained.com/2017-04-07-all-dotnet-exception-list
[FileNotFoundException]: /dotnet/api/System.IO.FileNotFoundException
[Документация по .NET]: /dotnet/api
