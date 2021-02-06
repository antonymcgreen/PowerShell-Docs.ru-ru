---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 05/13/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/clear-history?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-History
ms.openlocfilehash: 1b465779f56c6bd71d7adfa7ffb5b391f5402656
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600199"
---
# <span data-ttu-id="70599-102">Clear-History</span><span class="sxs-lookup"><span data-stu-id="70599-102">Clear-History</span></span>

## <span data-ttu-id="70599-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="70599-103">SYNOPSIS</span></span>
<span data-ttu-id="70599-104">Удаляет записи из журнала команд сеанса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="70599-104">Deletes entries from the PowerShell session command history.</span></span>

## <span data-ttu-id="70599-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="70599-105">SYNTAX</span></span>

### <span data-ttu-id="70599-106">Идпараметер (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="70599-106">IDParameter (Default)</span></span>

```
Clear-History [[-Id] <int[]>] [[-Count] <int>] [-Newest] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="70599-107">коммандлинепараметер</span><span class="sxs-lookup"><span data-stu-id="70599-107">CommandLineParameter</span></span>

```
Clear-History [[-Count] <int>] [-CommandLine <string[]>] [-Newest] [-WhatIf] [-Confirm]
[<CommonParameters>]
```

## <span data-ttu-id="70599-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="70599-108">DESCRIPTION</span></span>

<span data-ttu-id="70599-109">`Clear-History` Удаляет журнал команд из сеанса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="70599-109">`Clear-History` deletes the command history from a PowerShell session.</span></span> <span data-ttu-id="70599-110">Каждый сеанс PowerShell имеет собственный журнал команд.</span><span class="sxs-lookup"><span data-stu-id="70599-110">Each PowerShell session has its own command history.</span></span> <span data-ttu-id="70599-111">Чтобы отобразить журнал команд, используйте `Get-History` командлет.</span><span class="sxs-lookup"><span data-stu-id="70599-111">To display the command history, use the `Get-History` cmdlet.</span></span>

<span data-ttu-id="70599-112">По умолчанию `Clear-History` удаляет весь журнал команд из сеанса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="70599-112">By default, `Clear-History` deletes the entire command history from a PowerShell session.</span></span> <span data-ttu-id="70599-113">`Clear-History`Для удаления выбранных команд можно использовать параметры.</span><span class="sxs-lookup"><span data-stu-id="70599-113">You can use parameters with `Clear-History` to delete selected commands.</span></span>

<span data-ttu-id="70599-114">`Clear-History` не очищает `PSReadLine` файл журнала команд.</span><span class="sxs-lookup"><span data-stu-id="70599-114">`Clear-History` does not clear the `PSReadLine` command history file.</span></span> <span data-ttu-id="70599-115">`PSReadLine`Модуль хранит файл журнала, содержащий все команды PowerShell из каждого сеанса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="70599-115">The `PSReadLine` module stores a history file that contains every PowerShell command from every PowerShell session.</span></span> <span data-ttu-id="70599-116">В командной строке PowerShell используйте клавиши со стрелками вверх и вниз для прокрутки журнала команд.</span><span class="sxs-lookup"><span data-stu-id="70599-116">From a PowerShell prompt, use the up and down arrows on your keyboard to scroll through the command history.</span></span> <span data-ttu-id="70599-117">Чтобы отобразить `PSReadLine` конфигурацию для журнала команд, используйте `Get-PSReadLineOption` .</span><span class="sxs-lookup"><span data-stu-id="70599-117">To display the `PSReadLine` configuration for command history, use `Get-PSReadLineOption`.</span></span>
<span data-ttu-id="70599-118">`PSReadLine` поставляется с PowerShell 5,0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="70599-118">`PSReadLine` shipped with PowerShell 5.0 and above.</span></span> <span data-ttu-id="70599-119">Дополнительные сведения см. в разделе [about_PSReadLine](../PSReadLine/About/about_PSReadLine.md).</span><span class="sxs-lookup"><span data-stu-id="70599-119">For more information, see [about_PSReadLine](../PSReadLine/About/about_PSReadLine.md).</span></span>

## <span data-ttu-id="70599-120">Примеры</span><span class="sxs-lookup"><span data-stu-id="70599-120">EXAMPLES</span></span>

### <span data-ttu-id="70599-121">Пример 1. Удаление журнала команд из сеанса PowerShell</span><span class="sxs-lookup"><span data-stu-id="70599-121">Example 1: Delete the command history from a PowerShell session</span></span>

<span data-ttu-id="70599-122">Эта команда удаляет все команды из журнала сеанса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="70599-122">This command deletes all of the commands from a PowerShell session's history.</span></span>

```powershell
Get-History
```

```Output
  Id CommandLine
  -- -----------
   1 Set-Location .\Test
   2 Update-Help
   3 Set-Location C:\Test\Logs
   4 Get-Location
```

```powershell
Clear-History
Get-History
```

```Output
  Id CommandLine
  -- -----------
   5 Clear-History
```

<span data-ttu-id="70599-123">`Get-History`Командлет отображает журнал сеанса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="70599-123">The `Get-History` cmdlet displays the PowerShell session's history.</span></span> <span data-ttu-id="70599-124">`Clear-History` Удаляет весь журнал команд.</span><span class="sxs-lookup"><span data-stu-id="70599-124">`Clear-History` deletes the entire command history.</span></span> <span data-ttu-id="70599-125">`Get-History` отображает обновленный журнал команд и подтверждает, что предыдущая история была удалена.</span><span class="sxs-lookup"><span data-stu-id="70599-125">`Get-History` displays the updated command history and confirms the prior history was deleted.</span></span>

### <span data-ttu-id="70599-126">Пример 2. Удаление последних команд</span><span class="sxs-lookup"><span data-stu-id="70599-126">Example 2: Delete the newest commands</span></span>

<span data-ttu-id="70599-127">Эта команда использует параметры **Count** и **новейшие** для удаления последних команд из журнала сеанса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="70599-127">This command uses the **Count** and **Newest** parameters to delete the newest commands from a PowerShell session's history.</span></span>

```powershell
Get-History
```

```Output
  Id CommandLine
  -- -----------
   1 Set-Location C:\Test\
   2 Get-Command Clear-History
   3 Get-Command Clear-History -Syntax
   4 Get-Command Clear-History -ShowCommandInfo
   5 Get-Help Get-Alias
   6 Get-Command Get-ChildItem -Syntax
   7 Get-Help Clear-History
   8 Set-Location C:\Test\Logs
   9 Get-Help Get-Variable
  10 Get-Help Get-ChildItem
```

```powershell
Clear-History -Count 5 -Newest
Get-History
```

```Output
  Id CommandLine
  -- -----------
   1 Set-Location C:\Test\
   2 Get-Command Clear-History
   3 Get-Command Clear-History -Syntax
   4 Get-Command Clear-History -ShowCommandInfo
   5 Get-Help Get-Alias
  11 Clear-History -Count 5 -Newest
```

<span data-ttu-id="70599-128">`Get-History`Командлет отображает журнал сеанса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="70599-128">The `Get-History` cmdlet displays the PowerShell session's history.</span></span> <span data-ttu-id="70599-129">`Clear-History` используется для удаления журнала команд.</span><span class="sxs-lookup"><span data-stu-id="70599-129">`Clear-History` is used to delete the command history.</span></span> <span data-ttu-id="70599-130">Параметр **Count** указывает количество команд для удаления, включая указанный **идентификатор**. **Последний** параметр указывает, что из журнала удаляются последние команды.</span><span class="sxs-lookup"><span data-stu-id="70599-130">The **Count** parameter specifies the number of commands to delete, inclusive of the specified **Id**. The **Newest** parameter specifies that the newest commands are cleared from the history.</span></span> <span data-ttu-id="70599-131">`Get-History`отображает обновленный журнал команд и подтверждает, что были удалены пять последних команд с **идентификатором 6**  -  **ID 10**.</span><span class="sxs-lookup"><span data-stu-id="70599-131">`Get-History` displays the updated command history and confirms that the five newest commands were deleted, **Id 6** - **Id 10**.</span></span>

### <span data-ttu-id="70599-132">Пример 3. Удаление команд, соответствующих указанным условиям</span><span class="sxs-lookup"><span data-stu-id="70599-132">Example 3: Delete commands that match specific criteria</span></span>

<span data-ttu-id="70599-133">Эта команда удаляет команды, соответствующие определенным условиям, определенным параметром **commandline** .</span><span class="sxs-lookup"><span data-stu-id="70599-133">This command deletes commands that match specific criteria defined by the **CommandLine** parameter.</span></span>

```powershell
Get-History
```

```Output
  Id CommandLine
  -- -----------
   1 Set-Location C:\Test\
   2 Get-Command Clear-History
   3 Get-Command Clear-History -Syntax
   4 Get-Command Clear-History -ShowCommandInfo
   5 Get-Help Get-Alias
   6 Get-Command Get-ChildItem -Syntax
   7 Get-Help Clear-History
```

```powershell
Clear-History -CommandLine *Help*, *Syntax
Get-History
```

```Output
  Id CommandLine
  -- -----------
   1 Set-Location C:\Test\
   2 Get-Command Clear-History
   4 Get-Command Clear-History -ShowCommandInfo
   8 Clear-History -CommandLine *Help*, *Syntax
```

<span data-ttu-id="70599-134">`Get-History`Командлет отображает журнал сеанса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="70599-134">The `Get-History` cmdlet displays the PowerShell session's history.</span></span> <span data-ttu-id="70599-135">`Clear-History` Удаляет журнал команд.</span><span class="sxs-lookup"><span data-stu-id="70599-135">`Clear-History` deletes the command history.</span></span> <span data-ttu-id="70599-136">Параметр **commandline** указывает команды, которые содержат **справку** или End с **синтаксисом**.</span><span class="sxs-lookup"><span data-stu-id="70599-136">The **CommandLine** parameter specifies commands that contain **Help** or end with **Syntax**.</span></span> <span data-ttu-id="70599-137">`Get-History` отображает обновленный журнал команд и подтверждает удаление команд с **идентификатором 3**, **идентификатор 5**, **идентификатор 6** и **идентификатор 7** .</span><span class="sxs-lookup"><span data-stu-id="70599-137">`Get-History` displays the updated command history and confirms that commands **Id 3**, **Id 5**, **Id 6**, and **Id 7** were deleted.</span></span>

### <span data-ttu-id="70599-138">Пример 4. Удаление команд по идентификационному номеру</span><span class="sxs-lookup"><span data-stu-id="70599-138">Example 4: Delete commands by Id number</span></span>

<span data-ttu-id="70599-139">Эта команда удаляет определенные элементы журнала с помощью **идентификатора**. Чтобы удалить несколько команд, отправьте список **идентификаторов** с разделителями-запятыми.</span><span class="sxs-lookup"><span data-stu-id="70599-139">This command deletes specific history items using the **Id**. To delete multiple commands, submit a comma-separated list of **Id** numbers.</span></span>

```powershell
Get-History
```

```Output
  Id CommandLine
  -- -----------
   1 Set-Location C:\Test\
   2 Get-History
   3 Get-Help Get-Alias
   4 Get-Command Clear-History
   5 Get-Command Clear-History -Syntax
   6 Get-Command Clear-History -ShowCommandInfo
```

```powershell
Clear-History -Id 3, 5
Get-History
```

```Output
  Id CommandLine
  -- -----------
   1 Set-Location C:\Test\
   2 Get-History
   4 Get-Command Clear-History
   6 Get-Command Clear-History -ShowCommandInfo
   7 Get-History
   8 Clear-History -Id 3, 5
```

<span data-ttu-id="70599-140">`Get-History`Командлет отображает журнал сеанса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="70599-140">The `Get-History` cmdlet displays the PowerShell session's history.</span></span> <span data-ttu-id="70599-141">`Clear-History` Удаляет журнал команд.</span><span class="sxs-lookup"><span data-stu-id="70599-141">`Clear-History` deletes the command history.</span></span> <span data-ttu-id="70599-142">Параметр **ID** указывает, какие команды следует удалить.</span><span class="sxs-lookup"><span data-stu-id="70599-142">The **Id** parameter specifies which commands to delete.</span></span> <span data-ttu-id="70599-143">`Get-History` Отображение обновленного журнала команд и подтверждение удаления **идентификатора 3** и **идентификатора 5** .</span><span class="sxs-lookup"><span data-stu-id="70599-143">`Get-History` displays the updated command history and confirms that **Id 3** and **Id 5** were deleted.</span></span>

### <span data-ttu-id="70599-144">Пример 5. Удаление команд по идентификатору и количеству</span><span class="sxs-lookup"><span data-stu-id="70599-144">Example 5: Delete commands by Id number and count</span></span>

<span data-ttu-id="70599-145">Эта команда использует параметры **ID** и **Count** для удаления журнала команд.</span><span class="sxs-lookup"><span data-stu-id="70599-145">This command uses the **Id** and **Count** parameters to delete command history.</span></span> <span data-ttu-id="70599-146">Команды удаляются из указанного **идентификатора** в обратном порядке, от новых к старым.</span><span class="sxs-lookup"><span data-stu-id="70599-146">Commands are deleted from the specified **Id** in reverse order, newest to oldest.</span></span>

```powershell
Get-History
```

```Output
  Id CommandLine
  -- -----------
   1 Set-Location C:\Test\
   2 Get-Command Clear-History
   3 Get-Command Clear-History -Syntax
   4 Get-Command Clear-History -ShowCommandInfo
   5 Get-Help Get-Alias
   6 Get-Command Get-ChildItem -Syntax
   7 Get-Help Clear-History
   8 Set-Location C:\Test\Logs
   9 Get-Help Get-Variable
  10 Get-Help Get-ChildItem
```

```powershell
Clear-History -Id 7 -Count 5
Get-History
```

```Output
  Id CommandLine
  -- -----------
   1 Set-Location C:\Test\
   2 Get-Command Clear-History
   8 Set-Location C:\Test\Logs
   9 Get-Help Get-Variable
  10 Get-Help Get-ChildItem
  11 Clear-History -Id 7 -Count 5
```

<span data-ttu-id="70599-147">`Get-History`Командлет отображает журнал сеанса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="70599-147">The `Get-History` cmdlet displays the PowerShell session's history.</span></span> <span data-ttu-id="70599-148">`Clear-History` Удаляет журнал команд.</span><span class="sxs-lookup"><span data-stu-id="70599-148">`Clear-History` deletes the command history.</span></span> <span data-ttu-id="70599-149">Параметр **ID** указывает, что начинается с **ID 7**.</span><span class="sxs-lookup"><span data-stu-id="70599-149">The **Id** parameter specifies to begin with **Id 7**.</span></span> <span data-ttu-id="70599-150">Параметр **Count** указывает удалить пять команд, включая заданный **идентификатор**. `Get-History`отображает обновленный журнал команд и подтверждает удаление пяти команд, **идентификатор 3**  -  **ID 7**.</span><span class="sxs-lookup"><span data-stu-id="70599-150">The **Count** parameter specifies to delete five commands, inclusive of the specified **Id**. `Get-History` displays the updated command history and confirms that five commands were deleted, **Id 3** - **Id 7**.</span></span>

## <span data-ttu-id="70599-151">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="70599-151">PARAMETERS</span></span>

### <span data-ttu-id="70599-152">-CommandLine</span><span class="sxs-lookup"><span data-stu-id="70599-152">-CommandLine</span></span>

<span data-ttu-id="70599-153">Удаляет журнал команд из сеанса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="70599-153">Deletes command history from a PowerShell session.</span></span> <span data-ttu-id="70599-154">Строка должна быть точным совпадением или использовать подстановочные знаки для сопоставления команд в журнале сеанса PowerShell, который отображается в `Get-History` .</span><span class="sxs-lookup"><span data-stu-id="70599-154">The string must be an exact match or use wildcards to match commands in the PowerShell session history displayed by `Get-History`.</span></span> <span data-ttu-id="70599-155">Если ввести более одной строки, `Clear-History` удаляет команды, соответствующие любой из строк.</span><span class="sxs-lookup"><span data-stu-id="70599-155">If you enter more than one string, `Clear-History` deletes commands that match any of the strings.</span></span> <span data-ttu-id="70599-156">Параметр **commandline** можно использовать с **Count**.</span><span class="sxs-lookup"><span data-stu-id="70599-156">The **CommandLine** parameter can be used with **Count**.</span></span>

<span data-ttu-id="70599-157">Для строк с пробелом используйте одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="70599-157">For strings with a space, use single quotations.</span></span> <span data-ttu-id="70599-158">Дополнительные сведения см. в разделе [about_Quoting_Rules](About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="70599-158">For more information, see [about_Quoting_Rules](About/about_Quoting_Rules.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: CommandLineParameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="70599-159">— Количество</span><span class="sxs-lookup"><span data-stu-id="70599-159">-Count</span></span>

<span data-ttu-id="70599-160">Указывает количество записей журнала, которые `Clear-History` удаляются.</span><span class="sxs-lookup"><span data-stu-id="70599-160">Specifies the number of history entries that `Clear-History` deletes.</span></span> <span data-ttu-id="70599-161">Команды удаляются по порядку, начиная с самой старой записи в журнале.</span><span class="sxs-lookup"><span data-stu-id="70599-161">Commands are deleted in order, beginning with the oldest entry in the history.</span></span>

<span data-ttu-id="70599-162">Параметры **Count** и **ID** можно использовать совместно.</span><span class="sxs-lookup"><span data-stu-id="70599-162">The **Count** and **Id** parameters can be used together.</span></span> <span data-ttu-id="70599-163">Параметр **Count** указывает количество команд для удаления, включая указанный **идентификатор**. Начиная с указанного **идентификатора**, команды удаляются в обратную последовательность.</span><span class="sxs-lookup"><span data-stu-id="70599-163">The **Count** parameter specifies the number of commands to delete, inclusive of the specified **Id**. Beginning at the specified **Id**, commands are deleted in reverse sequential order.</span></span> <span data-ttu-id="70599-164">Например, если **идентификатор** равен 30, а значение **счетчика** — 10, то `Clear-History` элементы удаляются с 21 до 30.</span><span class="sxs-lookup"><span data-stu-id="70599-164">For example, if the **Id** is 30 and the **Count** is 10, `Clear-History` deletes items 21 through 30.</span></span>

<span data-ttu-id="70599-165">Параметры **Count** и **commandline** можно использовать совместно.</span><span class="sxs-lookup"><span data-stu-id="70599-165">The **Count** and **CommandLine** parameters can be used together.</span></span> <span data-ttu-id="70599-166">**Count** указывает количество команд для удаления, соответствующих значению параметра **командной строки** .</span><span class="sxs-lookup"><span data-stu-id="70599-166">**Count** specifies the number of commands to delete that match **CommandLine** parameter value.</span></span> <span data-ttu-id="70599-167">Команды удаляются в последовательном порядке.</span><span class="sxs-lookup"><span data-stu-id="70599-167">The commands are deleted in sequential order.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="70599-168">-Id</span><span class="sxs-lookup"><span data-stu-id="70599-168">-Id</span></span>

<span data-ttu-id="70599-169">Указывает **идентификатор** журнала команд, который `Clear-History` удаляется.</span><span class="sxs-lookup"><span data-stu-id="70599-169">Specifies the command history **Id** that `Clear-History` deletes.</span></span> <span data-ttu-id="70599-170">Чтобы отобразить **идентификационные** номера, используйте `Get-History` командлет.</span><span class="sxs-lookup"><span data-stu-id="70599-170">To display **Id** numbers, use the `Get-History` cmdlet.</span></span> <span data-ttu-id="70599-171">Номера **идентификаторов** являются последовательными, а команды сохраняют свой **идентификационный** номер во время сеанса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="70599-171">The **Id** numbers are sequential and commands keep their **Id** number throughout a PowerShell session.</span></span> <span data-ttu-id="70599-172">Параметр **ID** можно использовать с параметрами **Count** и **новейшие**.</span><span class="sxs-lookup"><span data-stu-id="70599-172">The **Id** parameter can be used with **Count** and **Newest**.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: IDParameter
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="70599-173">— Самый новый</span><span class="sxs-lookup"><span data-stu-id="70599-173">-Newest</span></span>

<span data-ttu-id="70599-174">При использовании **последнего** параметра `Clear-History` удаляет последние записи в журнале.</span><span class="sxs-lookup"><span data-stu-id="70599-174">When the **Newest** parameter is used, `Clear-History` deletes the newest entries in the history.</span></span> <span data-ttu-id="70599-175">По умолчанию `Clear-History` удаляет самые старые записи в журнале.</span><span class="sxs-lookup"><span data-stu-id="70599-175">By default, `Clear-History` deletes the oldest entries in the history.</span></span>

<span data-ttu-id="70599-176">**Последний** параметр можно использовать с **идентификатором** и **счетчиком**.</span><span class="sxs-lookup"><span data-stu-id="70599-176">The **Newest** parameter can be used with **Id** and **Count**.</span></span> <span data-ttu-id="70599-177">Параметр **Count** указывает количество команд для удаления, включая указанный **идентификатор**. Начиная с указанного **идентификатора**, команды удаляются в последовательном порядке.</span><span class="sxs-lookup"><span data-stu-id="70599-177">The **Count** parameter specifies the number of commands to delete, inclusive of the specified **Id**. Beginning at the specified **Id**, commands are deleted in sequential order.</span></span> <span data-ttu-id="70599-178">Например, если **идентификатор** равен 30, а значение **счетчика** — 10, то `Clear-History` удаляются элементы с 30 по 39.</span><span class="sxs-lookup"><span data-stu-id="70599-178">For example, if the **Id** is 30 and the **Count** is 10, `Clear-History` deletes items 30 through 39.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="70599-179">-Confirm</span><span class="sxs-lookup"><span data-stu-id="70599-179">-Confirm</span></span>

<span data-ttu-id="70599-180">Запрашивает подтверждение перед запуском `Clear-History` командлета.</span><span class="sxs-lookup"><span data-stu-id="70599-180">Prompts you for confirmation before running the `Clear-History` cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="70599-181">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="70599-181">-WhatIf</span></span>

<span data-ttu-id="70599-182">Показывает, что произойдет при `Clear-History` запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="70599-182">Shows what would happen if the `Clear-History` cmdlet runs.</span></span> <span data-ttu-id="70599-183">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="70599-183">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="70599-184">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="70599-184">CommonParameters</span></span>

<span data-ttu-id="70599-185">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="70599-185">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="70599-186">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="70599-186">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="70599-187">Входные данные</span><span class="sxs-lookup"><span data-stu-id="70599-187">INPUTS</span></span>

### <span data-ttu-id="70599-188">None</span><span class="sxs-lookup"><span data-stu-id="70599-188">None</span></span>

<span data-ttu-id="70599-189">Вы не можете передать объекты в `Clear-History` .</span><span class="sxs-lookup"><span data-stu-id="70599-189">You cannot pipe objects to `Clear-History`.</span></span>

## <span data-ttu-id="70599-190">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="70599-190">OUTPUTS</span></span>

### <span data-ttu-id="70599-191">None</span><span class="sxs-lookup"><span data-stu-id="70599-191">None</span></span>

<span data-ttu-id="70599-192">`Clear-History` не создает никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="70599-192">`Clear-History` does not generate any output.</span></span>

## <span data-ttu-id="70599-193">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="70599-193">NOTES</span></span>

<span data-ttu-id="70599-194">Журнал сеанса PowerShell представляет собой список команд, вводимых во время сеанса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="70599-194">The PowerShell session history is a list of the commands entered during a PowerShell session.</span></span> <span data-ttu-id="70599-195">Вы можете просматривать журнал, добавлять и удалять команды, а также выполнять команды, хранящиеся в журнале.</span><span class="sxs-lookup"><span data-stu-id="70599-195">You can view the history, add and delete commands, and run commands from the history.</span></span> <span data-ttu-id="70599-196">Дополнительные сведения см. в разделе [about_History](About/about_History.md).</span><span class="sxs-lookup"><span data-stu-id="70599-196">For more information, see [about_History](About/about_History.md).</span></span>

<span data-ttu-id="70599-197">Журнал сеанса управляется отдельно от журнала, поддерживаемого модулем **PSReadLine** .</span><span class="sxs-lookup"><span data-stu-id="70599-197">The session history is managed separately from the history maintained by the **PSReadLine** module.</span></span>
<span data-ttu-id="70599-198">Оба журнала доступны в сеансах, где загружен **PSReadLine** .</span><span class="sxs-lookup"><span data-stu-id="70599-198">Both histories are available in sessions where **PSReadLine** is loaded.</span></span> <span data-ttu-id="70599-199">Этот командлет работает только с журналом сеанса.</span><span class="sxs-lookup"><span data-stu-id="70599-199">This cmdlet only works with the session history.</span></span> <span data-ttu-id="70599-200">Дополнительные сведения см. в разделе [about_PSReadLine](../PSReadLine/About/about_PSReadLine.md).</span><span class="sxs-lookup"><span data-stu-id="70599-200">For more information see, [about_PSReadLine](../PSReadLine/About/about_PSReadLine.md).</span></span>

## <span data-ttu-id="70599-201">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="70599-201">RELATED LINKS</span></span>

[<span data-ttu-id="70599-202">about_History</span><span class="sxs-lookup"><span data-stu-id="70599-202">about_History</span></span>](About/about_History.md)

[<span data-ttu-id="70599-203">about_PSReadLine</span><span class="sxs-lookup"><span data-stu-id="70599-203">about_PSReadLine</span></span>](../PSReadLine/About/about_PSReadLine.md)

[<span data-ttu-id="70599-204">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="70599-204">about_Quoting_Rules</span></span>](About/about_Quoting_Rules.md)

[<span data-ttu-id="70599-205">Add-History</span><span class="sxs-lookup"><span data-stu-id="70599-205">Add-History</span></span>](Add-History.md)

[<span data-ttu-id="70599-206">Get-History</span><span class="sxs-lookup"><span data-stu-id="70599-206">Get-History</span></span>](Get-History.md)

[<span data-ttu-id="70599-207">Invoke-History</span><span class="sxs-lookup"><span data-stu-id="70599-207">Invoke-History</span></span>](Invoke-History.md)

[<span data-ttu-id="70599-208">Get-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="70599-208">Get-PSReadLineOption</span></span>](/powershell/module/psreadline/get-psreadlineoption)

[<span data-ttu-id="70599-209">Set-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="70599-209">Set-PSReadLineOption</span></span>](/powershell/module/psreadline/set-psreadlineoption)

