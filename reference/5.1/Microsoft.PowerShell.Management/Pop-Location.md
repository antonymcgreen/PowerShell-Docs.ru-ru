---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 02/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/pop-location?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Pop-Location
ms.openlocfilehash: 6843a598b5d20ebd9819b2ed0b180cd21f0416f4
ms.sourcegitcommit: 01a1c253f48b61c943f6d6aca4e603118014015f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/06/2020
ms.locfileid: "93230258"
---
# <span data-ttu-id="8f7cb-103">Pop-Location</span><span class="sxs-lookup"><span data-stu-id="8f7cb-103">Pop-Location</span></span>

## <span data-ttu-id="8f7cb-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="8f7cb-104">SYNOPSIS</span></span>
<span data-ttu-id="8f7cb-105">Меняет текущее расположение на расположение, указанное в последней записи стека.</span><span class="sxs-lookup"><span data-stu-id="8f7cb-105">Changes the current location to the location most recently pushed onto the stack.</span></span>

## <span data-ttu-id="8f7cb-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8f7cb-106">SYNTAX</span></span>

```
Pop-Location [-PassThru] [-StackName <String>] [-UseTransaction] [<CommonParameters>]
```

## <span data-ttu-id="8f7cb-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="8f7cb-107">DESCRIPTION</span></span>

<span data-ttu-id="8f7cb-108">`Pop-Location`Командлет изменяет текущее расположение на расположение, которое недавно было отправлено в стек с помощью `Push-Location` командлета.</span><span class="sxs-lookup"><span data-stu-id="8f7cb-108">The `Pop-Location` cmdlet changes the current location to the location most recently pushed onto the stack by using the `Push-Location` cmdlet.</span></span> <span data-ttu-id="8f7cb-109">Можно открыть расположение из стека по умолчанию или из стека, созданного с помощью `Push-Location` команды.</span><span class="sxs-lookup"><span data-stu-id="8f7cb-109">You can pop a location from the default stack or from a stack that you create by using a `Push-Location` command.</span></span>

## <span data-ttu-id="8f7cb-110">Примеры</span><span class="sxs-lookup"><span data-stu-id="8f7cb-110">EXAMPLES</span></span>

### <span data-ttu-id="8f7cb-111">Пример 1. Переход к последнему расположению</span><span class="sxs-lookup"><span data-stu-id="8f7cb-111">Example 1: Change to most recent location</span></span>

```
PS C:\> Pop-Location
```

<span data-ttu-id="8f7cb-112">Эта команда меняет текущее расположение на расположение, указанное в последней записи текущего стека.</span><span class="sxs-lookup"><span data-stu-id="8f7cb-112">This command changes your location to the location most recently added to the current stack.</span></span>

### <span data-ttu-id="8f7cb-113">Пример 2. Переход к последнему расположению в именованном стеке</span><span class="sxs-lookup"><span data-stu-id="8f7cb-113">Example 2: Change to most recent location in a named stack</span></span>

```
PS C:\> Pop-Location -StackName "Stack2"
```

<span data-ttu-id="8f7cb-114">Эта команда меняет текущее расположение на расположение, указанное в последней записи стека Stack2.</span><span class="sxs-lookup"><span data-stu-id="8f7cb-114">This command changes your location to the location most recently added to the Stack2 location stack.</span></span>

<span data-ttu-id="8f7cb-115">Дополнительные сведения о стеках расположений см. в [примечаниях](#notes).</span><span class="sxs-lookup"><span data-stu-id="8f7cb-115">For more information about location stacks, see the [Notes](#notes).</span></span>

### <span data-ttu-id="8f7cb-116">Пример 3. Перемещение между расположениями для разных поставщиков</span><span class="sxs-lookup"><span data-stu-id="8f7cb-116">Example 3: Move between locations for different providers</span></span>

```
PS C:\> pushd HKLM:\Software\Microsoft\PowerShell
PS HKLM:\Software\Microsoft\PowerShell> pushd Cert:\LocalMachine\TrustedPublisher
PS cert:\LocalMachine\TrustedPublisher> popd
PS HKLM:\Software\Microsoft\PowerShell> popd
PS C:\>
```

<span data-ttu-id="8f7cb-117">Эти команды используют `Push-Location` `Pop-Location` командлеты и для перемещения между расположениями, поддерживаемыми различными поставщиками PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8f7cb-117">These commands use the `Push-Location` and `Pop-Location` cmdlets to move between locations supported by different PowerShell providers.</span></span> <span data-ttu-id="8f7cb-118">Команды используют `pushd` псевдоним для `Push-Location` и `popd` псевдоним для `Pop-Location` .</span><span class="sxs-lookup"><span data-stu-id="8f7cb-118">The commands use the `pushd` alias for `Push-Location` and the `popd` alias for `Pop-Location`.</span></span>

<span data-ttu-id="8f7cb-119">Первая команда помещает текущее расположение файловой системы в стек и переходит на диск HKLM, поддерживаемый поставщиком реестра PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8f7cb-119">The first command pushes the current file system location onto the stack and moves to the HKLM drive supported by the PowerShell Registry provider.</span></span>

<span data-ttu-id="8f7cb-120">Вторая команда помещает расположение реестра в стек и переходит в расположение, поддерживаемое поставщиком сертификатов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8f7cb-120">The second command pushes the registry location onto the stack and moves to a location supported by the PowerShell certificate provider.</span></span>

<span data-ttu-id="8f7cb-121">Две последние команды извлекают эти расположения из стека.</span><span class="sxs-lookup"><span data-stu-id="8f7cb-121">The last two commands pop those locations off the stack.</span></span> <span data-ttu-id="8f7cb-122">Первая `popd` команда возвращается к диску реестра, а вторая команда возвращается к диску файловой системы.</span><span class="sxs-lookup"><span data-stu-id="8f7cb-122">The first `popd` command returns to the Registry drive, and the second command returns to the file system drive.</span></span>

## <span data-ttu-id="8f7cb-123">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8f7cb-123">PARAMETERS</span></span>

### <span data-ttu-id="8f7cb-124">-PassThru</span><span class="sxs-lookup"><span data-stu-id="8f7cb-124">-PassThru</span></span>

<span data-ttu-id="8f7cb-125">Передает объект, представляющий расположение в конвейер.</span><span class="sxs-lookup"><span data-stu-id="8f7cb-125">Passes an object that represents the location to the pipeline.</span></span> <span data-ttu-id="8f7cb-126">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="8f7cb-126">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="8f7cb-127">-StackName</span><span class="sxs-lookup"><span data-stu-id="8f7cb-127">-StackName</span></span>

<span data-ttu-id="8f7cb-128">Указывает стек папок, из которого будет взято расположение.</span><span class="sxs-lookup"><span data-stu-id="8f7cb-128">Specifies the location stack from which the location is popped.</span></span> <span data-ttu-id="8f7cb-129">Введите имя стека папок.</span><span class="sxs-lookup"><span data-stu-id="8f7cb-129">Enter a location stack name.</span></span>

<span data-ttu-id="8f7cb-130">Без этого параметра `Pop-Location` извлекает расположение из текущего стека расположения.</span><span class="sxs-lookup"><span data-stu-id="8f7cb-130">Without this parameter, `Pop-Location` pops a location from the current location stack.</span></span> <span data-ttu-id="8f7cb-131">По умолчанию текущий стек расположений — это безымянный стек расположения по умолчанию, создаваемый PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8f7cb-131">By default, the current location stack is the unnamed default location stack that PowerShell creates.</span></span> <span data-ttu-id="8f7cb-132">Чтобы сделать стек расположения текущим стеком расположения, используйте параметр **StackName** `Set-Location` командлета.</span><span class="sxs-lookup"><span data-stu-id="8f7cb-132">To make a location stack the current location stack, use the **StackName** parameter of the `Set-Location` cmdlet.</span></span> <span data-ttu-id="8f7cb-133">Дополнительные сведения о стеках расположений см. в [примечаниях](#notes).</span><span class="sxs-lookup"><span data-stu-id="8f7cb-133">For more information about location stacks, see the [Notes](#notes).</span></span>

<span data-ttu-id="8f7cb-134">`Pop-Location` невозможно открыть расположение из неименованного стека по умолчанию, если он не является текущим стеком расположения.</span><span class="sxs-lookup"><span data-stu-id="8f7cb-134">`Pop-Location` cannot pop a location from the unnamed default stack unless it is the current location stack.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="8f7cb-135">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="8f7cb-135">-UseTransaction</span></span>

<span data-ttu-id="8f7cb-136">Включает команду в активную транзакцию.</span><span class="sxs-lookup"><span data-stu-id="8f7cb-136">Includes the command in the active transaction.</span></span> <span data-ttu-id="8f7cb-137">Этот параметр доступен только при выполнении транзакции.</span><span class="sxs-lookup"><span data-stu-id="8f7cb-137">This parameter is valid only when a transaction is in progress.</span></span> <span data-ttu-id="8f7cb-138">Дополнительные сведения см. в разделе [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md).</span><span class="sxs-lookup"><span data-stu-id="8f7cb-138">For more information, see [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md).</span></span>

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

### <span data-ttu-id="8f7cb-139">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="8f7cb-139">CommonParameters</span></span>

<span data-ttu-id="8f7cb-140">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="8f7cb-140">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="8f7cb-141">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="8f7cb-141">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="8f7cb-142">Входные данные</span><span class="sxs-lookup"><span data-stu-id="8f7cb-142">INPUTS</span></span>

### <span data-ttu-id="8f7cb-143">Нет</span><span class="sxs-lookup"><span data-stu-id="8f7cb-143">None</span></span>

<span data-ttu-id="8f7cb-144">В этот командлет нельзя передать входные данные.</span><span class="sxs-lookup"><span data-stu-id="8f7cb-144">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="8f7cb-145">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="8f7cb-145">OUTPUTS</span></span>

### <span data-ttu-id="8f7cb-146">Нет, System. Management. Automation. PathInfo</span><span class="sxs-lookup"><span data-stu-id="8f7cb-146">None, System.Management.Automation.PathInfo</span></span>

<span data-ttu-id="8f7cb-147">Этот командлет создает объект **System. Management. Automation. PathInfo** , представляющий расположение, если указан параметр **PassThru** .</span><span class="sxs-lookup"><span data-stu-id="8f7cb-147">This cmdlet generates a **System.Management.Automation.PathInfo** object that represents the location, if you specify the **PassThru** parameter.</span></span> <span data-ttu-id="8f7cb-148">В противном случае командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="8f7cb-148">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="8f7cb-149">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="8f7cb-149">NOTES</span></span>

<span data-ttu-id="8f7cb-150">PowerShell поддерживает несколько пространств выполнения для каждого процесса.</span><span class="sxs-lookup"><span data-stu-id="8f7cb-150">PowerShell supports multiple runspaces per process.</span></span> <span data-ttu-id="8f7cb-151">Каждое пространство выполнения имеет свой собственный _текущий каталог_ .</span><span class="sxs-lookup"><span data-stu-id="8f7cb-151">Each runspace has its own _current directory_ .</span></span>
<span data-ttu-id="8f7cb-152">Это не то же самое, что `[System.Environment]::CurrentDirectory` .</span><span class="sxs-lookup"><span data-stu-id="8f7cb-152">This is not the same as `[System.Environment]::CurrentDirectory`.</span></span> <span data-ttu-id="8f7cb-153">Такое поведение может быть проблемой при вызове API .NET или запуске собственных приложений без предоставления явных путей к каталогу.</span><span class="sxs-lookup"><span data-stu-id="8f7cb-153">This behavior can be an issue when calling .NET APIs or running native applications without providing explicit directory paths.</span></span>

<span data-ttu-id="8f7cb-154">Даже если командлеты Location установили текущий каталог на уровне процесса, вы не можете зависеть от него, так как другое пространство выполнения может изменить его в любое время.</span><span class="sxs-lookup"><span data-stu-id="8f7cb-154">Even if the location cmdlets did set the process-wide current directory, you can't depend on it because another runspace might change it at any time.</span></span> <span data-ttu-id="8f7cb-155">Командлеты Location следует использовать для выполнения операций на основе пути с использованием текущего рабочего каталога, относящегося к текущему пространству выполнения.</span><span class="sxs-lookup"><span data-stu-id="8f7cb-155">You should use the location cmdlets to perform path-based operations using the current working directory specific to the current runspace.</span></span>

<span data-ttu-id="8f7cb-156">Стек — это последний список, в котором можно получить доступ только к последним добавленным элементам.</span><span class="sxs-lookup"><span data-stu-id="8f7cb-156">A stack is a last-in, first-out list in which only the most recently added item can be accessed.</span></span> <span data-ttu-id="8f7cb-157">Элементы добавляются в стек в порядке их использования, а извлекаются в обратном порядке.</span><span class="sxs-lookup"><span data-stu-id="8f7cb-157">You add items to a stack in the order that you use them, and then retrieve them for use in the reverse order.</span></span> <span data-ttu-id="8f7cb-158">PowerShell позволяет хранить расположения поставщиков в стеках расположений.</span><span class="sxs-lookup"><span data-stu-id="8f7cb-158">PowerShell lets you store provider locations in location stacks.</span></span>

<span data-ttu-id="8f7cb-159">PowerShell создает неименованный стек расположения по умолчанию и позволяет создать несколько именованных стеков расположения.</span><span class="sxs-lookup"><span data-stu-id="8f7cb-159">PowerShell creates an unnamed default location stack and you can create multiple named location stacks.</span></span> <span data-ttu-id="8f7cb-160">Если имя стека не указано, PowerShell использует текущий стек расположения.</span><span class="sxs-lookup"><span data-stu-id="8f7cb-160">If you do not specify a stack name, PowerShell uses the current location stack.</span></span> <span data-ttu-id="8f7cb-161">По умолчанию безымянным расположением по умолчанию является текущий стек расположения, но можно использовать `Set-Location` командлет для изменения текущего стека расположения.</span><span class="sxs-lookup"><span data-stu-id="8f7cb-161">By default, the unnamed default location is the current location stack, but you can use the `Set-Location` cmdlet to change the current location stack.</span></span>

<span data-ttu-id="8f7cb-162">Для управления стеками расположений используйте `*-Location` командлеты PowerShell следующим образом:</span><span class="sxs-lookup"><span data-stu-id="8f7cb-162">To manage location stacks, use the PowerShell `*-Location` cmdlets, as follows:</span></span>

- <span data-ttu-id="8f7cb-163">Чтобы добавить расположение в стек расположений, используйте `Push-Location` командлет.</span><span class="sxs-lookup"><span data-stu-id="8f7cb-163">To add a location to a location stack, use the `Push-Location` cmdlet.</span></span>

- <span data-ttu-id="8f7cb-164">Чтобы получить расположение из стека расположения, используйте `Pop-Location` командлет.</span><span class="sxs-lookup"><span data-stu-id="8f7cb-164">To get a location from a location stack, use the `Pop-Location` cmdlet.</span></span>

- <span data-ttu-id="8f7cb-165">Чтобы отобразить расположения в текущем стеке расположений, используйте параметр **Stack** `Get-Location` командлета.</span><span class="sxs-lookup"><span data-stu-id="8f7cb-165">To display the locations in the current location stack, use the **Stack** parameter of the `Get-Location` cmdlet.</span></span>

- <span data-ttu-id="8f7cb-166">Чтобы отобразить расположения в именованном стеке расположений, используйте параметр **StackName** `Get-Location` командлета.</span><span class="sxs-lookup"><span data-stu-id="8f7cb-166">To display the locations in a named location stack, use the **StackName** parameter of the `Get-Location` cmdlet.</span></span>

- <span data-ttu-id="8f7cb-167">Чтобы создать новый стек расположений, используйте параметр **StackName** `Push-Location` командлета.</span><span class="sxs-lookup"><span data-stu-id="8f7cb-167">To create a new location stack, use the **StackName** parameter of the `Push-Location` cmdlet.</span></span> <span data-ttu-id="8f7cb-168">Если указан несуществующий стек, `Push-Location` создает стек.</span><span class="sxs-lookup"><span data-stu-id="8f7cb-168">If you specify a stack that does not exist, `Push-Location` creates the stack.</span></span>

- <span data-ttu-id="8f7cb-169">Чтобы сделать стек расположения текущим стеком расположения, используйте параметр **StackName** `Set-Location` командлета.</span><span class="sxs-lookup"><span data-stu-id="8f7cb-169">To make a location stack the current location stack, use the **StackName** parameter of the `Set-Location` cmdlet.</span></span>

<span data-ttu-id="8f7cb-170">Безымянный стек папок по умолчанию будет полностью доступен, только если он является текущим.</span><span class="sxs-lookup"><span data-stu-id="8f7cb-170">The unnamed default location stack is fully accessible only when it is the current location stack.</span></span>
<span data-ttu-id="8f7cb-171">Если вы сделаете именованный стек расположения текущим стеком расположения, вы больше не сможете использовать `Push-Location` `Pop-Location` командлеты или для добавления или получения элементов из стека по умолчанию или использовать `Get-Location` командлет для вывода расположений в безымянном стеке.</span><span class="sxs-lookup"><span data-stu-id="8f7cb-171">If you make a named location stack the current location stack, you can no longer use the `Push-Location` or `Pop-Location` cmdlets to add or get items from the default stack or use the `Get-Location` cmdlet to display the locations in the unnamed stack.</span></span> <span data-ttu-id="8f7cb-172">Чтобы сделать неименованным стек текущего стека, используйте параметр **StackName** `Set-Location` командлета со значением `$Null` или пустой строкой ( `""` ).</span><span class="sxs-lookup"><span data-stu-id="8f7cb-172">To make the unnamed stack the current stack, use the **StackName** parameter of the `Set-Location` cmdlet with a value of `$Null` or an empty string (`""`).</span></span>

<span data-ttu-id="8f7cb-173">Также можно ссылаться `Pop-Location` по встроенному псевдониму `popd` .</span><span class="sxs-lookup"><span data-stu-id="8f7cb-173">You can also refer to `Pop-Location` by its built-in alias, `popd`.</span></span> <span data-ttu-id="8f7cb-174">Дополнительные сведения см. в разделе [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="8f7cb-174">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>

<span data-ttu-id="8f7cb-175">`Pop-Location` предназначен для работы с данными, предоставляемыми любым поставщиком.</span><span class="sxs-lookup"><span data-stu-id="8f7cb-175">`Pop-Location` is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="8f7cb-176">Чтобы вывести список поставщиков, доступных в данном сеансе, введите командлет `Get-PSProvider`.</span><span class="sxs-lookup"><span data-stu-id="8f7cb-176">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="8f7cb-177">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="8f7cb-177">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="8f7cb-178">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="8f7cb-178">RELATED LINKS</span></span>

[<span data-ttu-id="8f7cb-179">Get-Location</span><span class="sxs-lookup"><span data-stu-id="8f7cb-179">Get-Location</span></span>](Get-Location.md)

[<span data-ttu-id="8f7cb-180">Push-Location</span><span class="sxs-lookup"><span data-stu-id="8f7cb-180">Push-Location</span></span>](Push-Location.md)

[<span data-ttu-id="8f7cb-181">Set-Location</span><span class="sxs-lookup"><span data-stu-id="8f7cb-181">Set-Location</span></span>](Set-Location.md)

[<span data-ttu-id="8f7cb-182">about_Aliases</span><span class="sxs-lookup"><span data-stu-id="8f7cb-182">about_Aliases</span></span>](../Microsoft.PowerShell.Core/About/about_Aliases.md)

[<span data-ttu-id="8f7cb-183">about_Providers</span><span class="sxs-lookup"><span data-stu-id="8f7cb-183">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)
