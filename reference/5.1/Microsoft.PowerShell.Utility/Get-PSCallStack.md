---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-pscallstack?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSCallStack
ms.openlocfilehash: 45c2ea5bc166e2d21153ae8b19c1c0afe4ca0640
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "93209017"
---
# <span data-ttu-id="505d2-103">Get-PSCallStack</span><span class="sxs-lookup"><span data-stu-id="505d2-103">Get-PSCallStack</span></span>

## <span data-ttu-id="505d2-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="505d2-104">SYNOPSIS</span></span>
<span data-ttu-id="505d2-105">Отображает текущий стек вызовов.</span><span class="sxs-lookup"><span data-stu-id="505d2-105">Displays the current call stack.</span></span>

## <span data-ttu-id="505d2-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="505d2-106">SYNTAX</span></span>

```
Get-PSCallStack [<CommonParameters>]
```

## <span data-ttu-id="505d2-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="505d2-107">DESCRIPTION</span></span>
<span data-ttu-id="505d2-108">Командлет **Get-PSCallStack** отображает текущий стек вызовов.</span><span class="sxs-lookup"><span data-stu-id="505d2-108">The **Get-PSCallStack** cmdlet displays the current call stack.</span></span>

<span data-ttu-id="505d2-109">Несмотря на то, что этот командлет предназначен для использования с отладчиком Windows PowerShell, его можно использовать для отображения стека вызова в скрипте или функции вне отладчика.</span><span class="sxs-lookup"><span data-stu-id="505d2-109">Although it is designed to be used with the Windows PowerShell debugger, you can use this cmdlet to display the call stack in a script or function outside of the debugger.</span></span>

<span data-ttu-id="505d2-110">Чтобы выполнить команду **Get-PSCallStack** в отладчике, введите `k` или `Get-PSCallStack` .</span><span class="sxs-lookup"><span data-stu-id="505d2-110">To run a **Get-PSCallStack** command while in the debugger, type `k` or `Get-PSCallStack`.</span></span>

## <span data-ttu-id="505d2-111">Примеры</span><span class="sxs-lookup"><span data-stu-id="505d2-111">EXAMPLES</span></span>

### <span data-ttu-id="505d2-112">Пример 1. получение стека вызовов для функции</span><span class="sxs-lookup"><span data-stu-id="505d2-112">Example 1: Get the call stack for a function</span></span>

```
PS C:\> function my-alias {
$p = $args[0]
Get-Alias | where {$_.definition -like "*$p"} | format-table definition, name -auto
}
PS C:\ps-test> Set-PSBreakpoint -Command my-alias
Command    : my-alias
Action     :
Enabled    : True
HitCount   : 0
Id         : 0
Script     : prompt PS C:\> my-alias Get-Content

Entering debug mode. Use h or ? for help.
Hit Command breakpoint on 'prompt:my-alias'
my-alias get-content
[DBG]: PS C:\ps-test> s
$p = $args[0]
DEBUG: Stepped to ':    $p = $args[0]    '
[DBG]: PS C:\ps-test> s
get-alias | Where {$_.Definition -like "*$p*"} | format-table Definition,
[DBG]: PS C:\ps-test>get-pscallstack

Name        CommandLineParameters         UnboundArguments              Location
----        ---------------------         ----------------              --------
prompt      {}                            {}                            prompt
my-alias    {}                            {get-content}                 prompt
prompt      {}                            {}                            prompt PS C:\> [DBG]: PS C:\ps-test> o
Definition  Name
----------  ----
Get-Content gc
Get-Content cat
Get-Content type
```

<span data-ttu-id="505d2-113">Эта команда использует командлет **Get-PSCallStack** для вывода стека вызовов для простой функции My-Alias, которая получает псевдонимы для имени командлета.</span><span class="sxs-lookup"><span data-stu-id="505d2-113">This command uses the **Get-PSCallStack** cmdlet to display the call stack for My-Alias, a simple function that gets the aliases for a cmdlet name.</span></span>

<span data-ttu-id="505d2-114">Первая команда входит в функцию в командной строке Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="505d2-114">The first command enters the function at the Windows PowerShell prompt.</span></span>
<span data-ttu-id="505d2-115">Вторая команда использует командлет Set-PSBreakpoint, чтобы установить точку останова на функции My-Alias.</span><span class="sxs-lookup"><span data-stu-id="505d2-115">The second command uses the Set-PSBreakpoint cmdlet to set a breakpoint on the My-Alias function.</span></span>
<span data-ttu-id="505d2-116">Третья команда использует функцию My-Alias, чтобы получить все псевдонимы в текущем сеансе для командлета Get-Content.</span><span class="sxs-lookup"><span data-stu-id="505d2-116">The third command uses the My-Alias function to get all of the aliases in the current session for the Get-Content cmdlet.</span></span>

<span data-ttu-id="505d2-117">Отладчик останавливается на вызове функции.</span><span class="sxs-lookup"><span data-stu-id="505d2-117">The debugger breaks in at the function call.</span></span>
<span data-ttu-id="505d2-118">Две последовательные команды step-into начинают построчное выполнение функции.</span><span class="sxs-lookup"><span data-stu-id="505d2-118">Two consecutive step-into (s) commands begin executing the function line by line.</span></span>
<span data-ttu-id="505d2-119">Затем для получения стека вызовов используется команда **Get-PSCallStack** .</span><span class="sxs-lookup"><span data-stu-id="505d2-119">Then, a **Get-PSCallStack** command is used to retrieve the call stack.</span></span>

<span data-ttu-id="505d2-120">Последняя команда Step-Out выходит из отладчика и продолжает выполнение скрипта до конца.</span><span class="sxs-lookup"><span data-stu-id="505d2-120">The final command is a Step-Out command (o) that exits the debugger and continues executing the script to completion.</span></span>

## <span data-ttu-id="505d2-121">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="505d2-121">PARAMETERS</span></span>

### <span data-ttu-id="505d2-122">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="505d2-122">CommonParameters</span></span>
<span data-ttu-id="505d2-123">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="505d2-123">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="505d2-124">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="505d2-124">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="505d2-125">Входные данные</span><span class="sxs-lookup"><span data-stu-id="505d2-125">INPUTS</span></span>

### <span data-ttu-id="505d2-126">Нет</span><span class="sxs-lookup"><span data-stu-id="505d2-126">None</span></span>
<span data-ttu-id="505d2-127">Нельзя передать объекты в этот командлет с помощью конвейера.</span><span class="sxs-lookup"><span data-stu-id="505d2-127">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="505d2-128">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="505d2-128">OUTPUTS</span></span>

### <span data-ttu-id="505d2-129">System. Management. Automation. Каллстаккфраме</span><span class="sxs-lookup"><span data-stu-id="505d2-129">System.Management.Automation.CallStackFrame</span></span>
<span data-ttu-id="505d2-130">Командлет **Get-PSCallStack** возвращает объект, представляющий элементы в стеке вызовов.</span><span class="sxs-lookup"><span data-stu-id="505d2-130">**Get-PSCallStack** returns an object that represents the items in the call stack.</span></span>

## <span data-ttu-id="505d2-131">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="505d2-131">NOTES</span></span>

## <span data-ttu-id="505d2-132">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="505d2-132">RELATED LINKS</span></span>

[<span data-ttu-id="505d2-133">Disable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="505d2-133">Disable-PSBreakpoint</span></span>](Disable-PSBreakpoint.md)

[<span data-ttu-id="505d2-134">Enable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="505d2-134">Enable-PSBreakpoint</span></span>](Enable-PSBreakpoint.md)

[<span data-ttu-id="505d2-135">Format-Table</span><span class="sxs-lookup"><span data-stu-id="505d2-135">Format-Table</span></span>](Format-Table.md)

[<span data-ttu-id="505d2-136">Get-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="505d2-136">Get-PSBreakpoint</span></span>](Get-PSBreakpoint.md)

[<span data-ttu-id="505d2-137">Remove-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="505d2-137">Remove-PSBreakpoint</span></span>](Remove-PSBreakpoint.md)

[<span data-ttu-id="505d2-138">Set-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="505d2-138">Set-PSBreakpoint</span></span>](Set-PSBreakpoint.md)
