---
description: Переменные, которые настраивают поведение PowerShell.
keywords: powershell,командлет
Locale: en-US
ms.date: 04/22/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_preference_variables?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Preference_Variables
ms.openlocfilehash: 2f290020a66b2db15c41cc9581ae3582dda8c96d
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231006"
---
# <a name="about-preference-variables"></a>Сведения о переменных предпочтений

## <a name="short-description"></a>Краткое описание

Переменные, которые настраивают поведение PowerShell.

## <a name="long-description"></a>Подробное описание

PowerShell включает набор переменных, которые позволяют настроить его поведение. Эти переменные предпочтений работают подобно параметрам в системах на основе графического пользовательского интерфейса.

Переменные предпочтений влияют на операционную среду PowerShell, и все команды выполняются в среде. Во многих случаях командлеты имеют параметры, которые можно использовать для переопределения поведения предпочтений для конкретной команды.

В следующей таблице перечислены переменные предпочтений и их значения по умолчанию.

|             Переменная             |       Значение по умолчанию       |
| -------------------------------- | ------------------------- |
| `$ConfirmPreference`             | Высокий                      |
| `$DebugPreference`               | SilentlyContinue          |
| `$ErrorActionPreference`         | Continue                  |
| `$ErrorView`                     | конЦисевиев               |
| `$FormatEnumerationLimit`        | 4                         |
| `$InformationPreference`         | SilentlyContinue          |
| `$LogCommandHealthEvent`         | False (не записано в журнал)        |
| `$LogCommandLifecycleEvent`      | False (не записано в журнал)        |
| `$LogEngineHealthEvent`          | True (в журнале)             |
| `$LogEngineLifecycleEvent`       | True (в журнале)             |
| `$LogProviderLifecycleEvent`     | True (в журнале)             |
| `$LogProviderHealthEvent`        | True (в журнале)             |
| `$MaximumHistoryCount`           | 4096                      |
| `$OFS`                           | (Символ пробела ( `" "` )) |
| `$OutputEncoding`                | Объект UTF8Encoding       |
| `$ProgressPreference`            | Продолжить                  |
| `$PSDefaultParameterValues`      | (Нет-пустая хэш-таблица) |
| `$PSEmailServer`                 | (нет)                    |
| `$PSModuleAutoLoadingPreference` | Все                       |
| `$PSSessionApplicationName`      | wsman                     |
| `$PSSessionConfigurationName`    | `http://schemas.microsoft.com/powershell/Microsoft.PowerShell` |
| `$PSSessionOption`               | См. [$PSSessionOption](#pssessionoption) |
| `$Transcript`                    | (нет)                    |
| `$VerbosePreference`             | SilentlyContinue          |
| `$WarningPreference`             | Continue                  |
| `$WhatIfPreference`              | Неверно                     |

PowerShell включает в себя следующие переменные среды, в которых хранятся пользовательские настройки. Дополнительные сведения об этих переменных среды см. в разделе [about_Environment_Variables](about_Environment_Variables.md).

- `env:PSExecutionPolicyPreference`
- `$env:PSModulePath`

> [!NOTE]
> Изменения в привилегированной переменной вступают в силу только в скриптах и функциях, если эти скрипты или функции определены в той же области видимости, в которой использовалась предпочтение. Дополнительные сведения см. в разделе [about_Scopes](about_Scopes.md).

## <a name="working-with-preference-variables"></a>Работа с переменными предпочтений

В этом документе описываются все переменные предпочтений.

Чтобы отобразить текущее значение конкретной привилегированной переменной, введите имя переменной. Например, следующая команда отображает `$ConfirmPreference` значение переменной.

```powershell
 $ConfirmPreference
```

```Output
High
```

Чтобы изменить значение переменной, используйте инструкцию присваивания. Например, следующая инструкция изменяет `$ConfirmPreference` значение параметра на **Medium**.

```powershell
$ConfirmPreference = "Medium"
```

Заданные значения относятся к текущему сеансу PowerShell. Чтобы сделать переменные эффективными во всех сеансах PowerShell, добавьте их в профиль PowerShell. Дополнительные сведения см. в разделе [about_Profiles](about_Profiles.md).

## <a name="working-remotely"></a>Работа в удаленном режиме

При выполнении команд на удаленном компьютере эти удаленные команды распространяются только на настройки, заданные в клиенте PowerShell удаленного компьютера. Например, при выполнении удаленной команды значение переменной удаленного компьютера `$DebugPreference` определяет реакцию PowerShell на отладку сообщений.

Дополнительные сведения об удаленных командах см. в разделе [about_Remote](about_Remote.md).

### <a name="confirmpreference"></a>\$ConfirmPreference

Определяет, будет ли PowerShell автоматически запрашивать подтверждение перед запуском командлета или функции.

`$ConfirmPreference`Допустимые значения переменной: **High** , **Medium** или **Low**. Командлетам и функциям назначается риск: **высокий** , **средний** или **низкий**. Если значение `$ConfirmPreference` переменной меньше или равно риску, назначенному командлету или функции, PowerShell автоматически запрашивает подтверждение перед выполнением командлета или функции.

Если `$ConfirmPreference` переменная имеет значение **None** , PowerShell никогда не выводит запрос автоматически перед выполнением командлета или функции.

Чтобы изменить поведение подтверждения для всех командлетов и функций в сеансе, измените `$ConfirmPreference` значение переменной.

Чтобы переопределить `$ConfirmPreference` для одной команды, используйте параметр **Confirm** командлета или функции. Чтобы запросить подтверждение, используйте `-Confirm` . Чтобы отключить подтверждение, используйте `-Confirm:$false` .

Допустимые значения `$ConfirmPreference` :

- **Нет** : PowerShell не выводит запрос автоматически. Чтобы запросить подтверждение определенной команды, используйте параметр **Confirm** командлета или функции.
- **Низкий** : PowerShell запрашивает подтверждение перед выполнением командлетов или функций с низким, средним или высоким уровнем риска.
- **Средний** : PowerShell запрашивает подтверждение перед выполнением командлетов или функций со средним или высоким уровнем риска.
- **Высокий** : PowerShell запрашивает подтверждение перед запуском командлетов или функций с высоким риском.

#### <a name="detailed-explanation"></a>Подробное описание

PowerShell может автоматически запрашивать подтверждение перед выполнением действия. Например, если командлет или функция значительно затронет систему, чтобы удалить данные или использовать значительный объем системных ресурсов.

```powershell
Remove-Item -Path C:\file.txt
```

```Output
Confirm
Are you sure you want to perform this action?
Performing operation "Remove File" on Target "C:\file.txt".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [?] Help (default is "Y"):
```

Оценка риска — это атрибут командлета или функции, известный как его **ConfirmImpact**. Пользователи не могут изменить этот параметр.

Командлеты и функции, которые могут представлять риск для системы, имеют параметр **Confirm** , который можно использовать для запроса или подавления подтверждения отдельной команды.

Так как большинство командлетов и функций используют значение риска по умолчанию ( **ConfirmImpact** ) **Medium** , а значение по умолчанию `$ConfirmPreference` — **High** , возникает нередкое автоматическое подтверждение. Однако можно активировать автоматическое подтверждение, изменив значение `$ConfirmPreference` на **средний** или **низкий**.

#### <a name="examples"></a>Примеры

В этом примере показано воздействие `$ConfirmPreference` значения переменной по умолчанию **High**. **Высокое** значение служит только для подтверждения командлетов и функций с высоким риском. Поскольку большинство командлетов и функций являются средним риском, они не подтверждают и не `Remove-Item` удаляют файл. `-Confirm`При добавлении команды к команде пользователю предлагается подтверждение.

```powershell
$ConfirmPreference
```

```Output
High
```

```powershell
Remove-Item -Path C:\temp1.txt
```

Используйте `-Confirm` для запроса подтверждения.

```powershell
Remove-Item -Path C:\temp2.txt -Confirm
```

```Output
Confirm
Are you sure you want to perform this action?
Performing operation "Remove File" on Target "C:\temp2.txt".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All
[?] Help (default is "Y"):
```

В следующем примере показан результат изменения значения `$ConfirmPreference` на **Medium**. Так как большинство командлетов и функций являются средним уровнем риска, они автоматически подтверждаются. Чтобы отключить запрос подтверждения для одной команды, используйте параметр **Confirm** со значением `$false` .

```powershell
$ConfirmPreference = "Medium"
Remove-Item -Path C:\temp2.txt
```

```Output
Confirm
Are you sure you want to perform this action?
Performing operation "Remove File" on Target "C:\temp2.txt".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All
[?] Help (default is "Y"):
```

```powershell
Remove-Item -Path C:\temp3.txt -Confirm:$false
```

### <a name="debugpreference"></a>\$DebugPreference

Определяет реакцию PowerShell на отладку сообщений, созданных скриптом, командлетом или поставщиком, или с помощью `Write-Debug` команды в командной строке.

Некоторые командлеты отображают сообщения об отладке, которые обычно являются техническими сообщениями, предназначенными для программистов и специалистов технической поддержки. По умолчанию сообщения отладки не отображаются, но можно отобразить сообщения отладки, изменив значение `$DebugPreference` .

Для отображения или скрытия сообщений об отладке для определенной команды можно использовать параметр **отладки** Common командлета. См. сведения в разделе [about_CommonParameters](about_CommonParameters.md).

Допустимы следующие значения.

- **Остановить** : отображает сообщение отладки и прекращает выполнение. Записывает ошибку в консоль.
- **Запрос** : отображает сообщение об отладке и спрашивает, нужно ли продолжить. Добавление общего параметра **Debug** к команде, если команда настроена для создания сообщения отладки, изменяет значение `$DebugPreference` переменной на " **запрос** ".
- **Продолжить** : отображает сообщение отладки и продолжает выполнение.
- **SilentlyContinue** : (по умолчанию) не оказывает никакого влияния. Сообщение отладки не отображается, и выполнение продолжается без прерывания.

#### <a name="examples"></a>Примеры

В следующих примерах показан результат изменения значений `$DebugPreference` при `Write-Debug` входе команды в командную строку.
Это изменение затрагивает все сообщения отладки, включая сообщения, созданные командлетами и скриптами. В примерах показан параметр **Debug** , который отображает или скрывает сообщения отладки, связанные с одной командой.

В этом примере показано воздействие `$DebugPreference` значения переменной по умолчанию **SilentlyContinue**. По умолчанию `Write-Debug` сообщение отладки командлета не отображается, и обработка продолжится. При использовании параметра **Debug** он переопределяет предпочтение для одной команды. Отобразится сообщение отладки.

```powershell
$DebugPreference
```

```Output
SilentlyContinue
```

```powershell
Write-Debug -Message "Hello, World"
```

```powershell
Write-Debug -Message "Hello, World" -Debug
```

```Output
DEBUG: Hello, World
```

В этом примере показан результат действия `$DebugPreference` со значением **Continue** . Отобразится сообщение отладки, и команда продолжит обработку.

```powershell
$DebugPreference = "Continue"
Write-Debug -Message "Hello, World"
```

```Output
DEBUG: Hello, World
```

В этом примере используется параметр **Debug** со значением, `$false` чтобы подавить сообщение для одной команды. Сообщение отладки не отображается.

```powershell
Write-Debug -Message "Hello, World" -Debug:$false
```

В этом примере показано, как `$DebugPreference` задается значение параметра « **останавливает** ». Появится сообщение об отладке, и команда будет остановлена.

```powershell
$DebugPreference = "Stop"
Write-Debug -Message "Hello, World"
```

```Output
DEBUG: Hello, World
Write-Debug : The running command stopped because the preference variable
 "DebugPreference" or common parameter is set to Stop: Hello, World
At line:1 char:1
+ Write-Debug -Message "Hello, World"
```

В этом примере используется параметр **Debug** со значением, `$false` чтобы подавить сообщение для одной команды. Сообщение отладки не отображается, и обработка не остановлена.

```powershell
Write-Debug -Message "Hello, World" -Debug:$false
```

В этом примере показан результат `$DebugPreference` задания значения запроса. **Inquire** Появится сообщение об отладке, и пользователю будет предложено подтвердить.

```powershell
$DebugPreference = "Inquire"
Write-Debug -Message "Hello, World"
```

```Output
DEBUG: Hello, World

Confirm
Continue with this operation?
[Y] Yes  [A] Yes to All  [H] Halt Command  [?] Help (default is "Y"):
```

В этом примере используется параметр **Debug** со значением, `$false` чтобы подавить сообщение для одной команды. Сообщение отладки не отображается, и обработка продолжится.

```powershell
Write-Debug -Message "Hello, World" -Debug:$false
```

### <a name="erroractionpreference"></a>\$ErrorActionPreference

Определяет, как PowerShell реагирует на устранимую ошибку, которая не останавливает обработку командлетов. Например, в командной строке или в скрипте, командлете или поставщике, например в ошибках, создаваемых `Write-Error` командлетом.

Можно использовать общий параметр командлета **ErrorAction** , чтобы переопределить предпочтения для определенной команды.

Допустимы следующие значения.

- **Останов** — введите отладчик при возникновении ошибки или при возникновении исключения.
- **Продолжить** : (по умолчанию) отображает сообщение об ошибке и продолжает выполнение.
- **Ignore** : подавляет вывод сообщения об ошибке и продолжение выполнения команды. Значение **Ignore** предназначено для использования в отдельных командах, а не для использования в качестве сохраненного предпочтения. **Ignore** не является допустимым значением для `$ErrorActionPreference` переменной.
- **Запрос** : отображает сообщение об ошибке и запрашивает, нужно ли продолжить.
- **SilentlyContinue** : не влияет. Сообщение об ошибке не отображается, и выполнение продолжается без прерывания.
- **Остановить** : отображает сообщение об ошибке и прекращает выполнение. В дополнение к созданной ошибке, значение « **останавливает** » создает объект актионпреференцестопексцептион для потока ошибок.
  поток
- **Приостановить** : автоматически приостанавливает задание рабочего процесса, чтобы обеспечить дальнейшее исследование. После изучения рабочий процесс можно возобновить. Значение **приостановки** предназначено для использования в отдельных командах, а не для использования в качестве сохраненного предпочтения. **Приостановка** не является допустимым значением для `$ErrorActionPreference` переменной.

`$ErrorActionPreference` и параметр **ErrorAction** не влияет на то, как PowerShell реагирует на прерывание ошибок, которые останавливают обработку командлетов. Дополнительные сведения об общем параметре **ErrorAction** см. в разделе [about_CommonParameters](about_CommonParameters.md).

#### <a name="examples"></a>Примеры

В этих примерах показано воздействие различных значений `$ErrorActionPreference` переменной. Параметр **ErrorAction** используется для переопределения `$ErrorActionPreference` значения.

В этом примере показано `$ErrorActionPreference` значение по умолчанию, **продолжить**. Создается устранимая ошибка. Сообщение отображается и обработка продолжится.

```powershell
# Change the ErrorActionPreference to 'Continue'
$ErrorActionPreference = 'Continue'
# Generate a non-terminating error and continue processing the script.
Write-Error -Message  'Test Error' ; Write-Host 'Hello World'
```

```Output
Write-Error: Test Error
Hello World
```

В этом примере показано `$ErrorActionPreference` значение по умолчанию — **запрос**. Выводится сообщение об ошибке, и отображается запрос на ввод действия.

```powershell
# Change the ErrorActionPreference to 'Inquire'
$ErrorActionPreference = 'Inquire'
Write-Error -Message 'Test Error' ; Write-Host 'Hello World'
```

```Output
Confirm
Test Error
[Y] Yes  [A] Yes to All  [H] Halt Command  [S] Suspend  [?] Help (default is "Y"):
```

В этом примере показан `$ErrorActionPreference` набор для **SilentlyContinue**.
Сообщение об ошибке подавляется.

```powershell
# Change the ErrorActionPreference to 'SilentlyContinue'
$ErrorActionPreference = 'SilentlyContinue'
# Generate an error message
Write-Error -Message 'Test Error' ; Write-Host 'Hello World'
# Error message is suppressed and script continues processing
```

```Output
Hello World
```

В этом примере показан `$ErrorActionPreference` набор для **отмены**. Он также показывает дополнительный объект, созданный для `$Error` переменной.

```powershell
# Change the ErrorActionPreference to 'Stop'
$ErrorActionPreference = 'Stop'
# Error message is is generated and script stops processing
Write-Error -Message 'Test Error' ; Write-Host 'Hello World'

# Show the ActionPreferenceStopException and the error generated
$Error[0]
$Error[1]
```

```Output
Write-Error: Test Error

ErrorRecord                 : Test Error
WasThrownFromThrowStatement : False
TargetSite                  : System.Collections.ObjectModel.Collection`1[System.Management.Automation.PSObject]
                              Invoke(System.Collections.IEnumerable)
StackTrace                  :    at System.Management.Automation.Runspaces.PipelineBase.Invoke(IEnumerable input)
                                 at Microsoft.PowerShell.Executor.ExecuteCommandHelper(Pipeline tempPipeline,
                              Exception& exceptionThrown, ExecutionOptions options)
Message                     : The running command stopped because the preference variable "ErrorActionPreference" or
                              common parameter is set to Stop: Test Error
Data                        : {System.Management.Automation.Interpreter.InterpretedFrameInfo}
InnerException              :
HelpLink                    :
Source                      : System.Management.Automation
HResult                     : -2146233087

Write-Error: Test Error
```

### <a name="errorview"></a>\$еррорвиев

Определяет формат вывода сообщений об ошибках в PowerShell.

Допустимы следующие значения.

- **КонЦисевиев** : (по умолчанию) предоставляет краткое сообщение об ошибке и рефакторингное представление для расширенных построителей модулей. Если ошибка происходит из командной строки, это сообщение об ошибке одной строки. В противном случае вы получите многострочное сообщение об ошибке, содержащее ошибку, и указатель на ошибку, указывающий, где она встречается в этой строке. Если терминал поддерживает виртуальный терминал, то для предоставления цветовой контрастности используются коды цветов ANSI. Цвет диакритических знаков можно изменить в `$Host.PrivateData.ErrorAccentColor` . Используйте `Get-Error` командлет, чтобы получить исчерпывающее подробное представление о полном сообщении об ошибке, включая внутренние исключения.

  **КонЦисевиев** был добавлен в PowerShell 7.

- **Нормалвиев** : подробное представление, предназначенное для большинства пользователей. Состоит из описания ошибки и имени объекта, участвующего в ошибке.

- **Категоривиев** : краткое структурированное представление, предназначенное для рабочих сред. Используется следующий формат:

  {Category}: ({TargetName}: {TargetType}): [{Activity}], {Reason}

Дополнительные сведения о полях в **категоривиев** см. в разделе класс [ерроркатегоринфо](/dotnet/api/system.management.automation.errorcategoryinfo) .

#### <a name="examples"></a>Примеры

В этом примере показано, как возникает ошибка, если значением `$ErrorView` по умолчанию является **конЦисевиев**. `Get-ChildItem` используется для поиска несуществующего каталога.

```powershell
Get-ChildItem -path 'C:\NoRealDirectory'
```

```Output
Get-ChildItem: Cannot find path 'C:\NoRealDirectory' because it does not exist.
```

В этом примере показано, как возникает ошибка, если значением `$ErrorView` по умолчанию является **конЦисевиев**. `Script.ps1` запускается и вызывает ошибку из `Get-Item` инструкции.

```powershell
./Script.ps1
```

```Output
Get-Item: C:\Script.ps1
Line |
  11 | Get-Item -Path .\stuff
     | ^ Cannot find path 'C:\demo\stuff' because it does not exist.
```

В этом примере показано, как возникает ошибка при изменении значения `$ErrorView` на **нормалвиев**. `Get-ChildItem` используется для поиска несуществующего файла.

```powershell
Get-ChildItem -Path C:\nofile.txt
```

```Output
Get-ChildItem : Cannot find path 'C:\nofile.txt' because it does not exist.
At line:1 char:1
+ Get-ChildItem -Path C:\nofile.txt
```

В этом примере показано, как эта же ошибка возникает при `$ErrorView` изменении значения на **категоривиев**.

```powershell
$ErrorView = "CategoryView"
Get-ChildItem -Path C:\nofile.txt
```

```Output
ObjectNotFound: (C:\nofile.txt:String) [Get-ChildItem], ItemNotFoundException
```

В этом примере показано, что значение `$ErrorView` влияет только на отображение ошибок. Она не изменяет структуру объекта Error, который хранится в `$Error` автоматической переменной. Дополнительные сведения об `$Error` автоматической переменной см. в разделе [about_automatic_variables](about_Automatic_Variables.md).

Следующая команда принимает объект **ерроррекорд** , связанный с самой последней ошибкой в массиве ошибок, **элемент 0** , и форматирует все свойства объекта Error в списке.

```powershell
$Error[0] | Format-List -Property * -Force
```

```Output
PSMessageDetails      :
Exception             : System.Management.Automation.ItemNotFoundException:
                          Cannot find path 'C:\nofile.txt' because it does
                          not exist.
                        at System.Management.Automation.SessionStateInternal.
                          GetChildItems(String path, Boolean recurse, UInt32
                          depth, CmdletProviderContext context)
                        at System.Management.Automation.ChildItemCmdlet
                          ProviderIntrinsics.Get(String path, Boolean
                          recurse, UInt32 depth, CmdletProviderContext context)
                        at Microsoft.PowerShell.Commands.GetChildItemCommand.
                          ProcessRecord()
TargetObject          : C:\nofile.txt
CategoryInfo          : ObjectNotFound: (C:\nofile.txt:String) [Get-ChildItem],
                          ItemNotFoundException
FullyQualifiedErrorId : PathNotFound,
                          Microsoft.PowerShell.Commands.GetChildItemCommand
ErrorDetails          :
InvocationInfo        : System.Management.Automation.InvocationInfo
ScriptStackTrace      : at <ScriptBlock>, <No file>: line 1
PipelineIterationInfo : {0, 1}
```

### <a name="formatenumerationlimit"></a>\$форматенумератионлимит

Определяет, сколько элементов перечисления включается в отображение. Эта переменная не влияет на базовые объекты, а только на отображение. Если значение меньше `$FormatEnumerationLimit` числа перечисленных элементов, в PowerShell добавляется многоточие ( `...` ), показывающее, что элементы не показаны.

**Допустимые значения** : целые числа ( `Int32` )

**Значение по умолчанию** : 4

#### <a name="examples"></a>Примеры

В этом примере показано, как использовать `$FormatEnumerationLimit` переменную для улучшения отображения перечисленных элементов.

В этом примере команда создает таблицу, в которой перечислены все службы, выполняющиеся на компьютере, в двух группах: одна для **запуска** служб, а другая для **остановленных** служб. Он использует `Get-Service` команду для получения всех служб, а затем отправляет результаты по конвейеру в `Group-Object` командлет, который группирует результаты по состоянию службы.

Результатом является таблица со списком состояний в столбце **имя** и процессами в столбце **Group** . Чтобы изменить метки столбцов, используйте хэш-таблицу, описанную в разделе [about_Hash_Tables](about_Hash_Tables.md). Дополнительные сведения см. в примерах в разделе [Format-Table](xref:Microsoft.PowerShell.Utility.Format-Table).

Найти текущее значение `$FormatEnumerationLimit` .

```powershell
$FormatEnumerationLimit
```

```Output
4
```

Список всех служб, сгруппированных по **состоянию**. Существует не более четырех служб, перечисленных в столбце **Group** для каждого состояния, так как `$FormatEnumerationLimit` имеет значение **4**.

```powershell
Get-Service | Group-Object -Property Status
```

```Output
Count  Name       Group
-----  ----       -----
60     Running    {AdtAgent, ALG, Ati HotKey Poller, AudioSrv...}
41     Stopped    {Alerter, AppMgmt, aspnet_state, ATI Smart...}
```

Чтобы увеличить количество элементов в списке, увеличьте значение `$FormatEnumerationLimit` до **1000**. Используйте `Get-Service` и `Group-Object` для вывода служб.

```powershell
$FormatEnumerationLimit = 1000
Get-Service | Group-Object -Property Status
```

```Output
Count  Name       Group
-----  ----       -----
60     Running    {AdtAgent, ALG, Ati HotKey Poller, AudioSrv, BITS, CcmExec...
41     Stopped    {Alerter, AppMgmt, aspnet_state, ATI Smart, Browser, CiSvc...
```

Используйте `Format-Table` с параметром **Wrap** для вывода списка служб.

```powershell
Get-Service | Group-Object -Property Status | Format-Table -Wrap
```

```Output
Count  Name       Group
-----  ----       -----
60     Running    {AdtAgent, ALG, Ati HotKey Poller, AudioSrv, BITS, CcmExec,
                  Client for NFS, CryptSvc, DcomLaunch, Dhcp, dmserver,
                  Dnscache, ERSvc, Eventlog, EventSystem, FwcAgent, helpsvc,
                  HidServ, IISADMIN, InoRPC, InoRT, InoTask, lanmanserver,
                  lanmanworkstation, LmHosts, MDM, Netlogon, Netman, Nla,
                  NtLmSsp, PlugPlay, PolicyAgent, ProtectedStorage, RasMan,
                  RemoteRegistry, RpcSs, SamSs, Schedule, seclogon, SENS,
                  SharedAccess, ShellHWDetection, SMT PSVC, Spooler,
                  srservice, SSDPSRV, stisvc, TapiSrv, TermService, Themes,
                  TrkWks, UMWdf, W32Time, W3SVC, WebClient, winmgmt, wscsvc,
                  wuauserv, WZCSVC, zzInterix}

41     Stopped    {Alerter, AppMgmt, aspnet_state, ATI Smart, Browser, CiSvc,
                  ClipSrv, clr_optimization_v2.0.50727_32, COMSysApp,
                  CronService, dmadmin, FastUserSwitchingCompatibility,
                  HTTPFilter, ImapiService, Mapsvc, Messenger, mnmsrvc,
                  MSDTC, MSIServer, msvsmon80, NetDDE, NetDDEdsdm, NtmsSvc,
                  NVSvc, ose, RasAuto, RDSessMgr, RemoteAccess, RpcLocator,
                  SCardSvr, SwPrv, SysmonLog, TlntSvr, upnphost, UPS, VSS,
                  WmdmPmSN, Wmi, WmiApSrv, xmlprov}
```

### <a name="informationpreference"></a>\$InformationPreference

`$InformationPreference`Переменная позволяет задать параметры потока информации, которые должны отображаться для пользователей. В частности, информационные сообщения, добавленные в команды или скрипты путем добавления командлета [Write-Information](xref:Microsoft.PowerShell.Utility.Write-Information) . Если используется параметр **InformationAction** , его значение переопределяет значение `$InformationPreference` переменной. `Write-Information` впервые появился в PowerShell 5,0.

Допустимы следующие значения.

- **Остановить** : останавливает выполнение команды или скрипта при возникновении `Write-Information` команды.
- **Запрос** : отображает информационное сообщение, указанное в `Write-Information` команде, а затем спрашивает, хотите ли вы продолжить.
- **Продолжить** : отображает информационное сообщение и продолжает выполняться.
- **Приостановка** доступна только для рабочих процессов, которые не поддерживаются в PowerShell 6 и более поздних версиях.
- **SilentlyContinue** : (по умолчанию) не оказывает никакого влияния. Информационные сообщения не отображаются, и сценарий продолжается без прерывания.

### <a name="logevent"></a>\$Событие log *

Переменные настройки **события log *** определяют, какие типы событий записываются в журнал событий PowerShell в Просмотр событий. По умолчанию регистрируются только события подсистемы и поставщика. Но вы можете использовать переменные настройки **событий Log *** для настройки журнала, например ведения журнала событий о командах.

Ниже приведены переменные настройки **события log *** .

- `$LogCommandHealthEvent`: Регистрирует ошибки и исключения при инициализации и обработке команды. Значение по умолчанию — `$false` (не заносится в журнал).
- `$LogCommandLifecycleEvent`: Записывает в журнал запуск и остановку команд и командных конвейеров и исключений безопасности при обнаружении команд. Значение по умолчанию — `$false` (не заносится в журнал).
- `$LogEngineHealthEvent`: Регистрирует ошибки и сбои сеансов. Значение по умолчанию — `$true` (Протоколируется).
- `$LogEngineLifecycleEvent`: Записывает в журнал открытие и закрытие сеансов. Значение по умолчанию — `$true` (Протоколируется).
- `$LogProviderHealthEvent`: Регистрирует ошибки поставщика, такие как ошибки чтения и записи, ошибки поиска и ошибки вызова. Значение по умолчанию — `$true` (Протоколируется).
- `$LogProviderLifecycleEvent`: Регистрирует Добавление и удаление поставщиков PowerShell. Значение по умолчанию — `$true` (Протоколируется). Дополнительные сведения о поставщиках PowerShell см. в разделе [about_Providers](about_Providers.md).

Чтобы включить **событие log *** , введите переменную со значением `$true` , например:

```powershell
$LogCommandLifeCycleEvent = $true
```

Чтобы отключить тип события, введите переменную со значением `$false` , например:

```powershell
$LogCommandLifeCycleEvent = $false
```

Включенные события вступают в силу только для текущей консоли PowerShell. Чтобы применить конфигурацию ко всем консолям, сохраните параметры переменной в профиле PowerShell. Дополнительные сведения см. в разделе [about_Profiles](about_Profiles.md).

### <a name="maximumhistorycount"></a>\$максимумхисторикаунт

Определяет, сколько команд сохраняется в журнале команд для текущего сеанса.

**Допустимые значения** : 1-32768 ( `Int32` )

**По умолчанию** : 4096

Чтобы определить количество команд, сохраненных в журнале команд, введите:

```powershell
(Get-History).Count
```

Чтобы просмотреть команды, сохраненные в журнале сеанса, используйте `Get-History` командлет. Дополнительные сведения см. в разделе [about_History](about_History.md).

### <a name="ofs"></a>\$OFS

Разделитель полей вывода (OFS) определяет символ, разделяющий элементы массива, которые преобразуются в строку.

**Допустимые значения** : любая строка.

**По умолчанию** : пробел

По умолчанию `$OFS` переменная не существует, а разделитель выходного файла является пробелом, но можно добавить эту переменную и задать ее в любой строке. Вы можете изменить значение `$OFS` в своем сеансе, введя `$OFS="<value>"` .

> [!NOTE]
> Если вы ожидаете значение по умолчанию пробела ( `" "` ) в скрипте, модуле или выходных данных конфигурации, будьте внимательны в том, что `$OFS` значение по умолчанию не было изменено в других местах кода.

#### <a name="examples"></a>Примеры

В этом примере показано, что пространство используется для разделения значений при преобразовании массива в строку. В этом случае массив целых чисел хранится в переменной, а переменная преобразуется в строку.

```powershell
$array = 1,2,3,4
[string]$array
```

```Output
1 2 3 4
```

Чтобы изменить разделитель, добавьте `$OFS` переменную, назначив ей значение.
Переменная должна иметь имя `$OFS` .

```powershell
$OFS = "+"
[string]$array
```

```Output
1+2+3+4
```

Чтобы восстановить поведение по умолчанию, можно назначить пробел ( `" "` ) значению `$OFS` или удалить переменную. Следующие команды удаляют переменную и проверяют, что разделитель является пробелом.

```powershell
Remove-Variable OFS
[string]$array
```

```Output
1 2 3 4
```

### <a name="outputencoding"></a>\$OutputEncoding

Определяет метод кодировки символов, используемый PowerShell при отправке текста в другие приложения.

Например, если приложение возвращает строки в Юникоде в PowerShell, может потребоваться изменить значение на **UnicodeEncoding** , чтобы правильно отправить символы.

Допустимы следующие значения: объекты, производные от класса кодирования, такие как **ASCIIEncoding** , **сбкскодепажеенкодинг** , **UTF7Encoding** , **UTF8Encoding** , **UTF32Encoding** и **UnicodeEncoding**.

**По умолчанию** : объект UTF8Encoding (System. Text. UTF8Encoding)

#### <a name="examples"></a>Примеры

В этом примере показано, как заставить команду Windows **findstr.exe** работать в PowerShell на компьютере, локализованном для языка, который использует символы Юникода, например китайский.

Первая команда находит значение `$OutputEncoding` . Поскольку значение является объектом кодировки, отобразится только свойство **EncodingName** .

```powershell
$OutputEncoding.EncodingName
```

В этом примере используется команда **findstr.exe** для поиска двух китайских символов, которые содержатся в `Test.txt` файле. При выполнении этой **findstr.exe** команды в командной строке Windows ( **cmd.exe** ) **findstr.exe** находит символы в текстовом файле. Однако при выполнении той **findstr.exe** же команды в PowerShell символы не найдены, так как PowerShell отправляет их в **findstr.exe** в тексте ASCII, а не в тексте в Юникоде.

```powershell
findstr <Unicode-characters>
```

Чтобы команда работала в PowerShell, присвойте `$OutputEncoding` свойству **OutputEncoding** консоли значение, основанное на языковом стандарте, выбранном для Windows. Поскольку **OutputEncoding** является статическим свойством консоли, в команде следует использовать двойные двоеточия ( `::` ).

```powershell
$OutputEncoding = [console]::OutputEncoding
$OutputEncoding.EncodingName
```

```Output
OEM United States
```

После изменения кодировки команда **findstr.exe** находит символы Юникода.

```powershell
findstr <Unicode-characters>
```

```Output
test.txt:         <Unicode-characters>
```

### <a name="progresspreference"></a>\$прогресспреференце

Определяет, как PowerShell реагирует на обновления хода выполнения, создаваемые сценарием, командлетом или поставщиком, например индикаторами выполнения, созданными командлетом [записи](xref:Microsoft.PowerShell.Utility.Write-Progress) .
`Write-Progress`Командлет создает индикаторы выполнения, отображающие состояние команды.

Допустимы следующие значения.

- **Завершение** : не отображает индикатор выполнения. Вместо этого отображается сообщение об ошибке и прекращается выполнение.
- **Запрос** : не отображает индикатор выполнения. Запрашивает разрешение на продолжение. При ответе с помощью `Y` или `A` отображается индикатор выполнения.
- **Продолжить** : (по умолчанию) отображает индикатор выполнения и продолжает выполнение.
- **SilentlyContinue** : выполняет команду, но не отображает индикатор выполнения.

### <a name="psemailserver"></a>\$Привилегированной PSEmailServer

Указывает сервер электронной почты по умолчанию, используемый для отправки сообщений электронной почты. Эта переменная предпочтений используется командлетами, которые отправляют электронную почту, например командлет [Send-MailMessage](xref:Microsoft.PowerShell.Utility.Send-MailMessage) .

### <a name="psdefaultparametervalues"></a>\$псдефаултпараметервалуес

Задает значения по умолчанию для параметров командлетов и дополнительных функций.
Значение `$PSDefaultParameterValues` является хэш-таблицей, в которой ключ состоит из имени командлета и имени параметра, разделенных двоеточием ( `:` ). Значение — это пользовательское значение по умолчанию, которое вы указали.

`$PSDefaultParameterValues` впервые появился в PowerShell 3,0.

Дополнительные сведения об этой переменной предпочтений см. в разделе [about_Parameters_Default_Values](about_Parameters_Default_Values.md).

### <a name="psmoduleautoloadingpreference"></a>\$PSModuleAutoloadingPreference

Включает и отключает автоматический импорт модулей в сеансе. По умолчанию используется значение **ALL** . Независимо от значения переменной можно импортировать модуль с помощью [Import-Module](xref:Microsoft.PowerShell.Core.Import-Module) .

Допустимые значения:

- **Все** : модули импортируются автоматически при первом использовании. Чтобы импортировать модуль, необходимо получить или использовать любую команду в модуле. Например, воспользуйтесь `Get-Command`.
- **Модулекуалифиед** : модули импортируются автоматически только в том случае, если пользователь использует полное имя модуля команды в модуле. Например, если пользователь вводит `MyModule\MyCommand` , PowerShell импортирует модуль **MyModule** .
- **Нет** : автоматический импорт модулей отключен в сеансе. Чтобы импортировать модуль, используйте `Import-Module` командлет.

Дополнительные сведения об автоматическом импорте модулей см. в разделе [about_Modules](about_Modules.md).

### <a name="pssessionapplicationname"></a>\$PSSessionApplicationName

Указывает имя приложения по умолчанию для удаленной команды, которая использует веб-службы для технологии управления (WS-Management). Дополнительные сведения см. в разделе [About служба удаленного управления Windows](/windows/win32/winrm/about-windows-remote-management).

Имя системного приложения по умолчанию — `WSMAN` , но вы можете использовать эту переменную настройки, чтобы изменить значение по умолчанию.

Имя приложения — это последний узел в универсальном коде ресурса (URI) соединения. Например, имя приложения в следующем примере URI — `WSMAN` .

`http://Server01:8080/WSMAN`

Имя приложения по умолчанию используется, если в удаленной команде не указан универсальный код ресурса (URI) соединения или имя приложения.

Служба **WinRM** использует имя приложения для выбора прослушивателя, который будет обслуживать запрос на подключение. Значение параметра должно соответствовать значению свойства **URLPrefix** прослушивателя на удаленном компьютере.

Чтобы переопределить системные значения по умолчанию и значение этой переменной и выбрать другое имя приложения для конкретного сеанса, используйте параметры **ConnectionURI** или **applicationName** командлетов [New-PSSession](xref:Microsoft.PowerShell.Core.New-PSSession), [Enter-PSSession](xref:Microsoft.PowerShell.Core.Enter-PSSession)или [Invoke-Command](xref:Microsoft.PowerShell.Core.Invoke-Command) .

`$PSSessionApplicationName`Переменная предпочтений задается на локальном компьютере, но указывает на прослушиватель на удаленном компьютере. Если указанное имя приложения не существует на удаленном компьютере, команда для установки сеанса завершается с ошибкой.

### <a name="pssessionconfigurationname"></a>\$PSSessionConfigurationName

Задает конфигурацию сеанса по умолчанию, используемую для **PSSession** , созданной в текущем сеансе.

Эта переменная предпочтений задается на локальном компьютере, но она указывает конфигурацию сеанса, расположенную на удаленном компьютере.

Значение `$PSSessionConfigurationName` переменной является полным URI ресурса.

Значение по умолчанию `http://schemas.microsoft.com/PowerShell/microsoft.PowerShell` указывает на конфигурацию сеанса **Microsoft. PowerShell** на удаленном компьютере.

Если указано только имя конфигурации, в начале добавляется следующий URI схемы:

`http://schemas.microsoft.com/PowerShell/`

Можно переопределить значение по умолчанию и выбрать другую конфигурацию сеанса для конкретного сеанса с помощью параметра **configurationName** `New-PSSession` `Enter-PSSession` `Invoke-Command` командлетов, или.

Значение этой переменной можно изменить в любое время. В этом случае следует помнить, что выбранная конфигурация сеанса должна существовать на удаленном компьютере. В противном случае команда для создания сеанса, использующего конфигурацию сеанса, завершится ошибкой.

Эта переменная предпочтений не определяет, какие конфигурации локального сеанса используются, когда удаленные пользователи создают сеанс, который подключается к этому компьютеру.
Однако можно использовать разрешения для конфигураций локального сеанса, чтобы определить, какие пользователи могут их использовать.

### <a name="pssessionoption"></a>\$PSSessionOption

Устанавливает значения по умолчанию для дополнительных параметров пользователя в удаленном сеансе.
Эти настройки параметров переопределяют системные значения по умолчанию для параметров сеанса.

`$PSSessionOption`Переменная содержит объект **PSSessionOption** . Дополнительные сведения см. в разделе [System. Management. Automation. Remoting. PSSessionOption](/dotnet/api/system.management.automation.remoting.pssessionoption).
Каждое свойство объекта представляет параметр сеанса. Например, свойство « **уплотнение** » включает сжатие данных во время сеанса.

По умолчанию `$PSSessionOption` переменная содержит объект **PSSessionOption** со значениями по умолчанию для всех параметров, как показано ниже.

```Output
MaximumConnectionRedirectionCount : 5
NoCompression                     : False
NoMachineProfile                  : False
ProxyAccessType                   : None
ProxyAuthentication               : Negotiate
ProxyCredential                   :
SkipCACheck                       : False
SkipCNCheck                       : False
SkipRevocationCheck               : False
OperationTimeout                  : 00:03:00
NoEncryption                      : False
UseUTF16                          : False
IncludePortInSPN                  : False
OutputBufferingMode               : None
Culture                           :
UICulture                         :
MaximumReceivedDataSizePerCommand :
MaximumReceivedObjectSize         : 209715200
ApplicationArguments              :
OpenTimeout                       : 00:03:00
CancelTimeout                     : 00:01:00
IdleTimeout                       : -00:00:00.0010000
```

Описание этих параметров и дополнительные сведения см. в разделе [New-PSSessionOption](xref:Microsoft.PowerShell.Core.New-PSSessionOption). Дополнительные сведения об удаленных командах и сеансах см. в разделе [about_Remote](about_Remote.md) и [about_PSSessions](about_PSSessions.md).

Чтобы изменить значение `$PSSessionOption` привилегированной переменной, используйте `New-PSSessionOption` командлет, чтобы создать объект **PSSessionOption** с предпочтительными значениями параметров. Сохраните выходные данные в переменную с именем `$PSSessionOption` .

```powershell
$PSSessionOption = New-PSSessionOption -NoCompression
```

Чтобы использовать `$PSSessionOption` переменную предпочтений в каждом сеансе PowerShell, добавьте `New-PSSessionOption` команду, которая создает `$PSSessionOption` переменную в профиле PowerShell. Дополнительные сведения см. в разделе [about_Profiles](about_Profiles.md).

Можно задать пользовательские параметры для определенного удаленного сеанса. Заданные параметры имеют приоритет над системными значениями по умолчанию и значением `$PSSessionOption` привилегированной переменной.

Чтобы задать настраиваемые параметры сеанса, используйте `New-PSSessionOption` командлет для создания объекта **PSSessionOption** . Затем используйте объект **PSSessionOption** в качестве значения параметра **SessionOption** в командлетах, которые создают сеанс, например `New-PSSession` , `Enter-PSSession` и `Invoke-Command` .

### <a name="transcript"></a>$Transcript

Используется `Start-Transcript` для указания имени и расположения файла транскрипции. Если значение параметра **path** не указано, `Start-Transcript` использует путь в значении `$Transcript` глобальной переменной. Если эта переменная не создана, сохраняет записи `Start-Transcript` в `$Home\My Documents` каталоге в виде `\PowerShell_transcript.<time-stamp>.txt` файлов.

### <a name="verbosepreference"></a>\$VerbosePreference

Определяет, как PowerShell реагирует на подробные сообщения, создаваемые сценарием, командлетом или поставщиком, например сообщения, созданные командлетом [Write-Verbose](xref:Microsoft.PowerShell.Utility.Write-Verbose) .
Подробные сообщения описывают действия, выполняемые для выполнения команды.

По умолчанию подробные сообщения не отображаются, но это поведение можно изменить, изменив значение `$VerbosePreference` .

Для отображения или скрытия подробных сообщений для определенной команды можно использовать параметр **verbose** Common. См. сведения в разделе [about_CommonParameters](about_CommonParameters.md).

Допустимы следующие значения.

- **Остановить**. Отображает подробное сообщение и сообщение об ошибке, а затем прекращает выполнение.
- **Запрос** : Отображает подробное сообщение, а затем выводит приглашение, указывающее, нужно ли продолжить.
- **Продолжить** : Отображает подробное сообщение, а затем продолжает выполнение.
- **SilentlyContinue** : (по умолчанию) не отображает подробное сообщение. Продолжение исполнения.

#### <a name="examples"></a>Примеры

В этих примерах показан результат различных значений `$VerbosePreference` параметров и параметр **verbose** для переопределения значения предпочтения.

В этом примере показано действие значения **SilentlyContinue** , которое является значением по умолчанию. Команда использует параметр **Message** , но не записывает сообщение в консоль PowerShell.

```powershell
Write-Verbose -Message "Verbose message test."
```

При использовании параметра **verbose** сообщение записывается.

```powershell
Write-Verbose -Message "Verbose message test." -Verbose
```

```Output
VERBOSE: Verbose message test.
```

В этом примере показан результат выполнения значения **Continue** . `$VerbosePreference`Переменная установлена для **продолжения** и отображается сообщение.

```powershell
$VerbosePreference = "Continue"
Write-Verbose -Message "Verbose message test."
```

```Output
VERBOSE: Verbose message test.
```

В этом примере используется параметр **verbose** со значением `$false` , переопределяющим значение **Continue** . Сообщение не отображается.

```powershell
Write-Verbose -Message "Verbose message test." -Verbose:$false
```

В этом примере показано воздействие значения " **Отключить** ". `$VerbosePreference`Для переменной задано значение " **останавливаться** ", и отображается сообщение. Команда остановлена.

```powershell
$VerbosePreference = "Stop"
Write-Verbose -Message "Verbose message test."
```

```Output
VERBOSE: Verbose message test.
Write-Verbose : The running command stopped because the preference variable
  "VerbosePreference" or common parameter is set to Stop: Verbose message test.
At line:1 char:1
+ Write-Verbose -Message "Verbose message test."
```

В этом примере используется параметр **verbose** со значением `$false` , переопределяющим значение параметра **останавливает** . Сообщение не отображается.

```powershell
Write-Verbose -Message "Verbose message test." -Verbose:$false
```

В этом примере показано **воздействие значения запроса** . `$VerbosePreference`Для переменной задано значение " **запрос** ". Отображается сообщение, и пользователю предлагается подтверждение.

```powershell
$VerbosePreference = "Inquire"
Write-Verbose -Message "Verbose message test."
```

```Output
VERBOSE: Verbose message test.

Confirm
Continue with this operation?
[Y] Yes  [A] Yes to All  [H] Halt Command  [?] Help (default is "Y"):
```

В этом примере используется параметр **verbose** со значением `$false` , переопределяющим значение запроса **Inquire** . Пользователю не выводится запрос, и сообщение не отображается.

```powershell
Write-Verbose -Message "Verbose message test." -Verbose:$false
```

### <a name="warningpreference"></a>\$WarningPreference

Определяет, как PowerShell реагирует на предупреждающие сообщения, созданные сценарием, командлетом или поставщиком, например сообщения, созданные командлетом [Write-Warning](xref:Microsoft.PowerShell.Utility.Write-Warning) .

По умолчанию отображаются предупреждающие сообщения, и выполнение продолжится, но это поведение можно изменить, изменив значение `$WarningPreference` .

Вы можете использовать общий параметр **WarningAction** командлета, чтобы определить реакцию PowerShell на предупреждения от определенной команды. См. сведения в разделе [about_CommonParameters](about_CommonParameters.md).

Допустимы следующие значения.

- **Остановить** : отображает предупреждающее сообщение и сообщение об ошибке, а затем прекращает выполнение.
- **Запрос** : отображает предупреждающее сообщение, а затем запрашивает разрешение на продолжение.
- **Продолжить** : (по умолчанию) отображает предупреждающее сообщение, а затем продолжает выполнение.
- **SilentlyContinue** : не отображает предупреждающее сообщение. Продолжение исполнения.

#### <a name="examples"></a>Примеры

В этих примерах показано воздействие различных значений `$WarningPreference` .
Параметр **WarningAction** переопределяет значение предпочтения.

В этом примере показано воздействие значения по умолчанию на **Continue**.

```powershell
$m = "This action can delete data."
Write-Warning -Message $m
```

```Output
WARNING: This action can delete data.
```

В этом примере для подавления предупреждения используется параметр **WarningAction** со значением **SilentlyContinue** . Сообщение не отображается.

```powershell
$m = "This action can delete data."
Write-Warning -Message $m -WarningAction SilentlyContinue
```

В этом примере `$WarningPreference` переменная изменяется на значение **SilentlyContinue** . Сообщение не отображается.

```powershell
$WarningPreference = "SilentlyContinue"
$m = "This action can delete data."
Write-Warning -Message $m
```

В этом примере параметр **WarningAction** используется для отмены при создании предупреждения.

```powershell
$m = "This action can delete data."
Write-Warning -Message $m -WarningAction Stop
```

```Output
WARNING: This action can delete data.
Write-Warning : The running command stopped because the preference variable
  "WarningPreference" or common parameter is set to Stop:
    This action can delete data.
At line:1 char:1
+ Write-Warning -Message $m -WarningAction Stop
```

В этом примере `$WarningPreference` переменная изменяется на значение **Inquire** запроса. Пользователю предлагается подтверждение.

```powershell
$WarningPreference = "Inquire"
$m = "This action can delete data."
Write-Warning -Message $m
```

```Output
WARNING: This action can delete data.

Confirm
Continue with this operation?
[Y] Yes  [A] Yes to All  [H] Halt Command  [?] Help (default is "Y"):
```

В этом примере используется параметр **WarningAction** со значением **SilentlyContinue**. Команда продолжит выполняться, и сообщение не будет выводиться.

```powershell
$m = "This action can delete data."
Write-Warning -Message $m -WarningAction SilentlyContinue
```

В этом примере `$WarningPreference` значение изменяется на « **останавливается** ».

```powershell
$WarningPreference = "Stop"
$m = "This action can delete data."
Write-Warning -Message $m
```

```Output
WARNING: This action can delete data.
Write-Warning : The running command stopped because the preference variable
  "WarningPreference" or common parameter is set to Stop:
    This action can delete data.
At line:1 char:1
+ Write-Warning -Message $m
```

В этом примере используется **WarningAction** **со значением запроса** . Пользователь получает запрос при возникновении предупреждения.

```powershell
$m = "This action can delete data."
Write-Warning -Message $m -WarningAction Inquire
```

```Output
WARNING: This action can delete data.

Confirm
Continue with this operation?
[Y] Yes  [A] Yes to All  [H] Halt Command  [?] Help (default is "Y"):
```

### <a name="whatifpreference"></a>\$вхатифпреференце

Определяет, включается ли параметр **WhatIf** автоматически для каждой команды, поддерживающей эту возможность. Если параметр **WhatIf** включен, командлет сообщает о ожидаемом результате команды, но не выполняет команду.

Допустимы следующие значения.

- **False** ( **0** , не включено): (по умолчанию) **WhatIf** не включен автоматически. Чтобы включить его вручную, используйте параметр **WhatIf** командлета.
- **True** ( **1** , включено): **WhatIf** автоматически включается для любой команды, которая его поддерживает. Пользователи могут использовать параметр **WhatIf** со значением **false** , чтобы отключить его вручную, например `-WhatIf:$false` .

#### <a name="examples"></a>Примеры

В этих примерах показано воздействие различных значений `$WhatIfPreference` .
Они показывают, как использовать параметр **WhatIf** для переопределения значения предпочтений для определенной команды.

В этом примере показан результат использования `$WhatIfPreference` переменной значения по умолчанию, равной **false**. Используйте `Get-ChildItem` , чтобы убедиться, что файл существует.
`Remove-Item` Удаляет файл. После удаления файла можно проверить его удаление с помощью `Get-ChildItem` .

```powershell
Get-ChildItem -Path .\test.txt
Remove-Item -Path ./test.txt
```

```Output
    Directory: C:\Test

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a---           9/13/2019    10:53             10 test.txt
```

```powershell
Get-ChildItem -Path .\test.txt
```

```Output
Get-ChildItem : Cannot find path 'C:\Test\test.txt' because it does not exist.
At line:1 char:1
+ Get-ChildItem -File test.txt
```

В этом примере показан результат использования параметра **WhatIf** , если значение `$WhatIfPreference` равно **false**.

Убедитесь, что файл существует.

```powershell
Get-ChildItem -Path .\test2.txt
```

```Output
    Directory: C:\Test

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a---           2/28/2019    17:06             12 test2.txt
```

Используйте параметр **WhatIf** для определения результата попытки удаления файла.

```powershell
Remove-Item -Path .\test2.txt -WhatIf
```

```Output
What if: Performing the operation "Remove File" on target "C:\Test\test2.txt".
``````

Убедитесь, что файл не был удален.

```powershell
Get-ChildItem -Path .\test2.txt
```

```Output
    Directory: C:\Test

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a---           2/28/2019    17:06             12 test2.txt
```

В этом примере показан результат выполнения `$WhatIfPreference` переменной значения **true**. При использовании `Remove-Item` для удаления файла отображается путь к файлу, но файл не удаляется.

Попытка удаления файла. Появится сообщение о том, что произойдет при `Remove-Item` запуске, но файл не будет удален.

```powershell
$WhatIfPreference = "True"
Remove-Item -Path .\test2.txt
```

```Output
What if: Performing the operation "Remove File" on target "C:\Test\test2.txt".
```

Используйте `Get-ChildItem` для проверки того, что файл не был удален.

```powershell
Get-ChildItem -Path .\test2.txt
```

```Output
    Directory: C:\Test

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a---           2/28/2019    17:06             12 test2.txt
```

В этом примере показано, как удалить файл, если значение `$WhatIfPreference` равно **true**. В нем используется параметр **WhatIf** со значением `$false` . Используйте `Get-ChildItem` для проверки удаления файла.

```powershell
Remove-Item -Path .\test2.txt -WhatIf:$false
Get-ChildItem -Path .\test2.txt
```

```Output
Get-ChildItem : Cannot find path 'C:\Test\test2.txt' because it does not exist.
At line:1 char:1
+ Get-ChildItem -Path .\test2.txt
```

Ниже приведены примеры `Get-Process` командлета, который не поддерживает **WhatIf** и `Stop-Process` поддерживает **WhatIf**. `$WhatIfPreference`Значение переменной равно **true**.

`Get-Process` не поддерживает **WhatIf**. При выполнении команды отображается процесс **Winword** .

```powershell
Get-Process -Name Winword
```

```Output
 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
    130   119.84     173.38       8.39   15024   4 WINWORD
```

`Stop-Process` поддерживает **WhatIf**. Процесс **Winword** не остановлен.

```powershell
Stop-Process -Name Winword
```

```Output
What if: Performing the operation "Stop-Process" on target "WINWORD (15024)".
```

Поведение WhatIf можно переопределить с `Stop-Process` **WhatIf** помощью параметра **WhatIf** со значением `$false` . Процесс **Winword** остановлен.

```powershell
Stop-Process -Name Winword -WhatIf:$false
```

Чтобы убедиться, что процесс **Winword** был остановлен, используйте `Get-Process` .

```powershell
Get-Process -Name Winword
```

```Output
Get-Process : Cannot find a process with the name "Winword".
  Verify the process name and call the cmdlet again.
At line:1 char:1
+ Get-Process -Name Winword
```

## <a name="see-also"></a>См. также статью

[about_Automatic_Variables](about_Automatic_Variables.md)

[about_CommonParameters](about_CommonParameters.md)

[about_Environment_Variables](about_Environment_Variables.md)

[about_Profiles](about_Profiles.md)

[about_Remote](about_Remote.md)

[about_Scopes](about_Scopes.md)

[about_Variables](about_Variables.md)
