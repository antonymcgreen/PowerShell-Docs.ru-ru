---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 03/12/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-location?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Location
ms.openlocfilehash: 647424d8148cad8830235abc7b238b79b552c4fb
ms.sourcegitcommit: fe1e20f8523e3663d68546093aaf3670182337b8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "93230449"
---
# <span data-ttu-id="a2848-103">Get-Location</span><span class="sxs-lookup"><span data-stu-id="a2848-103">Get-Location</span></span>

## <span data-ttu-id="a2848-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="a2848-104">SYNOPSIS</span></span>
<span data-ttu-id="a2848-105">Возвращает сведения о текущем рабочем расположении или стеке расположения.</span><span class="sxs-lookup"><span data-stu-id="a2848-105">Gets information about the current working location or a location stack.</span></span>

## <span data-ttu-id="a2848-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a2848-106">SYNTAX</span></span>

### <span data-ttu-id="a2848-107">Расположение (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="a2848-107">Location (Default)</span></span>

```
Get-Location [-PSProvider <String[]>] [-PSDrive <String[]>] [-UseTransaction] [<CommonParameters>]
```

### <span data-ttu-id="a2848-108">Стек</span><span class="sxs-lookup"><span data-stu-id="a2848-108">Stack</span></span>

```
Get-Location [-Stack] [-StackName <String[]>] [-UseTransaction] [<CommonParameters>]
```

## <span data-ttu-id="a2848-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a2848-109">DESCRIPTION</span></span>

<span data-ttu-id="a2848-110">`Get-Location`Командлет возвращает объект, представляющий текущий каталог, во многом похоже на команду Print Work Directory (PWD).</span><span class="sxs-lookup"><span data-stu-id="a2848-110">The `Get-Location` cmdlet gets an object that represents the current directory, much like the print working directory (pwd) command.</span></span>

<span data-ttu-id="a2848-111">При переходе между дисками PowerShell в PowerShell остается расположение на каждом диске.</span><span class="sxs-lookup"><span data-stu-id="a2848-111">When you move between PowerShell drives, PowerShell retains your location in each drive.</span></span> <span data-ttu-id="a2848-112">С помощью этого командлета можно найти расположение на каждом диске.</span><span class="sxs-lookup"><span data-stu-id="a2848-112">You can use this cmdlet to find your location in each drive.</span></span>

<span data-ttu-id="a2848-113">С помощью этого командлета можно получить текущий каталог во время выполнения и использовать его в функциях и скриптах, например в функции, которая отображает текущий каталог в командной строке PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a2848-113">You can use this cmdlet to get the current directory at run time and use it in functions and scripts, such as in a function that displays the current directory in the PowerShell prompt.</span></span>

<span data-ttu-id="a2848-114">Этот командлет также можно использовать для вывода расположений в стеке расположений.</span><span class="sxs-lookup"><span data-stu-id="a2848-114">You can also use this cmdlet to display the locations in a location stack.</span></span> <span data-ttu-id="a2848-115">Дополнительные сведения см. в примечаниях и описаниях параметров **Stack** и **StackName** .</span><span class="sxs-lookup"><span data-stu-id="a2848-115">For more information, see the Notes and the descriptions of the **Stack** and **StackName** parameters.</span></span>

## <span data-ttu-id="a2848-116">Примеры</span><span class="sxs-lookup"><span data-stu-id="a2848-116">EXAMPLES</span></span>

### <span data-ttu-id="a2848-117">Пример 1. Отображение текущего расположения диска</span><span class="sxs-lookup"><span data-stu-id="a2848-117">Example 1: Display your current drive location</span></span>

<span data-ttu-id="a2848-118">Эта команда отображает ваше расположение на текущем диске PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a2848-118">This command displays your location in the current PowerShell drive.</span></span>

```powershell
PS C:\Windows> Get-Location
```

```Output
Path
----
C:\Windows
```

<span data-ttu-id="a2848-119">Например, если вы используете `Windows` каталог `C:` диска, он отображает путь к этому каталогу.</span><span class="sxs-lookup"><span data-stu-id="a2848-119">For instance, if you are in the `Windows` directory of the `C:` drive, it displays the path to that directory.</span></span>

### <span data-ttu-id="a2848-120">Пример 2. Отображение текущего расположения для разных дисков</span><span class="sxs-lookup"><span data-stu-id="a2848-120">Example 2: Display your current location for different drives</span></span>

<span data-ttu-id="a2848-121">В этом примере показано использование `Get-Location` для вывода текущего расположения на разных дисках PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a2848-121">This example demonstrates the use of `Get-Location` to display your current location in different PowerShell drives.</span></span> <span data-ttu-id="a2848-122">`Set-Location` используется для изменения расположения на несколько разных путей в разных Псдривес.</span><span class="sxs-lookup"><span data-stu-id="a2848-122">`Set-Location` is used to change the location to several different paths on different PSDrives.</span></span>

```powershell
PS C:\> Set-Location C:\Windows
PS C:\Windows> Set-Location HKLM:\Software\Microsoft
PS HKLM:\Software\Microsoft> Set-Location "HKCU:\Control Panel\Input Method"
PS HKCU:\Control Panel\Input Method> Get-Location -PSDrive C

Path
----
C:\Windows

PS HKCU:\Control Panel\Input Method> Get-Location -PSDrive HKLM

Path
----
HKLM:\Software\Microsoft

PS HKCU:\Control Panel\Input Method> Set-Location C:
PS C:\Windows> Get-Location -PSProvider Registry

Path
----
HKCU:\Control Panel\Input Method
```

### <span data-ttu-id="a2848-123">Пример 3. получение расположений с помощью стеков</span><span class="sxs-lookup"><span data-stu-id="a2848-123">Example 3: Get locations using stacks</span></span>

<span data-ttu-id="a2848-124">В этом примере показано, как использовать параметры **Stack** и **StackName** `Get-Location` для перечисления расположений в текущем стеке расположения и альтернативных стеках расположения.</span><span class="sxs-lookup"><span data-stu-id="a2848-124">This example shows how to use the **Stack** and **StackName** parameters of `Get-Location` to list the locations in the current location stack and alternate location stacks.</span></span>

<span data-ttu-id="a2848-125">`Push-Location`Командлет используется для изменения трех различных расположений.</span><span class="sxs-lookup"><span data-stu-id="a2848-125">The `Push-Location` cmdlet is used to change into three different locations.</span></span> <span data-ttu-id="a2848-126">Третья отправка использует другое имя стека.</span><span class="sxs-lookup"><span data-stu-id="a2848-126">The third push uses a different stack name.</span></span> <span data-ttu-id="a2848-127">Параметр **Stack** объекта `Get-Location` отображает содержимое стека по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a2848-127">The **Stack** parameter of `Get-Location` displays the contents of the default stack.</span></span> <span data-ttu-id="a2848-128">Параметр **StackName** объекта `Get-Location` отображает содержимое стека с именем `Stack2` .</span><span class="sxs-lookup"><span data-stu-id="a2848-128">The **StackName** parameter of `Get-Location` displays the contents of the stack named `Stack2`.</span></span>

```powershell
PS C:\> Push-Location C:\Windows
PS C:\Windows>Push-Location System32
PS C:\Windows\System32>Push-Location WindowsPowerShell -StackName Stack2
C:\Windows\System32\WindowsPowerShell>Get-Location -Stack

Path
----
C:\Windows
C:\

C:\Windows\System32\WindowsPowerShell>Get-Location -StackName Stack2

Path
----
C:\Windows\System32
```

### <span data-ttu-id="a2848-129">Пример 4. Настройка командной строки PowerShell</span><span class="sxs-lookup"><span data-stu-id="a2848-129">Example 4: Customize the PowerShell prompt</span></span>

<span data-ttu-id="a2848-130">В этом примере показано, как настроить командную строку PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a2848-130">This example shows how to customize the PowerShell prompt.</span></span>

```powershell
PS C:\>
function prompt { 'PowerShell: ' + (Get-Location) + '> '}
PowerShell: C:\>
```

<span data-ttu-id="a2848-131">Функция, определяющая запрос `Get-Location` , включает команду, которая выполняется при появлении запроса в консоли.</span><span class="sxs-lookup"><span data-stu-id="a2848-131">The function that defines the prompt includes a `Get-Location` command, which is run whenever the prompt appears in the console.</span></span>

<span data-ttu-id="a2848-132">Формат командной строки PowerShell по умолчанию определяется специальной функцией с именем `prompt` .</span><span class="sxs-lookup"><span data-stu-id="a2848-132">The format of the default PowerShell prompt is defined by a special function named `prompt`.</span></span> <span data-ttu-id="a2848-133">Вы можете изменить запрос в консоли, создав новую функцию с именем `prompt` .</span><span class="sxs-lookup"><span data-stu-id="a2848-133">You can change the prompt in your console by creating a new function named `prompt`.</span></span>

<span data-ttu-id="a2848-134">Чтобы просмотреть текущую функцию Prompt, введите следующую команду: `Get-Content Function:\prompt`</span><span class="sxs-lookup"><span data-stu-id="a2848-134">To see the current prompt function, type the following command: `Get-Content Function:\prompt`</span></span>

## <span data-ttu-id="a2848-135">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a2848-135">PARAMETERS</span></span>

### <span data-ttu-id="a2848-136">-PSDrive</span><span class="sxs-lookup"><span data-stu-id="a2848-136">-PSDrive</span></span>

<span data-ttu-id="a2848-137">Возвращает текущее расположение в указанном диске PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a2848-137">Gets the current location in the specified PowerShell drive.</span></span>

<span data-ttu-id="a2848-138">Например, если вы используете `Cert:` диск, этот параметр можно использовать для поиска текущего расположения на `C:` диске.</span><span class="sxs-lookup"><span data-stu-id="a2848-138">For instance, if you are in the `Cert:` drive, you can use this parameter to find your current location in the `C:` drive.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Location
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a2848-139">-PSProvider</span><span class="sxs-lookup"><span data-stu-id="a2848-139">-PSProvider</span></span>

<span data-ttu-id="a2848-140">Возвращает текущее расположение на диске, поддерживаемое указанным поставщиком PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a2848-140">Gets the current location in the drive supported by the specified PowerShell provider.</span></span>
<span data-ttu-id="a2848-141">Если указанный поставщик поддерживает более одного диска, этот командлет возвращает расположение на последнем доступном диске.</span><span class="sxs-lookup"><span data-stu-id="a2848-141">If the specified provider supports more than one drive, this cmdlet returns the location on the most recently accessed drive.</span></span>

<span data-ttu-id="a2848-142">Например, если вы используете `C:` диск, этот параметр можно использовать для поиска текущего расположения на дисках поставщика **реестра** PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a2848-142">For example, if you are in the `C:` drive, you can use this parameter to find your current location in the drives of the PowerShell **Registry** provider.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Location
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a2848-143">-Stack</span><span class="sxs-lookup"><span data-stu-id="a2848-143">-Stack</span></span>

<span data-ttu-id="a2848-144">Указывает, что этот командлет отображает расположения, добавленные в текущий стек расположений.</span><span class="sxs-lookup"><span data-stu-id="a2848-144">Indicates that this cmdlet displays the locations added to the current location stack.</span></span> <span data-ttu-id="a2848-145">Вы можете добавлять расположения в стеки с помощью `Push-Location` командлета.</span><span class="sxs-lookup"><span data-stu-id="a2848-145">You can add locations to stacks by using the `Push-Location` cmdlet.</span></span>

<span data-ttu-id="a2848-146">Чтобы отобразить расположения в другом стеке расположения, используйте параметр **StackName** .</span><span class="sxs-lookup"><span data-stu-id="a2848-146">To display the locations in a different location stack, use the **StackName** parameter.</span></span> <span data-ttu-id="a2848-147">Дополнительные сведения о стеках расположений см. в [примечаниях](#notes).</span><span class="sxs-lookup"><span data-stu-id="a2848-147">For information about location stacks, see the [Notes](#notes).</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Stack
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a2848-148">-StackName</span><span class="sxs-lookup"><span data-stu-id="a2848-148">-StackName</span></span>

<span data-ttu-id="a2848-149">Указывает в виде массива строк именованные стеки расположения.</span><span class="sxs-lookup"><span data-stu-id="a2848-149">Specifies, as a string array, the named location stacks.</span></span> <span data-ttu-id="a2848-150">Введите одно или несколько имен стеков расположения.</span><span class="sxs-lookup"><span data-stu-id="a2848-150">Enter one or more location stack names.</span></span>

<span data-ttu-id="a2848-151">Чтобы отобразить расположения в текущем стеке расположений, используйте параметр **Stack** .</span><span class="sxs-lookup"><span data-stu-id="a2848-151">To display the locations in the current location stack, use the **Stack** parameter.</span></span> <span data-ttu-id="a2848-152">Чтобы сделать стек расположения текущим стеком расположения, используйте `Set-Location` командлет.</span><span class="sxs-lookup"><span data-stu-id="a2848-152">To make a location stack the current location stack, use the `Set-Location` cmdlet.</span></span>

<span data-ttu-id="a2848-153">Этот командлет не может отобразить расположения в неименованном стеке по умолчанию, если только это не текущий стек.</span><span class="sxs-lookup"><span data-stu-id="a2848-153">This cmdlet cannot display the locations in the unnamed default stack unless it is the current stack.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Stack
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a2848-154">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="a2848-154">-UseTransaction</span></span>
<span data-ttu-id="a2848-155">Включает команду в активную транзакцию.</span><span class="sxs-lookup"><span data-stu-id="a2848-155">Includes the command in the active transaction.</span></span>
<span data-ttu-id="a2848-156">Этот параметр доступен только при выполнении транзакции.</span><span class="sxs-lookup"><span data-stu-id="a2848-156">This parameter is valid only when a transaction is in progress.</span></span>
<span data-ttu-id="a2848-157">Дополнительные сведения см. в разделе about_transactions.</span><span class="sxs-lookup"><span data-stu-id="a2848-157">For more information, see about_transactions.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: usetx

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a2848-158">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="a2848-158">CommonParameters</span></span>

<span data-ttu-id="a2848-159">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="a2848-159">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a2848-160">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="a2848-160">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a2848-161">Входные данные</span><span class="sxs-lookup"><span data-stu-id="a2848-161">INPUTS</span></span>

### <span data-ttu-id="a2848-162">Нет</span><span class="sxs-lookup"><span data-stu-id="a2848-162">None</span></span>

<span data-ttu-id="a2848-163">В этот командлет нельзя передать входные данные.</span><span class="sxs-lookup"><span data-stu-id="a2848-163">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="a2848-164">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="a2848-164">OUTPUTS</span></span>

### <span data-ttu-id="a2848-165">System. Management. Automation. PathInfo или System. Management. Automation. Пасинфостакк</span><span class="sxs-lookup"><span data-stu-id="a2848-165">System.Management.Automation.PathInfo or System.Management.Automation.PathInfoStack</span></span>

<span data-ttu-id="a2848-166">При использовании параметров **Stack** или **StackName** этот командлет возвращает объект **пасинфостакк** .</span><span class="sxs-lookup"><span data-stu-id="a2848-166">If you use the **Stack** or **StackName** parameters, this cmdlet returns a **PathInfoStack** object.</span></span> <span data-ttu-id="a2848-167">В противном случае возвращается объект **PathInfo** .</span><span class="sxs-lookup"><span data-stu-id="a2848-167">Otherwise, it returns a **PathInfo** object.</span></span>

## <span data-ttu-id="a2848-168">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="a2848-168">NOTES</span></span>

<span data-ttu-id="a2848-169">PowerShell поддерживает несколько пространств выполнения для каждого процесса.</span><span class="sxs-lookup"><span data-stu-id="a2848-169">PowerShell supports multiple runspaces per process.</span></span> <span data-ttu-id="a2848-170">Каждое пространство выполнения имеет свой собственный _текущий каталог_ .</span><span class="sxs-lookup"><span data-stu-id="a2848-170">Each runspace has its own _current directory_ .</span></span>
<span data-ttu-id="a2848-171">Это не то же самое, что `[System.Environment]::CurrentDirectory` .</span><span class="sxs-lookup"><span data-stu-id="a2848-171">This is not the same as `[System.Environment]::CurrentDirectory`.</span></span> <span data-ttu-id="a2848-172">Такое поведение может быть проблемой при вызове API .NET или запуске собственных приложений без предоставления явных путей к каталогу.</span><span class="sxs-lookup"><span data-stu-id="a2848-172">This behavior can be an issue when calling .NET APIs or running native applications without providing explicit directory paths.</span></span>
<span data-ttu-id="a2848-173">`Get-Location`Командлет возвращает текущий каталог текущего пространства выполнения PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a2848-173">The `Get-Location` cmdlet returns the current directory of the current PowerShell runspace.</span></span>

<span data-ttu-id="a2848-174">Этот командлет предназначен для работы с данными, предоставляемыми любым поставщиком.</span><span class="sxs-lookup"><span data-stu-id="a2848-174">This cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="a2848-175">Чтобы получить список поставщиков в сеансе, введите `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="a2848-175">To list the providers in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="a2848-176">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="a2848-176">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

<span data-ttu-id="a2848-177">Способы, с помощью которых взаимодействуют параметры **psprovider** , **PSDrive** , **Stack** и **StackName** , зависят от поставщика.</span><span class="sxs-lookup"><span data-stu-id="a2848-177">The ways that the **PSProvider** , **PSDrive** , **Stack** , and **StackName** parameters interact depends on the provider.</span></span> <span data-ttu-id="a2848-178">Некоторые сочетания приводят к ошибкам, например указание и диска, и поставщика, который не предоставляет доступ к этому диску.</span><span class="sxs-lookup"><span data-stu-id="a2848-178">Some combinations will result in errors, such as specifying both a drive and a provider that does not expose that drive.</span></span> <span data-ttu-id="a2848-179">Если параметры не указаны, этот командлет возвращает объект **PathInfo** для поставщика, который содержит текущее рабочее расположение.</span><span class="sxs-lookup"><span data-stu-id="a2848-179">If no parameters are specified, this cmdlet returns the **PathInfo** object for the provider that contains the current working location.</span></span>

<span data-ttu-id="a2848-180">Стек — это последний список, в котором доступен только последний добавленный элемент.</span><span class="sxs-lookup"><span data-stu-id="a2848-180">A stack is a last-in, first-out list in which only the most recently added item is accessible.</span></span> <span data-ttu-id="a2848-181">Элементы добавляются в стек в порядке их использования, а извлекаются в обратном порядке.</span><span class="sxs-lookup"><span data-stu-id="a2848-181">You add items to a stack in the order that you use them, and then retrieve them for use in the reverse order.</span></span> <span data-ttu-id="a2848-182">PowerShell позволяет хранить расположения поставщиков в стеках расположений.</span><span class="sxs-lookup"><span data-stu-id="a2848-182">PowerShell lets you store provider locations in location stacks.</span></span> <span data-ttu-id="a2848-183">PowerShell создает неименованный стек расположения по умолчанию и позволяет создать несколько именованных стеков расположения.</span><span class="sxs-lookup"><span data-stu-id="a2848-183">PowerShell creates an unnamed default location stack and you can create multiple named location stacks.</span></span> <span data-ttu-id="a2848-184">Если имя стека не указано, PowerShell использует текущий стек расположения.</span><span class="sxs-lookup"><span data-stu-id="a2848-184">If you do not specify a stack name, PowerShell uses the current location stack.</span></span> <span data-ttu-id="a2848-185">По умолчанию безымянным расположением по умолчанию является текущий стек расположения, но можно использовать `Set-Location` командлет для изменения текущего стека расположения.</span><span class="sxs-lookup"><span data-stu-id="a2848-185">By default, the unnamed default location is the current location stack, but you can use the `Set-Location` cmdlet to change the current location stack.</span></span>

<span data-ttu-id="a2848-186">Для управления стеками расположений используйте `*-Location` командлеты PowerShell, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="a2848-186">To manage location stacks, use the PowerShell `*-Location` cmdlets, as follows.</span></span>

- <span data-ttu-id="a2848-187">Чтобы добавить расположение в стек расположений, используйте `Push-Location` командлет.</span><span class="sxs-lookup"><span data-stu-id="a2848-187">To add a location to a location stack, use the `Push-Location` cmdlet.</span></span>

- <span data-ttu-id="a2848-188">Чтобы получить расположение из стека расположения, используйте `Pop-Location` командлет.</span><span class="sxs-lookup"><span data-stu-id="a2848-188">To get a location from a location stack, use the `Pop-Location` cmdlet.</span></span>

- <span data-ttu-id="a2848-189">Чтобы отобразить расположения в текущем стеке расположений, используйте параметр **Stack** `Get-Location` командлета.</span><span class="sxs-lookup"><span data-stu-id="a2848-189">To display the locations in the current location stack, use the **Stack** parameter of the `Get-Location` cmdlet.</span></span> <span data-ttu-id="a2848-190">Чтобы отобразить расположения в именованном стеке расположений, используйте параметр **StackName** `Get-Location` командлета.</span><span class="sxs-lookup"><span data-stu-id="a2848-190">To display the locations in a named location stack, use the **StackName** parameter of the `Get-Location` cmdlet.</span></span>

- <span data-ttu-id="a2848-191">Чтобы создать новый стек расположений, используйте параметр **StackName** `Push-Location` командлета.</span><span class="sxs-lookup"><span data-stu-id="a2848-191">To create a new location stack, use the **StackName** parameter of the `Push-Location` cmdlet.</span></span>
  <span data-ttu-id="a2848-192">Если указан несуществующий стек, `Push-Location` создает стек.</span><span class="sxs-lookup"><span data-stu-id="a2848-192">If you specify a stack that does not exist, `Push-Location` creates the stack.</span></span>

- <span data-ttu-id="a2848-193">Чтобы сделать стек расположения текущим стеком расположения, используйте параметр **StackName** `Set-Location` командлета.</span><span class="sxs-lookup"><span data-stu-id="a2848-193">To make a location stack the current location stack, use the **StackName** parameter of the `Set-Location` cmdlet.</span></span>

<span data-ttu-id="a2848-194">Безымянный стек папок по умолчанию будет полностью доступен, только если он является текущим.</span><span class="sxs-lookup"><span data-stu-id="a2848-194">The unnamed default location stack is fully accessible only when it is the current location stack.</span></span>
<span data-ttu-id="a2848-195">Если вы сделаете именованный стек расположения текущим стеком расположения, вы больше не сможете использовать `Push-Location` `Pop-Location` командлеты или для добавления или получения элементов из стека по умолчанию или использовать этот командлет для вывода расположений в неименованном стеке.</span><span class="sxs-lookup"><span data-stu-id="a2848-195">If you make a named location stack the current location stack, you can no longer use the `Push-Location` or `Pop-Location` cmdlets to add or get items from the default stack or use this cmdlet to display the locations in the unnamed stack.</span></span> <span data-ttu-id="a2848-196">Чтобы сделать неименованным стек текущего стека, используйте параметр **StackName** `Set-Location` командлета со значением `$null` или пустой строкой ( `""` ).</span><span class="sxs-lookup"><span data-stu-id="a2848-196">To make the unnamed stack the current stack, use the **StackName** parameter of the `Set-Location` cmdlet with a value of `$null` or an empty string (`""`).</span></span>

## <span data-ttu-id="a2848-197">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="a2848-197">RELATED LINKS</span></span>

[<span data-ttu-id="a2848-198">Pop-Location</span><span class="sxs-lookup"><span data-stu-id="a2848-198">Pop-Location</span></span>](Pop-Location.md)

[<span data-ttu-id="a2848-199">Push-Location</span><span class="sxs-lookup"><span data-stu-id="a2848-199">Push-Location</span></span>](Push-Location.md)

[<span data-ttu-id="a2848-200">Set-Location</span><span class="sxs-lookup"><span data-stu-id="a2848-200">Set-Location</span></span>](Set-Location.md)
