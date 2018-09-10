---
ms.date: 08/27/2018
keywords: powershell,командлет
title: Получение информации о командах
ms.assetid: 56f8e5b4-d97c-4e59-abbe-bf13e464eb0d
ms.openlocfilehash: 7af83e3a0e776d96e580b442430357b4ea063a72
ms.sourcegitcommit: c170a1608d20d3c925d79c35fa208f650d014146
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/31/2018
ms.locfileid: "43353176"
---
# <a name="getting-information-about-commands"></a>Получение информации о командах

В выходных данных командлета `Get-Command` в PowerShell отображаются команды, доступные в текущем сеансе.
При запуске командлета `Get-Command` можно увидеть примерно следующие выходные данные:

```output
CommandType     Name                    Version    Source
-----------     ----                    -------    ------
Cmdlet          Add-Computer            3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Add-Content             3.1.0.0    Microsoft.PowerShell.Management
Cmdlet          Add-History             3.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Add-JobTrigger          1.1.0.0    PSScheduledJob
Cmdlet          Add-LocalGroupMember    1.0.0.0    Microsoft.PowerShell.LocalAccounts
Cmdlet          Add-Member              3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Add-PSSnapin            3.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Add-Type                3.1.0.0    Microsoft.PowerShell.Utility
...
```

Эти выходные данные выглядят почти так же, как и выходные данные справки **cmd.exe**: сводная таблица внутренних команд. Во фрагменте выходных данных команды `Get-Command`, показанном выше, все команды имеют тип командлета. Командлет является встроенным типом команды PowerShell. Этот тип примерно соответствует таким командам, как `dir` и `cd` в **cmd.exe**, и встроенным командам в оболочках Unix, например Bash.

Командлет `Get-Command` содержит параметр **Syntax**, который возвращает синтаксис каждого командлета. В следующем примере показано, как получить синтаксис командлета `Get-Help`:

```powershell
Get-Command Get-Help -Syntax
```

```output
Get-Help [[-Name] <String>] [-Path <String>] [-Category <String[]>] [-Component <String[]>] [-Functionality <String[]>]
 [-Role <String[]>] [-Full] [-Online] [-Verbose] [-Debug] [-ErrorAction <ActionPreference>] [-WarningAction <ActionPreference>] [-ErrorVariable <String>] [-WarningVariable <String>] [-OutVariable <String>] [-OutBuffer <Int32>]

Get-Help [[-Name] <String>] [-Path <String>] [-Category <String[]>] [-Component <String[]>] [-Functionality <String[]>]
 [-Role <String[]>] [-Detailed] [-Online] [-Verbose] [-Debug] [-ErrorAction <ActionPreference>] [-WarningAction <ActionPreference>] [-ErrorVariable <String>] [-WarningVariable <String>] [-OutVariable <String>] [-OutBuffer <Int32>]

Get-Help [[-Name] <String>] [-Path <String>] [-Category <String[]>] [-Component <String[]>] [-Functionality <String[]>]
 [-Role <String[]>] [-Examples] [-Online] [-Verbose] [-Debug] [-ErrorAction <ActionPreference>] [-WarningAction <ActionPreference>] [-ErrorVariable <String>] [-WarningVariable <String>] [-OutVariable <String>] [-OutBuffer <Int32>]

Get-Help [[-Name] <String>] [-Path <String>] [-Category <String[]>] [-Component <String[]>] [-Functionality <String[]>]
 [-Role <String[]>] [-Parameter <String>] [-Online] [-Verbose] [-Debug] [-ErrorAction <ActionPreference>] [-WarningAction <ActionPreference>] [-ErrorVariable <String>] [-WarningVariable <String>] [-OutVariable <String>] [-OutBuffer <Int32>]
```

## <a name="displaying-available-command-by-type"></a>Отображение доступных команд по типам

Команда `Get-Command` перечисляет только командлеты в текущем сеансе. PowerShell фактически поддерживает несколько других типов команд.

- Псевдонимы
- Функции
- Сценарии

Внешние исполняемые файлы или файлы, содержащие обработчик зарегистрированных типов файлов, также классифицируются как команды.

Чтобы получить все команды в сеансе, введите следующую команду:

```powershell
Get-Command *
```

Этот список включает внешние команды в пути поиска, поэтому они могут содержать тысячи элементов.
Полезнее рассмотреть сокращенный набор команд.

> [!NOTE]
> Звездочка (\*) используется для сопоставления подстановочных знаков в аргументах командной строки PowerShell. Знак "\*" означает "сопоставление одного или нескольких символов". Чтобы найти все команды, которые начинаются с буквы "a", введите `Get-Command a*`. В отличие от сопоставления подстановочных знаков в **cmd.exe** подстановочный знак PowerShell будет также сопоставлять точку.

Используйте параметр **CommandType** командлета `Get-Command`, чтобы получить собственные команды других типов.
.

Чтобы получить псевдонимы команд, которые являются назначенными псевдонимами команд, введите:

```powershell
Get-Command -CommandType Alias
```

Чтобы получить функции текущего сеанса, введите:

```powershell
Get-Command -CommandType Function
```

Чтобы отобразить скрипты в пути поиска PowerShell, введите следующее:

```powershell
Get-Command -CommandType Script
```