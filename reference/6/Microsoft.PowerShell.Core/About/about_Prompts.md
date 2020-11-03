---
description: Описывает `Prompt` функцию и демонстрирует создание пользовательской `Prompt` функции.
keywords: powershell,командлет
Locale: en-US
ms.date: 04/15/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_prompts?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Prompts
ms.openlocfilehash: 9ae18afce9aec258181f4829b02b33bd942b3e10
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231341"
---
# <a name="about-prompts"></a>О запросах

## <a name="short-description"></a>Краткое описание
Описывает `Prompt` функцию и демонстрирует создание пользовательской `Prompt` функции.

## <a name="long-description"></a>Подробное описание

Командная строка PowerShell указывает, что PowerShell готов выполнить команду:

```
PS C:\>
```

Командная строка PowerShell определяется встроенной `Prompt` функцией. Вы можете настроить запрос, создав собственную `Prompt` функцию и сохранив ее в профиле PowerShell.

## <a name="about-the-prompt-function"></a>О функции Prompt

`Prompt`Функция определяет внешний вид командной строки PowerShell.
PowerShell поставляется с встроенной `Prompt` функцией, но ее можно переопределить, определив собственную `Prompt` функцию.

`Prompt`Функция имеет следующий синтаксис:

```powershell
function Prompt { <function-body> }
```

`Prompt`Функция должна возвращать объект. Рекомендуется возвращать строку или объект, отформатированный в виде строки. Максимальная рекомендуемая длина — 80 символов.

Например, следующая `Prompt` функция возвращает строку "Hello, World", за которой следует правая угловая скобка ( `>` ).

```powershell
PS C:\> function prompt {"Hello, World > "}
Hello, World >
```

### <a name="getting-the-prompt-function"></a>Получение функции Prompt

Чтобы получить `Prompt` функцию, используйте `Get-Command` командлет или `Get-Item` командлет на диске функции.

Пример:

```powershell
PS C:\> Get-Command Prompt

CommandType     Name      ModuleName
-----------     ----      ----------
Function        prompt
```

Чтобы получить скрипт, который задает значение запроса, используйте метод Dot, чтобы получить свойство **ScriptBlock** `Prompt` функции.

Пример:

```powershell
(Get-Command Prompt).ScriptBlock
```

```Output
"PS $($executionContext.SessionState.Path.CurrentLocation)$('>' * ($nestedPromptLevel + 1)) "
# .Link
# https://go.microsoft.com/fwlink/?LinkID=225750
# .ExternalHelp System.Management.Automation.dll-help.xml
```

Как и все функции, `Prompt` функция хранится на `Function:` диске.
Чтобы отобразить скрипт, который создает текущую `Prompt` функцию, введите:

```powershell
(Get-Item function:prompt).ScriptBlock
```

### <a name="the-default-prompt"></a>Запрос по умолчанию

Запрос по умолчанию отображается только в том случае, если `Prompt` функция создает ошибку или не возвращает объект.

Запрос PowerShell по умолчанию:

```
PS>
```

Например, следующая команда задает `Prompt` для функции значение `$null` , которое является недопустимым. В результате появится запрос по умолчанию.

```powershell
PS C:\> function prompt {$null}
PS>
```

Так как PowerShell поставляется со встроенным запросом, обычно не отображается запрос по умолчанию.

### <a name="built-in-prompt"></a>Встроенный запрос

PowerShell включает встроенную `Prompt` функцию.

```powershell
function prompt {
    $(if (Test-Path variable:/PSDebugContext) { '[DBG]: ' }
      else { '' }) + 'PS ' + $(Get-Location) +
        $(if ($NestedPromptLevel -ge 1) { '>>' }) + '> '
}
```

Функция использует командлет, `Test-Path` чтобы определить, `$PSDebugContext` заполнена ли автоматическая переменная. Если `$PSDebugContext` заполняется, выполняется в режиме отладки и `[DBG]:` добавляется в командную строку следующим образом:

```Output
[DBG]: PS C:\ps-test>
```

Если `$PSDebugContext` параметр не заполнен, функция добавляет `PS` в запрос.
И функция использует `Get-Location` командлет для получения текущего расположения каталога файловой системы. Затем добавляется правая угловая скобка ( `>` ).

Пример:

```Output
PS C:\ps-test>
```

В случае вложенного запроса функция добавляет в запрос две угловые скобки ( `>>` ). (Во вложенном запросе, если значение `$NestedPromptLevel` автоматической переменной больше 1.)

Например, при отладке во вложенной командной строке запрос будет выглядеть следующим образом:

```Output
[DBG] PS C:\ps-test>>>
```

### <a name="changes-to-the-prompt"></a>Изменения в приглашении

`Enter-PSSession`Командлет добавляет имя удаленного компьютера к текущей `Prompt` функции. При использовании `Enter-PSSession` командлета для запуска сеанса с удаленным компьютером Командная строка изменится, включив в нее имя удаленного компьютера. Пример:

```Output
PS Hello, World> Enter-PSSession Server01
[Server01]: PS Hello, World>
```

Другие хост приложения PowerShell и другие оболочки могут иметь собственные настраиваемые командные запросы.

Дополнительные сведения об `$PSDebugContext` и `$NestedPromptLevel` автоматических переменных см. в разделе [about_Automatic_Variables](about_Automatic_Variables.md).

### <a name="how-to-customize-the-prompt"></a>Настройка командной строки

Чтобы настроить запрос, напишите новую `Prompt` функцию. Функция не защищена, поэтому ее можно перезаписать.

Чтобы написать `Prompt` функцию, введите следующую команду:

```powershell
function prompt { }
```

Затем между фигурными скобками введите команды или строку, которая создает запрос.

Например, следующий запрос включает имя компьютера:

```powershell
function prompt {"PS [$env:COMPUTERNAME]> "}
```

На компьютере Server01 запрос будет выглядеть следующим образом:

```Output
PS [Server01] >
```

Следующая `Prompt` функция включает текущие дату и время:

```powershell
function prompt {"$(Get-Date)> "}
```

Запрос будет выглядеть следующим образом:

```Output
03/15/2012 17:49:47>
```

Можно также изменить функцию по умолчанию `Prompt` .

Например, следующая измененная `Prompt` функция добавляет во `[ADMIN]:` встроенный запрос PowerShell при открытии PowerShell с помощью команды **Запуск от имени администратора** :

```powershell
function prompt {
  $identity = [Security.Principal.WindowsIdentity]::GetCurrent()
  $principal = [Security.Principal.WindowsPrincipal] $identity
  $adminRole = [Security.Principal.WindowsBuiltInRole]::Administrator

  $(if (Test-Path variable:/PSDebugContext) { '[DBG]: ' }
    elseif($principal.IsInRole($adminRole)) { "[ADMIN]: " }
    else { '' }
  ) + 'PS ' + $(Get-Location) +
    $(if ($NestedPromptLevel -ge 1) { '>>' }) + '> '
}
```

При запуске PowerShell с помощью команды **Запуск от имени администратора** отображается запрос, напоминающий следующий запрос:

```Output
[ADMIN]: PS C:\ps-test>
```

Следующая `Prompt` функция ОТОБРАЖАЕТ идентификатор журнала следующей команды. Чтобы просмотреть журнал команд, используйте `Get-History` командлет.

```powershell
function prompt {
   # The at sign creates an array in case only one history item exists.
   $history = @(Get-History)
   if($history.Count -gt 0)
   {
      $lastItem = $history[$history.Count - 1]
      $lastId = $lastItem.Id
   }

   $nextCommand = $lastId + 1
   $currentDirectory = Get-Location
   "PS: $nextCommand $currentDirectory >"
}
```

В следующем запросе `Write-Host` `Get-Random` командлеты и используются для создания запроса, который изменяет цвет случайным образом. Поскольку `Write-Host` операции записи в текущее ведущее приложение не возвращают объект, эта функция включает `Return` оператор. Без него PowerShell использует запрос по умолчанию `PS>` .

```powershell
function prompt {
    $color = Get-Random -Min 1 -Max 16
    Write-Host ("PS " + $(Get-Location) +">") -NoNewLine `
     -ForegroundColor $Color
    return " "
}
```

### <a name="saving-the-prompt-function"></a>Сохранение функции Prompt

Как и любая функция, `Prompt` функция существует только в текущем сеансе. Чтобы сохранить `Prompt` функцию для будущих сеансов, добавьте ее в профили PowerShell. Дополнительные сведения о профилях см. в разделе [about_Profiles](about_Profiles.md).

## <a name="see-also"></a>См. также статью

[Get-Location](xref:Microsoft.PowerShell.Management.Get-Location)

[Enter-PSSession](xref:Microsoft.PowerShell.Core.Enter-PSSession)

[Get-History](xref:Microsoft.PowerShell.Core.Get-History)

[Get-Random](xref:Microsoft.PowerShell.Utility.Get-Random)

[Write-Host](xref:Microsoft.PowerShell.Utility.Write-Host)

[about_Profiles](about_Profiles.md)

[about_Functions](about_Functions.md)

[about_Scopes](about_Scopes.md)

[about_Debuggers](about_Debuggers.md)

[about_Automatic_Variables](about_Automatic_Variables.md)
