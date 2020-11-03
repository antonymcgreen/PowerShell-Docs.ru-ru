---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 2/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/set-alias?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Alias
ms.openlocfilehash: 2a84c08022689d53c3273f1b6f802cfeae67953d
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93226577"
---
# <span data-ttu-id="7cdcb-103">Set-Alias</span><span class="sxs-lookup"><span data-stu-id="7cdcb-103">Set-Alias</span></span>

## <span data-ttu-id="7cdcb-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="7cdcb-104">SYNOPSIS</span></span>
<span data-ttu-id="7cdcb-105">Создает или изменяет псевдоним для командлета или другой команды в текущем сеансе PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7cdcb-105">Creates or changes an alias for a cmdlet or other command in the current PowerShell session.</span></span>

## <span data-ttu-id="7cdcb-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7cdcb-106">SYNTAX</span></span>

### <span data-ttu-id="7cdcb-107">Default (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="7cdcb-107">Default (Default)</span></span>

```
Set-Alias [-Name] <string> [-Value] <string> [-Description <string>] [-Option <ScopedItemOptions>]
 [-PassThru] [-Scope <string>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="7cdcb-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7cdcb-108">DESCRIPTION</span></span>

<span data-ttu-id="7cdcb-109">`Set-Alias`Командлет создает или изменяет псевдоним для командлета или команды, например функции, скрипта, файла или другого исполняемого файла.</span><span class="sxs-lookup"><span data-stu-id="7cdcb-109">The `Set-Alias` cmdlet creates or changes an alias for a cmdlet or a command, such as a function, script, file, or other executable.</span></span> <span data-ttu-id="7cdcb-110">Псевдоним — это альтернативное имя, которое ссылается на командлет или команду.</span><span class="sxs-lookup"><span data-stu-id="7cdcb-110">An alias is an alternate name that refers to a cmdlet or command.</span></span>
<span data-ttu-id="7cdcb-111">Например, `sal` является псевдонимом для `Set-Alias` командлета.</span><span class="sxs-lookup"><span data-stu-id="7cdcb-111">For example, `sal` is the alias for the `Set-Alias` cmdlet.</span></span> <span data-ttu-id="7cdcb-112">Дополнительные сведения см. в разделе [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="7cdcb-112">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>

<span data-ttu-id="7cdcb-113">Командлет может иметь несколько псевдонимов, но псевдоним может быть связан только с одним командлетом.</span><span class="sxs-lookup"><span data-stu-id="7cdcb-113">A cmdlet can have multiple aliases, but an alias can only be associated with one cmdlet.</span></span> <span data-ttu-id="7cdcb-114">Можно использовать для повторного `Set-Alias` назначения существующего псевдонима другому командлету или для изменения свойств псевдонима, таких как описание.</span><span class="sxs-lookup"><span data-stu-id="7cdcb-114">You can use `Set-Alias` to reassign an existing alias to another cmdlet, or change an alias's properties, such as the description.</span></span>

<span data-ttu-id="7cdcb-115">Псевдоним, созданный или измененный, `Set-Alias` не является постоянным и доступен только во время текущего сеанса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7cdcb-115">An alias that is created or changed by `Set-Alias` is not permanent and is only available during the current PowerShell session.</span></span> <span data-ttu-id="7cdcb-116">При закрытии сеанса PowerShell псевдоним удаляется.</span><span class="sxs-lookup"><span data-stu-id="7cdcb-116">When the PowerShell session is closed, the alias is removed.</span></span>

## <span data-ttu-id="7cdcb-117">Примеры</span><span class="sxs-lookup"><span data-stu-id="7cdcb-117">EXAMPLES</span></span>

### <span data-ttu-id="7cdcb-118">Пример 1. Создание псевдонима для командлета</span><span class="sxs-lookup"><span data-stu-id="7cdcb-118">Example 1: Create an alias for a cmdlet</span></span>

<span data-ttu-id="7cdcb-119">Эта команда создает псевдоним для командлета в текущем сеансе PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7cdcb-119">This command creates an alias to a cmdlet in the current PowerShell session.</span></span>

```
PS> Set-Alias -Name list -Value Get-ChildItem

PS> Get-Alias -Name list

CommandType     Name
-----------     ----
Alias           list -> Get-ChildItem
```

<span data-ttu-id="7cdcb-120">`Set-Alias`Командлет создает псевдоним в текущем сеансе PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7cdcb-120">The `Set-Alias` cmdlet creates an alias in the current PowerShell session.</span></span> <span data-ttu-id="7cdcb-121">Параметр **Name** задает имя псевдонима, `list` .</span><span class="sxs-lookup"><span data-stu-id="7cdcb-121">The **Name** parameter specifies the alias's name, `list`.</span></span> <span data-ttu-id="7cdcb-122">Параметр **value** указывает командлет, который выполняется псевдонимом.</span><span class="sxs-lookup"><span data-stu-id="7cdcb-122">The **Value** parameter specifies the cmdlet that the alias runs.</span></span>

<span data-ttu-id="7cdcb-123">Чтобы запустить псевдоним, введите `list` в командной строке PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7cdcb-123">To run the alias, type `list` on the PowerShell command line.</span></span>

### <span data-ttu-id="7cdcb-124">Пример 2. повторное назначение существующего псевдонима другому командлету</span><span class="sxs-lookup"><span data-stu-id="7cdcb-124">Example 2: Reassign an existing alias to a different cmdlet</span></span>

<span data-ttu-id="7cdcb-125">Эта команда переназначает существующий псевдоним для выполнения другого командлета.</span><span class="sxs-lookup"><span data-stu-id="7cdcb-125">This command reassigns an existing alias to run a different cmdlet.</span></span>

```
PS> Get-Alias -Name list

CommandType     Name
-----------     ----
Alias           list -> Get-ChildItem

PS> Set-Alias -Name list -Value Get-Location

PS> Get-Alias -Name list

CommandType     Name
-----------     ----
Alias           list -> Get-Location
```

<span data-ttu-id="7cdcb-126">`Get-Alias`Командлет использует параметр **Name** для вывода `list` псевдонима.</span><span class="sxs-lookup"><span data-stu-id="7cdcb-126">The `Get-Alias` cmdlet uses the **Name** parameter to display the `list` alias.</span></span> <span data-ttu-id="7cdcb-127">`list`Псевдоним связан с `Get-ChildItem` командлетом.</span><span class="sxs-lookup"><span data-stu-id="7cdcb-127">The `list` alias is associated with the `Get-ChildItem` cmdlet.</span></span> <span data-ttu-id="7cdcb-128">При `list` запуске псевдонима отображаются элементы в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="7cdcb-128">When the `list` alias is run, the items in the current directory are displayed.</span></span>

<span data-ttu-id="7cdcb-129">`Set-Alias`Командлет использует параметр **Name** для указания `list` псевдонима.</span><span class="sxs-lookup"><span data-stu-id="7cdcb-129">The `Set-Alias` cmdlet uses the **Name** parameter to specify the `list` alias.</span></span> <span data-ttu-id="7cdcb-130">Параметр **value** связывает псевдоним с `Get-Location` командлетом.</span><span class="sxs-lookup"><span data-stu-id="7cdcb-130">The **Value** parameter associates the alias to the `Get-Location` cmdlet.</span></span>

<span data-ttu-id="7cdcb-131">`Get-Alias`Командлет использует параметр **Name** для вывода `list` псевдонима.</span><span class="sxs-lookup"><span data-stu-id="7cdcb-131">The `Get-Alias` cmdlet uses the **Name** parameter to display the `list` alias.</span></span> <span data-ttu-id="7cdcb-132">`list`Псевдоним связан с `Get-Location` командлетом.</span><span class="sxs-lookup"><span data-stu-id="7cdcb-132">The `list` alias is associated with the `Get-Location` cmdlet.</span></span> <span data-ttu-id="7cdcb-133">При `list` запуске псевдонима отображается расположение текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="7cdcb-133">When the `list` alias is run, the current directory's location is displayed.</span></span>

### <span data-ttu-id="7cdcb-134">Пример 3. Создание и изменение псевдонима, доступного только для чтения</span><span class="sxs-lookup"><span data-stu-id="7cdcb-134">Example 3: Create and change a read-only alias</span></span>

<span data-ttu-id="7cdcb-135">Эта команда создает псевдоним только для чтения.</span><span class="sxs-lookup"><span data-stu-id="7cdcb-135">This command creates a read-only alias.</span></span> <span data-ttu-id="7cdcb-136">Параметр только для чтения предотвращает непреднамеренное изменение псевдонима.</span><span class="sxs-lookup"><span data-stu-id="7cdcb-136">The read-only option prevents unintended changes to an alias.</span></span> <span data-ttu-id="7cdcb-137">Чтобы изменить или удалить псевдоним только для чтения, используйте параметр **Force** .</span><span class="sxs-lookup"><span data-stu-id="7cdcb-137">To change or delete a read-only alias, use the **Force** parameter.</span></span>

```
PS> Set-Alias -Name loc -Value Get-Location -Option ReadOnly -PassThru | Format-List -Property *

DisplayName         : loc -> Get-Location
Definition          : Get-Location
Options             : ReadOnly
Description         :
Name                : loc
CommandType         : Alias

PS> Set-Alias -Name loc -Value Get-Location -Option ReadOnly -Description 'Displays the current directory' -Force -PassThru | Format-List -Property *

DisplayName         : loc -> Get-Location
Definition          : Get-Location
Options             : ReadOnly
Description         : Displays the current directory
Name                : loc
CommandType         : Alias
```

<span data-ttu-id="7cdcb-138">`Set-Alias`Командлет создает псевдоним в текущем сеансе PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7cdcb-138">The `Set-Alias` cmdlet creates an alias in the current PowerShell session.</span></span> <span data-ttu-id="7cdcb-139">Параметр **Name** задает имя псевдонима, `loc` .</span><span class="sxs-lookup"><span data-stu-id="7cdcb-139">The **Name** parameter specifies the alias's name, `loc`.</span></span> <span data-ttu-id="7cdcb-140">Параметр **value** указывает `Get-Location` командлет, который выполняется псевдонимом.</span><span class="sxs-lookup"><span data-stu-id="7cdcb-140">The **Value** parameter specifies the `Get-Location` cmdlet that the alias runs.</span></span> <span data-ttu-id="7cdcb-141">Параметр **Option** задает значение **ReadOnly** .</span><span class="sxs-lookup"><span data-stu-id="7cdcb-141">The **Option** parameter specifies the **ReadOnly** value.</span></span> <span data-ttu-id="7cdcb-142">Параметр **PassThru** представляет объект Alias и отправляет объект по конвейеру в `Format-List` командлет.</span><span class="sxs-lookup"><span data-stu-id="7cdcb-142">The **PassThru** parameter represents the alias object and sends the object down the pipeline to the `Format-List` cmdlet.</span></span> <span data-ttu-id="7cdcb-143">`Format-List` использует параметр **Property** со звездочкой ( `*` ), чтобы отображались все свойства.</span><span class="sxs-lookup"><span data-stu-id="7cdcb-143">`Format-List` uses the **Property** parameter with an asterisk (`*`) so that all of the properties are displayed.</span></span> <span data-ttu-id="7cdcb-144">В примере выходных данных показан частичный список этих свойств.</span><span class="sxs-lookup"><span data-stu-id="7cdcb-144">The example output shows a partial list of those properties.</span></span>

<span data-ttu-id="7cdcb-145">`loc`Псевдоним изменяется с добавлением двух параметров.</span><span class="sxs-lookup"><span data-stu-id="7cdcb-145">The `loc` alias is changed with the addition of two parameters.</span></span> <span data-ttu-id="7cdcb-146">**Описание** добавляет текст для объяснения назначения псевдонима.</span><span class="sxs-lookup"><span data-stu-id="7cdcb-146">**Description** adds text to explain the alias's purpose.</span></span> <span data-ttu-id="7cdcb-147">Параметр **Force** необходим, так как `loc` псевдоним доступен только для чтения.</span><span class="sxs-lookup"><span data-stu-id="7cdcb-147">The **Force** parameter is needed because the `loc` alias is read-only.</span></span> <span data-ttu-id="7cdcb-148">Если параметр **Force** не используется, изменение завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="7cdcb-148">If the **Force** parameter is not used, the change fails.</span></span>

### <span data-ttu-id="7cdcb-149">Пример 4. Создание псевдонима для исполняемого файла</span><span class="sxs-lookup"><span data-stu-id="7cdcb-149">Example 4: Create an alias to an executable file</span></span>

<span data-ttu-id="7cdcb-150">В этом примере создается псевдоним для исполняемого файла на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="7cdcb-150">This example creates an alias to an executable file on the local computer.</span></span>

```
PS> Set-Alias -Name np -Value C:\Windows\notepad.exe

PS> Get-Alias -Name np

CommandType     Name
-----------     ----
Alias           np -> notepad.exe
```

<span data-ttu-id="7cdcb-151">`Set-Alias`Командлет создает псевдоним в текущем сеансе PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7cdcb-151">The `Set-Alias` cmdlet creates an alias in the current PowerShell session.</span></span> <span data-ttu-id="7cdcb-152">Параметр **Name** задает имя псевдонима, `np` .</span><span class="sxs-lookup"><span data-stu-id="7cdcb-152">The **Name** parameter specifies the alias's name, `np`.</span></span> <span data-ttu-id="7cdcb-153">Параметр **value** задает путь и имя приложения **C:\Windows\notepad.exe**.</span><span class="sxs-lookup"><span data-stu-id="7cdcb-153">The **Value** parameter specifies the path and application name **C:\Windows\notepad.exe**.</span></span> <span data-ttu-id="7cdcb-154">`Get-Alias`Командлет использует параметр **Name** , чтобы отобразить `np` псевдоним, связанный с **notepad.exe**.</span><span class="sxs-lookup"><span data-stu-id="7cdcb-154">The `Get-Alias` cmdlet uses the **Name** parameter to show that the `np` alias is associated with **notepad.exe**.</span></span>

<span data-ttu-id="7cdcb-155">Чтобы запустить псевдоним, введите `np` команду в командной строке PowerShell, чтобы открыть **notepad.exe**.</span><span class="sxs-lookup"><span data-stu-id="7cdcb-155">To run the alias, type `np` on the PowerShell command line to open **notepad.exe**.</span></span>

### <span data-ttu-id="7cdcb-156">Пример 5. Создание псевдонима для команды с параметрами</span><span class="sxs-lookup"><span data-stu-id="7cdcb-156">Example 5: Create an alias for a command with parameters</span></span>

<span data-ttu-id="7cdcb-157">В этом примере показано, как назначить псевдоним команде с параметрами.</span><span class="sxs-lookup"><span data-stu-id="7cdcb-157">This example shows how to assign an alias to a command with parameters.</span></span>

<span data-ttu-id="7cdcb-158">Можно создать псевдоним для командлета, например `Set-Location` .</span><span class="sxs-lookup"><span data-stu-id="7cdcb-158">You can create an alias for a cmdlet, such as `Set-Location`.</span></span> <span data-ttu-id="7cdcb-159">Нельзя создать псевдоним для команды с параметрами и значениями, такими как `Set-Location -Path C:\Windows\System32` .</span><span class="sxs-lookup"><span data-stu-id="7cdcb-159">You cannot create an alias for a command with parameters and values, such as `Set-Location -Path C:\Windows\System32`.</span></span> <span data-ttu-id="7cdcb-160">Чтобы создать псевдоним для команды, создайте функцию, которая содержит команду, а затем создайте псевдоним для функции.</span><span class="sxs-lookup"><span data-stu-id="7cdcb-160">To create an alias for a command, create a function that includes the command, and then create an alias to the function.</span></span> <span data-ttu-id="7cdcb-161">Дополнительные сведения см. в разделе [about_Functions](../Microsoft.PowerShell.Core/about/about_Functions.md).</span><span class="sxs-lookup"><span data-stu-id="7cdcb-161">For more information, see [about_Functions](../Microsoft.PowerShell.Core/about/about_Functions.md).</span></span>

```
PS> Function CD32 {Set-Location -Path C:\Windows\System32}

PS> Set-Alias -Name Go -Value CD32
```

<span data-ttu-id="7cdcb-162">Создается функция с именем `CD32` .</span><span class="sxs-lookup"><span data-stu-id="7cdcb-162">A function named `CD32` is created.</span></span> <span data-ttu-id="7cdcb-163">Функция использует `Set-Location` командлет с параметром **path** для указания каталога **C:\Windows\System32**.</span><span class="sxs-lookup"><span data-stu-id="7cdcb-163">The function uses the `Set-Location` cmdlet with the **Path** parameter to specify the directory, **C:\Windows\System32**.</span></span>

<span data-ttu-id="7cdcb-164">`Set-Alias`Командлет создает псевдоним для функции в текущем сеансе PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7cdcb-164">The `Set-Alias` cmdlet creates an alias to the function in the current PowerShell session.</span></span> <span data-ttu-id="7cdcb-165">Параметр **Name** задает имя псевдонима, `Go` .</span><span class="sxs-lookup"><span data-stu-id="7cdcb-165">The **Name** parameter specifies the alias's name, `Go`.</span></span> <span data-ttu-id="7cdcb-166">Параметр **value** задает имя функции, `CD32` .</span><span class="sxs-lookup"><span data-stu-id="7cdcb-166">The **Value** parameter specifies the function's name, `CD32`.</span></span>

<span data-ttu-id="7cdcb-167">Чтобы запустить псевдоним, введите `Go` в командной строке PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7cdcb-167">To run the alias, type `Go` on the PowerShell command line.</span></span> <span data-ttu-id="7cdcb-168">`CD32`Функция выполняется и изменяется в каталоге **C:\Windows\System32**.</span><span class="sxs-lookup"><span data-stu-id="7cdcb-168">The `CD32` function runs and changes to the directory **C:\Windows\System32**.</span></span>

## <span data-ttu-id="7cdcb-169">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7cdcb-169">PARAMETERS</span></span>

### <span data-ttu-id="7cdcb-170">-Description</span><span class="sxs-lookup"><span data-stu-id="7cdcb-170">-Description</span></span>

<span data-ttu-id="7cdcb-171">Указывает описание псевдонима.</span><span class="sxs-lookup"><span data-stu-id="7cdcb-171">Specifies a description of the alias.</span></span> <span data-ttu-id="7cdcb-172">Можно ввести любую строку.</span><span class="sxs-lookup"><span data-stu-id="7cdcb-172">You can type any string.</span></span> <span data-ttu-id="7cdcb-173">Если описание содержит пробелы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="7cdcb-173">If the description includes spaces, enclose it single quotation marks.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7cdcb-174">-Force</span><span class="sxs-lookup"><span data-stu-id="7cdcb-174">-Force</span></span>

<span data-ttu-id="7cdcb-175">Используйте параметр **Force** для изменения или удаления псевдонима, у которого параметр **Option** установлен в значение **ReadOnly**.</span><span class="sxs-lookup"><span data-stu-id="7cdcb-175">Use the **Force** parameter to change or delete an alias that has the **Option** parameter set to **ReadOnly**.</span></span>

<span data-ttu-id="7cdcb-176">Параметр **Force** не может изменить или удалить псевдоним **с параметром параметра,** установленным в значение **Constant**.</span><span class="sxs-lookup"><span data-stu-id="7cdcb-176">The **Force** parameter cannot change or delete an alias with the **Option** parameter set to **Constant**.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7cdcb-177">-Name</span><span class="sxs-lookup"><span data-stu-id="7cdcb-177">-Name</span></span>

<span data-ttu-id="7cdcb-178">Задает имя нового псевдонима.</span><span class="sxs-lookup"><span data-stu-id="7cdcb-178">Specifies the name of a new alias.</span></span> <span data-ttu-id="7cdcb-179">Имя псевдонима может содержать буквенно-цифровые символы и дефисы.</span><span class="sxs-lookup"><span data-stu-id="7cdcb-179">An alias name can contain alphanumeric characters and hyphens.</span></span> <span data-ttu-id="7cdcb-180">Имена псевдонимов не могут быть числовыми, например 123.</span><span class="sxs-lookup"><span data-stu-id="7cdcb-180">Alias names cannot be numeric, such as 123.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="7cdcb-181">Параметр-Option</span><span class="sxs-lookup"><span data-stu-id="7cdcb-181">-Option</span></span>

<span data-ttu-id="7cdcb-182">Задает значение свойства **параметра** для псевдонима.</span><span class="sxs-lookup"><span data-stu-id="7cdcb-182">Sets the **Option** property value of the alias.</span></span> <span data-ttu-id="7cdcb-183">Такие значения, как **ReadOnly** и **Constant** , защищают псевдоним от непреднамеренного изменения.</span><span class="sxs-lookup"><span data-stu-id="7cdcb-183">Values such as **ReadOnly** and **Constant** protect an alias from unintended changes.</span></span> <span data-ttu-id="7cdcb-184">Чтобы просмотреть свойство **параметра** всех псевдонимов в сеансе, введите `Get-Alias | Format-Table -Property Name, Options -Autosize` .</span><span class="sxs-lookup"><span data-stu-id="7cdcb-184">To see the **Option** property of all aliases in the session, type `Get-Alias | Format-Table -Property Name, Options -Autosize`.</span></span>

<span data-ttu-id="7cdcb-185">Для этого параметра допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="7cdcb-185">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="7cdcb-186">**AllScope** Псевдоним копируется во все новые создаваемые области.</span><span class="sxs-lookup"><span data-stu-id="7cdcb-186">**AllScope** The alias is copied to any new scopes that are created.</span></span>
- <span data-ttu-id="7cdcb-187">**Константа** Нельзя изменить или удалить.</span><span class="sxs-lookup"><span data-stu-id="7cdcb-187">**Constant** Cannot be changed or deleted.</span></span>
- <span data-ttu-id="7cdcb-188">**Нет** Задает параметры без параметров и является значением по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="7cdcb-188">**None** Sets no options and is the default.</span></span>
- <span data-ttu-id="7cdcb-189">**Частный** Псевдоним доступен только в текущей области.</span><span class="sxs-lookup"><span data-stu-id="7cdcb-189">**Private** The alias is available only in the current scope.</span></span>
- <span data-ttu-id="7cdcb-190">**Только для чтения** Нельзя изменить или удалить, если не используется параметр **Force** .</span><span class="sxs-lookup"><span data-stu-id="7cdcb-190">**ReadOnly** Cannot be changed or deleted unless the **Force** parameter is used.</span></span>
- <span data-ttu-id="7cdcb-191">**Unspecified**</span><span class="sxs-lookup"><span data-stu-id="7cdcb-191">**Unspecified**</span></span>

```yaml
Type: System.Management.Automation.ScopedItemOptions
Parameter Sets: (All)
Aliases:
Accepted values: AllScope, Constant, None, Private, ReadOnly, Unspecified

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7cdcb-192">-PassThru</span><span class="sxs-lookup"><span data-stu-id="7cdcb-192">-PassThru</span></span>

<span data-ttu-id="7cdcb-193">Возвращает объект, представляющий псевдоним.</span><span class="sxs-lookup"><span data-stu-id="7cdcb-193">Returns an object that represents the alias.</span></span> <span data-ttu-id="7cdcb-194">Используйте командлет Format, например, `Format-List` для вывода объекта.</span><span class="sxs-lookup"><span data-stu-id="7cdcb-194">Use a format cmdlet such as `Format-List` to display the object.</span></span> <span data-ttu-id="7cdcb-195">По умолчанию не `Set-Alias` создает никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="7cdcb-195">By default, `Set-Alias` does not generate any output.</span></span>

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

### <span data-ttu-id="7cdcb-196">-Scope</span><span class="sxs-lookup"><span data-stu-id="7cdcb-196">-Scope</span></span>

<span data-ttu-id="7cdcb-197">Задает область действия псевдонима.</span><span class="sxs-lookup"><span data-stu-id="7cdcb-197">Specifies the scope in which this alias is valid.</span></span> <span data-ttu-id="7cdcb-198">Значение по умолчанию — **Local**.</span><span class="sxs-lookup"><span data-stu-id="7cdcb-198">The default value is **Local**.</span></span> <span data-ttu-id="7cdcb-199">Дополнительные сведения см. в разделе [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span><span class="sxs-lookup"><span data-stu-id="7cdcb-199">For more information, see [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span></span>

<span data-ttu-id="7cdcb-200">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="7cdcb-200">The acceptable values are as follows:</span></span>

- <span data-ttu-id="7cdcb-201">Глобальный</span><span class="sxs-lookup"><span data-stu-id="7cdcb-201">Global</span></span>
- <span data-ttu-id="7cdcb-202">Локальная</span><span class="sxs-lookup"><span data-stu-id="7cdcb-202">Local</span></span>
- <span data-ttu-id="7cdcb-203">Private</span><span class="sxs-lookup"><span data-stu-id="7cdcb-203">Private</span></span>
- <span data-ttu-id="7cdcb-204">Пронумерованные области</span><span class="sxs-lookup"><span data-stu-id="7cdcb-204">Numbered scopes</span></span>
- <span data-ttu-id="7cdcb-205">Сценарий</span><span class="sxs-lookup"><span data-stu-id="7cdcb-205">Script</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Global, Local, Private, Numbered scopes, Script

Required: False
Position: Named
Default value: Local
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7cdcb-206">-Value</span><span class="sxs-lookup"><span data-stu-id="7cdcb-206">-Value</span></span>

<span data-ttu-id="7cdcb-207">Указывает имя командлета или команды, которую выполняет псевдоним.</span><span class="sxs-lookup"><span data-stu-id="7cdcb-207">Specifies the name of the cmdlet or command that the alias runs.</span></span> <span data-ttu-id="7cdcb-208">Параметр **value** является свойством **определения** псевдонима.</span><span class="sxs-lookup"><span data-stu-id="7cdcb-208">The **Value** parameter is the alias's **Definition** property.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="7cdcb-209">-Confirm</span><span class="sxs-lookup"><span data-stu-id="7cdcb-209">-Confirm</span></span>

<span data-ttu-id="7cdcb-210">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="7cdcb-210">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="7cdcb-211">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="7cdcb-211">-WhatIf</span></span>

<span data-ttu-id="7cdcb-212">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="7cdcb-212">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="7cdcb-213">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="7cdcb-213">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="7cdcb-214">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="7cdcb-214">CommonParameters</span></span>

<span data-ttu-id="7cdcb-215">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="7cdcb-215">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="7cdcb-216">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="7cdcb-216">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="7cdcb-217">Входные данные</span><span class="sxs-lookup"><span data-stu-id="7cdcb-217">INPUTS</span></span>

### <span data-ttu-id="7cdcb-218">Нет</span><span class="sxs-lookup"><span data-stu-id="7cdcb-218">None</span></span>

<span data-ttu-id="7cdcb-219">`Set-Alias` не принимает входные данные из конвейера.</span><span class="sxs-lookup"><span data-stu-id="7cdcb-219">`Set-Alias` does not accept input from the pipeline.</span></span>

## <span data-ttu-id="7cdcb-220">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="7cdcb-220">OUTPUTS</span></span>

### <span data-ttu-id="7cdcb-221">None или System. Management. Automation. AliasInfo</span><span class="sxs-lookup"><span data-stu-id="7cdcb-221">None or System.Management.Automation.AliasInfo</span></span>

<span data-ttu-id="7cdcb-222">При использовании параметра **PassThru** `Set-Alias` создает объект **System. Management. Automation. AliasInfo** , представляющий псевдоним.</span><span class="sxs-lookup"><span data-stu-id="7cdcb-222">When you use the **PassThru** parameter, `Set-Alias` generates a **System.Management.Automation.AliasInfo** object representing the alias.</span></span> <span data-ttu-id="7cdcb-223">В противном случае не `Set-Alias` создает никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="7cdcb-223">Otherwise, `Set-Alias` does not generate any output.</span></span>

## <span data-ttu-id="7cdcb-224">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="7cdcb-224">NOTES</span></span>

<span data-ttu-id="7cdcb-225">PowerShell включает встроенные псевдонимы, доступные в каждом сеансе PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7cdcb-225">PowerShell includes built-in aliases that are available in each PowerShell session.</span></span> <span data-ttu-id="7cdcb-226">`Get-Alias`Командлет отображает псевдонимы, доступные в сеансе PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7cdcb-226">The `Get-Alias` cmdlet displays the aliases available in a PowerShell session.</span></span>

<span data-ttu-id="7cdcb-227">Чтобы создать псевдоним, используйте командлеты `Set-Alias` или `New-Alias` .</span><span class="sxs-lookup"><span data-stu-id="7cdcb-227">To create an alias, use the cmdlets `Set-Alias` or `New-Alias`.</span></span> <span data-ttu-id="7cdcb-228">Чтобы удалить псевдоним в PowerShell 6, используйте `Remove-Alias` командлет.</span><span class="sxs-lookup"><span data-stu-id="7cdcb-228">In PowerShell 6, to delete an alias, use the `Remove-Alias` cmdlet.</span></span> <span data-ttu-id="7cdcb-229">`Remove-Item` принимается для обеспечения обратной совместимости, например для скриптов, созданных с помощью предыдущих версий PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7cdcb-229">`Remove-Item` is accepted for backwards compatibility such as for scripts created with prior versions of PowerShell.</span></span> <span data-ttu-id="7cdcb-230">Используйте команду, например `Remove-Item -Path Alias:aliasname` .</span><span class="sxs-lookup"><span data-stu-id="7cdcb-230">Use a command such as `Remove-Item -Path Alias:aliasname`.</span></span>

<span data-ttu-id="7cdcb-231">Чтобы создать псевдоним, доступный в каждом сеансе PowerShell, добавьте его в профиль PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7cdcb-231">To create an alias that is available in each PowerShell session, add it to your PowerShell profile.</span></span>
<span data-ttu-id="7cdcb-232">Дополнительные сведения см. в разделе [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="7cdcb-232">For more information, see [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span></span>

<span data-ttu-id="7cdcb-233">Псевдоним можно сохранить и повторно использовать в другом сеансе PowerShell, выполнив экспорт и импорт.</span><span class="sxs-lookup"><span data-stu-id="7cdcb-233">An alias can be saved and reused in another PowerShell session by doing an export and import.</span></span> <span data-ttu-id="7cdcb-234">Чтобы сохранить псевдоним в файл, используйте `Export-Alias` .</span><span class="sxs-lookup"><span data-stu-id="7cdcb-234">To save an alias to a file, use `Export-Alias`.</span></span> <span data-ttu-id="7cdcb-235">Чтобы добавить сохраненный псевдоним в новый сеанс PowerShell, используйте `Import-Alias` .</span><span class="sxs-lookup"><span data-stu-id="7cdcb-235">To add a saved alias to a new PowerShell session, use `Import-Alias`.</span></span>

## <span data-ttu-id="7cdcb-236">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="7cdcb-236">RELATED LINKS</span></span>

[<span data-ttu-id="7cdcb-237">about_Aliases</span><span class="sxs-lookup"><span data-stu-id="7cdcb-237">about_Aliases</span></span>](../Microsoft.PowerShell.Core/About/about_Aliases.md)

[<span data-ttu-id="7cdcb-238">about_Functions</span><span class="sxs-lookup"><span data-stu-id="7cdcb-238">about_Functions</span></span>](../Microsoft.PowerShell.Core/about/about_Functions.md)

[<span data-ttu-id="7cdcb-239">about_Profiles</span><span class="sxs-lookup"><span data-stu-id="7cdcb-239">about_Profiles</span></span>](../Microsoft.PowerShell.Core/About/about_Profiles.md)

[<span data-ttu-id="7cdcb-240">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="7cdcb-240">about_Scopes</span></span>](../Microsoft.PowerShell.Core/About/about_Scopes.md)

[<span data-ttu-id="7cdcb-241">Export-Alias</span><span class="sxs-lookup"><span data-stu-id="7cdcb-241">Export-Alias</span></span>](Export-Alias.md)

[<span data-ttu-id="7cdcb-242">Get-Alias</span><span class="sxs-lookup"><span data-stu-id="7cdcb-242">Get-Alias</span></span>](Get-Alias.md)

[<span data-ttu-id="7cdcb-243">Import-Alias</span><span class="sxs-lookup"><span data-stu-id="7cdcb-243">Import-Alias</span></span>](Import-Alias.md)

[<span data-ttu-id="7cdcb-244">New-Alias</span><span class="sxs-lookup"><span data-stu-id="7cdcb-244">New-Alias</span></span>](New-Alias.md)

[<span data-ttu-id="7cdcb-245">Remove-Alias</span><span class="sxs-lookup"><span data-stu-id="7cdcb-245">Remove-Alias</span></span>](Remove-Alias.md)

[<span data-ttu-id="7cdcb-246">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="7cdcb-246">Remove-Item</span></span>](../Microsoft.PowerShell.Management/Remove-Item.md)

