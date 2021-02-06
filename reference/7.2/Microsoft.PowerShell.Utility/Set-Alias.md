---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 02/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/set-alias?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Alias
ms.openlocfilehash: e9e80b4bf558dcf1e225868a1138979270ea304f
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602271"
---
# <span data-ttu-id="07398-102">Set-Alias</span><span class="sxs-lookup"><span data-stu-id="07398-102">Set-Alias</span></span>

## <span data-ttu-id="07398-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="07398-103">SYNOPSIS</span></span>
<span data-ttu-id="07398-104">Создает или изменяет псевдоним для командлета или другой команды в текущем сеансе PowerShell.</span><span class="sxs-lookup"><span data-stu-id="07398-104">Creates or changes an alias for a cmdlet or other command in the current PowerShell session.</span></span>

## <span data-ttu-id="07398-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="07398-105">SYNTAX</span></span>

### <span data-ttu-id="07398-106">Default (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="07398-106">Default (Default)</span></span>

```
Set-Alias [-Name] <string> [-Value] <string> [-Description <string>] [-Option <ScopedItemOptions>]
 [-PassThru] [-Scope <string>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="07398-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="07398-107">DESCRIPTION</span></span>

<span data-ttu-id="07398-108">`Set-Alias`Командлет создает или изменяет псевдоним для командлета или команды, например функции, скрипта, файла или другого исполняемого файла.</span><span class="sxs-lookup"><span data-stu-id="07398-108">The `Set-Alias` cmdlet creates or changes an alias for a cmdlet or a command, such as a function, script, file, or other executable.</span></span> <span data-ttu-id="07398-109">Псевдоним — это альтернативное имя, которое ссылается на командлет или команду.</span><span class="sxs-lookup"><span data-stu-id="07398-109">An alias is an alternate name that refers to a cmdlet or command.</span></span>
<span data-ttu-id="07398-110">Например, `sal` является псевдонимом для `Set-Alias` командлета.</span><span class="sxs-lookup"><span data-stu-id="07398-110">For example, `sal` is the alias for the `Set-Alias` cmdlet.</span></span> <span data-ttu-id="07398-111">Дополнительные сведения см. в разделе [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="07398-111">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>

<span data-ttu-id="07398-112">Командлет может иметь несколько псевдонимов, но псевдоним может быть связан только с одним командлетом.</span><span class="sxs-lookup"><span data-stu-id="07398-112">A cmdlet can have multiple aliases, but an alias can only be associated with one cmdlet.</span></span> <span data-ttu-id="07398-113">Можно использовать для повторного `Set-Alias` назначения существующего псевдонима другому командлету или для изменения свойств псевдонима, таких как описание.</span><span class="sxs-lookup"><span data-stu-id="07398-113">You can use `Set-Alias` to reassign an existing alias to another cmdlet, or change an alias's properties, such as the description.</span></span>

<span data-ttu-id="07398-114">Псевдоним, созданный или измененный, `Set-Alias` не является постоянным и доступен только во время текущего сеанса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="07398-114">An alias that is created or changed by `Set-Alias` is not permanent and is only available during the current PowerShell session.</span></span> <span data-ttu-id="07398-115">При закрытии сеанса PowerShell псевдоним удаляется.</span><span class="sxs-lookup"><span data-stu-id="07398-115">When the PowerShell session is closed, the alias is removed.</span></span>

## <span data-ttu-id="07398-116">Примеры</span><span class="sxs-lookup"><span data-stu-id="07398-116">EXAMPLES</span></span>

### <span data-ttu-id="07398-117">Пример 1. Создание псевдонима для командлета</span><span class="sxs-lookup"><span data-stu-id="07398-117">Example 1: Create an alias for a cmdlet</span></span>

<span data-ttu-id="07398-118">Эта команда создает псевдоним для командлета в текущем сеансе PowerShell.</span><span class="sxs-lookup"><span data-stu-id="07398-118">This command creates an alias to a cmdlet in the current PowerShell session.</span></span>

```
PS> Set-Alias -Name list -Value Get-ChildItem

PS> Get-Alias -Name list

CommandType     Name
-----------     ----
Alias           list -> Get-ChildItem
```

<span data-ttu-id="07398-119">`Set-Alias`Командлет создает псевдоним в текущем сеансе PowerShell.</span><span class="sxs-lookup"><span data-stu-id="07398-119">The `Set-Alias` cmdlet creates an alias in the current PowerShell session.</span></span> <span data-ttu-id="07398-120">Параметр **Name** задает имя псевдонима, `list` .</span><span class="sxs-lookup"><span data-stu-id="07398-120">The **Name** parameter specifies the alias's name, `list`.</span></span> <span data-ttu-id="07398-121">Параметр **value** указывает командлет, который выполняется псевдонимом.</span><span class="sxs-lookup"><span data-stu-id="07398-121">The **Value** parameter specifies the cmdlet that the alias runs.</span></span>

<span data-ttu-id="07398-122">Чтобы запустить псевдоним, введите `list` в командной строке PowerShell.</span><span class="sxs-lookup"><span data-stu-id="07398-122">To run the alias, type `list` on the PowerShell command line.</span></span>

### <span data-ttu-id="07398-123">Пример 2. повторное назначение существующего псевдонима другому командлету</span><span class="sxs-lookup"><span data-stu-id="07398-123">Example 2: Reassign an existing alias to a different cmdlet</span></span>

<span data-ttu-id="07398-124">Эта команда переназначает существующий псевдоним для выполнения другого командлета.</span><span class="sxs-lookup"><span data-stu-id="07398-124">This command reassigns an existing alias to run a different cmdlet.</span></span>

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

<span data-ttu-id="07398-125">`Get-Alias`Командлет использует параметр **Name** для вывода `list` псевдонима.</span><span class="sxs-lookup"><span data-stu-id="07398-125">The `Get-Alias` cmdlet uses the **Name** parameter to display the `list` alias.</span></span> <span data-ttu-id="07398-126">`list`Псевдоним связан с `Get-ChildItem` командлетом.</span><span class="sxs-lookup"><span data-stu-id="07398-126">The `list` alias is associated with the `Get-ChildItem` cmdlet.</span></span> <span data-ttu-id="07398-127">При `list` запуске псевдонима отображаются элементы в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="07398-127">When the `list` alias is run, the items in the current directory are displayed.</span></span>

<span data-ttu-id="07398-128">`Set-Alias`Командлет использует параметр **Name** для указания `list` псевдонима.</span><span class="sxs-lookup"><span data-stu-id="07398-128">The `Set-Alias` cmdlet uses the **Name** parameter to specify the `list` alias.</span></span> <span data-ttu-id="07398-129">Параметр **value** связывает псевдоним с `Get-Location` командлетом.</span><span class="sxs-lookup"><span data-stu-id="07398-129">The **Value** parameter associates the alias to the `Get-Location` cmdlet.</span></span>

<span data-ttu-id="07398-130">`Get-Alias`Командлет использует параметр **Name** для вывода `list` псевдонима.</span><span class="sxs-lookup"><span data-stu-id="07398-130">The `Get-Alias` cmdlet uses the **Name** parameter to display the `list` alias.</span></span> <span data-ttu-id="07398-131">`list`Псевдоним связан с `Get-Location` командлетом.</span><span class="sxs-lookup"><span data-stu-id="07398-131">The `list` alias is associated with the `Get-Location` cmdlet.</span></span> <span data-ttu-id="07398-132">При `list` запуске псевдонима отображается расположение текущего каталога.</span><span class="sxs-lookup"><span data-stu-id="07398-132">When the `list` alias is run, the current directory's location is displayed.</span></span>

### <span data-ttu-id="07398-133">Пример 3. Создание и изменение псевдонима, доступного только для чтения</span><span class="sxs-lookup"><span data-stu-id="07398-133">Example 3: Create and change a read-only alias</span></span>

<span data-ttu-id="07398-134">Эта команда создает псевдоним только для чтения.</span><span class="sxs-lookup"><span data-stu-id="07398-134">This command creates a read-only alias.</span></span> <span data-ttu-id="07398-135">Параметр только для чтения предотвращает непреднамеренное изменение псевдонима.</span><span class="sxs-lookup"><span data-stu-id="07398-135">The read-only option prevents unintended changes to an alias.</span></span> <span data-ttu-id="07398-136">Чтобы изменить или удалить псевдоним только для чтения, используйте параметр **Force** .</span><span class="sxs-lookup"><span data-stu-id="07398-136">To change or delete a read-only alias, use the **Force** parameter.</span></span>

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

<span data-ttu-id="07398-137">`Set-Alias`Командлет создает псевдоним в текущем сеансе PowerShell.</span><span class="sxs-lookup"><span data-stu-id="07398-137">The `Set-Alias` cmdlet creates an alias in the current PowerShell session.</span></span> <span data-ttu-id="07398-138">Параметр **Name** задает имя псевдонима, `loc` .</span><span class="sxs-lookup"><span data-stu-id="07398-138">The **Name** parameter specifies the alias's name, `loc`.</span></span> <span data-ttu-id="07398-139">Параметр **value** указывает `Get-Location` командлет, который выполняется псевдонимом.</span><span class="sxs-lookup"><span data-stu-id="07398-139">The **Value** parameter specifies the `Get-Location` cmdlet that the alias runs.</span></span> <span data-ttu-id="07398-140">Параметр **Option** задает значение **ReadOnly** .</span><span class="sxs-lookup"><span data-stu-id="07398-140">The **Option** parameter specifies the **ReadOnly** value.</span></span> <span data-ttu-id="07398-141">Параметр **PassThru** представляет объект Alias и отправляет объект по конвейеру в `Format-List` командлет.</span><span class="sxs-lookup"><span data-stu-id="07398-141">The **PassThru** parameter represents the alias object and sends the object down the pipeline to the `Format-List` cmdlet.</span></span> <span data-ttu-id="07398-142">`Format-List` использует параметр **Property** со звездочкой ( `*` ), чтобы отображались все свойства.</span><span class="sxs-lookup"><span data-stu-id="07398-142">`Format-List` uses the **Property** parameter with an asterisk (`*`) so that all of the properties are displayed.</span></span> <span data-ttu-id="07398-143">В примере выходных данных показан частичный список этих свойств.</span><span class="sxs-lookup"><span data-stu-id="07398-143">The example output shows a partial list of those properties.</span></span>

<span data-ttu-id="07398-144">`loc`Псевдоним изменяется с добавлением двух параметров.</span><span class="sxs-lookup"><span data-stu-id="07398-144">The `loc` alias is changed with the addition of two parameters.</span></span> <span data-ttu-id="07398-145">**Описание** добавляет текст для объяснения назначения псевдонима.</span><span class="sxs-lookup"><span data-stu-id="07398-145">**Description** adds text to explain the alias's purpose.</span></span> <span data-ttu-id="07398-146">Параметр **Force** необходим, так как `loc` псевдоним доступен только для чтения.</span><span class="sxs-lookup"><span data-stu-id="07398-146">The **Force** parameter is needed because the `loc` alias is read-only.</span></span> <span data-ttu-id="07398-147">Если параметр **Force** не используется, изменение завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="07398-147">If the **Force** parameter is not used, the change fails.</span></span>

### <span data-ttu-id="07398-148">Пример 4. Создание псевдонима для исполняемого файла</span><span class="sxs-lookup"><span data-stu-id="07398-148">Example 4: Create an alias to an executable file</span></span>

<span data-ttu-id="07398-149">В этом примере создается псевдоним для исполняемого файла на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="07398-149">This example creates an alias to an executable file on the local computer.</span></span>

```
PS> Set-Alias -Name np -Value C:\Windows\notepad.exe

PS> Get-Alias -Name np

CommandType     Name
-----------     ----
Alias           np -> notepad.exe
```

<span data-ttu-id="07398-150">`Set-Alias`Командлет создает псевдоним в текущем сеансе PowerShell.</span><span class="sxs-lookup"><span data-stu-id="07398-150">The `Set-Alias` cmdlet creates an alias in the current PowerShell session.</span></span> <span data-ttu-id="07398-151">Параметр **Name** задает имя псевдонима, `np` .</span><span class="sxs-lookup"><span data-stu-id="07398-151">The **Name** parameter specifies the alias's name, `np`.</span></span> <span data-ttu-id="07398-152">Параметр **value** задает путь и имя приложения **C:\Windows\notepad.exe**.</span><span class="sxs-lookup"><span data-stu-id="07398-152">The **Value** parameter specifies the path and application name **C:\Windows\notepad.exe**.</span></span> <span data-ttu-id="07398-153">`Get-Alias`Командлет использует параметр **Name** , чтобы отобразить `np` псевдоним, связанный с **notepad.exe**.</span><span class="sxs-lookup"><span data-stu-id="07398-153">The `Get-Alias` cmdlet uses the **Name** parameter to show that the `np` alias is associated with **notepad.exe**.</span></span>

<span data-ttu-id="07398-154">Чтобы запустить псевдоним, введите `np` команду в командной строке PowerShell, чтобы открыть **notepad.exe**.</span><span class="sxs-lookup"><span data-stu-id="07398-154">To run the alias, type `np` on the PowerShell command line to open **notepad.exe**.</span></span>

### <span data-ttu-id="07398-155">Пример 5. Создание псевдонима для команды с параметрами</span><span class="sxs-lookup"><span data-stu-id="07398-155">Example 5: Create an alias for a command with parameters</span></span>

<span data-ttu-id="07398-156">В этом примере показано, как назначить псевдоним команде с параметрами.</span><span class="sxs-lookup"><span data-stu-id="07398-156">This example shows how to assign an alias to a command with parameters.</span></span>

<span data-ttu-id="07398-157">Можно создать псевдоним для командлета, например `Set-Location` .</span><span class="sxs-lookup"><span data-stu-id="07398-157">You can create an alias for a cmdlet, such as `Set-Location`.</span></span> <span data-ttu-id="07398-158">Нельзя создать псевдоним для команды с параметрами и значениями, такими как `Set-Location -Path C:\Windows\System32` .</span><span class="sxs-lookup"><span data-stu-id="07398-158">You cannot create an alias for a command with parameters and values, such as `Set-Location -Path C:\Windows\System32`.</span></span> <span data-ttu-id="07398-159">Чтобы создать псевдоним для команды, создайте функцию, которая содержит команду, а затем создайте псевдоним для функции.</span><span class="sxs-lookup"><span data-stu-id="07398-159">To create an alias for a command, create a function that includes the command, and then create an alias to the function.</span></span> <span data-ttu-id="07398-160">Дополнительные сведения см. в разделе [about_Functions](../Microsoft.PowerShell.Core/about/about_Functions.md).</span><span class="sxs-lookup"><span data-stu-id="07398-160">For more information, see [about_Functions](../Microsoft.PowerShell.Core/about/about_Functions.md).</span></span>

```
PS> Function CD32 {Set-Location -Path C:\Windows\System32}

PS> Set-Alias -Name Go -Value CD32
```

<span data-ttu-id="07398-161">Создается функция с именем `CD32` .</span><span class="sxs-lookup"><span data-stu-id="07398-161">A function named `CD32` is created.</span></span> <span data-ttu-id="07398-162">Функция использует `Set-Location` командлет с параметром **path** для указания каталога **C:\Windows\System32**.</span><span class="sxs-lookup"><span data-stu-id="07398-162">The function uses the `Set-Location` cmdlet with the **Path** parameter to specify the directory, **C:\Windows\System32**.</span></span>

<span data-ttu-id="07398-163">`Set-Alias`Командлет создает псевдоним для функции в текущем сеансе PowerShell.</span><span class="sxs-lookup"><span data-stu-id="07398-163">The `Set-Alias` cmdlet creates an alias to the function in the current PowerShell session.</span></span> <span data-ttu-id="07398-164">Параметр **Name** задает имя псевдонима, `Go` .</span><span class="sxs-lookup"><span data-stu-id="07398-164">The **Name** parameter specifies the alias's name, `Go`.</span></span> <span data-ttu-id="07398-165">Параметр **value** задает имя функции, `CD32` .</span><span class="sxs-lookup"><span data-stu-id="07398-165">The **Value** parameter specifies the function's name, `CD32`.</span></span>

<span data-ttu-id="07398-166">Чтобы запустить псевдоним, введите `Go` в командной строке PowerShell.</span><span class="sxs-lookup"><span data-stu-id="07398-166">To run the alias, type `Go` on the PowerShell command line.</span></span> <span data-ttu-id="07398-167">`CD32`Функция выполняется и изменяется в каталоге **C:\Windows\System32**.</span><span class="sxs-lookup"><span data-stu-id="07398-167">The `CD32` function runs and changes to the directory **C:\Windows\System32**.</span></span>

## <span data-ttu-id="07398-168">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="07398-168">PARAMETERS</span></span>

### <span data-ttu-id="07398-169">-Description</span><span class="sxs-lookup"><span data-stu-id="07398-169">-Description</span></span>

<span data-ttu-id="07398-170">Указывает описание псевдонима.</span><span class="sxs-lookup"><span data-stu-id="07398-170">Specifies a description of the alias.</span></span> <span data-ttu-id="07398-171">Можно ввести любую строку.</span><span class="sxs-lookup"><span data-stu-id="07398-171">You can type any string.</span></span> <span data-ttu-id="07398-172">Если описание содержит пробелы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="07398-172">If the description includes spaces, enclose it single quotation marks.</span></span>

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

### <span data-ttu-id="07398-173">-Force</span><span class="sxs-lookup"><span data-stu-id="07398-173">-Force</span></span>

<span data-ttu-id="07398-174">Используйте параметр **Force** для изменения или удаления псевдонима, у которого параметр **Option** установлен в значение **ReadOnly**.</span><span class="sxs-lookup"><span data-stu-id="07398-174">Use the **Force** parameter to change or delete an alias that has the **Option** parameter set to **ReadOnly**.</span></span>

<span data-ttu-id="07398-175">Параметр **Force** не может изменить или удалить псевдоним **с параметром параметра,** установленным в значение **Constant**.</span><span class="sxs-lookup"><span data-stu-id="07398-175">The **Force** parameter cannot change or delete an alias with the **Option** parameter set to **Constant**.</span></span>

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

### <span data-ttu-id="07398-176">-Name</span><span class="sxs-lookup"><span data-stu-id="07398-176">-Name</span></span>

<span data-ttu-id="07398-177">Задает имя нового псевдонима.</span><span class="sxs-lookup"><span data-stu-id="07398-177">Specifies the name of a new alias.</span></span> <span data-ttu-id="07398-178">Имя псевдонима может содержать буквенно-цифровые символы и дефисы.</span><span class="sxs-lookup"><span data-stu-id="07398-178">An alias name can contain alphanumeric characters and hyphens.</span></span> <span data-ttu-id="07398-179">Имена псевдонимов не могут быть числовыми, например 123.</span><span class="sxs-lookup"><span data-stu-id="07398-179">Alias names cannot be numeric, such as 123.</span></span>

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

### <span data-ttu-id="07398-180">Параметр-Option</span><span class="sxs-lookup"><span data-stu-id="07398-180">-Option</span></span>

<span data-ttu-id="07398-181">Задает значение свойства **параметра** для псевдонима.</span><span class="sxs-lookup"><span data-stu-id="07398-181">Sets the **Option** property value of the alias.</span></span> <span data-ttu-id="07398-182">Такие значения, как **ReadOnly** и **Constant** , защищают псевдоним от непреднамеренного изменения.</span><span class="sxs-lookup"><span data-stu-id="07398-182">Values such as **ReadOnly** and **Constant** protect an alias from unintended changes.</span></span> <span data-ttu-id="07398-183">Чтобы просмотреть свойство **параметра** всех псевдонимов в сеансе, введите `Get-Alias | Format-Table -Property Name, Options -Autosize` .</span><span class="sxs-lookup"><span data-stu-id="07398-183">To see the **Option** property of all aliases in the session, type `Get-Alias | Format-Table -Property Name, Options -Autosize`.</span></span>

<span data-ttu-id="07398-184">Для этого параметра допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="07398-184">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="07398-185">**AllScope** Псевдоним копируется во все новые создаваемые области.</span><span class="sxs-lookup"><span data-stu-id="07398-185">**AllScope** The alias is copied to any new scopes that are created.</span></span>
- <span data-ttu-id="07398-186">**Константа** Нельзя изменить или удалить.</span><span class="sxs-lookup"><span data-stu-id="07398-186">**Constant** Cannot be changed or deleted.</span></span>
- <span data-ttu-id="07398-187">**Нет** Задает параметры без параметров и является значением по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="07398-187">**None** Sets no options and is the default.</span></span>
- <span data-ttu-id="07398-188">**Частный** Псевдоним доступен только в текущей области.</span><span class="sxs-lookup"><span data-stu-id="07398-188">**Private** The alias is available only in the current scope.</span></span>
- <span data-ttu-id="07398-189">**Только для чтения** Нельзя изменить или удалить, если не используется параметр **Force** .</span><span class="sxs-lookup"><span data-stu-id="07398-189">**ReadOnly** Cannot be changed or deleted unless the **Force** parameter is used.</span></span>
- <span data-ttu-id="07398-190">**Unspecified**</span><span class="sxs-lookup"><span data-stu-id="07398-190">**Unspecified**</span></span>

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

### <span data-ttu-id="07398-191">-PassThru</span><span class="sxs-lookup"><span data-stu-id="07398-191">-PassThru</span></span>

<span data-ttu-id="07398-192">Возвращает объект, представляющий псевдоним.</span><span class="sxs-lookup"><span data-stu-id="07398-192">Returns an object that represents the alias.</span></span> <span data-ttu-id="07398-193">Используйте командлет Format, например, `Format-List` для вывода объекта.</span><span class="sxs-lookup"><span data-stu-id="07398-193">Use a format cmdlet such as `Format-List` to display the object.</span></span> <span data-ttu-id="07398-194">По умолчанию не `Set-Alias` создает никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="07398-194">By default, `Set-Alias` does not generate any output.</span></span>

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

### <span data-ttu-id="07398-195">-Scope</span><span class="sxs-lookup"><span data-stu-id="07398-195">-Scope</span></span>

<span data-ttu-id="07398-196">Задает область действия псевдонима.</span><span class="sxs-lookup"><span data-stu-id="07398-196">Specifies the scope in which this alias is valid.</span></span> <span data-ttu-id="07398-197">Значение по умолчанию — **Local**.</span><span class="sxs-lookup"><span data-stu-id="07398-197">The default value is **Local**.</span></span> <span data-ttu-id="07398-198">Дополнительные сведения см. в разделе [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span><span class="sxs-lookup"><span data-stu-id="07398-198">For more information, see [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span></span>

<span data-ttu-id="07398-199">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="07398-199">The acceptable values are as follows:</span></span>

- <span data-ttu-id="07398-200">Глобальный</span><span class="sxs-lookup"><span data-stu-id="07398-200">Global</span></span>
- <span data-ttu-id="07398-201">Локальная</span><span class="sxs-lookup"><span data-stu-id="07398-201">Local</span></span>
- <span data-ttu-id="07398-202">Частные</span><span class="sxs-lookup"><span data-stu-id="07398-202">Private</span></span>
- <span data-ttu-id="07398-203">Пронумерованные области</span><span class="sxs-lookup"><span data-stu-id="07398-203">Numbered scopes</span></span>
- <span data-ttu-id="07398-204">Скрипт</span><span class="sxs-lookup"><span data-stu-id="07398-204">Script</span></span>

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

### <span data-ttu-id="07398-205">-Value</span><span class="sxs-lookup"><span data-stu-id="07398-205">-Value</span></span>

<span data-ttu-id="07398-206">Указывает имя командлета или команды, которую выполняет псевдоним.</span><span class="sxs-lookup"><span data-stu-id="07398-206">Specifies the name of the cmdlet or command that the alias runs.</span></span> <span data-ttu-id="07398-207">Параметр **value** является свойством **определения** псевдонима.</span><span class="sxs-lookup"><span data-stu-id="07398-207">The **Value** parameter is the alias's **Definition** property.</span></span>

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

### <span data-ttu-id="07398-208">-Confirm</span><span class="sxs-lookup"><span data-stu-id="07398-208">-Confirm</span></span>

<span data-ttu-id="07398-209">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="07398-209">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="07398-210">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="07398-210">-WhatIf</span></span>

<span data-ttu-id="07398-211">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="07398-211">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="07398-212">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="07398-212">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="07398-213">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="07398-213">CommonParameters</span></span>

<span data-ttu-id="07398-214">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="07398-214">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="07398-215">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="07398-215">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="07398-216">Входные данные</span><span class="sxs-lookup"><span data-stu-id="07398-216">INPUTS</span></span>

### <span data-ttu-id="07398-217">None</span><span class="sxs-lookup"><span data-stu-id="07398-217">None</span></span>

<span data-ttu-id="07398-218">`Set-Alias` не принимает входные данные из конвейера.</span><span class="sxs-lookup"><span data-stu-id="07398-218">`Set-Alias` does not accept input from the pipeline.</span></span>

## <span data-ttu-id="07398-219">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="07398-219">OUTPUTS</span></span>

### <span data-ttu-id="07398-220">None или System. Management. Automation. AliasInfo</span><span class="sxs-lookup"><span data-stu-id="07398-220">None or System.Management.Automation.AliasInfo</span></span>

<span data-ttu-id="07398-221">При использовании параметра **PassThru** `Set-Alias` создает объект **System. Management. Automation. AliasInfo** , представляющий псевдоним.</span><span class="sxs-lookup"><span data-stu-id="07398-221">When you use the **PassThru** parameter, `Set-Alias` generates a **System.Management.Automation.AliasInfo** object representing the alias.</span></span> <span data-ttu-id="07398-222">В противном случае не `Set-Alias` создает никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="07398-222">Otherwise, `Set-Alias` does not generate any output.</span></span>

## <span data-ttu-id="07398-223">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="07398-223">NOTES</span></span>

<span data-ttu-id="07398-224">PowerShell включает встроенные псевдонимы, доступные в каждом сеансе PowerShell.</span><span class="sxs-lookup"><span data-stu-id="07398-224">PowerShell includes built-in aliases that are available in each PowerShell session.</span></span> <span data-ttu-id="07398-225">`Get-Alias`Командлет отображает псевдонимы, доступные в сеансе PowerShell.</span><span class="sxs-lookup"><span data-stu-id="07398-225">The `Get-Alias` cmdlet displays the aliases available in a PowerShell session.</span></span>

<span data-ttu-id="07398-226">Чтобы создать псевдоним, используйте командлеты `Set-Alias` или `New-Alias` .</span><span class="sxs-lookup"><span data-stu-id="07398-226">To create an alias, use the cmdlets `Set-Alias` or `New-Alias`.</span></span> <span data-ttu-id="07398-227">Чтобы удалить псевдоним в PowerShell 6, используйте `Remove-Alias` командлет.</span><span class="sxs-lookup"><span data-stu-id="07398-227">In PowerShell 6, to delete an alias, use the `Remove-Alias` cmdlet.</span></span> <span data-ttu-id="07398-228">`Remove-Item` принимается для обеспечения обратной совместимости, например для скриптов, созданных с помощью предыдущих версий PowerShell.</span><span class="sxs-lookup"><span data-stu-id="07398-228">`Remove-Item` is accepted for backwards compatibility such as for scripts created with prior versions of PowerShell.</span></span> <span data-ttu-id="07398-229">Используйте команду, например `Remove-Item -Path Alias:aliasname` .</span><span class="sxs-lookup"><span data-stu-id="07398-229">Use a command such as `Remove-Item -Path Alias:aliasname`.</span></span>

<span data-ttu-id="07398-230">Чтобы создать псевдоним, доступный в каждом сеансе PowerShell, добавьте его в профиль PowerShell.</span><span class="sxs-lookup"><span data-stu-id="07398-230">To create an alias that is available in each PowerShell session, add it to your PowerShell profile.</span></span>
<span data-ttu-id="07398-231">Дополнительные сведения см. в разделе [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="07398-231">For more information, see [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span></span>

<span data-ttu-id="07398-232">Псевдоним можно сохранить и повторно использовать в другом сеансе PowerShell, выполнив экспорт и импорт.</span><span class="sxs-lookup"><span data-stu-id="07398-232">An alias can be saved and reused in another PowerShell session by doing an export and import.</span></span> <span data-ttu-id="07398-233">Чтобы сохранить псевдоним в файл, используйте `Export-Alias` .</span><span class="sxs-lookup"><span data-stu-id="07398-233">To save an alias to a file, use `Export-Alias`.</span></span> <span data-ttu-id="07398-234">Чтобы добавить сохраненный псевдоним в новый сеанс PowerShell, используйте `Import-Alias` .</span><span class="sxs-lookup"><span data-stu-id="07398-234">To add a saved alias to a new PowerShell session, use `Import-Alias`.</span></span>

## <span data-ttu-id="07398-235">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="07398-235">RELATED LINKS</span></span>

[<span data-ttu-id="07398-236">about_Aliases</span><span class="sxs-lookup"><span data-stu-id="07398-236">about_Aliases</span></span>](../Microsoft.PowerShell.Core/About/about_Aliases.md)

[<span data-ttu-id="07398-237">about_Functions</span><span class="sxs-lookup"><span data-stu-id="07398-237">about_Functions</span></span>](../Microsoft.PowerShell.Core/about/about_Functions.md)

[<span data-ttu-id="07398-238">about_Profiles</span><span class="sxs-lookup"><span data-stu-id="07398-238">about_Profiles</span></span>](../Microsoft.PowerShell.Core/About/about_Profiles.md)

[<span data-ttu-id="07398-239">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="07398-239">about_Scopes</span></span>](../Microsoft.PowerShell.Core/About/about_Scopes.md)

[<span data-ttu-id="07398-240">Export-Alias</span><span class="sxs-lookup"><span data-stu-id="07398-240">Export-Alias</span></span>](Export-Alias.md)

[<span data-ttu-id="07398-241">Get-Alias</span><span class="sxs-lookup"><span data-stu-id="07398-241">Get-Alias</span></span>](Get-Alias.md)

[<span data-ttu-id="07398-242">Import-Alias</span><span class="sxs-lookup"><span data-stu-id="07398-242">Import-Alias</span></span>](Import-Alias.md)

[<span data-ttu-id="07398-243">New-Alias</span><span class="sxs-lookup"><span data-stu-id="07398-243">New-Alias</span></span>](New-Alias.md)

[<span data-ttu-id="07398-244">Remove-Alias</span><span class="sxs-lookup"><span data-stu-id="07398-244">Remove-Alias</span></span>](Remove-Alias.md)

[<span data-ttu-id="07398-245">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="07398-245">Remove-Item</span></span>](../Microsoft.PowerShell.Management/Remove-Item.md)

