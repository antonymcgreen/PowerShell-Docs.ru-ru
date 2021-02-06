---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-pscallstack?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSCallStack
ms.openlocfilehash: 607e3999a1dbe9a4f22a751f11ac93ee3f9d9409
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599792"
---
# <span data-ttu-id="9c1ff-102">Get-PSCallStack</span><span class="sxs-lookup"><span data-stu-id="9c1ff-102">Get-PSCallStack</span></span>

## <span data-ttu-id="9c1ff-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="9c1ff-103">SYNOPSIS</span></span>
<span data-ttu-id="9c1ff-104">Отображает текущий стек вызовов.</span><span class="sxs-lookup"><span data-stu-id="9c1ff-104">Displays the current call stack.</span></span>

## <span data-ttu-id="9c1ff-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9c1ff-105">SYNTAX</span></span>

```
Get-PSCallStack [<CommonParameters>]
```

## <span data-ttu-id="9c1ff-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9c1ff-106">DESCRIPTION</span></span>

<span data-ttu-id="9c1ff-107">Командлет **Get-PSCallStack** отображает текущий стек вызовов.</span><span class="sxs-lookup"><span data-stu-id="9c1ff-107">The **Get-PSCallStack** cmdlet displays the current call stack.</span></span>

<span data-ttu-id="9c1ff-108">Хотя он предназначен для использования с отладчиком PowerShell, этот командлет можно использовать для вывода стека вызовов в скрипте или функции за пределами отладчика.</span><span class="sxs-lookup"><span data-stu-id="9c1ff-108">Although it is designed to be used with the PowerShell debugger, you can use this cmdlet to display the call stack in a script or function outside of the debugger.</span></span>

<span data-ttu-id="9c1ff-109">Чтобы выполнить команду **Get-PSCallStack** в отладчике, введите `k` или `Get-PSCallStack` .</span><span class="sxs-lookup"><span data-stu-id="9c1ff-109">To run a **Get-PSCallStack** command while in the debugger, type `k` or `Get-PSCallStack`.</span></span>

## <span data-ttu-id="9c1ff-110">Примеры</span><span class="sxs-lookup"><span data-stu-id="9c1ff-110">EXAMPLES</span></span>

### <span data-ttu-id="9c1ff-111">Пример 1. получение стека вызовов для функции</span><span class="sxs-lookup"><span data-stu-id="9c1ff-111">Example 1: Get the call stack for a function</span></span>

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

<span data-ttu-id="9c1ff-112">Эта команда использует командлет **Get-PSCallStack** для вывода стека вызовов для простой функции My-Alias, которая получает псевдонимы для имени командлета.</span><span class="sxs-lookup"><span data-stu-id="9c1ff-112">This command uses the **Get-PSCallStack** cmdlet to display the call stack for My-Alias, a simple function that gets the aliases for a cmdlet name.</span></span>

<span data-ttu-id="9c1ff-113">Первая команда вводит функцию в командной строке PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9c1ff-113">The first command enters the function at the PowerShell prompt.</span></span>
<span data-ttu-id="9c1ff-114">Вторая команда использует командлет Set-PSBreakpoint, чтобы установить точку останова на функции My-Alias.</span><span class="sxs-lookup"><span data-stu-id="9c1ff-114">The second command uses the Set-PSBreakpoint cmdlet to set a breakpoint on the My-Alias function.</span></span>
<span data-ttu-id="9c1ff-115">Третья команда использует функцию My-Alias, чтобы получить все псевдонимы в текущем сеансе для командлета Get-Content.</span><span class="sxs-lookup"><span data-stu-id="9c1ff-115">The third command uses the My-Alias function to get all of the aliases in the current session for the Get-Content cmdlet.</span></span>

<span data-ttu-id="9c1ff-116">Отладчик останавливается на вызове функции.</span><span class="sxs-lookup"><span data-stu-id="9c1ff-116">The debugger breaks in at the function call.</span></span>
<span data-ttu-id="9c1ff-117">Две последовательные команды step-into начинают построчное выполнение функции.</span><span class="sxs-lookup"><span data-stu-id="9c1ff-117">Two consecutive step-into (s) commands begin executing the function line by line.</span></span>
<span data-ttu-id="9c1ff-118">Затем для получения стека вызовов используется команда **Get-PSCallStack** .</span><span class="sxs-lookup"><span data-stu-id="9c1ff-118">Then, a **Get-PSCallStack** command is used to retrieve the call stack.</span></span>

<span data-ttu-id="9c1ff-119">Последняя команда Step-Out выходит из отладчика и продолжает выполнение скрипта до конца.</span><span class="sxs-lookup"><span data-stu-id="9c1ff-119">The final command is a Step-Out command (o) that exits the debugger and continues executing the script to completion.</span></span>

## <span data-ttu-id="9c1ff-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9c1ff-120">PARAMETERS</span></span>

### <span data-ttu-id="9c1ff-121">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="9c1ff-121">CommonParameters</span></span>

<span data-ttu-id="9c1ff-122">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="9c1ff-122">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9c1ff-123">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="9c1ff-123">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="9c1ff-124">Входные данные</span><span class="sxs-lookup"><span data-stu-id="9c1ff-124">INPUTS</span></span>

### <span data-ttu-id="9c1ff-125">None</span><span class="sxs-lookup"><span data-stu-id="9c1ff-125">None</span></span>

<span data-ttu-id="9c1ff-126">Нельзя передать объекты в этот командлет с помощью конвейера.</span><span class="sxs-lookup"><span data-stu-id="9c1ff-126">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="9c1ff-127">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="9c1ff-127">OUTPUTS</span></span>

### <span data-ttu-id="9c1ff-128">System. Management. Automation. Каллстаккфраме</span><span class="sxs-lookup"><span data-stu-id="9c1ff-128">System.Management.Automation.CallStackFrame</span></span>

<span data-ttu-id="9c1ff-129">Командлет **Get-PSCallStack** возвращает объект, представляющий элементы в стеке вызовов.</span><span class="sxs-lookup"><span data-stu-id="9c1ff-129">**Get-PSCallStack** returns an object that represents the items in the call stack.</span></span>

## <span data-ttu-id="9c1ff-130">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="9c1ff-130">NOTES</span></span>

## <span data-ttu-id="9c1ff-131">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="9c1ff-131">RELATED LINKS</span></span>

[<span data-ttu-id="9c1ff-132">Disable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="9c1ff-132">Disable-PSBreakpoint</span></span>](Disable-PSBreakpoint.md)

[<span data-ttu-id="9c1ff-133">Enable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="9c1ff-133">Enable-PSBreakpoint</span></span>](Enable-PSBreakpoint.md)

[<span data-ttu-id="9c1ff-134">Format-Table</span><span class="sxs-lookup"><span data-stu-id="9c1ff-134">Format-Table</span></span>](Format-Table.md)

[<span data-ttu-id="9c1ff-135">Get-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="9c1ff-135">Get-PSBreakpoint</span></span>](Get-PSBreakpoint.md)

[<span data-ttu-id="9c1ff-136">Remove-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="9c1ff-136">Remove-PSBreakpoint</span></span>](Remove-PSBreakpoint.md)

[<span data-ttu-id="9c1ff-137">Set-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="9c1ff-137">Set-PSBreakpoint</span></span>](Set-PSBreakpoint.md)

