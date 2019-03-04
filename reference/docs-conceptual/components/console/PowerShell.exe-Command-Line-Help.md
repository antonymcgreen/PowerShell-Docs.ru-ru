---
ms.date: 08/14/2018
keywords: powershell,командлет
title: Справка по командной строке PowerShell.exe
ms.assetid: 1ab7b93b-6785-42c6-a1c9-35ff686a958f
ms.openlocfilehash: 0a11ebb11d29adf5853c232b3aa10bc72f92bf0c
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 12/14/2018
ms.locfileid: "53402459"
---
# <a name="powershellexe-command-line-help"></a>Справка по командной строке PowerShell.exe

Вы можете использовать PowerShell.exe для запуска сеанса PowerShell из командной строки другого средства, такого как Cmd.exe, или использовать его в командной строке PowerShell для запуска нового сеанса. Используйте указанные параметры для настройки сеанса.

## <a name="syntax"></a>Синтаксис

```syntax
PowerShell[.exe]
       [-Command { - | <script-block> [-args <arg-array>]
                     | <string> [<CommandParameters>] } ]
       [-EncodedCommand <Base64EncodedCommand>]
       [-ExecutionPolicy <ExecutionPolicy>]
       [-File <FilePath> [<Args>]]
       [-InputFormat {Text | XML}]
       [-Mta]
       [-NoExit]
       [-NoLogo]
       [-NonInteractive]
       [-NoProfile]
       [-OutputFormat {Text | XML}]
       [-PSConsoleFile <FilePath> | -Version <PowerShell version>]
       [-Sta]
       [-WindowStyle <style>]

PowerShell[.exe] -Help | -? | /?
```

## <a name="parameters"></a>Параметры

### <a name="-encodedcommand-base64encodedcommand"></a>-EncodedCommand <Base64EncodedCommand>

Принимает строковую версию команды в кодировке Base 64. Используйте этот параметр для отправки в PowerShell команд, требующих сложных кавычек или фигурных скобок.

### <a name="-executionpolicy-executionpolicy"></a>-ExecutionPolicy <ExecutionPolicy>

Задает политику выполнения по умолчанию для текущего сеанса и сохраняет ее в переменной среды $env:PSExecutionPolicyPreference. Этот параметр не изменяет политику выполнения PowerShell, заданную в реестре. Дополнительные сведения о политиках выполнения PowerShell, включая список допустимых значений, см. в статье [about_Execution_Policies](/powershell/module/microsoft.powershell.core/about/about_execution_policies).

### <a name="-file-filepath-parameters"></a>-File <FilePath> \[<Parameters>]

Запускает указанный сценарий в локальной области ("с точкой"), чтобы создаваемые сценарием функции и переменные были доступны в текущем сеансе. Введите путь к файлу сценария и любые параметры. **File** должен быть последним параметром в команде. Все значения, введенные после параметра **-File** интерпретируются как путь к файлу скрипта и параметры, передаваемые в него.

Передаваемые в скрипт параметры имеют вид строк литералов (после интерпретации текущей оболочкой). Например если вы находитесь в cmd.exe и хотите передать значение переменной среды, используется синтаксис cmd.exe: `powershell.exe -File .\test.ps1 -TestParam %windir%`

Напротив, запускать `powershell.exe -File .\test.ps1 -TestParam $env:windir` в результатах cmd.exe в скрипте, получение строковый литерал `$env:windir` , так как он не имеет специального значения в текущей оболочке cmd.exe.
`$env:windir` Стиль ссылка на переменную среды _можно_ использоваться внутри `-Command` параметра, так как существует будут интерпретироваться как код PowerShell.

### <a name="-inputformat-text--xml"></a>\-InputFormat {Text | XML}

Описывает формат данных, отправляемых в PowerShell. Допустимые значения: "Text" (текстовые строки) или "XML" (сериализованный формат CLIXML).

### <a name="-mta"></a>-Mta

Запускает PowerShell с использованием многопотокового подразделения. Этот параметр впервые появился в PowerShell 3.0. В PowerShell 3.0 по умолчанию используется однопотоковое подразделение (STA). В PowerShell 2.0 по умолчанию используется многопотоковое подразделение (MTA).

### <a name="-noexit"></a>-NoExit

Не завершает работу после выполнения команд запуска.

### <a name="-nologo"></a>-NoLogo

Скрывает баннер авторских прав при запуске программы.

### <a name="-noninteractive"></a>-NonInteractive

Не предоставляет пользователю интерактивный запрос.

### <a name="-noprofile"></a>-NoProfile

Не загружает профиль PowerShell.

### <a name="-outputformat-text--xml"></a>-OutputFormat {Text | XML}

Определяет формат выходных данных PowerShell. Допустимые значения: "Text" (текстовые строки) или "XML" (сериализованный формат CLIXML).

### <a name="-psconsolefile-filepath"></a>-PSConsoleFile <FilePath>

Загружает указанный файл консоли PowerShell. Введите путь и имя файла консоли. Чтобы создать файл консоли, используйте командлет [`Export-Console`](/powershell/module/Microsoft.PowerShell.Core/Export-Console) в PowerShell.

### <a name="-sta"></a>-Sta

Запускает PowerShell с использованием многопотокового подразделения. В PowerShell 3.0 по умолчанию используется однопотоковое подразделение (STA). В PowerShell 2.0 по умолчанию используется многопотоковое подразделение (MTA).

### <a name="-version-powershell-version"></a>-Version <PowerShell Version>

Запускает заданную версию PowerShell. Указанная версия должна быть установлена в системе. Если на компьютере установлен PowerShell 3.0, допустимыми значениями являются "3.0" и "2.0". По умолчанию используется значение "3.0".

Если версия PowerShell 3.0 не установлена, допустимо только значение 2.0. Другие значения игнорируются.

Дополнительные сведения см. в статье [Установка Windows PowerShell](../../setup/installing-windows-powershell.md).

### <a name="-windowstyle-window-style"></a>-WindowStyle <Window style>

Задает стиль окна для сеанса. Допустимые значения: Normal, Minimized, Maximized и Hidden.

### <a name="-command"></a>-Command

Выполняет указанные команды (с любыми параметрами) как введенные в командной строке PowerShell.
После выполнения PowerShell завершает работу, если не **NoExit** указан параметр.
Любой текст после `-Command` отправляется в PowerShell как одна командная строка.
Это отличается от того, как `-File` обрабатывает параметры, передаваемые в скрипт.

Значение `-Command` может быть «-», строка или блок скрипта.
Результаты выполнения команды возвращаются родительской оболочке как десериализованные объекты XML, а не как активные объекты.

Если значение `-Command` — «-», текст команды считывается из стандартного ввода.

Когда значение `-Command` представляет собой строку, **команда** _необходимо_ быть последним параметром, так как любой знак, введенный после команды, интерпретируется как ее аргумент.

**Команда** параметр принимает только блок скрипта для выполнения при его может распознать значение, передаваемое `-Command` как тип блок сценария.
Это _только_ возможно при использовании PowerShell.exe с другого узла PowerShell.
Тип может содержаться в существующей переменной, возвращаемый из выражения или проанализированный с PowerShell блок сценария размещения как блок скрипта литерала, заключенных в фигурные скобки `{}`, перед передачей в PowerShell.exe.

В cmd.exe, нет такого понятия, как блок скрипта (или тип блок сценария), поэтому значение, передаваемое **команда** будет _всегда_ быть строкой.
Можно написать блок скрипта внутри строки, но вместо выполнения он будет вести себя точно так, будто бы он был введен в обычной командной строке PowerShell, выводя содержимое скрипта заблокировать обратно вам.

Строка, передаваемая в `-Command` по-прежнему будет выполняться как PowerShell, чтобы фигурные скобки блок скрипта часто не являются обязательными в первую очередь при запуске из cmd.exe.
Для выполнения встроенного блока скрипта, определенные внутри строки, [оператор вызова](/powershell/module/microsoft.powershell.core/about/about_operators#call-operator-) `&` можно использовать:

```console
"& {<command>}"
```

### <a name="-help---"></a>-Help, -?, /?

Показывает синтаксис powershell.exe. При вводе команды PowerShell.exe в PowerShell добавляйте в начало параметров команды дефис (-), а не косую черту (/). В Cmd.exe можно использовать как дефис, так и косую черту.

> [!NOTE]
> Замечание по устранению неполадок. В PowerShell 2.0 запуск некоторых программ в Windows PowerShell, завершается ошибкой с кодом LastExitCode 0xc0000142.

## <a name="examples"></a>ПРИМЕРЫ

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