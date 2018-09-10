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
# <a name="getting-information-about-commands"></a><span data-ttu-id="14cbf-103">Получение информации о командах</span><span class="sxs-lookup"><span data-stu-id="14cbf-103">Getting information about commands</span></span>

<span data-ttu-id="14cbf-104">В выходных данных командлета `Get-Command` в PowerShell отображаются команды, доступные в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="14cbf-104">The PowerShell `Get-Command` displays commands that are available in your current session.</span></span>
<span data-ttu-id="14cbf-105">При запуске командлета `Get-Command` можно увидеть примерно следующие выходные данные:</span><span class="sxs-lookup"><span data-stu-id="14cbf-105">When you run the `Get-Command` cmdlet, you see something similar to the following output:</span></span>

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

<span data-ttu-id="14cbf-106">Эти выходные данные выглядят почти так же, как и выходные данные справки **cmd.exe**: сводная таблица внутренних команд.</span><span class="sxs-lookup"><span data-stu-id="14cbf-106">This output looks a lot like the Help output of **cmd.exe**: a tabular summary of internal commands.</span></span> <span data-ttu-id="14cbf-107">Во фрагменте выходных данных команды `Get-Command`, показанном выше, все команды имеют тип командлета.</span><span class="sxs-lookup"><span data-stu-id="14cbf-107">In the excerpt of the `Get-Command` command output shown above, every command shown has a CommandType of Cmdlet.</span></span> <span data-ttu-id="14cbf-108">Командлет является встроенным типом команды PowerShell.</span><span class="sxs-lookup"><span data-stu-id="14cbf-108">A cmdlet is PowerShell's intrinsic command type.</span></span> <span data-ttu-id="14cbf-109">Этот тип примерно соответствует таким командам, как `dir` и `cd` в **cmd.exe**, и встроенным командам в оболочках Unix, например Bash.</span><span class="sxs-lookup"><span data-stu-id="14cbf-109">This type corresponds roughly to commands like `dir` and `cd` in **cmd.exe** or the built-in commands of Unix shells like bash.</span></span>

<span data-ttu-id="14cbf-110">Командлет `Get-Command` содержит параметр **Syntax**, который возвращает синтаксис каждого командлета.</span><span class="sxs-lookup"><span data-stu-id="14cbf-110">The `Get-Command` cmdlet has a **Syntax** parameter that returns syntax of each cmdlet.</span></span> <span data-ttu-id="14cbf-111">В следующем примере показано, как получить синтаксис командлета `Get-Help`:</span><span class="sxs-lookup"><span data-stu-id="14cbf-111">The following example shows how to get the syntax of the `Get-Help` cmdlet:</span></span>

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

## <a name="displaying-available-command-by-type"></a><span data-ttu-id="14cbf-112">Отображение доступных команд по типам</span><span class="sxs-lookup"><span data-stu-id="14cbf-112">Displaying available command by type</span></span>

<span data-ttu-id="14cbf-113">Команда `Get-Command` перечисляет только командлеты в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="14cbf-113">The `Get-Command` command lists only the cmdlets in the current session.</span></span> <span data-ttu-id="14cbf-114">PowerShell фактически поддерживает несколько других типов команд.</span><span class="sxs-lookup"><span data-stu-id="14cbf-114">PowerShell actually supports several other types of commands:</span></span>

- <span data-ttu-id="14cbf-115">Псевдонимы</span><span class="sxs-lookup"><span data-stu-id="14cbf-115">Aliases</span></span>
- <span data-ttu-id="14cbf-116">Функции</span><span class="sxs-lookup"><span data-stu-id="14cbf-116">Functions</span></span>
- <span data-ttu-id="14cbf-117">Сценарии</span><span class="sxs-lookup"><span data-stu-id="14cbf-117">Scripts</span></span>

<span data-ttu-id="14cbf-118">Внешние исполняемые файлы или файлы, содержащие обработчик зарегистрированных типов файлов, также классифицируются как команды.</span><span class="sxs-lookup"><span data-stu-id="14cbf-118">External executable files, or files that have a registered file type handler, are also classified as commands.</span></span>

<span data-ttu-id="14cbf-119">Чтобы получить все команды в сеансе, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="14cbf-119">To get all commands in the session, type:</span></span>

```powershell
Get-Command *
```

<span data-ttu-id="14cbf-120">Этот список включает внешние команды в пути поиска, поэтому они могут содержать тысячи элементов.</span><span class="sxs-lookup"><span data-stu-id="14cbf-120">This list includes external commands in your search path so it can contain thousands of items.</span></span>
<span data-ttu-id="14cbf-121">Полезнее рассмотреть сокращенный набор команд.</span><span class="sxs-lookup"><span data-stu-id="14cbf-121">It is more useful to look at a reduced set of commands.</span></span>

> [!NOTE]
> <span data-ttu-id="14cbf-122">Звездочка (\*) используется для сопоставления подстановочных знаков в аргументах командной строки PowerShell.</span><span class="sxs-lookup"><span data-stu-id="14cbf-122">The asterisk (\*) is used for wildcard matching in PowerShell command arguments.</span></span> <span data-ttu-id="14cbf-123">Знак "\*" означает "сопоставление одного или нескольких символов".</span><span class="sxs-lookup"><span data-stu-id="14cbf-123">The \* means "match one or more of any characters".</span></span> <span data-ttu-id="14cbf-124">Чтобы найти все команды, которые начинаются с буквы "a", введите `Get-Command a*`.</span><span class="sxs-lookup"><span data-stu-id="14cbf-124">You can type `Get-Command a*` to find all commands that begin with the letter "a".</span></span> <span data-ttu-id="14cbf-125">В отличие от сопоставления подстановочных знаков в **cmd.exe** подстановочный знак PowerShell будет также сопоставлять точку.</span><span class="sxs-lookup"><span data-stu-id="14cbf-125">Unlike wildcard matching in **cmd.exe**, PowerShell's wildcard will also match a period.</span></span>

<span data-ttu-id="14cbf-126">Используйте параметр **CommandType** командлета `Get-Command`, чтобы получить собственные команды других типов.</span><span class="sxs-lookup"><span data-stu-id="14cbf-126">Use the **CommandType** parameter of `Get-Command` to get native commands of other types.</span></span>
<span data-ttu-id="14cbf-127">.</span><span class="sxs-lookup"><span data-stu-id="14cbf-127">cmdlet.</span></span>

<span data-ttu-id="14cbf-128">Чтобы получить псевдонимы команд, которые являются назначенными псевдонимами команд, введите:</span><span class="sxs-lookup"><span data-stu-id="14cbf-128">To get command aliases, which are the assigned nicknames of commands, type:</span></span>

```powershell
Get-Command -CommandType Alias
```

<span data-ttu-id="14cbf-129">Чтобы получить функции текущего сеанса, введите:</span><span class="sxs-lookup"><span data-stu-id="14cbf-129">To get the functions in the current session, type:</span></span>

```powershell
Get-Command -CommandType Function
```

<span data-ttu-id="14cbf-130">Чтобы отобразить скрипты в пути поиска PowerShell, введите следующее:</span><span class="sxs-lookup"><span data-stu-id="14cbf-130">To display scripts in PowerShell's search path, type:</span></span>

```powershell
Get-Command -CommandType Script
```