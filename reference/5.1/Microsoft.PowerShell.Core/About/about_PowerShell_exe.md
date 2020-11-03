---
description: Объясняет, как использовать `powershell.exe` интерфейс командной строки. Отображает параметры командной строки и описание синтаксиса.
keywords: powershell,командлет
Locale: en-US
ms.date: 10/05/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_powershell_exe?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_PowerShell_exe
ms.openlocfilehash: ef03558a6b58868b98c9da488934b0bfbbce9fe7
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93232330"
---
# <a name="about-powershellexe"></a>О PowerShell.exe

## <a name="short-description"></a>Краткое описание
Объясняет, как использовать `powershell.exe` интерфейс командной строки. Отображает параметры командной строки и описание синтаксиса.

## <a name="long-description"></a>Полное описание

### <a name="syntax"></a>SYNTAX

```
PowerShell[.exe]
    [-PSConsoleFile <file> | -Version <version>]
    [-NoLogo]
    [-NoExit]
    [-Sta]
    [-Mta]
    [-NoProfile]
    [-NonInteractive]
    [-InputFormat {Text | XML}]
    [-OutputFormat {Text | XML}]
    [-WindowStyle <style>]
    [-EncodedCommand <Base64EncodedCommand>]
    [-ConfigurationName <string>]
    [-File - | <filePath> <args>]
    [-ExecutionPolicy <ExecutionPolicy>]
    [-Command - | { <script-block> [-args <arg-array>] }
                | { <string> [<CommandParameters>] } ]

PowerShell[.exe] -Help | -? | /?
```

### <a name="parameters"></a>Параметры

#### <a name="-psconsolefile-filepath"></a>-PSConsoleFile \<FilePath\>

Загружает указанный файл консоли PowerShell. Введите путь и имя файла консоли. Для создания файла консоли используйте командлет Export-Console в PowerShell.

#### <a name="-version-powershell-version"></a>-Version \<PowerShell Version\>

Запускает заданную версию PowerShell. Допустимые значения: 2.0 и 3.0. Указанная версия должна быть установлена в системе. Если на компьютере установлена оболочка Windows PowerShell 3,0, версия по умолчанию — 3,0.
В противном случае версия по умолчанию — "2,0". Дополнительные сведения см. в разделе [Установка PowerShell](/powershell/scripting/install/installing-windows-powershell).

#### <a name="-nologo"></a>-NoLogo

Скрывает баннер авторских прав при запуске программы.

#### <a name="-noexit"></a>-NoExit

Не завершает работу после выполнения команд запуска.

#### <a name="-sta"></a>-Sta

Запускает PowerShell с использованием многопотокового подразделения. В Windows PowerShell 2.0 по умолчанию используется многопотоковое подразделение (MTA). В Windows PowerShell 3.0 по умолчанию используется однопотоковое подразделение (STA).

#### <a name="-mta"></a>-Mta

Запускает PowerShell с использованием многопотокового подразделения. Этот параметр впервые появился в PowerShell 3.0. В PowerShell 2.0 по умолчанию используется многопотоковое подразделение (MTA). В PowerShell 3.0 по умолчанию используется однопотоковое подразделение (STA).

#### <a name="-noprofile"></a>-NoProfile

Не загружает профиль PowerShell.

#### <a name="-noninteractive"></a>-NonInteractive

Не предоставляет пользователю интерактивную командную строку.

#### <a name="-inputformat-text--xml"></a>-InputFormat {Text | XML}

Описывает формат данных, отправляемых в PowerShell. Допустимые значения: "Text" (текстовые строки) или "XML" (сериализованный формат CLIXML).

#### <a name="-outputformat-text--xml"></a>-OutputFormat {Text | XML}

Определяет формат выходных данных PowerShell. Допустимые значения: "Text" (текстовые строки) или "XML" (сериализованный формат CLIXML).

#### <a name="-windowstyle-window-style"></a>-WindowStyle \<Window style\>

Задает стиль окна для сеанса. Допустимые значения: Normal, Minimized, Maximized и Hidden.

#### <a name="-encodedcommand-base64encodedcommand"></a>-EncodedCommand \<Base64EncodedCommand\>

Принимает строковую версию команды в кодировке Base 64. Используйте этот параметр для отправки в PowerShell команд, требующих сложных кавычек или фигурных скобок. Строка должна быть отформатирована с использованием кодировки UTF-16LE.

#### <a name="-configurationname-string"></a>-ConfigurationName \<string\>

Указывает конечную точку конфигурации, в которой выполняется PowerShell. Это может быть любая конечная точка, зарегистрированная на локальном компьютере, включая конечные точки удаленного взаимодействия PowerShell по умолчанию или пользовательскую конечную точку с конкретными возможностями роли пользователя.

#### <a name="-file----filepath-args"></a>-File-| \<filePath\>\<args\>

Если значение **File** равно "-", текст команды считывается из стандартного ввода.
Запуск `powershell -File -` без перенаправленного стандартного ввода запускает обычный сеанс. Это то же самое, что не указывает параметр **файла** .

Если значение **файла** является путем к файлу, сценарий выполняется в локальной области ("с последовательной точкой"), чтобы функции и переменные, создаваемые сценарием, были доступны в текущем сеансе. Введите путь к файлу сценария и любые параметры. **File** должен быть последним параметром в команде. Все значения, введенные после параметра **File** , обрабатываются как путь к файлу скрипта и параметры, передаваемые этому скрипту.

Передаваемые в скрипт параметры имеют вид строк литералов (после интерпретации текущей оболочкой). Например, если вы используете **cmd.exe** и хотите передать значение переменной среды, используйте синтаксис **cmd.exe** : `powershell.exe -File .\test.ps1 -TestParam %windir%`

В отличие от этого, выполнение `powershell.exe -File .\test.ps1 -TestParam $env:windir` в **cmd.exe** приводит к получению сценария, получающего литеральную строку, `$env:windir` так как она не имеет специального значения для текущей оболочки **cmd.exe** . `$env:windir`Стиль ссылки на переменную среды _можно_ использовать внутри параметра **команды** , так как он будет интерпретирован как код PowerShell.

Аналогично, если вы хотите выполнить ту же команду из **пакетного скрипта** , используйте `%~dp0` вместо `.\` или `$PSScriptRoot` для представления текущего каталога выполнения: `powershell.exe -File %~dp0test.ps1 -TestParam %windir%` .
Если вместо этого используется `.\test.ps1` , PowerShell выдаст ошибку, так как не может найти литеральный путь. `.\test.ps1`

Если значение **File** является путем к файлу, то **File** _должен_ быть последним параметром в команде, так как все символы, введенные после имени параметра **файла** , будут интерпретированы как путь к файлу скрипта, за которым следуют параметры сценария.

Можно включить параметры и значения скрипта в значение параметра **File** . Пример: `-File .\Get-Script.ps1 -Domain Central`

Обычно параметры-переключатели сценария включаются или опускаются.
Например, следующая команда использует параметр **ALL** `Get-Script.ps1` файла скрипта: `-File .\Get-Script.ps1 -All`

В редких случаях может потребоваться указать **логическое** значение для параметра.
Невозможно передать явное логическое значение для параметра Switch при выполнении сценария таким образом. Это ограничение было удалено в PowerShell 6 ( `pwsh.exe` ).

#### <a name="-executionpolicy-executionpolicy"></a>-ExecutionPolicy \<ExecutionPolicy\>

Задает политику выполнения по умолчанию для текущего сеанса и сохраняет ее в `$env:PSExecutionPolicyPreference` переменной среды. Этот параметр не изменяет политику выполнения PowerShell, заданную в реестре. Дополнительные сведения о политиках выполнения PowerShell, включая список допустимых значений, см. в статье [about_Execution_Policies](about_Execution_Policies.md).

#### <a name="-command"></a>-Command

Выполняет указанные команды (и любые параметры), как если бы они были введены в командной строке PowerShell, а затем завершает работу, если `NoExit` не указан параметр.

Значение **команды** может быть `-` , блоком скрипта или строкой. Если значение **Command** равно `-` , текст команды считывается из стандартного ввода.

Параметр **команды** принимает блок сценария только для выполнения, если он может распознать значение, передаваемое **команде** , в качестве типа **ScriptBlock** . Это возможно _только_ при запуске `powershell.exe` с другого узла PowerShell. Тип **ScriptBlock** может содержаться в существующей переменной, возвращенной из выражения, или в процессе анализа узлом PowerShell в виде литерального блока скрипта, заключенного в фигурные скобки ( `{}` ), перед передачей в `powershell.exe` .

```powershell
powershell -Command {Get-WinEvent -LogName security}
```

В не `cmd.exe` существует такого понятия, как блок сценария (или тип **ScriptBlock** ), поэтому значение, передаваемое **команде** , _всегда_ будет строкой. Вы можете написать блок сценария в строке, но вместо выполнения его поведение будет таким, как если бы вы набирали его в типичном приглашении PowerShell, возвращая содержимое блока сценария обратно.

Строка, передаваемая **команде** , по-прежнему выполняется как код PowerShell, поэтому в первом месте при запуске из не требуется закрывающая фигурная скобка блока script `cmd.exe` . Для выполнения встроенного блока сценария, определенного внутри строки, можно использовать [оператор вызова](about_operators.md#special-operators) `&`.

```cmd
pwsh -Command "& {Get-WinEvent -LogName security}"
```

Если значение **Command** является строкой, **команда** должна быть последним параметром для pwsh, так как все приведенные ниже аргументы будут интерпретироваться как часть выполняемой команды.

При вызове из существующего сеанса PowerShell результаты возвращаются в родительскую оболочку как десериализованные объекты XML, а не в активные объекты. Для других оболочек результаты возвращаются в виде строк.

Если значение **Command** равно `-` , текст команды считывается из стандартного ввода. При использовании параметра **команды** со стандартным входом необходимо перенаправить стандартный ввод. Пример:

```powershell
@'
"in"

"hi" |
  % { "$_ there" }

"out"
'@ | powershell -NoProfile -Command -
```

В этом примере выводятся следующие данные:

```Output
in
hi there
out
```

Код завершения процесса определяется состоянием последней команды (выполненной) в блоке скрипта. Код выхода — `0` когда `$?` имеет значение `$true` или `1` когда `$?` имеет значение `$false` . Если последняя команда является внешней программой или скриптом PowerShell, который явно задает код выхода, отличный от `0` или `1` , то код выхода преобразуется в `1` для кода завершения процесса. Чтобы сохранить конкретный код выхода, добавьте `exit $LASTEXITCODE` в командную строку или блок скрипта.

Аналогичным образом, значение 1 возвращается при ошибке завершения скрипта (прекращение выполнения, завершающейся), например `throw` , или `-ErrorAction Stop` при прерывании выполнения с помощью <kbd>клавиши CTRL</kbd> - <kbd>C</kbd>.

возможно _только_ при запуске **PowerShell.exe** с другого узла PowerShell.
Тип **ScriptBlock** может содержаться в существующей переменной, возвращенной из выражения, или в виде литерального блока сценария, заключенного в фигурные скобки `{}` , перед передачей в **PowerShell.exe**.

В **cmd.exe** не существует такого понятия, как блок сценария (или тип **ScriptBlock** ), поэтому значение, передаваемое **команде** , _всегда_ будет строкой. Вы можете написать блок сценария в строке, но вместо выполнения его поведение будет таким, как если бы вы набирали его в типичном приглашении PowerShell, возвращая содержимое блока сценария обратно.

Строка, передаваемая **команде** , по-прежнему будет выполняться как PowerShell, поэтому в первом месте при запуске из **cmd.exe** часто не требуются фигурные скобки блока script. Чтобы выполнить встроенный блок скрипта, определенный внутри строки, можно использовать [оператор Call](about_operators.md#special-operators) 
 `&` :

```console
"& {<command>}"
```

#### <a name="-help---"></a>-Help, -?, /?

Отображает справку для **PowerShell.exe**. При вводе команды **PowerShell.exe** в сеансе PowerShell перед параметрами команды используется дефис (-), а не косая черта (/). В **cmd.exe** можно использовать дефис или прямую косую черту.

### <a name="remarks"></a>ПРИМЕЧАНИЯ

Устранение неполадок Примечание. в PowerShell 2,0 запуск некоторых программ из консоли PowerShell завершается сбоем с **LastExitCode** 0xc0000142.

### <a name="examples"></a>Примеры

```powershell
# Create a new PowerShell session and load a saved console file
PowerShell -PSConsoleFile sqlsnapin.psc1

# Create a new PowerShell V2 session with text input, XML output, and no logo
PowerShell -Version 2.0 -NoLogo -InputFormat text -OutputFormat XML

# Execute a PowerShell Command in a session
PowerShell -Command "Get-EventLog -LogName security"

# Run a script block in a session
PowerShell -Command {Get-EventLog -LogName security}

# An alternate way to run a command in a new session
PowerShell -Command "& {Get-EventLog -LogName security}"

# To use the -EncodedCommand parameter:
$command = "dir 'c:\program files' "
$bytes = [System.Text.Encoding]::Unicode.GetBytes($command)
$encodedCommand = [Convert]::ToBase64String($bytes)
powershell.exe -encodedCommand $encodedCommand
```
