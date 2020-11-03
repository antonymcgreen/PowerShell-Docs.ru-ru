---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 05/13/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/clear-history?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-History
ms.openlocfilehash: 332cab9d8a635bd4b7deb3c4792e528c8a25e887
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93226725"
---
# <span data-ttu-id="844e7-103">Clear-History</span><span class="sxs-lookup"><span data-stu-id="844e7-103">Clear-History</span></span>

## <span data-ttu-id="844e7-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="844e7-104">SYNOPSIS</span></span>
<span data-ttu-id="844e7-105">Удаляет записи из журнала команд сеанса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="844e7-105">Deletes entries from the PowerShell session command history.</span></span>

## <span data-ttu-id="844e7-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="844e7-106">SYNTAX</span></span>

### <span data-ttu-id="844e7-107">Идпараметер (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="844e7-107">IDParameter (Default)</span></span>

```
Clear-History [[-Id] <int[]>] [[-Count] <int>] [-Newest] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="844e7-108">коммандлинепараметер</span><span class="sxs-lookup"><span data-stu-id="844e7-108">CommandLineParameter</span></span>

```
Clear-History [[-Count] <int>] [-CommandLine <string[]>] [-Newest] [-WhatIf] [-Confirm]
[<CommonParameters>]
```

## <span data-ttu-id="844e7-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="844e7-109">DESCRIPTION</span></span>

<span data-ttu-id="844e7-110">`Clear-History` Удаляет журнал команд из сеанса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="844e7-110">`Clear-History` deletes the command history from a PowerShell session.</span></span> <span data-ttu-id="844e7-111">Каждый сеанс PowerShell имеет собственный журнал команд.</span><span class="sxs-lookup"><span data-stu-id="844e7-111">Each PowerShell session has its own command history.</span></span> <span data-ttu-id="844e7-112">Чтобы отобразить журнал команд, используйте `Get-History` командлет.</span><span class="sxs-lookup"><span data-stu-id="844e7-112">To display the command history, use the `Get-History` cmdlet.</span></span>

<span data-ttu-id="844e7-113">По умолчанию `Clear-History` удаляет весь журнал команд из сеанса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="844e7-113">By default, `Clear-History` deletes the entire command history from a PowerShell session.</span></span> <span data-ttu-id="844e7-114">`Clear-History`Для удаления выбранных команд можно использовать параметры.</span><span class="sxs-lookup"><span data-stu-id="844e7-114">You can use parameters with `Clear-History` to delete selected commands.</span></span>

<span data-ttu-id="844e7-115">`Clear-History` не очищает `PSReadLine` файл журнала команд.</span><span class="sxs-lookup"><span data-stu-id="844e7-115">`Clear-History` does not clear the `PSReadLine` command history file.</span></span> <span data-ttu-id="844e7-116">`PSReadLine`Модуль хранит файл журнала, содержащий все команды PowerShell из каждого сеанса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="844e7-116">The `PSReadLine` module stores a history file that contains every PowerShell command from every PowerShell session.</span></span> <span data-ttu-id="844e7-117">В командной строке PowerShell используйте клавиши со стрелками вверх и вниз для прокрутки журнала команд.</span><span class="sxs-lookup"><span data-stu-id="844e7-117">From a PowerShell prompt, use the up and down arrows on your keyboard to scroll through the command history.</span></span> <span data-ttu-id="844e7-118">Чтобы отобразить `PSReadLine` конфигурацию для журнала команд, используйте `Get-PSReadLineOption` .</span><span class="sxs-lookup"><span data-stu-id="844e7-118">To display the `PSReadLine` configuration for command history, use `Get-PSReadLineOption`.</span></span>
<span data-ttu-id="844e7-119">`PSReadLine` поставляется с PowerShell 5,0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="844e7-119">`PSReadLine` shipped with PowerShell 5.0 and above.</span></span> <span data-ttu-id="844e7-120">Дополнительные сведения см. в разделе [about_PSReadLine](../PSReadLine/About/about_PSReadLine.md).</span><span class="sxs-lookup"><span data-stu-id="844e7-120">For more information, see [about_PSReadLine](../PSReadLine/About/about_PSReadLine.md).</span></span>

## <span data-ttu-id="844e7-121">Примеры</span><span class="sxs-lookup"><span data-stu-id="844e7-121">EXAMPLES</span></span>

### <span data-ttu-id="844e7-122">Пример 1. Удаление журнала команд из сеанса PowerShell</span><span class="sxs-lookup"><span data-stu-id="844e7-122">Example 1: Delete the command history from a PowerShell session</span></span>

<span data-ttu-id="844e7-123">Эта команда удаляет все команды из журнала сеанса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="844e7-123">This command deletes all of the commands from a PowerShell session's history.</span></span>

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

<span data-ttu-id="844e7-124">`Get-History`Командлет отображает журнал сеанса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="844e7-124">The `Get-History` cmdlet displays the PowerShell session's history.</span></span> <span data-ttu-id="844e7-125">`Clear-History` Удаляет весь журнал команд.</span><span class="sxs-lookup"><span data-stu-id="844e7-125">`Clear-History` deletes the entire command history.</span></span> <span data-ttu-id="844e7-126">`Get-History` отображает обновленный журнал команд и подтверждает, что предыдущая история была удалена.</span><span class="sxs-lookup"><span data-stu-id="844e7-126">`Get-History` displays the updated command history and confirms the prior history was deleted.</span></span>

### <span data-ttu-id="844e7-127">Пример 2. Удаление последних команд</span><span class="sxs-lookup"><span data-stu-id="844e7-127">Example 2: Delete the newest commands</span></span>

<span data-ttu-id="844e7-128">Эта команда использует параметры **Count** и **новейшие** для удаления последних команд из журнала сеанса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="844e7-128">This command uses the **Count** and **Newest** parameters to delete the newest commands from a PowerShell session's history.</span></span>

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

<span data-ttu-id="844e7-129">`Get-History`Командлет отображает журнал сеанса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="844e7-129">The `Get-History` cmdlet displays the PowerShell session's history.</span></span> <span data-ttu-id="844e7-130">`Clear-History` используется для удаления журнала команд.</span><span class="sxs-lookup"><span data-stu-id="844e7-130">`Clear-History` is used to delete the command history.</span></span> <span data-ttu-id="844e7-131">Параметр **Count** указывает количество команд для удаления, включая указанный **идентификатор**. **Последний** параметр указывает, что из журнала удаляются последние команды.</span><span class="sxs-lookup"><span data-stu-id="844e7-131">The **Count** parameter specifies the number of commands to delete, inclusive of the specified **Id**. The **Newest** parameter specifies that the newest commands are cleared from the history.</span></span> <span data-ttu-id="844e7-132">`Get-History`отображает обновленный журнал команд и подтверждает, что были удалены пять последних команд с **идентификатором 6**  -  **ID 10**.</span><span class="sxs-lookup"><span data-stu-id="844e7-132">`Get-History` displays the updated command history and confirms that the five newest commands were deleted, **Id 6** - **Id 10**.</span></span>

### <span data-ttu-id="844e7-133">Пример 3. Удаление команд, соответствующих указанным условиям</span><span class="sxs-lookup"><span data-stu-id="844e7-133">Example 3: Delete commands that match specific criteria</span></span>

<span data-ttu-id="844e7-134">Эта команда удаляет команды, соответствующие определенным условиям, определенным параметром **commandline** .</span><span class="sxs-lookup"><span data-stu-id="844e7-134">This command deletes commands that match specific criteria defined by the **CommandLine** parameter.</span></span>

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

<span data-ttu-id="844e7-135">`Get-History`Командлет отображает журнал сеанса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="844e7-135">The `Get-History` cmdlet displays the PowerShell session's history.</span></span> <span data-ttu-id="844e7-136">`Clear-History` Удаляет журнал команд.</span><span class="sxs-lookup"><span data-stu-id="844e7-136">`Clear-History` deletes the command history.</span></span> <span data-ttu-id="844e7-137">Параметр **commandline** указывает команды, которые содержат **справку** или End с **синтаксисом**.</span><span class="sxs-lookup"><span data-stu-id="844e7-137">The **CommandLine** parameter specifies commands that contain **Help** or end with **Syntax**.</span></span> <span data-ttu-id="844e7-138">`Get-History` отображает обновленный журнал команд и подтверждает удаление команд с **идентификатором 3** , **идентификатор 5** , **идентификатор 6** и **идентификатор 7** .</span><span class="sxs-lookup"><span data-stu-id="844e7-138">`Get-History` displays the updated command history and confirms that commands **Id 3** , **Id 5** , **Id 6** , and **Id 7** were deleted.</span></span>

### <span data-ttu-id="844e7-139">Пример 4. Удаление команд по идентификационному номеру</span><span class="sxs-lookup"><span data-stu-id="844e7-139">Example 4: Delete commands by Id number</span></span>

<span data-ttu-id="844e7-140">Эта команда удаляет определенные элементы журнала с помощью **идентификатора**. Чтобы удалить несколько команд, отправьте список **идентификаторов** с разделителями-запятыми.</span><span class="sxs-lookup"><span data-stu-id="844e7-140">This command deletes specific history items using the **Id**. To delete multiple commands, submit a comma-separated list of **Id** numbers.</span></span>

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

<span data-ttu-id="844e7-141">`Get-History`Командлет отображает журнал сеанса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="844e7-141">The `Get-History` cmdlet displays the PowerShell session's history.</span></span> <span data-ttu-id="844e7-142">`Clear-History` Удаляет журнал команд.</span><span class="sxs-lookup"><span data-stu-id="844e7-142">`Clear-History` deletes the command history.</span></span> <span data-ttu-id="844e7-143">Параметр **ID** указывает, какие команды следует удалить.</span><span class="sxs-lookup"><span data-stu-id="844e7-143">The **Id** parameter specifies which commands to delete.</span></span> <span data-ttu-id="844e7-144">`Get-History` Отображение обновленного журнала команд и подтверждение удаления **идентификатора 3** и **идентификатора 5** .</span><span class="sxs-lookup"><span data-stu-id="844e7-144">`Get-History` displays the updated command history and confirms that **Id 3** and **Id 5** were deleted.</span></span>

### <span data-ttu-id="844e7-145">Пример 5. Удаление команд по идентификатору и количеству</span><span class="sxs-lookup"><span data-stu-id="844e7-145">Example 5: Delete commands by Id number and count</span></span>

<span data-ttu-id="844e7-146">Эта команда использует параметры **ID** и **Count** для удаления журнала команд.</span><span class="sxs-lookup"><span data-stu-id="844e7-146">This command uses the **Id** and **Count** parameters to delete command history.</span></span> <span data-ttu-id="844e7-147">Команды удаляются из указанного **идентификатора** в обратном порядке, от новых к старым.</span><span class="sxs-lookup"><span data-stu-id="844e7-147">Commands are deleted from the specified **Id** in reverse order, newest to oldest.</span></span>

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

<span data-ttu-id="844e7-148">`Get-History`Командлет отображает журнал сеанса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="844e7-148">The `Get-History` cmdlet displays the PowerShell session's history.</span></span> <span data-ttu-id="844e7-149">`Clear-History` Удаляет журнал команд.</span><span class="sxs-lookup"><span data-stu-id="844e7-149">`Clear-History` deletes the command history.</span></span> <span data-ttu-id="844e7-150">Параметр **ID** указывает, что начинается с **ID 7**.</span><span class="sxs-lookup"><span data-stu-id="844e7-150">The **Id** parameter specifies to begin with **Id 7**.</span></span> <span data-ttu-id="844e7-151">Параметр **Count** указывает удалить пять команд, включая заданный **идентификатор**. `Get-History`отображает обновленный журнал команд и подтверждает удаление пяти команд, **идентификатор 3**  -  **ID 7**.</span><span class="sxs-lookup"><span data-stu-id="844e7-151">The **Count** parameter specifies to delete five commands, inclusive of the specified **Id**. `Get-History` displays the updated command history and confirms that five commands were deleted, **Id 3** - **Id 7**.</span></span>

## <span data-ttu-id="844e7-152">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="844e7-152">PARAMETERS</span></span>

### <span data-ttu-id="844e7-153">-CommandLine</span><span class="sxs-lookup"><span data-stu-id="844e7-153">-CommandLine</span></span>

<span data-ttu-id="844e7-154">Удаляет журнал команд из сеанса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="844e7-154">Deletes command history from a PowerShell session.</span></span> <span data-ttu-id="844e7-155">Строка должна быть точным совпадением или использовать подстановочные знаки для сопоставления команд в журнале сеанса PowerShell, который отображается в `Get-History` .</span><span class="sxs-lookup"><span data-stu-id="844e7-155">The string must be an exact match or use wildcards to match commands in the PowerShell session history displayed by `Get-History`.</span></span> <span data-ttu-id="844e7-156">Если ввести более одной строки, `Clear-History` удаляет команды, соответствующие любой из строк.</span><span class="sxs-lookup"><span data-stu-id="844e7-156">If you enter more than one string, `Clear-History` deletes commands that match any of the strings.</span></span> <span data-ttu-id="844e7-157">Параметр **commandline** можно использовать с **Count**.</span><span class="sxs-lookup"><span data-stu-id="844e7-157">The **CommandLine** parameter can be used with **Count**.</span></span>

<span data-ttu-id="844e7-158">Для строк с пробелом используйте одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="844e7-158">For strings with a space, use single quotations.</span></span> <span data-ttu-id="844e7-159">Дополнительные сведения см. в разделе [about_Quoting_Rules](About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="844e7-159">For more information, see [about_Quoting_Rules](About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="844e7-160">— Количество</span><span class="sxs-lookup"><span data-stu-id="844e7-160">-Count</span></span>

<span data-ttu-id="844e7-161">Указывает количество записей журнала, которые `Clear-History` удаляются.</span><span class="sxs-lookup"><span data-stu-id="844e7-161">Specifies the number of history entries that `Clear-History` deletes.</span></span> <span data-ttu-id="844e7-162">Команды удаляются по порядку, начиная с самой старой записи в журнале.</span><span class="sxs-lookup"><span data-stu-id="844e7-162">Commands are deleted in order, beginning with the oldest entry in the history.</span></span>

<span data-ttu-id="844e7-163">Параметры **Count** и **ID** можно использовать совместно.</span><span class="sxs-lookup"><span data-stu-id="844e7-163">The **Count** and **Id** parameters can be used together.</span></span> <span data-ttu-id="844e7-164">Параметр **Count** указывает количество команд для удаления, включая указанный **идентификатор**. Начиная с указанного **идентификатора** , команды удаляются в обратную последовательность.</span><span class="sxs-lookup"><span data-stu-id="844e7-164">The **Count** parameter specifies the number of commands to delete, inclusive of the specified **Id**. Beginning at the specified **Id** , commands are deleted in reverse sequential order.</span></span> <span data-ttu-id="844e7-165">Например, если **идентификатор** равен 30, а значение **счетчика** — 10, то `Clear-History` элементы удаляются с 21 до 30.</span><span class="sxs-lookup"><span data-stu-id="844e7-165">For example, if the **Id** is 30 and the **Count** is 10, `Clear-History` deletes items 21 through 30.</span></span>

<span data-ttu-id="844e7-166">Параметры **Count** и **commandline** можно использовать совместно.</span><span class="sxs-lookup"><span data-stu-id="844e7-166">The **Count** and **CommandLine** parameters can be used together.</span></span> <span data-ttu-id="844e7-167">**Count** указывает количество команд для удаления, соответствующих значению параметра **командной строки** .</span><span class="sxs-lookup"><span data-stu-id="844e7-167">**Count** specifies the number of commands to delete that match **CommandLine** parameter value.</span></span> <span data-ttu-id="844e7-168">Команды удаляются в последовательном порядке.</span><span class="sxs-lookup"><span data-stu-id="844e7-168">The commands are deleted in sequential order.</span></span>

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

### <span data-ttu-id="844e7-169">-Id</span><span class="sxs-lookup"><span data-stu-id="844e7-169">-Id</span></span>

<span data-ttu-id="844e7-170">Указывает **идентификатор** журнала команд, который `Clear-History` удаляется.</span><span class="sxs-lookup"><span data-stu-id="844e7-170">Specifies the command history **Id** that `Clear-History` deletes.</span></span> <span data-ttu-id="844e7-171">Чтобы отобразить **идентификационные** номера, используйте `Get-History` командлет.</span><span class="sxs-lookup"><span data-stu-id="844e7-171">To display **Id** numbers, use the `Get-History` cmdlet.</span></span> <span data-ttu-id="844e7-172">Номера **идентификаторов** являются последовательными, а команды сохраняют свой **идентификационный** номер во время сеанса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="844e7-172">The **Id** numbers are sequential and commands keep their **Id** number throughout a PowerShell session.</span></span> <span data-ttu-id="844e7-173">Параметр **ID** можно использовать с параметрами **Count** и **новейшие**.</span><span class="sxs-lookup"><span data-stu-id="844e7-173">The **Id** parameter can be used with **Count** and **Newest**.</span></span>

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

### <span data-ttu-id="844e7-174">— Самый новый</span><span class="sxs-lookup"><span data-stu-id="844e7-174">-Newest</span></span>

<span data-ttu-id="844e7-175">При использовании **последнего** параметра `Clear-History` удаляет последние записи в журнале.</span><span class="sxs-lookup"><span data-stu-id="844e7-175">When the **Newest** parameter is used, `Clear-History` deletes the newest entries in the history.</span></span> <span data-ttu-id="844e7-176">По умолчанию `Clear-History` удаляет самые старые записи в журнале.</span><span class="sxs-lookup"><span data-stu-id="844e7-176">By default, `Clear-History` deletes the oldest entries in the history.</span></span>

<span data-ttu-id="844e7-177">**Последний** параметр можно использовать с **идентификатором** и **счетчиком**.</span><span class="sxs-lookup"><span data-stu-id="844e7-177">The **Newest** parameter can be used with **Id** and **Count**.</span></span> <span data-ttu-id="844e7-178">Параметр **Count** указывает количество команд для удаления, включая указанный **идентификатор**. Начиная с указанного **идентификатора** , команды удаляются в последовательном порядке.</span><span class="sxs-lookup"><span data-stu-id="844e7-178">The **Count** parameter specifies the number of commands to delete, inclusive of the specified **Id**. Beginning at the specified **Id** , commands are deleted in sequential order.</span></span> <span data-ttu-id="844e7-179">Например, если **идентификатор** равен 30, а значение **счетчика** — 10, то `Clear-History` удаляются элементы с 30 по 39.</span><span class="sxs-lookup"><span data-stu-id="844e7-179">For example, if the **Id** is 30 and the **Count** is 10, `Clear-History` deletes items 30 through 39.</span></span>

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

### <span data-ttu-id="844e7-180">-Confirm</span><span class="sxs-lookup"><span data-stu-id="844e7-180">-Confirm</span></span>

<span data-ttu-id="844e7-181">Запрашивает подтверждение перед запуском `Clear-History` командлета.</span><span class="sxs-lookup"><span data-stu-id="844e7-181">Prompts you for confirmation before running the `Clear-History` cmdlet.</span></span>

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

### <span data-ttu-id="844e7-182">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="844e7-182">-WhatIf</span></span>

<span data-ttu-id="844e7-183">Показывает, что произойдет при `Clear-History` запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="844e7-183">Shows what would happen if the `Clear-History` cmdlet runs.</span></span> <span data-ttu-id="844e7-184">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="844e7-184">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="844e7-185">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="844e7-185">CommonParameters</span></span>

<span data-ttu-id="844e7-186">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="844e7-186">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="844e7-187">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="844e7-187">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="844e7-188">Входные данные</span><span class="sxs-lookup"><span data-stu-id="844e7-188">INPUTS</span></span>

### <span data-ttu-id="844e7-189">Нет</span><span class="sxs-lookup"><span data-stu-id="844e7-189">None</span></span>

<span data-ttu-id="844e7-190">Вы не можете передать объекты в `Clear-History` .</span><span class="sxs-lookup"><span data-stu-id="844e7-190">You cannot pipe objects to `Clear-History`.</span></span>

## <span data-ttu-id="844e7-191">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="844e7-191">OUTPUTS</span></span>

### <span data-ttu-id="844e7-192">Нет</span><span class="sxs-lookup"><span data-stu-id="844e7-192">None</span></span>

<span data-ttu-id="844e7-193">`Clear-History` не создает никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="844e7-193">`Clear-History` does not generate any output.</span></span>

## <span data-ttu-id="844e7-194">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="844e7-194">NOTES</span></span>

<span data-ttu-id="844e7-195">Журнал сеанса PowerShell представляет собой список команд, вводимых во время сеанса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="844e7-195">The PowerShell session history is a list of the commands entered during a PowerShell session.</span></span> <span data-ttu-id="844e7-196">Вы можете просматривать журнал, добавлять и удалять команды, а также выполнять команды, хранящиеся в журнале.</span><span class="sxs-lookup"><span data-stu-id="844e7-196">You can view the history, add and delete commands, and run commands from the history.</span></span> <span data-ttu-id="844e7-197">Дополнительные сведения см. в разделе [about_History](About/about_History.md).</span><span class="sxs-lookup"><span data-stu-id="844e7-197">For more information, see [about_History](About/about_History.md).</span></span>

<span data-ttu-id="844e7-198">Журнал сеанса управляется отдельно от журнала, поддерживаемого модулем **PSReadLine** .</span><span class="sxs-lookup"><span data-stu-id="844e7-198">The session history is managed separately from the history maintained by the **PSReadLine** module.</span></span>
<span data-ttu-id="844e7-199">Оба журнала доступны в сеансах, где загружен **PSReadLine** .</span><span class="sxs-lookup"><span data-stu-id="844e7-199">Both histories are available in sessions where **PSReadLine** is loaded.</span></span> <span data-ttu-id="844e7-200">Этот командлет работает только с журналом сеанса.</span><span class="sxs-lookup"><span data-stu-id="844e7-200">This cmdlet only works with the session history.</span></span> <span data-ttu-id="844e7-201">Дополнительные сведения см. в разделе [about_PSReadLine](../PSReadLine/About/about_PSReadLine.md).</span><span class="sxs-lookup"><span data-stu-id="844e7-201">For more information see, [about_PSReadLine](../PSReadLine/About/about_PSReadLine.md).</span></span>

## <span data-ttu-id="844e7-202">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="844e7-202">RELATED LINKS</span></span>

[<span data-ttu-id="844e7-203">about_History</span><span class="sxs-lookup"><span data-stu-id="844e7-203">about_History</span></span>](About/about_History.md)

[<span data-ttu-id="844e7-204">about_PSReadLine</span><span class="sxs-lookup"><span data-stu-id="844e7-204">about_PSReadLine</span></span>](../PSReadLine/About/about_PSReadLine.md)

[<span data-ttu-id="844e7-205">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="844e7-205">about_Quoting_Rules</span></span>](About/about_Quoting_Rules.md)

[<span data-ttu-id="844e7-206">Add-History</span><span class="sxs-lookup"><span data-stu-id="844e7-206">Add-History</span></span>](Add-History.md)

[<span data-ttu-id="844e7-207">Get-History</span><span class="sxs-lookup"><span data-stu-id="844e7-207">Get-History</span></span>](Get-History.md)

[<span data-ttu-id="844e7-208">Invoke-History</span><span class="sxs-lookup"><span data-stu-id="844e7-208">Invoke-History</span></span>](Invoke-History.md)

[<span data-ttu-id="844e7-209">Get-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="844e7-209">Get-PSReadLineOption</span></span>](/powershell/module/psreadline/get-psreadlineoption)

[<span data-ttu-id="844e7-210">Set-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="844e7-210">Set-PSReadLineOption</span></span>](/powershell/module/psreadline/set-psreadlineoption)
